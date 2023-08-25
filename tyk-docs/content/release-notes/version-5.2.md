## Changelog for Tyk Gateway:

### Fixed:
- **TT-9747:** Fixed an issue where the user was able to create multiple APIs with the same name and listen path.

- **TT-8526:** Fixed an issue with querying a UDG API containing a query parameter of array type in a REST data source. The UDG was dropping the array type parameter from the final request URL sent upstream.

- **TT-7550:** Fixed an issue where an error was raised when introspecting GraphQL schemas containing customised root types other than Query, Mutation or Subscription. Subsequently, introspection was unavailable for these types of schemas.

### Added:
- **TT-8809:** Added tracing to GraphQL execution for GraphQL proxy only and UDG.
- **TT-8005:** Added websocket protocol _graphql-transport-ws_.
- **TT-7488:** Added OAS Response body transformation contract within the OAS API Definition.


### No Release Notes Available:
- **TT-9527**
- **TT-9504**
- **TT-9460**
- **TT-9272**
- **TT-9192**

### Miscellaneous:
- **TT-9749:** Fixed a bug where allowed/blocked IP validation error in API definition suppressed all other API definition validation errors.
- **TT-9525:** Emit a signal of API change when the OAS migration script is executed, to notify data planes about the change in API structure in the database.
- **TT-9152:** Allows the user to save the data source settings and update the API with one click.
- **TT-8515:** Implemented and exposed a new function ctx.GetOASDefinition which provides access to the OAS API definition from within custom GoPlugins.
- **TT-7489:** Modified: Response processor doesn't need to be configured to enable transform response body middleware anymore.

## Changelog for Tyk Dashboard:

### Fixed:
- **TT-9467:** Fixed a bug where the _most popular endpoints_ was not displayed when filtering per API ("enable_aggregate_lookups": true) and the dashboard is using SQL aggregated analytics.
- **TT-9233:** Fixed a security issue where static and dynamic mTLS requests with an expired certificate could be proxied upstream.
- **TT-9275:** Fixed "show analytics for <date>" dropdown option on Gateway usage chart.
- **TT-9365:** Fixed a bug where a negative value could be provided in the Enforced Timeout configuration.

### Updated:
- **TT-9434:** Updated the process for creating a new API so that users stay on the same screen after saving. This means users are able to continue configuring the API without interruption. Previously, users were redirected to the APIs list after saving.
- **TT-9134:** Allow header injections to be configured for any UDG so that when the consumer request hits the Gateway it will be forwarded to all data sources by default.

### Added:

- **TT-9133:** Added support to use [request context variables]({{< ref "context-variables#the-available-context-variables-are" >}}) in UDG from a global or data source header. This feature can be very useful for customised transformation of request data, for example, in converting a Form-based POST into a JSON-based PUT or to capture an IP address as a header.
- **TT-9448:** Implemented UI for Request/Response Body Transformation middleware.
- **TT-8993:** Added a pre-filled default value to the data source name field when the user adds a new data source vi the _Configure Data Source_ screen. The data source name is pre-filled with <fieldName>_<typeName>, where _typeName_ is _Query_, _Mutation_, _Subscription_ etc.

User can edit the default value if they wish so
- **TT-9309:** Enable MDCB to track the number of connected gateways and gateway health info.
- **TT-9134:** Added a way to configure global headers for any UDG, that will by default be forwarded to all data sources.
- **TT-8959:** Added a new timeout option to allow granular control of cache timeout at the endpoint level.
- **TT-8959:** Enable MDCB to track the number of connected gateways and gateway health info.

### No Release Notes Available:
- **TT-9712**
- **TT-9687**
- **TT-9675**
- **TT-9636**
- **TT-9534**
- **TT-9194**
- **TT-8183**
