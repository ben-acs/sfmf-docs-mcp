# Access Data and Platform Capabilities

While Agentforce Vibes automatically generates code for data access, it's helpful to understand how you can write your own code to access Salesforce data and related platform capabilities from your web app.

Use the Data SDK for data access with these benefits:

- **Abstraction and consistency:** Data SDK abstracts environment-specific APIs, so you call a simple method and the SDK handles the implementation details for the specific host environment, for example, Lightning Experience or an Experience Builder site.
- **Capability detection:** Data SDK includes integrated capability detection to identify the runtime environment, infer its capabilities, and determine the concrete way to implement those capabilities. Given the built-in detection, component authors can code safely across deployment scenarios.
- **Modern developer experience:** Data SDK provides full TypeScript definitions to offer IntelliSense and autocomplete functionality, compile-time type safety, and uses Promises for structured error handling (try/catch blocks) instead of loosely-typed events.

Learn how you can access and update Salesforce data using the Data SDK.

- [Work with the Data SDK](data-sdk-intro.md)
- [Access Salesforce APIs](data-sdk-connect.md)
- [GraphQL Query Parameters](data-sdk-query.md)
- [GraphQL Mutate Parameters](data-sdk-mutate.md)
- [GraphQL Queries](data-sdk-graphql.md)
- [GraphQL Mutations](data-sdk-graphql-mutation.md)
- [Error Handling](data-sdk-graphql-error.md)
- [Cache Control](data-sdk-cache-control.md)
- [Per-Request Headers](data-sdk-request-headers.md)
- [Data SDK Extensions](data-sdk-extension.md)

Explore platform capabilities for your web app.

- [Get App Identity](data-sdk-identity.md)
- [Manage the Host UI](data-sdk-view.md)
- [Localize Your App](data-sdk-i18n.md)

Find out more about the agent skills you can use to speed up data access implementation in your web app.

- [Use Skills for Data Access](data-sdk-skills.md)
