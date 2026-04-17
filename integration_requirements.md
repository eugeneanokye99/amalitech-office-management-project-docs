## 1. Authentication (SSO Integration)

We require the following:

- SSO **authentication endpoint URL**
- Integration flow details (redirect / API-based)
- Expected **response format (token structure)**
  - Confirm fields included in token (e.g., `userId`, `name`, etc.)
- Public key or method for **token verification**
- Any required credentials (e.g., client ID, client secret if applicable)

---

## 2. User Data Access

We need a reliable way to retrieve employee information using `userId`.

### Option A (Preferred for now)
- REST/GraphQL endpoint to fetch user details:
  - `employeeId`
  - `firstName`
  - `lastName`
  - `email`
  - `department`
  - `jobTitle`
  - `managerId`
  - `employeeType`

### Clarifications:
- Base endpoint URL
- Authentication method for accessing this endpoint
- Rate limits (if any)

---

## 3. Employee Project Data

- Endpoint to fetch **employee project assignments**

### Clarification:
- Is this managed by:
  - AMS  
  - Or Resource Management (separate service)?

---

## 4. Organization & Office Data

We require endpoints for:

- **Organizations (Countries)**
- **Offices (Locations/Cities)**

### Clarifications:
- Data structure
- Relationship between organization and offices

---

## 5. Holidays Data

Please confirm one of the following:

- Direct access to the **external holidays API** used by AMS  
  **OR**
- AMS-provided endpoint for:
  - Upcoming holidays
  - Company-specific holiday announcements

---

## 6. Data Synchronization (Event-Driven - Kafka)

To support eventual consistency and reduce dependency on live API calls, we need:

- Kafka **topic(s) for employee data updates**
- Event schema (payload structure)
- Access credentials / connection details

### Events of interest:
- Employee created
- Employee updated
- Employee status changes