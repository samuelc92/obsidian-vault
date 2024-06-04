
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