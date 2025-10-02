# Epic 3: Core Event Calendar

## Goal/Story

Build the central coordination feature of linz.community: a shared calendar that displays all tech events in Linz with intelligent conflict detection. This epic creates the core experience that allows organizers to see the full landscape of community events, understand potential scheduling conflicts, and make informed decisions about when to schedule their activities.

The calendar serves as the "single source of truth" for what's happening in Linz's tech scene, addressing one of the most frequently cited pain points: accidentally double-booking dates or scheduling against major community events. Critically, the calendar shows all events by default - including tentative and placeholder events - ensuring organizers can coordinate effectively even during early planning stages. By making event conflicts visible and providing contextual information, the platform reduces coordination overhead and improves community-wide planning.

## Considerations

- **Mobile-First Design**: Many organizers plan events from phones
- **Accessibility**: WCAG AA compliance required for inclusive community platform
- **Performance**: Low computational complexity expected, focus on usability over speed optimization
- **Event Status Workflow**: Support tentative, confirmed, placeholder, and private event states
- **All Events Visible**: Tentative and placeholder events visible by default for effective conflict detection
- **Conflict Detection**: Real-time feedback when selecting dates, with contextual notes
- **Multi-Community Events**: Events can be organized by multiple communities together

## Relevant Documentation

- [ADR-001: Backend Technology](../adr/adr001-backend-technology.md)
- [ADR-002: Database Technology](../adr/adr002-database-technology.md)
- [ADR-003: Frontend Approach](../adr/adr003-frontend-approach.md)
- [Data Models: Event & Community](../guides/data-models.md)
- [Epic 1: Data Foundation](./epic1-data-foundation-scraping.md)

## Tasks

### Epic 3.1: Event Data Model & API
- [ ] Implement Event entity with all required fields (title, description, date, time, location, etc.)
- [ ] Create event status enum (tentative, confirmed, placeholder, private, published)
- [ ] Build community-event relationship (single and multi-community events)
- [ ] Implement event CRUD REST API endpoints
- [ ] Add conflict detection logic (same date/time/venue checks)
- [ ] Create API for fetching events by date range
- [ ] Implement event filtering and search capabilities

### Epic 3.2: Calendar Display Views
- [ ] Design calendar UI mockups (monthly and weekly views)
- [ ] Implement monthly calendar grid component
- [ ] Implement weekly calendar list view
- [ ] Display ALL event statuses by default (tentative, confirmed, placeholder, published)
- [ ] Add event status visual indicators (colors, icons) to distinguish status levels (maybe percentages?)
- [ ] Create event detail modal/page
- [ ] Implement optional status filters (hidden by default, all events shown)
- [ ] Implement responsive layout for mobile devices
- [ ] Add accessibility features (keyboard navigation, screen reader support)

### Epic 3.3: Event Creation Workflow
- [ ] Design event creation form UI
- [ ] Implement server-side form rendering
- [ ] Add Alpine.js for date picker interactivity
- [ ] Build real-time conflict detection on date selection
- [ ] Display conflict warnings with contextual information
- [ ] Implement form validation (client and server-side)
- [ ] Create success/error feedback messages

### Epic 3.4: Event Status Management
- [ ] Implement event status transitions (placeholder → tentative → confirmed → published)
- [ ] Add status change permissions (only organizers can modify)
- [ ] Create "hidden from all" checkbox for private planning
- [ ] Build status change history/audit log
- [ ] Add status filters to calendar view
- [ ] Implement notifications for status changes (optional for MVP)

### Epic 3.5: Multi-Community Event Support
- [ ] Enable adding multiple organizing communities to events
- [ ] Implement permissions (any organizer can add communities)
- [ ] Create UI for managing co-organizing communities
- [ ] Display all organizing communities on event details
- [ ] Handle event editing permissions across communities
- [ ] Support community-specific event notes/comments

### Epic 3.6: Event Edit & Delete
- [ ] Implement event editing form
- [ ] Add edit permissions (community members only)
- [ ] Create event update API endpoints
- [ ] Implement soft delete for events
- [ ] Add event history/changelog
- [ ] Build event duplication feature (for recurring events)

## Definition of Done

- [ ] Calendar displays all events from scraped data
- [ ] Monthly and weekly views both functional and responsive
- [ ] Event creation form works with conflict detection
- [ ] Conflicts shown in real-time when selecting dates
- [ ] All event status levels supported (tentative, confirmed, etc.)
- [ ] Multi-community events can be created and managed
- [ ] Calendar is mobile-friendly and WCAG AA compliant
- [ ] Event CRUD operations work correctly with proper permissions
- [ ] Conflict detection logic identifies overlapping events accurately
- [ ] UI provides clear feedback for all user actions
