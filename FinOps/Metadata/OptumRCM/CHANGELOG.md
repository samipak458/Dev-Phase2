# Changelog

All notable changes to the OptumRCM model will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.0] - Initial Release

### Added

#### Core Functionality
- Initial implementation of OptumRCM model for Dynamics 365 Finance and Operations
- Healthcare Revenue Cycle Management (RCM) capabilities
- Claims management system with support for multiple claim types:
  - CMS 1500 (Professional claims)
  - UB04 (Institutional claims)
  - PBM claims

#### Claims Management
- Claim header and line management
- Claim version archiving
- Claim totals and measurement tracking
- Priority-based claim workflow
- Pool-based claim organization
- Claim aging reports (0-30, 30-60, 60-90, 90-120, 120+ days)
- Action and notes tracking for claims
- Template support for action and notes

#### Patient Management
- Patient information management
- Patient insurance tracking
- Multiple insurance coverage support
- Contact information for patients
- Relationship code management

#### Payor Management
- Payor setup and configuration
- Billed sites management
- Payor type classification
- Timely filing tracking

#### Workflow and Assignment
- Agent-based claim assignment
- Supervisor oversight capabilities
- Manager-level reporting and control
- Auto-assignment of related claims
- Priority copying functionality
- Pool management with multiple thread support

#### User Interface
- Agent workspace with tiles for claim aging and assignment
- Supervisor workspace for team oversight
- Manager workspace for organization-wide visibility
- Claims list pages with filtering and sorting
- Detail forms for claims, patients, and payors
- Follow-up date tracking (next 7 days view)
- Claims worked in last 30 days view

#### Security
- Role-based access control with four primary roles:
  - HMClaimAgentRolesV2: For claim processing agents
  - mzkClaimManagerRolesV2: For claim managers
  - HMClaimSupervisorRole: For supervisors
  - HMMazikCareAdminRole: For system administrators
- Security privileges for maintain and view operations
- Security duties aligned with business processes

#### Data Entities
- Export/import entities for claims
- Patient data entities
- Payor information entities
- Insurance entity extensions
- Active and inactive user list entities
- Collection pool entities

#### Integration
- WellSky API integration support
- API request and response logging
- Batch job for WellSky API processing
- Service bus integration for data exchange

#### Setup and Configuration
- Therapy type setup
- Invoice type configuration
- Region management
- Billed sites setup
- Action type configuration
- Claim table setup
- Revenue category configuration
- Other coverage code management

#### Reporting
- Adjudication reports
- Claim aging by various periods
- Active claims by payor type
- Claim totals related to payor
- Patient claims overview
- Claims with no actions/notes (7+ days)
- Outbound inactivity feed

#### Localization
- English (US) label file with comprehensive labeling
- Support for localized text across all forms and reports

#### Extensions
- Extensions to base D365FO entities:
  - Patient entity extensions
  - Team member entity extensions
  - Contact information extensions
  - Various EDT (Extended Data Type) extensions

### Dependencies
- Base MazikCare model (required)
- Standard D365FO modules as listed in model descriptor
- Dynamics 365 Finance and Operations platform

### Known Limitations
- Currently supports English (US) localization only
- Requires MazikCare base model

### Technical Details
- Model ID: 896000229
- Publisher: Mazik Global
- Layer: 8 (ISV layer)
- Version: 1.0.0.0
- Customization: Allowed

---

## Version History Notes

This changelog will be updated with each release to document:
- **Added**: New features and functionality
- **Changed**: Changes to existing functionality
- **Deprecated**: Features that will be removed in future versions
- **Removed**: Features removed in this version
- **Fixed**: Bug fixes
- **Security**: Security-related changes and fixes

## How to Use This Changelog

- Each version is documented with a version number and release date
- Changes are categorized by type (Added, Changed, Fixed, etc.)
- Breaking changes are clearly marked with **BREAKING CHANGE** prefix
- Links to relevant issues or work items may be included for traceability

## Upgrade Notes

When upgrading between versions:
1. Review the changelog for breaking changes
2. Check dependencies and module requirements
3. Follow the upgrade path specified in release notes
4. Test thoroughly in a non-production environment
5. Back up data before applying updates

---

For questions about specific changes or version history, please contact the Mazik Global development team.
