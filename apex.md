
# Readability

* No dead code is found or introduced
* Style conventions apply (indentation, use of spaces and brackets)
* Comments are in simple, meaningful English
* Comments are used to clarify the “why” (not the “what”) the most complex code sections


# Maintainability

- Code is simple and not unnecessarily complicated
- Naming conventions apply (variables, methods, classes, pages, components)
- No code duplication is found or introduced
- Code doesn't contain any hardcoded IDs
- Core parameters are easy to maintain by using constants, custom settings or custom metadata types
- Code make the use of the appropriate design pattern, when applicable
- No multiple triggers on the same object
- No both workflows and triggers on the same objects at the same time
- Tests use object factories to create object instances and to setup their own data

# Performances

- Code invoked by triggers is bulkified to process multiple records at once
- Loops don’t contain SOQL, SOSL, `sendMails`, HTTP callouts or calls to `@future` methods
- The `transient` keyword is used for variables that are not strictly required to maintain page state
- All SOQL queries include a `LIMIT` to prevent exceeding the allowed resultset size

# Security

- Dynamic SOQL/SOSL are not used if a solution exists using standard bracket notation
- All input variables in dynamic SOQL/SOSL statements are escaped using `String.escapeSingleQuotes()`
- FLS is enforced using `isUpdateable()`, `isAccessible()` on fields read or written in controllers, controller extensions and Web Services
- CRUD is enforced using  `isCreateable()`, `isDeletable()` on SObject updates, creates, or deletes done within controllers, controller extensions and Web Services

# Robustness

- If methods use multiple DMLs, transaction control/savepoints are used to preserve data integrity on errors
- Positive scenarios are tested
- Negative scenarios are tested
- Boundary conditions are tested
- Error conditions are tested
- Behaviour with data bulks is tested
- User authorisastion is tested
- Tests are data-isolated by using `@SeeAllData=false`
- Tests are network-isolated by using the `HttpCalloutMock` or `WebServiceMock` interfaces

