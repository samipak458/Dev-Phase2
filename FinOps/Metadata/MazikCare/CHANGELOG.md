# Changelog

All notable changes to the MazikCare model will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.0.0] - 2024-10-08

### Added
- Initial release of MazikCare D365FO model
- Core claims management functionality
- Patient and case management features
- Healthcare provider and site management
- Revenue cycle management (RCM) capabilities
- Billing and invoicing features
- Calendar and appointment scheduling (HTML/CSS/JS resources)
- Security roles for various user types:
  - Claims agents
  - Billing administrators
  - Call center staff
  - Healthcare professionals
  - Clinic staff
  - IT administrators
- Label files for localization (en-US)
- Integration with iTextSharp for PDF generation
- Multiple data entities for integration
- Comprehensive security model with role-based access

### Dependencies
- D365FO ApplicationSuite and related modules
- iTextSharp library (Bin/itextsharp.dll) for PDF generation

### Technical Details
- Model ID: 895972557
- Publisher: Mazik Global
- Layer: 8 (ISV)
- Module References: ApplicationCommon, ApplicationFoundation, ApplicationPlatform, ApplicationSuite, and 25+ other standard modules

### Documentation
- Created comprehensive README.md
- Added this CHANGELOG.md for version tracking
- Added LICENSE.md for licensing information
- Added THIRD-PARTY-LICENSES.md for dependency licenses
- Added CODEOWNERS for maintainer assignments
- Added CONTRIBUTING.md for development guidelines
- Created .gitignore for repository hygiene

### Security
- Implemented role-based access control
- No hardcoded credentials or sensitive data
- Security best practices documentation added

---

## Template for Future Releases

When adding new changes, use the following format:

## [Unreleased]

### Added
- New features

### Changed
- Changes to existing functionality

### Deprecated
- Features that will be removed in future versions

### Removed
- Removed features

### Fixed
- Bug fixes

### Security
- Security improvements or vulnerability fixes

---

**Note:** This changelog was initialized as part of repository improvements. Prior history before version 1.0.0.0 was not formally tracked.
