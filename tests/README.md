# Tests Directory

This directory contains pytest-based tests for the Mergington High School Activities API.

## Test Structure

- `test_app.py`: Comprehensive tests for all API endpoints

## Test Coverage

The test suite includes:

### 1. Root Endpoint Tests (`TestRootEndpoint`)
- Tests that the root endpoint redirects to the static HTML page

### 2. Get Activities Tests (`TestGetActivities`)
- Tests fetching all activities
- Validates the structure of activity data
- Verifies initial participants are loaded correctly

### 3. Signup Tests (`TestSignupForActivity`)
- Tests successful student signup
- Tests signup for non-existent activities (404 error)
- Tests duplicate signup prevention (400 error)
- Tests handling of special characters in activity names

### 4. Unregister Tests (`TestUnregisterFromActivity`)
- Tests successful unregistration
- Tests unregistration from non-existent activities (404 error)
- Tests unregistration of non-registered students (400 error)
- Tests re-signup after unregistration

### 5. Integration Tests (`TestIntegrationScenarios`)
- Tests complete signup and unregister workflows
- Tests multiple students interacting with the system

## Running Tests

### Run all tests:
```bash
pytest tests/
```

### Run with verbose output:
```bash
pytest tests/ -v
```

### Run with coverage report:
```bash
pytest tests/ --cov=src --cov-report=term-missing
```

### Run a specific test class:
```bash
pytest tests/test_app.py::TestSignupForActivity -v
```

### Run a specific test:
```bash
pytest tests/test_app.py::TestSignupForActivity::test_signup_for_activity_success -v
```

## Test Results

All 14 tests are passing with **100% code coverage** of the `src/app.py` file.

## Dependencies

The following packages are required for testing (included in `requirements.txt`):
- `pytest`: Testing framework
- `httpx`: HTTP client for TestClient
- `pytest-cov`: Coverage plugin for pytest
