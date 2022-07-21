# Create wep api 
You can find source on GitHub at https://github.com/diplomegalo/Poc/tree/develop/Poc.GraphQL.

```shell
dotnet new webapi -o Poc.GraphQL/Poc.GraphQL.Web
dotnet new sln -o Poc.GraphQL
dotnet sln add Poc.GraphQL/Poc.GraphQL.Web
```

# Nuget dependencies

```shell
dotnet add package GraphQL.Server.All
```

Or more specifics:

```shell
dotnet add package GraphQL.SystemTextJson
dotnet add package GraphQL.MicrosoftDI
dotnet add package GraphQL.Server.Ui.Altair
dotnet add package GraphQL.Server.Transports.AspNetCore
```

# Scalar Type

## Entity definition

Create a new directory  `/Entities` and a the class behind which describe a case.

```c#
public class Case  
{  
    public int Id { get; set; }  
    public string? Ref { get; set; }   
}
```

## Type definition

Create new directory `/GraphQL/Types` and add the class behind to define the type case.

```c#
public sealed class CaseType : ObjectGraphType<Case>  
{  
    public CaseType()  
    {        
	    Name = "Case";  
        Description = "A case contains information about the customer.";  
        Field(dossier => dossier.Id).Description("The case unique identifier.");  
        Field(dossier => dossier.Ref).Description("The case business reference.");  
    }
}
```

## Query definition

Add the class `PocApplicationQuery` in the `GraphQL` directory. This class will define the available queries.

```c#
public class PocApplicationQuery : ObjectGraphType  
{  
    public PocApplicationQuery()  
    {        
		Field<ListGraphType<CaseType>>(  
            "dossier",  
            resolve: _ => new List<Case>()  
            {  
                new() { Id = 1, Ref = "plop reference 1" },  
                new() { Id = 2, Ref = "plop reference 2" },  
            });  
    }
}
```

## Schema definition

Finally add the `PocApplicationSchema` in the `GraphQL` directory and set the `Query` property.

```c#
public class PocApplicationSchema : Schema  
{  
    public PocApplicationSchema(IServiceProvider serviceProvider)  
        : base(serviceProvider)  
    {        
	    Query = serviceProvider.GetRequiredService<PocApplicationQuery>();  
    }
}
```

## Use `enum` property

Add the enum type in the `Entities` directory. 

```C#
public enum Status  
{  
    New,  
    InProgress,  
    OnHold,  
    Archive  
}
```

Add a new property in `Case` class

```C#
public class Case  
{  
    public int Id { get; set; }  
    public string? Ref { get; set; }

	// enum property
    public Status Status { get; set; }  
}
```

In the `Types` repository add a new type definition for the enumeration. 

```C#
public class StatusEnumType : EnumerationGraphType<Status>  
{  
    public StatusEnumType()  
    {        
	    Name = "Status";  
        Description = "The status of the case.";  
    }
}
```

Add field in the `CaseType` class constructor where 
- the generic type is the type definition of the enum field,
- the first parameter is the name of the property : `Case.Status`,
- the last parameter is the description.

```C#
public CaseType()  
{  
    Name = "Case";  
    Description = "A case contains information about the customer.";  
    Field(dossier => dossier.Id).Description("The case unique identifier.");  
    Field(dossier => dossier.Ref).Description("The case business reference.");
      
    // Enum type  
    Field<StatusEnumType>("Status", "The status of the case.");  
}
```

## Test

