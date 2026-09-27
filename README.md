# SAP B1 Multi-company Reporting Portal

Solution design for a read-only reporting portal that consolidates selected SAP Business One HANA data across multiple company databases.

## Status

**Solution design.** The repository describes the architecture, security model and report catalogue. It does not claim a production deployment.

## Reporting Scope

- Sales and Purchase
- Balance Sheet and Profit and Loss
- Inventory and Stock
- Customer and Vendor Outstanding
- Fixed Assets
- Production and operational KPIs

## Architecture

1. Each SAP B1 company exposes approved read-only reporting views.
2. A reporting service queries each company using least-privilege credentials.
3. A common data model standardizes company, branch, currency and account dimensions.
4. The portal applies company-level and report-level access.
5. Users can filter, compare and export approved results.

## Security Model

- Dedicated read-only database user
- Access only to approved reporting views
- No direct transactional updates
- Company and branch authorization
- Query timeout and result-size limits
- Audit log for access and exports

## Suggested Components

SAP HANA Views · FastAPI · REST API · Role Based Access · Web Dashboard · Excel Export

## Implementation Phases

1. Define KPI and report catalogue.
2. Standardize dimensions across company databases.
3. Create and validate reporting views.
4. Implement authentication and authorization.
5. Build dashboard and export functions.
6. Run reconciliation, performance and security testing.
