# postman_api_testing

**API testing** demo using **Postman**, targeting the [Simple Book API](https://simple-books-api.glitch.me).

### Overview

This Postman collection covers:

- Status check
- Client registration
- Book listing and filtering
- Single book details
- Book ordering
- Order lookup, update, and deletion

Includes automated tests for HTTP response codes and response structure, with use of variables and chaining via `setNextRequest()`.

### Notes

- Base URL: `https://simple-books-api.click/`
- Token and IDs are managed via Postman environment/globals
- Collection was manually imported for versioning purposes

> All tests are written using JavaScript in Postman's built-in test editor and executed within the Postman application.

📄 **Full API documentation** available in [`simple_books_api_documentation.md`](simple_books_api_documentation.md).
