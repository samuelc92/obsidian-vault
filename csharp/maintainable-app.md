
- Model validation: use Fluent Validation instead of Data Annotation
	- Fluent interface
	- Easy to maintain and read
	- Easy to test
	- Integrates with ModelState.IsValid
	
- Global Authorize Attribute via Fallback Policy:  always create a Fallback Policy, which is the policy that gets evaluated if no other policy is specified.
```csharp
		builder.Services.AddAuthorization(options =>
			options.FallbackPolicy = new AuthorizationPolicyBuilder()
				.RequireAuthenticatedUser()
				.Builder();)
```
- Logs
	- Developer focused
	- Example: log an exception or log response from external API
	- Stop abusing Information! You probably meant Debug. It is possible to define log level by namespace
	- It's okay to not have 100% guaranteed delivery of logs
- Metrics
	- Two types
	- Application: CPU, Network, Responses Times, Queue Depth, etc.
	- Business: How many time did someone click that button
- Audits
	- Recording who, did what, and when in your application
	- Usually for legal, compliance, or traceability reasons
	- Losing any data is unacceptable
	- Store audits with the same data store as the data that's being audited
- Remove the Server Header
	- By default ASP.NET Core adds a "Server Header" which says "Kestrel"
	- This exposes to black hats what you´re running
	- Focuses exploiting known CVEs
		```csharp
		builder.WebHost.UseKestrel(options => options.AddServerHeader = false);
```

- Register Options class directly
```csharp
services.Configure<AppSettings>(Configuration.GetSection("AppSettings"));
services.AddSingleton(registeredServices =>
		registeredServices.GetRequiredService<IOptions<AppSettings>>().Value);

public class A {
	public AppSettings AppSettings { get; }

	public IndexModel(AppSettings appSettings)
	{
		AppSettings = appSettings;	
	}
}
```

- HTTP Security Headers
	- Tells a browser what extra rules to enforce
	- Protects against MITM, clickjacking, cross-site scripting, and more.
	- Nuget package: NetEscapades.AspNetCore.SecurityHeaders
- ValidateOnBuild
	- Singletons can only depend on Singletons
		- The "captive dependency" problem
		- ASP.NET Core will catch this when running in Development but not other enviroments
		```csharp
		builder.Host.UseDefaultServiceProvider(config => 
		{
			// When build IoC containers
			config.ValidateOnBuild = true;
		})
```

- Automate Tests
	- Use FluentAssertions for assertions
- Central Package Management
	- Added in .NET 6
	- Create Directory.Packages.props at the root and define packages and versions there
	- Omit Version attribute in PackageReference
	- All packages will have to omit the Version attribute
	- Can override with VersionOverride attribute