At this step you should be able to test your application. See the [[#Configure Startup]] chapter to know how to build application with minimum services to have access.

# Complex Type

## Nuget dependencies

```shell
dotnet add package Microsoft.EntityFrameworkCore
dotnet add package Microsoft.EntityFrameworkCore.InMemory
```

## Entity definition

In the `Entities` directory, add a new class `Contract` which describes contracts associated to a case.

```C#  
public class Contract  
{  
    public int Id { get; set; }  
    public string Ref { get; set; }  
    public DateTime CreationDate { get; set; }  
    // Case  
    public int CaseId { get; set; }  
    public Case Case { get; set; }  
}
```

In the `Case` class, add the associated collection of contracts.

```C#
public class Case  
{  
    public int Id { get; set; }  
    public string? Ref { get; set; }  
    public Status Status { get; set; }  
 
	public ICollection<Contract> Contracts { get; set; }  
}

```

>Note that the type of collection is a `ICollection` to be compatible with EF Core.

## Contract repository

The repository will be used in the following type definition with the method `GetByCase` that returns contracts associated to a case.

In the `Repositories/EF` directory, create the db context class as below.

```C#
public class PocGraphQLContext : DbContext  
{  
    public PocGraphQLContext(DbContextOptions<PocGraphQLContext> options)  
        :base(options)  
    {    
    }    
	
	public DbSet<Case> Cases { get; set; }  
    public DbSet<Contract> Contracts { get; set; }  
  
    protected override void OnModelCreating(ModelBuilder modelBuilder)  
    {        
	    base.OnModelCreating(modelBuilder);  
        modelBuilder.Entity<Contract>()
        .HasData(  
            
            new Contract { Id = 1, Ref = "Ref-1", CreationDate = DateTime.Now.AddDays(-1), CaseId = 1 },  
            
            new Contract { Id = 2, Ref = "Ref-2", CreationDate = DateTime.Now.AddDays(-2), CaseId = 2 });  
    }
}
```

In the `Repositories` directory, first add the `IContractRepository` interface and then the `ContractRepository` wich implements the interface and use the `PocGraphQLContext`.

```C#
public interface IContractRepository  
{  
    IEnumerable<Contract> GetByCase(int caseId);  
}
```

```C#
public class ContractRepository : IContractRepository  
{  
    private readonly PocGraphQLContext _context;  
  
    public ContractRepository(PocGraphQLContext context)  
    {        
	    _context = context;
    }  
    
    public IEnumerable<Contract> GetByCase(int caseId) =>  
        _context.Contracts.Where(reason => reason.CaseId == caseId);  
}
```

Then modify the `Startup` class by adding the following code.

```C#
// DbContext  
builder.Services.AddDbContext<PocGraphQLContext>(options => 
	options.UseInMemoryDatabase("PocGraphQL"));  

builder.Services.BuildServiceProvider().GetRequiredService<PocGraphQLContext>()
	.Database
	.EnsureCreated();  
  
// Repositories  
builder.Services.AddScoped<IContractRepository, ContractRepository>();
```

## Type definition

In the `GraphQL/Types` directory, add a new class `ContractType` which defines the `ObjectGraphType` for this entity.

```C#
public sealed class ContractType : ObjectGraphType<Contract>  
{  
    public ContractType()  
    {        
	    Field(contract => contract.Id);  
        Field(contract => contract.Ref);  
        Field(contract => contract.CreationDate);  
    }
}
```

Next, adapt the existing `CaseType` class with dependencies on contract. 

There the `IServiceProvider` is used via the `RequestServices` property of the `context` to resolve the `IContractRepository` instanciation.

Then the instance is use to retrieve the list of `Contract` associated with a `Case`, based on the `Id` found in the `Source` property of the `context`. 

```C#
// Contracts  
Field<ListGraphType<ContractType>>(
	"contracts",  
    resolve: context =>  
    {  
	    // Get repository instance using the service provider
        var contactRepository = context
	        .RequestServices?
	        .GetRequiredService<IContractRepository>() 
		        ?? throw new InvalidOperationException("Unable to retrieve service provider.");

		// Get contract base on the case id
        return contactRepository.GetByCase(context.Source.Id);  
    });
```

# Configure Startup

Add snippets behind in the `Startup` class.

```c#
// GraphQL  
builder.Services    
.AddGraphQL(qlBuilder => qlBuilder
		.AddErrorInfoProvider(options => 
			options.ExposeExceptionStackTrace = builder.Environment.IsDevelopment()
        .AddHttpMiddleware<ISchema>()  
        .AddSelfActivatingSchema<PocApplicationSchema>()  
        .AddSystemTextJson());  

if (app.Environment.IsDevelopment())
{
	app.UseGraphQLAltair();
}

app.UseGraphQL<ISchema>();
```

Now test the appliction by running the command behind to start the webapi and go to GraphQL client by adding `ui/altair` at the end of the base url of your application.

```shell
 dotnet run --project .\Poc.GraphQL\Poc.GraphQL.Web\
```

In the altair web client, add this in the query frame :
```graphql
{
  dossier {
    id,
    ref,
    status
  }
}
```

## Exception stack trace

The method `.AddErrorInfoProvider` allows to manage the `IErrorInfoProvider` service. In the exemple below, the option `ExposeExceptionStackTrace` is set to `true` when the application run in development. This option allow to render the exception trace in the response when error occurs.

## Middleware

To create a GraphQL middleware, simply use the `.AddHttpMiddleware<ISchema>()` method.

---
Tags : #dotNET, #GraphQL