API Test Automation — Urban Grocers

Automated API testing project for the Urban Grocers application using Python, Pytest, and Requests.

The project focuses on testing the kit creation endpoint and validating different scenarios for the name field, including valid values, boundary values, missing parameters, and invalid data types.

Project Objective

The objective of this project is to automate functional API tests and verify that the Urban Grocers API returns the expected HTTP status codes for different input conditions.

The test suite covers both positive and negative scenarios for the name parameter when creating a kit.

The project was developed as part of QA Engineer training and demonstrates the process of converting API test scenarios into automated tests.

Technologies
Python 3.13.3 — Programming language
Pytest — Testing framework
Requests — HTTP requests and API interaction
Postman — Manual API testing and validation
apiDoc — API documentation and endpoint reference
Git / GitHub — Version control and project repository
API Testing Scope

The automated tests focus on the kit creation endpoint of the Urban Grocers API.

The name parameter is tested using different input conditions to verify the API's validation behavior.

Test Scenarios
Positive Test Cases

Expected HTTP response: 201 Created

Case	Scenario	Input
1	name with 1 character	"a"
2	name with 511 characters	511-character string
5	name with special characters	"№%@,"
6	name with spaces	" A Aaa "
7	name containing numbers	"123"
Negative Test Cases

Expected HTTP response: 400 Bad Request

Case	Scenario	Input
3	Empty name	""
4	name with 512 characters	512-character string
8	name parameter missing	{}
9	Invalid data type	{"name": 123}

Project Structure
qa-project-Urban-Grocers-app-es/
│
├── configuration.py
│   └── API URL and endpoint configuration
│
├── create_kit_name_kit_test.py
│   └── Automated test cases for the kit name validation
│
├── data.py
│   └── Test data
│
├── sender_stand_request.py
│   └── Functions used to send HTTP requests to the API
│
├── .gitignore
│
└── README.md

Testing Approach

The test scenarios were first validated manually using Postman and the API documentation provided through apiDoc.

The manual test scenarios were then automated using Python, Pytest, and Requests.

The automated tests verify the HTTP status code returned by the API for each input condition.

This approach helps make the API validation process repeatable and reduces the need to execute the same test scenarios manually.

How to Run the Tests
Prerequisites

Before running the tests, make sure you have:

Python installed.
Git installed.
Access to the Urban Grocers test environment.
The API server URL configured in configuration.py.
Pytest installed.
Requests installed.
1. Clone the repository
git clone https://github.com/jose-luis-serrano/qa-project-Urban-Grocers-app-es.git

Navigate to the project directory:

cd qa-project-Urban-Grocers-app-es
2. Create a virtual environment
python -m venv .venv

Activate it in Git Bash:

source .venv/Scripts/activate
3. Install dependencies
pip install pytest requests
4. Configure the API URL

Configure the Urban Grocers server URL in:

configuration.py

Make sure the test environment is available before running the tests.

5. Run the automated tests
pytest create_kit_name_kit_test.py

Test Results

The positive test cases were executed successfully and returned the expected:

201 Created

The negative test cases did not produce the expected result.

The expected response for these scenarios was:

400 Bad Request

However, the API returned:

201 Created
Result Summary
Test Type	Expected	Actual	Result
Positive scenarios	201	201	Passed
Negative scenarios	400	201	Failed

The failed negative scenarios indicate a discrepancy between the expected API validation behavior and the actual response returned by the test environment.

From a QA perspective, this result is relevant because the automated tests successfully detected that invalid input was being accepted with a 201 Created response instead of the expected 400 Bad Request.

Skills Demonstrated

This project demonstrates practical experience with:

API testing
REST API testing
Functional testing
Positive and negative test scenarios
Boundary value testing
HTTP status code validation
Python
Pytest
Requests
Postman
API documentation analysis
Test data management
Automated test execution
Git and GitHub

Key QA Concepts Applied
Positive Testing

Valid input data is used to verify that the API accepts supported values and creates the requested resource successfully.

Negative Testing

Invalid or unsupported input is used to verify that the API rejects incorrect requests with the expected error response.

Boundary Value Testing

The tests include boundary conditions such as:

Minimum valid length: 1 character
Maximum valid length: 511 characters
Invalid value above the maximum: 512 characters
Data Type Validation

The test suite also verifies the API behavior when the name parameter receives an invalid data type, such as a number instead of a string.

Author

José Luis Serrano

QA Automation / Functional Test Engineer

GitHub: https://github.com/jose-luis-serrano
