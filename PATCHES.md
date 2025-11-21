# Kairo Care Patches

## GraphQL Tracer Integration (v1.7.12)

- **File**: `lib/graphql/resolver.ex`
- **Purpose**: Pass domain tracer configuration to GraphQL queries for AppSignal integration
- **Changes**: Added `tracer: AshGraphql.Domain.Info.tracer(domain)` to the `Ash.Query.for_read/4` calls used by single-record and list resolvers
- **Reason**: Without this, GraphQL operations do not propagate the configured tracer, preventing our telemetry handlers from renaming AppSignal spans.
