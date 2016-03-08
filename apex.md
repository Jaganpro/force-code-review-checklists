
#Readability

- No dead code is found or introduced
- Style conventions are consistently applied (indentation, use of spaces and brackets)
- Comments are used to clarify the “why” (not the “what”) of all the most complex parts of the code
- Comments are simple, meaningful and written in English

#Maintainability

- Naming conventions are consistently applied (variables, methods, classes)
- No code duplication is found or introduced
- Code does not contain any hardcoded IDs
- Code is kept simple and not unnecessarily complicated
- Core parameters are easy to maintain by using constants, custom settings or custom metadata types
- Code make the use of the appropriate design pattern, when applicable
- No logic split between workflows/triggers on the same object

#Performances

- No multiple triggers on the same object
- Code invoked by triggers is bulkified to process multiple records at once
- Loops don’t contain SOQL, SOSL, Describe, `sendMails` or HTTP callouts
- The transient keyword is used for variables that are not required to maintain page state

#Security

- Dynamic SOQL/SOSL are not used if a solution exists using standard bracket notation
- All input variables in dynamic SOQL/SOSL statements are escaped using `String.escapeSingleQuotes()`
- CRUD/FLS are enforced using `isUpdateable()`, `isCreateable()`, `isAccessible()`, `isDeletable()` on field and SObject updates, creates, or deletes done within controllers, controller extensions and Web Services

#Testing Standards

- Positive scenarios are tested
- Negative scenarios are tested
- Boundary conditions are tested
- Error conditions are tested
- Behaviour with data bulks is tested
- Tests are data isolated (`@SeeAllData=false`)
- Tests are network isolated by leveraging the `HttpCalloutMock` or `WebServiceMock` interfaces
- Errors are transactionally rolled back
- Tests use object factories to create instances of standard or custom objects and setup their own data
