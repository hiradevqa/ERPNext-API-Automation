# ERPNext API Automation Testing

An API automation testing project built using **Postman and JavaScript** to test the backend functionality of ERPNext v16.

The project covers authentication, customer management, item management, and supplier management through positive and negative test scenarios.

## Tech Stack

- **Postman** — API testing and collection execution
- **JavaScript** — Test scripts and assertions
- **ERPNext v16** — Application under test
- **Git & GitHub** — Version control and project documentation

**Test Environment:** ERPNext v16 running locally through Docker.

## Test Coverage

| Module | Test Cases | Scenarios |
|---|---|---|
| Authentication | 5 | Valid/invalid login, unauthenticated access, role-based authorization, logout |
| Customer | 8 | Create, mandatory validation, retrieve, update, search, pagination, delete, not found |
| Item | 8 | Create, mandatory validation, duplicate detection, retrieve, update, schema validation, filtering, delete |
| Supplier | 5 | Create, mandatory validation, retrieve, update, delete |
| **Total** | **26** | |

## Framework Features

- Positive and negative API testing
- HTTP status code and response validation
- Automated assertions using JavaScript
- Reusable Before request scripts for test data setup
- Dynamic test data generation
- Environment-based API authentication
- Independent test scenarios
- Test data tracking using environment variables
- Centralized cleanup for Customers, Items, and Suppliers
- Collection Runner for executing API test scenarios

## Project Structure

```text
ERPNext Backend API Automation/
├── 01 - Authentication
├── 02 - Customer
├── 03 - Item
├── 04 - Supplier
└── 99 - Cleanup
    ├── Cleanup - Test Customers
    ├── Cleanup - Test Items
    └── Cleanup - Test Suppliers
```

## API Endpoints

| Module | Endpoint |
|---|---|
| Login | `POST /api/method/login` |
| Logout | `/api/method/logout` |
| Customer | `/api/resource/Customer` |
| Item | `/api/resource/Item` |
| Supplier | `/api/resource/Supplier` |

## Test Automation Approach

The framework uses Postman collections and JavaScript scripts to automate API testing.

**1. Test Setup**

Reusable Before request scripts create test records when required. Unique names are generated dynamically to prevent duplicate-record conflicts.

**2. Test Execution**

API requests are executed using Postman. JavaScript assertions validate status codes, response data, error handling, and expected application behavior.

**3. Test Data Management**

Created test records are tracked through environment variables so they can be identified during cleanup.

**4. Cleanup**

Dedicated cleanup requests remove tracked test Customers, Items, and Suppliers to reduce unnecessary test data in ERPNext.

## How to Run

1. Set up a local ERPNext v16 instance.
2. Import the Postman collection.
3. Create a Postman environment named `ERPNext Local`.
4. Configure the required environment variables.
5. Select the environment in Postman.
6. Execute individual requests or folders using the Collection Runner.
7. Review the test results.
8. Run the cleanup requests after test execution.

## Environment Variables

| Variable | Description |
|---|---|
| `base_url` | ERPNext API base URL |
| `api_key` | API authentication key |
| `api_secret` | API authentication secret |
| `supplierGroup` | Existing Supplier Group |
| `testCustomerIds` | Created test Customer IDs |
| `testItemIds` | Created test Item IDs |
| `testSupplierIds` | Created test Supplier IDs |

**Security:** API credentials and populated environment files should never be committed to GitHub.

## Future Improvements

- Newman command-line test execution
- GitHub Actions CI/CD integration
- Automated test reporting

## Project Objective

The objective of this project is to build practical experience in API automation testing, test case design, JavaScript assertions, authentication, response validation, and reusable test automation.

The project is designed around realistic ERP workflows rather than isolated API requests.
