# Epic 2: Deployment & Dev Infrastructure

## Goal/Story

Establish robust, low-maintenance deployment infrastructure that enables continuous integration, automated deployments, and sustainable operations for a volunteer-driven project. This epic creates the technical foundation that allows developers to deploy changes confidently while minimizing operational overhead.

The infrastructure should support rapid iteration during MVP development while establishing patterns that scale for long-term community maintenance. Emphasis on simplicity, automation, and clear documentation ensures that new contributors can understand and maintain the deployment process.

## Considerations

- **Operational Simplicity**: Zero-maintenance deployment preferred, minimal ongoing operational burden
- **Volunteer Sustainability**: Infrastructure must be maintainable by volunteers with varying skill levels
- **Cost Efficiency**: Minimal hosting costs, potentially free VPS hosting available
- **EU Data Sovereignty**: All hosting must comply with GDPR and Austrian data regulations
- **Development Parity**: Local development environment should mirror production closely

## Relevant Documentation

- [ADR-001: Backend Technology](../adr/adr001-backend-technology.md) - Kotlin/Spring Boot deployment requirements
- [ADR-002: Database Technology](../adr/adr002-database-technology.md) - PostgreSQL hosting and management
- [ADR-004: Hosting & Deployment](../adr/adr004-hosting-deployment.md) - VPS + Docker Compose strategy
- [ADR-005: CI/CD & Code Hosting](../adr/adr005-cicd-code-hosting.md) - GitHub Actions pipeline
- [ADR-006: Documentation Strategy](../adr/adr006-documentation-strategy.md) - Infrastructure documentation approach

## Tasks

### Epic 2.1: Infrastructure Planning & Setup
- [ ] Ask Sev & Abl about VPS hosting and potential DevOps support
- [ ] Define testing strategy (unit, integration, e2e testing approach)
- [ ] Document ADR-006: Monitoring & Logging Strategy
- [ ] Document ADR-007: Backup & Disaster Recovery Strategy
- [ ] Create infrastructure architecture diagram
- [ ] Define environment configuration strategy (dev/staging/prod)

### Epic 2.2: Local Development Environment
- [ ] Create Docker Compose setup for local development
- [ ] Configure PostgreSQL container with initialization scripts
- [ ] Set up Spring Boot development profile
- [ ] Document local setup process in developer guide
- [ ] Create database migration workflow (Flyway/Liquibase)
- [ ] Establish local testing database seeding

### Epic 2.3: CI/CD Pipeline Setup
- [ ] Configure GitHub Actions workflow for build
- [ ] Implement automated testing in CI pipeline
- [ ] Set up code quality checks (linting, formatting)
- [ ] Configure Docker image building and registry
- [ ] Implement automated deployment to VPS
- [ ] Create deployment rollback procedures

### Epic 2.4: Production Hosting Setup
- [ ] Configure VPS with Docker and Docker Compose
- [ ] Set up PostgreSQL production database
- [ ] Configure SSL/TLS certificates (Let's Encrypt)
- [ ] Implement reverse proxy (nginx/traefik)
- [ ] Configure application logging and log rotation
- [ ] Set up firewall and basic security hardening

### Epic 2.5: Monitoring & Observability
- [ ] Implement health check endpoints
- [ ] Configure basic uptime monitoring
- [ ] Set up application metrics collection
- [ ] Create alerting for critical failures
- [ ] Document monitoring dashboard access
- [ ] Establish incident response procedures

### Epic 2.6: Backup & Data Protection
- [ ] Implement automated database backups
- [ ] Configure backup retention policies
- [ ] Set up off-site backup storage
- [ ] Document restore procedures
- [ ] Test backup and restore process
- [ ] Create data export capabilities for GDPR compliance

### Epic 2.7: Documentation & Handoff
- [ ] Create comprehensive deployment guide
- [ ] Document infrastructure access and credentials management
- [ ] Write troubleshooting guide for common issues
- [ ] Create runbook for routine operations
- [ ] Document scaling and capacity planning approach
- [ ] Establish volunteer onboarding process for infrastructure

## Definition of Done

- [ ] Local development environment runs with single command
- [ ] CI/CD pipeline automatically tests and deploys code
- [ ] Production environment accessible via HTTPS
- [ ] Database backups run automatically and are tested
- [ ] Basic monitoring alerts infrastructure team of issues
- [ ] All infrastructure is documented and reproducible
- [ ] New developers can set up and deploy within 30 minutes
- [ ] VPS hosting confirmed and configured
- [ ] Testing strategy defined and implemented
- [ ] Zero-downtime deployment capability (nice-to-have for v2)
