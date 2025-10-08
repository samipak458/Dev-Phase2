# MazikCare - Dynamics 365 Finance and Operations Model

## Overview

MazikCare is a comprehensive Dynamics 365 Finance and Operations (D365FO) model package designed for healthcare management, including claims processing, patient management, billing, and revenue cycle management (RCM) functionality.

**Publisher:** Mazik Global  
**Version:** 1.0.0.0  
**Model ID:** 895972557

## Purpose

The MazikCare model extends D365FO with specialized healthcare and medical billing capabilities, including:

- Claims management and processing
- Patient and case management
- Healthcare provider and site management
- Revenue cycle management (RCM)
- Billing and invoicing for healthcare services
- Integration with various healthcare systems and APIs
- Compliance and security management for healthcare data

## Directory Structure

```
MazikCare/
├── Bin/                    # Binary dependencies
│   └── itextsharp.dll     # PDF generation library (see THIRD-PARTY-LICENSES.md)
├── Descriptor/            # Model descriptor files
│   └── MazikCare.xml      # Model metadata and dependencies
├── MazikCare/             # Model elements and artifacts
│   ├── AxClass/           # X++ classes
│   ├── AxDataEntityView/  # Data entities
│   ├── AxEnum/            # Enumerations
│   ├── AxForm/            # User interface forms
│   ├── AxLabelFile/       # Localization labels
│   ├── AxResource/        # Resources (HTML, CSS, JS)
│   ├── AxSecurityRole/    # Security roles and permissions
│   ├── AxTable/           # Data tables
│   └── ...                # Other model elements
└── README.md              # This file
```

## Dependencies

### D365FO Module References

MazikCare depends on the following standard D365FO modules:

- ApplicationCommon
- ApplicationFoundation
- ApplicationPlatform
- ApplicationSuite
- ApplicationWorkspaces
- Calendar
- CaseManagement
- Directory
- GeneralLedger
- Ledger
- Personnel
- Project
- And others (see Descriptor/MazikCare.xml for complete list)

### Third-Party Dependencies

- **iTextSharp** (itextsharp.dll) - PDF generation library
  - Version: 5.x (check THIRD-PARTY-LICENSES.md for details)
  - License: AGPL/Commercial (see THIRD-PARTY-LICENSES.md)
  - Used for: Generating PDF reports and documents

## Setup and Installation

### Prerequisites

1. Dynamics 365 Finance and Operations environment (version 10.0+)
2. Visual Studio with D365FO development tools
3. Access to D365FO development environment
4. Required module dependencies installed

### Installation Steps

1. **Clone or Download the Model**
   ```
   # Repository is already cloned if you're reading this
   ```

2. **Add Model to D365FO Environment**
   - Copy the entire `MazikCare` folder to your D365FO PackagesLocalDirectory
   - Typically located at: `K:\AosService\PackagesLocalDirectory\` or `C:\AOSService\PackagesLocalDirectory\`

3. **Build the Model**
   - Open Visual Studio
   - Go to Dynamics 365 > Build Models
   - Select MazikCare model and build

4. **Synchronize Database**
   - After successful build, synchronize the database
   - Dynamics 365 > Synchronize database

5. **Deploy to Environment**
   - Create a deployable package
   - Upload and apply through LCS (Lifecycle Services)

### Development Setup

1. Open Visual Studio with D365FO tools installed
2. Create or open a D365FO project
3. Add the MazikCare model to your project
4. Set MazikCare model in your project properties

## Usage

### Key Features

#### 1. Claims Management
- Create and manage healthcare claims
- Track claim status and workflow
- Integration with payors and clearinghouses

#### 2. Patient Management
- Patient records and demographics
- Case management
- Appointment scheduling

#### 3. Billing and Revenue Cycle
- Invoice generation
- Payment processing
- Revenue tracking and reporting

#### 4. Security Roles
MazikCare includes several predefined security roles:
- HMClaimAgentRoles - For claims processing agents
- HMBillingAdminRole - For billing administrators
- CallCenterManager/Agent - For call center operations
- ClinicHealthProfessional - For healthcare providers
- And more (see AxSecurityRole/ directory)

### Configuration

1. **Initial Setup**
   - Configure organization settings
   - Set up sites and locations
   - Configure security roles and users

2. **System Parameters**
   - Access MazikCare parameters through the main menu
   - Configure claim processing rules
   - Set up integration endpoints

3. **User Access**
   - Assign appropriate security roles to users
   - Configure user preferences
   - Set up workflows

## Development Guidelines

### Code Standards

- Follow Microsoft D365FO best practices
- Use proper naming conventions (HM prefix for MazikCare objects)
- Document all classes and methods
- Implement proper error handling

### Testing

- Run D365FO Best Practice checks before committing
- Test all customizations in a development environment
- Validate database synchronization
- Test security role access

### Contributing

Please see CONTRIBUTING.md for guidelines on:
- Code review process
- Branching strategy
- Pull request requirements
- Testing requirements

## Security Considerations

⚠️ **Important Security Notes:**

1. **No Secrets in Code**: Never commit credentials, API keys, or sensitive data
2. **Environment Variables**: Use environment-specific configuration files
3. **Data Protection**: Comply with HIPAA and other healthcare data regulations
4. **Access Control**: Use role-based security for all sensitive operations
5. **Audit Logging**: Enable and monitor audit logs for compliance

## Troubleshooting

### Common Issues

1. **Build Errors**
   - Ensure all dependent modules are present
   - Check for missing references
   - Verify Visual Studio D365FO tools are up to date

2. **Database Sync Failures**
   - Check for table conflicts
   - Review sync logs
   - Ensure proper permissions on the database

3. **Runtime Errors**
   - Check application event logs
   - Review D365FO trace logs
   - Verify configuration settings

## Support and Documentation

- **Internal Documentation**: See project wiki for detailed technical documentation
- **Microsoft Docs**: [Dynamics 365 Finance and Operations Documentation](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/)
- **Issue Tracking**: Report issues through the project's issue tracker

## License

See LICENSE.md for licensing information.

## Version History

See CHANGELOG.md for version history and release notes.

## Ownership

See CODEOWNERS file for maintainer information.

---

**Last Updated:** 2024  
**Maintained By:** Mazik Global Development Team
