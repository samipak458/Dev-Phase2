# OptumRCM Model

## Overview

The OptumRCM model is a Dynamics 365 Finance and Operations (D365FO) customization package that provides Revenue Cycle Management (RCM) functionality for healthcare claim processing. This model extends the base MazikCare functionality with specialized features for managing claims, patients, payors, and related healthcare operations.

## Purpose

OptumRCM enables comprehensive healthcare revenue cycle management by providing:

- **Claims Management**: Process and track various claim types (CMS 1500, UB04, institutional)
- **Patient Management**: Maintain patient information, insurance, and contact details
- **Payor Management**: Handle payor relationships and billing sites
- **Workflow Automation**: Priority-based claim routing and agent assignment
- **Action & Notes Tracking**: Document claim activities and communications
- **Reporting & Analytics**: Claims aging, totals, and measurement views
- **Integration Support**: WellSky API integration and data entities for external systems

## Version

**Current Version**: 1.0.0.0
- Major: 1
- Minor: 0
- Build: 0
- Revision: 0

See [CHANGELOG.md](CHANGELOG.md) for version history and updates.

## Dependencies

### Module References

This model depends on the following D365FO modules:

- ApplicationCommon
- ApplicationFoundation
- ApplicationPlatform
- ApplicationSuite
- ApplicationWorkspaces
- BankTypes
- Calendar
- CaseManagement
- ContactPerson
- Currency
- Dimensions
- Directory
- ElectronicReporting
- FinanceInsightsContracts
- FinancialReporting
- FiscalBooks
- GeneralLedger
- Ledger
- **MazikCare** (Base model - required)
- Measurement
- Personnel
- PersonnelCore
- PersonnelManagement
- Policy
- Project
- Retail
- SourceDocumentation
- SourceDocumentationTypes
- Subledger
- Tax
- TaxEngine
- UnitOfMeasure

### Model References

- **MazikCare**: The OptumRCM model extends and builds upon the MazikCare base model. Ensure MazikCare is deployed before installing OptumRCM.

## Setup Instructions

### Prerequisites

1. Dynamics 365 Finance and Operations environment (Cloud or on-premises)
2. MazikCare model installed and configured
3. Appropriate D365FO license with required modules
4. Administrator or developer access to the environment

### Installation Steps

1. **Deploy the Model Package**
   ```
   - Copy the OptumRCM model package to the D365FO environment
   - Deploy using ModelUtil.exe or through Lifecycle Services (LCS)
   ```

2. **Synchronize Database**
   ```
   - Run database synchronization to create tables, views, and other database objects
   - Can be performed via Visual Studio or through the D365FO UI
   ```

3. **Configure Security**
   ```
   - Assign security roles:
     * HMClaimAgentRolesV2: For claim agents
     * mzkClaimManagerRolesV2: For claim managers
     * HMClaimSupervisorRole: For supervisors
     * HMMazikCareAdminRole: For administrators
   ```

4. **Initialize Setup Data**
   ```
   - Configure claim types, therapy types, invoice types
   - Set up regions, billed sites, and payor information
   - Configure action types and templates
   - Set up pools and priorities for claim workflow
   ```

5. **Configure Integration (Optional)**
   ```
   - Set up WellSky API configuration if integration is required
   - Configure data entities for external data exchange
   ```

6. **Test the Installation**
   ```
   - Verify forms and menu items are accessible
   - Test claim creation and workflow
   - Validate security access for different roles
   ```

## Usage

### Key Features and Forms

1. **Claim Management**
   - Claims workspace for agents, supervisors, and managers
   - Claim detail forms with header and line information
   - Action and notes tracking
   - Priority and pool assignment

2. **Patient Management**
   - Patient information forms
   - Patient insurance setup
   - Contact information management

3. **Setup and Configuration**
   - Therapy types, invoice types, billed sites
   - Region management
   - Payor setup
   - Action and note templates
   - Priority and pool configuration

4. **Reporting**
   - Claim aging reports
   - Active claims by payor type
   - Claims with follow-up dates
   - User activity and inactivity feeds

### Workspaces

- **Agent Workspace**: View and work on assigned claims
- **Supervisor Workspace**: Monitor team performance and claim aging
- **Manager Workspace**: Oversight of all pools and claims

## Architecture

### Key Components

- **Tables**: Claim tables, patient tables, payor tables, setup tables
- **Forms**: Data entry and display forms for all entities
- **Classes**: Business logic for claim processing, validation, and workflow
- **Data Entities**: Views for data import/export and integration
- **Security**: Role-based access control with privileges and duties
- **Reports**: SSRS reports for claims and analytics
- **Labels**: Localized text resources (English-US included)

### Model Structure

```
OptumRCM/
├── Descriptor/
│   └── OptumRCM.xml          # Model metadata and dependencies
└── OptumRCM/
    ├── AxClass/              # X++ business logic classes
    ├── AxTable/              # Table definitions
    ├── AxForm/               # Form definitions
    ├── AxDataEntityView/     # Data entities for integration
    ├── AxSecurityRole/       # Security role definitions
    ├── AxSecurityPrivilege/  # Security privileges
    ├── AxSecurityDuty/       # Security duties
    ├── AxQuery/              # Query definitions
    ├── AxReport/             # Report definitions
    ├── AxEnum/               # Enumeration types
    ├── AxEdt/                # Extended data types
    ├── AxView/               # View definitions
    ├── AxTile/               # Workspace tiles
    ├── AxMenuItemDisplay/    # Display menu items
    ├── AxMenuItemAction/     # Action menu items
    ├── AxLabelFile/          # Label resources
    └── [Extensions]/         # Extensions to base D365FO objects
```

## Security Best Practices

### Data Protection

- **No Secrets in Code**: This model does not store secrets, API keys, or sensitive credentials in code or configuration files
- **Environment Variables**: Use D365FO Key Vault integration for storing sensitive configuration
- **Connection Strings**: Store connection strings in secure configuration, not in source code
- **Patient Data**: Handle PHI (Protected Health Information) according to HIPAA requirements

### Development Practices

- All code changes require peer review
- Use D365FO Best Practice checks before committing code
- Run static analysis and validate against D365FO standards
- Restrict direct commits to main branches
- Test security roles and access controls thoroughly

### Secure Configuration

1. Enable audit logging for sensitive operations
2. Use encrypted connections for integrations
3. Implement proper error handling to avoid information disclosure
4. Follow least privilege principle for security role assignments
5. Regularly review and update security configurations

## Contributing

Please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines on contributing to this model.

## Ownership

See [CODEOWNERS](CODEOWNERS) for information about code ownership and review requirements.

## License

See [LICENSE](LICENSE) for licensing information.

## Support

For issues, questions, or support requests, please contact the Mazik Global development team.

## Additional Resources

- [Dynamics 365 Finance and Operations Documentation](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/)
- [D365FO Development Best Practices](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/dev-tools/developer-home-page)
- [MazikCare Documentation](../MazikCare/README.md) (if available)
