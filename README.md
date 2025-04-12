## Script: Join Availability Group with Automatic Seeding Enabled

**Description**:
This script is used to add a **secondary replica** to an existing Always On Availability Group and enable **automatic seeding** by granting the required database creation permission.

**Steps Performed**:
1. Joins the replica to the Availability Group.
2. Grants `CREATE ANY DATABASE` permission to allow automatic seeding from the primary.

**Use Case**:
Run this on secondary replicas when setting up or reconfiguring AGs with automatic seeding enabled.

**Requirements**:
- SQL Server 2016 or later
- Always On Availability Groups must be enabled
- Endpoints must be configured
- Run with a user that has `sysadmin` permissions

**Example**:
```sql
ALTER AVAILABILITY GROUP [AG_Prod] JOIN;
GO
ALTER AVAILABILITY GROUP [AG_Prod] GRANT CREATE ANY DATABASE;
GO
