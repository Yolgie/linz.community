# ADR-001: Backend Technology

## Status
Accepted

## Context
The linz.community platform requires a backend technology that supports rapid MVP development, minimal operational overhead, and long-term volunteer maintainability. The platform will serve a relatively small community (15-20 active tech meetups in Linz) with modest traffic and data requirements.

Key requirements:
- Operational simplicity and zero-maintenance deployment
- Easy for volunteers with varying skill levels to understand and maintain
- Minimal hosting costs
- Built-in features for common requirements (auth, CRUD, real-time updates)
- GDPR compliance and EU data sovereignty
- Good LLM support for development assistance

## Decision
**Use PocketBase as the backend platform.**

PocketBase is an open-source backend consisting of embedded database (SQLite) with realtime subscriptions, built-in auth management, convenient dashboard UI and simple REST-ish API, packaged as a single portable file.

## Consequences

### Positive
- **Single binary deployment**: No JVM, no complex runtime dependencies
- **Drastically reduced code**: Built-in CRUD, auth, file storage, admin UI
- **Lower maintenance burden**: Fewer moving parts, simpler to debug
- **Real-time out of the box**: WebSocket subscriptions for calendar updates
- **Fast MVP development**: Most features are configuration, not code
- **Lower resource requirements**: Runs efficiently on minimal hardware
- **Simple backup**: Database is a single file
- **Admin UI included**: No need to build separate admin interfaces

### Negative
- **Less mature ecosystem**: Smaller community than Spring Boot
- **Go-based extensions**: Custom logic requires Go knowledge (vs Kotlin)
- **Fewer third-party integrations**: May need more custom code for specialized features
- **Less enterprise patterns**: Simpler architecture may require rethinking for complex features

### Neutral
- **Different paradigm**: PocketBase is more configuration-driven than code-driven
- **Framework lock-in**: Heavily tied to PocketBase patterns and conventions
- **Community size**: Growing rapidly but still smaller than established frameworks

## Alternatives Considered

### Kotlin + Spring Boot
- **Pros**: Robust, mature, excellent for complex business logic, strong typing
- **Cons**: Higher complexity, more code to maintain, heavier resource requirements, steeper learning curve for volunteers
- **Why rejected**: Operational overhead too high for volunteer-driven project

### Node.js + Express + TypeScript  
- **Pros**: Fast iteration, same language as potential frontend, good LLM support
- **Cons**: Still requires building auth, CRUD, admin UI from scratch
- **Why rejected**: Too much boilerplate for modest requirements

### Python + FastAPI
- **Pros**: Rapid API development, excellent documentation
- **Cons**: Still requires separate database, auth system, admin interface
- **Why rejected**: More moving parts than necessary

## Implementation Notes
- Use PocketBase JavaScript SDK for any client-side interactions
- Extend with Go hooks/routes only when necessary for complex business logic
- Leverage built-in collections for core data models (Events, Venues, Communities)
- Use PocketBase's realtime subscriptions for calendar conflict detection

## References
- [PocketBase Documentation](https://pocketbase.io/docs/)
- [PocketBase GitHub](https://github.com/pocketbase/pocketbase)
- [Epic 2: Deployment & Dev Infrastructure](../epics/epic2-deployment-infrastructure.md)
