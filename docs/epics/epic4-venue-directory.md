# Epic 4: Venue Directory

## Goal/Story

Create a comprehensive, searchable directory of tech-friendly venues in Linz that reduces the friction of finding appropriate event spaces. This epic addresses a key pain point: organizers repeatedly researching and contacting the same venues, often through fragmented personal networks or outdated information.

The venue directory serves as a public marketplace where venues can advertise their capabilities, hosting preferences, and contact information. By centralizing this information, we enable venues to reach more organizers while making it trivial for organizers to find suitable spaces. The directory includes both active venues that regularly host tech events (~10 primary venues) and occasional venues that are open to hosting (~20 secondary venues).

## Considerations

- **External Communication Only**: Contact happens via email/phone, not in-platform messaging
- **Venue Self-Service**: Venues should be able to add themselves, subject to review
- **Trust System**: New venue submissions require trusted member approval
- **Rich Metadata**: Capacity, A/V equipment, WiFi, catering options, accessibility features
- **GDPR Compliance**: Contact information handling, right to deletion
- **Scraping Protection**: Contact information must be protected from automated harvesting
- **Anti-Bot Measures**: Implement rate limiting and human verification for contact access
- **Privacy Controls**: Venues should control visibility of sensitive contact details
- **Mobile-First Design**: Organizers often search for venues on mobile devices
- **Accessibility**: WCAG AA compliance for inclusive directory

## Relevant Documentation

- [ADR-001: Backend Technology](../adr/adr001-backend-technology.md) - PocketBase collections for venues
- [ADR-002: Database Technology](../adr/adr002-database-technology.md) - SQLite storage for venue data
- [ADR-003: Frontend Approach](../adr/adr003-frontend-approach.md) - SSR venue directory pages
- [Data Models: Venue](../guides/data-models.md) - Venue data structure
- [Epic 1: Data Foundation](./epic1-data-foundation-scraping.md) - Initial venue data collection
- [Trust System Documentation](../guides/trust-system.md) - Review queue implementation

## Tasks

### Epic 4.1: Venue Data Model & API
- [ ] Design Venue collection in PocketBase with all required fields
- [ ] Define venue capacity, equipment, and feature fields
- [ ] Create contact person structure (name, email, phone, role)
- [ ] Implement venue hosting preferences (catering, sponsorship options)
- [ ] Build venue status workflow (pending review, approved, archived)
- [ ] Create venue CRUD API endpoints
- [ ] Implement venue search and filtering logic

### Epic 4.2: Venue Directory Display
- [ ] Design venue directory listing UI
- [ ] Implement venue card components with key information
- [ ] Create venue detail page with comprehensive information
- [ ] Add venue photos/images support (optional for MVP)
- [ ] Implement search functionality (name, capacity, features)
- [ ] Add filtering by capacity, equipment, location
- [ ] Create responsive mobile-friendly layout
- [ ] Implement accessibility features (keyboard navigation, ARIA labels)

### Epic 4.3: Venue Submission Workflow
- [ ] Design "Add New Venue" form
- [ ] Implement venue submission form with validation
- [ ] Create submission confirmation and status tracking
- [ ] Build review queue for pending venues
- [ ] Implement email notifications for submission status
- [ ] Add duplicate venue detection
- [ ] Create guidelines for venue submissions

### Epic 4.4: Review Queue & Approval System
- [ ] Build review queue interface for trusted members
- [ ] Implement venue approval/rejection workflow
- [ ] Add review notes and feedback mechanism
- [ ] Create bulk approval capabilities (for initial data import)
- [ ] Implement notifications for submitters
- [ ] Build audit log for approval actions
- [ ] Document review criteria and guidelines

### Epic 4.5: Contact Information Management
- [ ] Implement contact person display on venue pages
- [ ] Design and implement anti-bot measures for contact information protection
- [ ] Create "Contact This Venue" interaction (email/phone click-to-action)
- [ ] Add multiple contact persons support
- [ ] Implement GDPR-compliant contact data handling
- [ ] Create contact information update workflow
- [ ] Add privacy controls for contact visibility
- [ ] Document contact data retention policies

### Epic 4.6: Venue Management & Updates
- [ ] Enable venue editing by trusted members
- [ ] Implement venue update history/changelog
- [ ] Create venue claiming workflow (venues can claim their own listings)
- [ ] Add venue deactivation/archiving
- [ ] Build venue duplicate merging functionality
- [ ] Implement venue categorization/tagging
- [ ] Create venue statistics (events hosted, popularity)

## Definition of Done

- [ ] Directory displays all venues from scraped data
- [ ] Venue detail pages show complete information (capacity, equipment, contact)
- [ ] Venue submission workflow functional with review queue
- [ ] Trusted members can approve/reject new venue submissions
- [ ] Contact information properly displayed with click-to-action
- [ ] Search and filtering work effectively
- [ ] Mobile-responsive design implemented
- [ ] WCAG AA accessibility compliance verified
- [ ] GDPR requirements met for contact data
- [ ] Venue claiming workflow functional
- [ ] Review queue processes venue submissions correctly
