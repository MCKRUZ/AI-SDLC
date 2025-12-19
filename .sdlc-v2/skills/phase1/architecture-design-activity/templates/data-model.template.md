# Data Model Document Template

**Project Name**: [Descriptive name for this initiative]  
**Date**: [YYYY-MM-DD]  
**Version**: [v1.0, v2.0, etc.]  
**Status**: [Draft | Under Review | Approved]  
**Data Architect**: [Name/Role]

---

## Purpose of This Document

This data model document defines **how data is structured, stored, and related** within the system. It provides the blueprint for database design and ensures data integrity, performance, and maintainability.

**What This Document Defines**:
- Entities and their attributes
- Relationships between entities
- Constraints and validation rules
- Indexes and optimization strategies
- Data types and formats
- Privacy and compliance considerations
- Migration and evolution strategies

**What This Document Does NOT Define**:
- Application logic (that's in architecture and code)
- Business rules (those are in spec)
- User interface designs (that's UX/UI)

**Who Uses This Document**:
- Database administrators for implementation
- Backend developers for ORM configuration
- Data engineers for ETL processes
- QA team for data validation testing
- Security team for privacy review

---

## Executive Summary

**Data Model Type**: [Relational | Document | Graph | Key-Value | Hybrid]

**Primary Database**: [e.g., SQL Server 2022]

**Total Entities**: [X entities/tables]

**Data Volumes** (Projected):
- Year 1: [Size]
- Year 3: [Size]
- Year 5: [Size]

**Key Design Principles**:
1. [Principle 1 - e.g., "Normalized to 3NF with selective denormalization"]
2. [Principle 2 - e.g., "Performance-first for read-heavy operations"]
3. [Principle 3 - e.g., "Privacy by design - PII encrypted and segregated"]

---

## Data Modeling Approach

### Methodology

**Normalization Strategy**: [3NF / BCNF / Selective Denormalization]

**Rationale**: 
[Why this normalization level was chosen - balance between data integrity and performance]

**Denormalization Decisions**:
- [Decision 1]: [What was denormalized, why, trade-offs]
- [Decision 2]: [What was denormalized, why, trade-offs]

---

### Naming Conventions

**Tables/Collections**:
- **Format**: PascalCase, plural nouns (e.g., `Users`, `Orders`, `OrderItems`)
- **Junction Tables**: [Table1][Table2] (e.g., `UsersRoles`)

**Columns/Fields**:
- **Format**: PascalCase (e.g., `FirstName`, `EmailAddress`)
- **Primary Keys**: [EntityName]Id (e.g., `UserId`, `OrderId`)
- **Foreign Keys**: [ReferencedEntity]Id (e.g., `UserId` in Orders table)
- **Boolean Fields**: Is[Condition] (e.g., `IsActive`, `IsDeleted`)
- **Dates**: [Action]At or [Action]Date (e.g., `CreatedAt`, `UpdatedAt`)

**Indexes**:
- **Format**: IX_[TableName]_[Column(s)] (e.g., `IX_Users_Email`)
- **Unique Constraints**: UX_[TableName]_[Column(s)] (e.g., `UX_Users_Email`)

**Constraints**:
- **Primary Key**: PK_[TableName] (e.g., `PK_Users`)
- **Foreign Key**: FK_[ChildTable]_[ParentTable]_[Column] (e.g., `FK_Orders_Users_UserId`)
- **Check Constraint**: CK_[TableName]_[Condition] (e.g., `CK_Orders_AmountPositive`)

---

## Entity-Relationship Overview

### Domain Model Diagram

```
┌─────────────────────────────────────────────────────────────┐
│                     User Management Domain                   │
│                                                              │
│  ┌──────────┐                 ┌──────────┐                 │
│  │  Users   │──────────────────│  Roles   │                 │
│  └────┬─────┘  UsersRoles     └──────────┘                 │
│       │                                                      │
│       │ 1:N                                                  │
│       │                                                      │
│  ┌────▼──────┐                                              │
│  │  Sessions │                                              │
│  └───────────┘                                              │
└─────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────┐
│                     Order Management Domain                  │
│                                                              │
│  ┌──────────┐  1:N     ┌──────────────┐                    │
│  │  Orders  │──────────│  OrderItems  │                    │
│  └────┬─────┘          └──────┬───────┘                    │
│       │                       │                             │
│       │ N:1                   │ N:1                         │
│       │                       │                             │
│  ┌────▼─────┐            ┌────▼────┐                       │
│  │  Users   │            │ Products│                       │
│  └──────────┘            └─────────┘                       │
└─────────────────────────────────────────────────────────────┘
```

### Data Domains

**Domain 1: [Domain Name - e.g., "User Management"]**
- **Purpose**: [What this domain manages]
- **Core Entities**: [List of entities]
- **Key Relationships**: [Primary relationships]

**Domain 2: [Domain Name - e.g., "Order Management"]**
- **Purpose**: [What this domain manages]
- **Core Entities**: [List of entities]
- **Key Relationships**: [Primary relationships]

_[Continue for all domains]_

---

## Entity Definitions

### Entity Template

For each entity, provide:
- **Purpose**: What this entity represents
- **Attributes**: All columns/fields
- **Relationships**: Foreign keys and references
- **Constraints**: Business rules enforced at DB level
- **Indexes**: Performance optimization
- **Audit**: Tracking fields
- **Privacy**: PII classification

---

### Entity: Users

**Purpose**: Represents system users - people who can authenticate and use the system

**Category**: Master Data  
**Domain**: User Management  
**Estimated Rows**: 100,000 in Year 1, 500,000 in Year 3

---

#### Attributes

| Column Name | Data Type | Nullable | Default | Description |
|-------------|-----------|----------|---------|-------------|
| UserId | UNIQUEIDENTIFIER | No | NEWID() | Primary key, unique identifier |
| Email | NVARCHAR(255) | No | - | User's email address (also login) |
| PasswordHash | NVARCHAR(500) | No | - | Hashed password using bcrypt |
| FirstName | NVARCHAR(100) | No | - | User's first name |
| LastName | NVARCHAR(100) | No | - | User's last name |
| PhoneNumber | NVARCHAR(20) | Yes | NULL | Optional phone number |
| IsActive | BIT | No | 1 | Soft delete flag |
| IsEmailVerified | BIT | No | 0 | Email verification status |
| EmailVerifiedAt | DATETIME2 | Yes | NULL | Timestamp of email verification |
| LastLoginAt | DATETIME2 | Yes | NULL | Last successful login |
| FailedLoginAttempts | INT | No | 0 | Counter for failed login attempts |
| LockedUntil | DATETIME2 | Yes | NULL | Account lock expiration time |
| CreatedAt | DATETIME2 | No | GETUTCDATE() | Record creation timestamp |
| UpdatedAt | DATETIME2 | No | GETUTCDATE() | Last update timestamp |
| CreatedBy | UNIQUEIDENTIFIER | Yes | NULL | User who created this record |
| UpdatedBy | UNIQUEIDENTIFIER | Yes | NULL | User who last updated |

---

#### Relationships

**Outgoing** (This entity references):
- None (Users is typically a root entity)

**Incoming** (Other entities reference this):
- **Orders.UserId** → Users.UserId (One user can have many orders)
- **Sessions.UserId** → Users.UserId (One user can have many sessions)
- **UsersRoles.UserId** → Users.UserId (Many-to-many with Roles)

---

#### Constraints

**Primary Key**:
```sql
CONSTRAINT PK_Users PRIMARY KEY (UserId)
```

**Unique Constraints**:
```sql
CONSTRAINT UX_Users_Email UNIQUE (Email)
```

**Check Constraints**:
```sql
CONSTRAINT CK_Users_EmailFormat CHECK (Email LIKE '%@%.%')
CONSTRAINT CK_Users_FailedLoginAttempts CHECK (FailedLoginAttempts >= 0)
```

**Default Constraints**:
```sql
CONSTRAINT DF_Users_UserId DEFAULT NEWID() FOR UserId
CONSTRAINT DF_Users_IsActive DEFAULT 1 FOR IsActive
CONSTRAINT DF_Users_IsEmailVerified DEFAULT 0 FOR IsEmailVerified
CONSTRAINT DF_Users_FailedLoginAttempts DEFAULT 0 FOR FailedLoginAttempts
CONSTRAINT DF_Users_CreatedAt DEFAULT GETUTCDATE() FOR CreatedAt
CONSTRAINT DF_Users_UpdatedAt DEFAULT GETUTCDATE() FOR UpdatedAt
```

---

#### Indexes

**Primary Index**:
```sql
-- Clustered index on primary key (automatically created)
PK_Users ON Users (UserId)
```

**Secondary Indexes**:
```sql
-- For email lookup during login (most frequent query)
CREATE NONCLUSTERED INDEX IX_Users_Email 
ON Users (Email) 
INCLUDE (PasswordHash, IsActive, IsEmailVerified)
WHERE IsActive = 1;

-- For finding active users
CREATE NONCLUSTERED INDEX IX_Users_IsActive 
ON Users (IsActive)
INCLUDE (Email, FirstName, LastName);

-- For account security queries
CREATE NONCLUSTERED INDEX IX_Users_LockedUntil 
ON Users (LockedUntil)
WHERE LockedUntil IS NOT NULL AND LockedUntil > GETUTCDATE();
```

**Index Rationale**:
- `IX_Users_Email`: Login is most frequent operation, needs fast lookup
- `IX_Users_IsActive`: Admin queries frequently filter by active status
- `IX_Users_LockedUntil`: Security processes need to find locked accounts

---

#### Data Validation Rules

**Application-Level Validations** (enforced in code):
- Email format: RFC 5322 compliant
- Password: Min 12 chars, uppercase, lowercase, number, special char
- Phone: E.164 format if provided
- Name fields: No special characters except hyphens, apostrophes

**Database-Level Validations** (check constraints above):
- Email must contain @ and .
- FailedLoginAttempts cannot be negative

---

#### Audit & Tracking

**Audit Fields**:
- `CreatedAt`, `CreatedBy`: Who created and when
- `UpdatedAt`, `UpdatedBy`: Who last modified and when
- `LastLoginAt`: Last successful authentication

**Change Tracking**: 
- Consider implementing temporal tables (SQL Server) or audit log table
- Track changes to: Email, PasswordHash, IsActive, Roles

**Retention**: 
- Active users: Indefinite
- Inactive users: 7 years after account closure
- Audit logs: 7 years

---

#### Privacy & Compliance

**PII Classification**: **High**

**PII Fields**:
- Email (personal identifier)
- FirstName, LastName (personal information)
- PhoneNumber (personal contact)

**Encryption**:
- At Rest: Transparent Data Encryption (TDE) on entire database
- In Transit: TLS 1.3 for all database connections
- Column-Level: Consider encrypting Email and PhoneNumber with AES-256

**GDPR Compliance**:
- Right to Access: Export user data
- Right to Erasure: Anonymize or hard delete (see deletion strategy)
- Right to Portability: JSON export available

**Data Retention**:
- Active accounts: Retained while account is active
- Closed accounts: 2 years for business records
- After retention: Anonymize (replace with random data, keep UserId for referential integrity)

---

#### Deletion Strategy

**Soft Delete** (Default):
```sql
UPDATE Users 
SET IsActive = 0, 
    UpdatedAt = GETUTCDATE(),
    UpdatedBy = @CurrentUserId
WHERE UserId = @UserId;
```

**GDPR Right to Erasure** (Anonymization):
```sql
UPDATE Users
SET 
    Email = CONCAT('deleted_', UserId, '@anonymized.local'),
    PasswordHash = 'DELETED',
    FirstName = 'Deleted',
    LastName = 'User',
    PhoneNumber = NULL,
    IsActive = 0,
    IsEmailVerified = 0,
    UpdatedAt = GETUTCDATE()
WHERE UserId = @UserId;
```

**Hard Delete** (only after retention period):
```sql
-- Execute cascading deletes first
DELETE FROM Sessions WHERE UserId = @UserId;
DELETE FROM UsersRoles WHERE UserId = @UserId;
-- Then delete user
DELETE FROM Users WHERE UserId = @UserId;
```

---

#### Sample SQL

**Table Creation**:
```sql
CREATE TABLE Users (
    UserId UNIQUEIDENTIFIER NOT NULL DEFAULT NEWID(),
    Email NVARCHAR(255) NOT NULL,
    PasswordHash NVARCHAR(500) NOT NULL,
    FirstName NVARCHAR(100) NOT NULL,
    LastName NVARCHAR(100) NOT NULL,
    PhoneNumber NVARCHAR(20) NULL,
    IsActive BIT NOT NULL DEFAULT 1,
    IsEmailVerified BIT NOT NULL DEFAULT 0,
    EmailVerifiedAt DATETIME2 NULL,
    LastLoginAt DATETIME2 NULL,
    FailedLoginAttempts INT NOT NULL DEFAULT 0,
    LockedUntil DATETIME2 NULL,
    CreatedAt DATETIME2 NOT NULL DEFAULT GETUTCDATE(),
    UpdatedAt DATETIME2 NOT NULL DEFAULT GETUTCDATE(),
    CreatedBy UNIQUEIDENTIFIER NULL,
    UpdatedBy UNIQUEIDENTIFIER NULL,
    
    CONSTRAINT PK_Users PRIMARY KEY (UserId),
    CONSTRAINT UX_Users_Email UNIQUE (Email),
    CONSTRAINT CK_Users_EmailFormat CHECK (Email LIKE '%@%.%'),
    CONSTRAINT CK_Users_FailedLoginAttempts CHECK (FailedLoginAttempts >= 0)
);

CREATE NONCLUSTERED INDEX IX_Users_Email 
    ON Users (Email) 
    INCLUDE (PasswordHash, IsActive, IsEmailVerified)
    WHERE IsActive = 1;

CREATE NONCLUSTERED INDEX IX_Users_IsActive 
    ON Users (IsActive)
    INCLUDE (Email, FirstName, LastName);
```

**Sample C# Entity (Entity Framework)**:
```csharp
public class User
{
    public Guid UserId { get; set; }
    public string Email { get; set; } = string.Empty;
    public string PasswordHash { get; set; } = string.Empty;
    public string FirstName { get; set; } = string.Empty;
    public string LastName { get; set; } = string.Empty;
    public string? PhoneNumber { get; set; }
    public bool IsActive { get; set; } = true;
    public bool IsEmailVerified { get; set; } = false;
    public DateTime? EmailVerifiedAt { get; set; }
    public DateTime? LastLoginAt { get; set; }
    public int FailedLoginAttempts { get; set; } = 0;
    public DateTime? LockedUntil { get; set; }
    public DateTime CreatedAt { get; set; } = DateTime.UtcNow;
    public DateTime UpdatedAt { get; set; } = DateTime.UtcNow;
    public Guid? CreatedBy { get; set; }
    public Guid? UpdatedBy { get; set; }
    
    // Navigation properties
    public ICollection<Order> Orders { get; set; } = new List<Order>();
    public ICollection<Session> Sessions { get; set; } = new List<Session>();
    public ICollection<UserRole> UserRoles { get; set; } = new List<UserRole>();
}
```

---

### Entity: [Next Entity Name]

[Follow the same comprehensive format as above for each entity]

**Purpose**: [Description]

**Category**: [Master Data | Transaction Data | Reference Data | Configuration Data]  
**Domain**: [Domain name]  
**Estimated Rows**: [Volume projections]

#### Attributes
[Table of all columns]

#### Relationships
[Foreign keys and references]

#### Constraints
[All constraints with SQL]

#### Indexes
[All indexes with rationale]

#### Data Validation Rules
[Application and database level]

#### Audit & Tracking
[Audit fields and change tracking]

#### Privacy & Compliance
[PII classification, encryption, GDPR]

#### Deletion Strategy
[Soft delete, anonymization, hard delete SQL]

#### Sample SQL
[CREATE TABLE and sample C# entity]

---

_[Continue for ALL entities in the system]_

---

## Relationships Detail

### Relationship Types

**One-to-One (1:1)**:
- [Relationship description]
- Example: User ↔ UserProfile

**One-to-Many (1:N)**:
- [Relationship description]
- Example: User → Orders (one user has many orders)

**Many-to-Many (N:M)**:
- [Relationship description]
- Example: Users ↔ Roles (through UsersRoles junction table)

---

### Relationship: Users → Orders

**Type**: One-to-Many  
**Cardinality**: 1:N  
**Enforced At**: Database (Foreign Key)

**Parent Entity**: Users  
**Child Entity**: Orders  
**Foreign Key**: Orders.UserId → Users.UserId

**Business Rule**: Each order must belong to exactly one user. A user can have zero or many orders.

**Referential Integrity**:
```sql
ALTER TABLE Orders
ADD CONSTRAINT FK_Orders_Users_UserId
FOREIGN KEY (UserId) REFERENCES Users(UserId)
ON DELETE NO ACTION  -- Prevent deletion of users with orders
ON UPDATE CASCADE;   -- Update orders if UserId changes (rare)
```

**Rationale for ON DELETE NO ACTION**:
- Orders are business records and must be retained
- Deleting a user should not delete their order history
- Instead, implement soft delete on Users table

**Cascade Options Considered**:
- CASCADE: Not chosen - would delete business records
- SET NULL: Not chosen - orders must have a user
- SET DEFAULT: Not applicable - no default user
- NO ACTION: Chosen - maintain data integrity

---

### Relationship: [Next Relationship]

[Follow same format for all significant relationships]

---

## Data Integrity

### Primary Keys

**Strategy**: UNIQUEIDENTIFIER (GUID) for all primary keys

**Rationale**:
- Globally unique across systems (important for distributed systems)
- Non-sequential (security - can't guess IDs)
- Easier for merging data from multiple sources
- Works well with ORMs like Entity Framework

**Trade-offs**:
- Larger than INT (16 bytes vs 4 bytes)
- Non-sequential can fragment indexes
- Mitigation: Use NEWSEQUENTIALID() if needed

**Alternative Considered**: INT IDENTITY
- Pros: Smaller, faster joins, better for performance
- Cons: Not globally unique, sequential IDs are security risk
- Why not chosen: Distribution and security requirements outweigh size concerns

---

### Foreign Keys

**All foreign keys are enforced at database level** with constraints.

**Naming Convention**: FK_[ChildTable]_[ParentTable]_[Column]

**Cascade Behavior Strategy**:
- **ON DELETE**: Generally NO ACTION or RESTRICT
  - Prevents accidental data loss
  - Application handles logical deletion
- **ON UPDATE**: Generally CASCADE
  - Rare that primary keys change
  - If they do, update should cascade

**Exception Cases**:
- Audit/log tables: May use SET NULL on delete
- Cached data: May use CASCADE on delete

---

### Check Constraints

Use check constraints for:
- Range validation (e.g., Age between 0 and 150)
- Format validation (e.g., Email contains @)
- Business rule enforcement (e.g., EndDate > StartDate)
- Status validation (e.g., Status IN ('Active', 'Inactive', 'Pending'))

**Example**:
```sql
ALTER TABLE Orders
ADD CONSTRAINT CK_Orders_AmountPositive 
CHECK (TotalAmount > 0);

ALTER TABLE Orders
ADD CONSTRAINT CK_Orders_DateValid
CHECK (OrderDate <= DeliveryDate OR DeliveryDate IS NULL);
```

---

### Unique Constraints

**Strategy**: Use unique constraints for natural keys

**Examples**:
- Email addresses
- Username
- External IDs (from integrated systems)
- Business identifiers (order numbers, invoice numbers)

**Composite Unique Constraints**:
```sql
-- Ensure unique combination
ALTER TABLE OrderItems
ADD CONSTRAINT UX_OrderItems_OrderId_ProductId 
UNIQUE (OrderId, ProductId);
```

---

## Indexing Strategy

### Index Types Used

**Clustered Index**:
- One per table
- Determines physical order of data
- Generally on primary key
- Exception: If range queries on another column are more common

**Non-Clustered Index**:
- Multiple allowed per table
- Contains index key + pointer to data
- Used for frequent queries

**Filtered Index**:
- Index on subset of rows (WHERE clause)
- Used when queries frequently filter on same condition
- Example: Active users only

**Covering Index**:
- Includes additional columns (INCLUDE clause)
- Allows queries to be satisfied entirely from index
- Faster but takes more space

---

### Indexing Guidelines

**When to Add Index**:
- Foreign key columns (for join performance)
- Columns in WHERE clauses (frequently filtered)
- Columns in ORDER BY clauses (frequently sorted)
- Columns in GROUP BY clauses (frequently grouped)

**When NOT to Add Index**:
- Small tables (<1000 rows)
- Columns with low cardinality (few distinct values)
- Columns rarely queried
- Write-heavy tables (indexes slow down INSERT/UPDATE/DELETE)

**Index Maintenance**:
- Rebuild fragmented indexes monthly
- Update statistics weekly
- Monitor index usage (remove unused indexes)

---

### Index Documentation

For each index, document:
- Purpose: What query does this optimize?
- Rationale: Why these columns in this order?
- Trade-off: How does this impact writes?

**Example**:
```sql
CREATE NONCLUSTERED INDEX IX_Orders_UserId_OrderDate
ON Orders (UserId, OrderDate DESC)
INCLUDE (TotalAmount, Status);
```

**Purpose**: Optimize user order history queries (most recent first)  
**Query**: `SELECT * FROM Orders WHERE UserId = @UserId ORDER BY OrderDate DESC`  
**Rationale**: UserId filters to user's orders, OrderDate DESC allows sorted retrieval  
**Trade-off**: 20% write performance decrease acceptable for 10x read improvement

---

## Data Types & Standards

### Data Type Standards

**Text Data**:
- Use `NVARCHAR` for all text (Unicode support)
- Use `VARCHAR` only for ASCII-only data (rare)
- Specify length: NVARCHAR(100), not NVARCHAR(MAX)
- Use NVARCHAR(MAX) only for very large text (>8000 chars)

**Numeric Data**:
- **Integers**: INT for most cases (±2 billion range)
- **Large Integers**: BIGINT for IDs that might exceed 2 billion
- **Decimals**: DECIMAL(18,2) for money (18 digits, 2 decimal places)
- **Floats**: FLOAT only for scientific calculations (avoid for money!)

**Date/Time**:
- Use DATETIME2 (not DATETIME) for better precision and range
- Store in UTC always
- Convert to user timezone in application layer

**Boolean**:
- Use BIT (SQL Server) or BOOLEAN (PostgreSQL)
- Name as Is[Condition] or Has[Property]

**Binary Data**:
- VARBINARY for files, images (if storing in database)
- Consider external storage (blob storage) for large files

**Identifiers**:
- UNIQUEIDENTIFIER (GUID) for primary keys
- Alternative: BIGINT IDENTITY if performance is critical

---

### Format Standards

**Email**: RFC 5322 format, max 255 characters  
**Phone**: E.164 format (e.g., +1234567890), max 20 characters  
**URLs**: HTTP/HTTPS, max 2000 characters  
**Dates**: ISO 8601 format (YYYY-MM-DD or YYYY-MM-DDTHH:MM:SSZ)  
**Currency**: Store as DECIMAL(18,2), currency code in separate column  
**Percentages**: Store as DECIMAL (0.15 for 15%), not as INT (15)

---

## Data Migration Strategy

### Initial Migration

**From**: [Source system if migrating]  
**To**: [New system]  
**Volume**: [Data size]  
**Timeline**: [Migration window]

**Migration Steps**:
1. **Extract**: Export data from source
2. **Transform**: Clean, validate, map to new schema
3. **Validate**: Ensure data quality, run integrity checks
4. **Load**: Import into new database
5. **Verify**: Compare record counts, validate relationships
6. **Cutover**: Switch applications to new database

**Rollback Plan**:
[How to rollback if migration fails]

---

### Schema Evolution

**Versioning Strategy**: Database migrations tracked in version control

**Migration Tool**: [e.g., Entity Framework Migrations / Flyway / Liquibase]

**Process**:
1. Create migration script
2. Test in dev environment
3. Review and approve
4. Deploy to test/staging
5. Deploy to production (during maintenance window)

**Backward Compatibility**:
- Additive changes: Safe (add column, add table)
- Destructive changes: Require migration period
  - Add new column
  - Migrate data
  - Update application
  - Remove old column (later release)

---

### Data Transformation Rules

**Null Handling**:
- Source null → New null (if allowed)
- Source null → Default value (if required)
- Document all null handling rules

**Data Cleaning**:
- Trim whitespace
- Normalize case (email to lowercase)
- Format standardization (phone numbers)
- Remove invalid characters

**Data Enrichment**:
- Add audit fields (CreatedAt, CreatedBy)
- Generate GUIDs for primary keys
- Calculate derived fields

---

## Performance Optimization

### Query Optimization

**Common Query Patterns**:

**Pattern 1: User Login**
```sql
SELECT UserId, Email, PasswordHash, IsActive, IsEmailVerified
FROM Users
WHERE Email = @Email AND IsActive = 1;
```
**Optimization**: Covering index on Email includes PasswordHash, IsActive, IsEmailVerified

---

**Pattern 2: Order History**
```sql
SELECT OrderId, OrderDate, TotalAmount, Status
FROM Orders
WHERE UserId = @UserId
ORDER BY OrderDate DESC;
```
**Optimization**: Index on (UserId, OrderDate DESC) includes TotalAmount, Status

---

**Pattern 3: Search Products**
```sql
SELECT ProductId, Name, Price
FROM Products
WHERE Name LIKE '%' + @SearchTerm + '%'
  AND IsActive = 1;
```
**Optimization**: Full-text index on Name, or use external search (Elasticsearch)

---

### Partitioning Strategy

**Table Partitioning** (for very large tables):

**Partition By**: Date (monthly or yearly partitions)

**Example**: Orders table partitioned by OrderDate
```sql
CREATE PARTITION FUNCTION PF_Orders_OrderDate (DATETIME2)
AS RANGE RIGHT FOR VALUES 
('2024-01-01', '2024-02-01', '2024-03-01', ...);
```

**Benefits**:
- Faster queries (partition elimination)
- Easier archival (drop old partitions)
- Better maintenance (rebuild one partition at a time)

**Candidates for Partitioning**:
- Tables with time-series data
- Tables growing beyond 100GB
- Tables with clear range-based queries

---

### Archival Strategy

**Hot Data** (Active, frequently accessed):
- Current year orders
- Active users
- Recent transactions
- Keep in primary database

**Warm Data** (Less frequently accessed):
- Prior year orders
- Archived users
- Historical transactions
- Move to separate archive database or partitions

**Cold Data** (Rarely accessed):
- Orders older than 3 years
- Deleted user records (after retention period)
- Move to blob storage or data warehouse

**Archive Process**:
1. Identify data past hot threshold
2. Copy to archive storage
3. Validate data integrity
4. Delete from hot storage (or mark as archived)
5. Update queries to check archive if needed

---

## Compliance & Security

### Data Classification

| Classification | Definition | Examples | Controls |
|----------------|------------|----------|----------|
| Public | No confidentiality concern | Product catalog | None |
| Internal | Company internal only | Employee count | Access control |
| Confidential | Sensitive business data | Revenue data | Encryption + access control |
| Restricted | Highly sensitive | PII, passwords | Encryption + strict access + audit |

---

### PII Data Handling

**PII Fields Across All Entities**:
| Entity | Field | Classification | Encryption | Access Control |
|--------|-------|----------------|------------|----------------|
| Users | Email | PII | TDE | Authenticated users only |
| Users | FirstName, LastName | PII | TDE | Authenticated users only |
| Users | PhoneNumber | PII | TDE | Authenticated users only |
| Orders | ShippingAddress | PII | TDE | User + admin only |

**Data Minimization**:
- Collect only necessary PII
- Don't store credit card numbers (use tokens)
- Don't store SSN/national IDs unless legally required

---

### Encryption Strategy

**At Rest**:
- **Transparent Data Encryption (TDE)** on entire database
- **Column-Level Encryption** for highly sensitive fields (if needed)

**In Transit**:
- TLS 1.3 for all database connections
- Certificate pinning for production

**Key Management**:
- Keys stored in Azure Key Vault (or equivalent)
- Automated key rotation every 90 days
- Separate keys for dev/test/prod

---

### Audit Logging

**What to Audit**:
- All access to PII fields
- All modifications to sensitive entities
- All permission changes
- All authentication events

**Audit Log Table**:
```sql
CREATE TABLE AuditLog (
    AuditLogId BIGINT IDENTITY PRIMARY KEY,
    EntityName NVARCHAR(100) NOT NULL,
    EntityId NVARCHAR(50) NOT NULL,
    Action NVARCHAR(50) NOT NULL, -- INSERT, UPDATE, DELETE
    OldValues NVARCHAR(MAX), -- JSON
    NewValues NVARCHAR(MAX), -- JSON
    ChangedBy UNIQUEIDENTIFIER NOT NULL,
    ChangedAt DATETIME2 NOT NULL DEFAULT GETUTCDATE(),
    IpAddress NVARCHAR(50),
    UserAgent NVARCHAR(500)
);
```

**Retention**: 7 years for compliance

---

## Data Quality

### Data Validation

**Validation Layers**:
1. **Client-Side**: Immediate feedback (not security)
2. **API Layer**: Business rule validation
3. **Database Layer**: Data integrity (constraints)

**Validation Types**:
- **Type Validation**: Correct data type
- **Format Validation**: Correct format (email, phone)
- **Range Validation**: Within acceptable range
- **Referential Validation**: Foreign keys exist
- **Business Rule Validation**: Meets business logic

---

### Data Quality Metrics

**Metrics to Track**:
- **Completeness**: % of required fields filled
- **Accuracy**: % of data matching known valid values
- **Consistency**: % of data consistent across related entities
- **Timeliness**: % of data updated within SLA
- **Uniqueness**: % of records without duplicates

**Quality Monitoring**:
```sql
-- Example: Check for incomplete user records
SELECT 
    COUNT(*) AS TotalUsers,
    SUM(CASE WHEN PhoneNumber IS NULL THEN 1 ELSE 0 END) AS MissingPhone,
    SUM(CASE WHEN IsEmailVerified = 0 THEN 1 ELSE 0 END) AS UnverifiedEmail
FROM Users
WHERE IsActive = 1;
```

---

## Disaster Recovery

### Backup Strategy

**Backup Types**:
- **Full Backup**: Daily at 2 AM UTC
- **Differential Backup**: Every 6 hours
- **Transaction Log Backup**: Every 15 minutes

**Retention**:
- Daily backups: 30 days
- Weekly backups: 90 days
- Monthly backups: 1 year
- Yearly backups: 7 years

**Backup Testing**: Monthly restore test to verify backups are valid

---

### Recovery Procedures

**Recovery Time Objective (RTO)**: 1 hour  
**Recovery Point Objective (RPO)**: 15 minutes (transaction log backup frequency)

**Recovery Process**:
1. Assess failure scope
2. Determine recovery point
3. Restore full backup
4. Apply differential backups
5. Apply transaction log backups
6. Verify data integrity
7. Bring application online
8. Monitor for issues

---

## Entity Summary

### All Entities

| Entity | Domain | Type | Est. Rows Year 1 | PII | Notes |
|--------|--------|------|------------------|-----|-------|
| Users | User Mgmt | Master | 100,000 | Yes | Core entity |
| Roles | User Mgmt | Reference | 10 | No | RBAC roles |
| UsersRoles | User Mgmt | Junction | 120,000 | No | Many-to-many |
| Sessions | User Mgmt | Transaction | 500,000 | No | Auth sessions |
| Orders | Orders | Transaction | 1,000,000 | No | Customer orders |
| OrderItems | Orders | Transaction | 3,000,000 | No | Line items |
| Products | Catalog | Master | 10,000 | No | Product catalog |
| [Additional entities...] | [...] | [...] | [...] | [...] | [...] |

**Total Entities**: [X]  
**Total Est. Rows Year 1**: [Y]  
**Entities with PII**: [Z]

---

## Appendices

### Appendix A: Complete ERD
[Full entity-relationship diagram with all entities and relationships]

### Appendix B: SQL Creation Scripts
[Complete SQL scripts to create all tables, indexes, constraints]

### Appendix C: Sample Data
[Sample data for testing and development]

### Appendix D: Migration Scripts
[Data migration scripts if migrating from existing system]

### Appendix E: Performance Benchmarks
[Query performance benchmarks and optimization notes]

### Appendix F: Data Dictionary (Complete)
[Comprehensive data dictionary with all entities and attributes]

---

**Remember**: Good data modeling is about balance - normalize enough to maintain integrity, denormalize enough for performance, and always prioritize data quality and security. The database will outlive any application, so design for longevity.
