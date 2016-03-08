#Readability

 - Code is XML valid and consistently indented

#Maintainability

- No code duplication is found or introduced
- Visualforce components are used whenever necessary to avoid code repetition
- Field sets are used to dynamically bind fields
- `URLFOR` is used to generate all links to records

#Performances

- Expensive calculation and data loading are lazy-loaded using JavaScript remoting and the `rerender` attribute
- The `actionRegion` tag is used to limit the view state size
- Both CSS and JavaScript are imported as static resources
- CSS resources are referred at the top of the page
- JavaScript resources are referred at the bottom of the page

#Security

- All JavaScript quoted variables loaded from server use `JSENCODE` to prevent XSS vulnerabilities
- All HTML directly generated with data coming from server uses `HTMLENCODE` to prevent XSS vulnerabilities
- All URLs composed with data coming from server use `URLENCODE` to prevent XSS vulnerabilities
