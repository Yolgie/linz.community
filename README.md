# linz.community

A coordination platform for tech meetups and community events in Linz, Austria.

Built by the community, for the community—because great events shouldn't require great spreadsheet skills.

## Vision

Linz has 20+ active tech meetups, but organizers still reinvent the wheel every time they plan an event. They waste hours rediscovering venues, re-contacting the same speakers, and accidentally double-booking popular dates. New organizers face a steep startup curve figuring out basic logistics, while experienced organizers juggle spreadsheets and Slack channels to manage resources.

This platform creates a shared organizational brain for the community. Organizers can instantly see what venues are available, which speakers are looking for opportunities, and whether their planned date conflicts with other events. Event templates and checklists codify years of community knowledge, letting new organizers launch professional events from day one.

**This isn't another event promotion tool—it's the coordination infrastructure that makes everything else work better.**

## Features

- **Event Calendar**: Shared calendar with conflict detection and multiple event statuses
- **Venue Directory**: Comprehensive database of event-friendly venues with capabilities and contact info
- **Speaker & Participation Opportunities**: Board where organizers post speaking and other participation opportunities and interrested people can respond
- **Event Templates**: Reusable templates with slots for speakers, venues, organizers, and sponsors
- **Checklists**: Customizable, shareable checklists with automated reminders
- **Community Coordination**: Multi-community event collaboration and resource sharing

## Target Impact

- Reduce event planning overhead
- Eliminate major scheduling conflicts
- Improve the barrier to entry for new organizers
- Make it easier for venues & hosts & sponsors & speakers to support local communities

## Technology Stack

- **Backend**: PocketBase ([ADR-001](docs/adr/adr001-backend-technology.md))
- **Database**: SQLite (bundled with PocketBase) ([ADR-002](docs/adr/adr002-database-technology.md))
- **Frontend**: Server-side rendering + Alpine.js ([ADR-003](docs/adr/adr003-frontend-approach.md))
- **Hosting**: VPS with Docker ([ADR-004](docs/adr/adr004-hosting-deployment.md))
- **CI/CD**: GitHub Actions ([ADR-005](docs/adr/adr005-cicd-code-hosting.md))

## Getting Started

### Prerequisites
- PocketBase binary
- Docker & Docker Compose (for deployment)

### Quick Start
```bash
git clone [repository-url]
cd linz.community
./pocketbase serve
```

Full setup instructions: [docs/guides/development-setup.md](docs/guides/development-setup.md)

## Roadmap to MVP

The MVP will be a publicly accessible demo system showcasing core coordination workflows for the Linz tech community.

### Epic Overview
- **[Epic 0](docs/epics/epic0-planning-documentation.md)**: Planning & Documentation  
- **[Epic 1](docs/epics/epic1-data-foundation-scraping.md)**: Data Foundation & Scraping
- **[Epic 2](docs/epics/epic2-deployment-infrastructure.md)**: Deployment & Dev Infrastructure  
- **[Epic 3](docs/epics/epic3-core-event-calendar.md)**: Core Event Calendar
- **[Epic 4](docs/epics/epic4-venue-directory.md)**: Venue Directory
- **[Epic 5](docs/epics/epic5-speaker-opportunity-board.md)**: Speaker Opportunity Board
- **[Epic 6](docs/epics/epic6-demo-infrastructure-polish.md)**: Demo Infrastructure & Polish

### MVP Scope
- Use some real scraped data from Linz tech events and venues to make demo more approachable
- Event calendar with conflict detection
- Venue directory with contact information
- Speaker opportunity board for coordination
- Role-based demo interface (no authentication required)
- Responsive design optimized for mobile-first usage

**Target**: Functional demo platform for community feedback and validation

## Documentation

- [**ADR-006: Documentation Strategy**](docs/adr/adr006-documentation-strategy.md)
- **Documentation**: [docs/](docs/)
- **Architecture Decisions**: [docs/adr/](docs/adr/)
- **Epic Breakdown**: [docs/epics/](docs/epics/)

## Contributing

This is a community project built by volunteers for the Linz tech community. We're always happy for input and pull requests!

See [CONTRIBUTORS.md](CONTRIBUTORS.md) for details.

## License

MIT License - see [LICENSE](LICENSE) file for details.

## Community

**Target Community**: Linz, Austria tech meetups and communities including Coderdojo, hackathons, game jams, student societies, and 15+ regular meetup groups.
