#Readability

 - Code is well formed and indented
 - Tags and attributes use "lowerCamelCase" naming

#Maintainability

- No code duplication is found or introduced
- Visualforce components are used whenever necessary to avoid code repetition
- Field sets are used to dynamically bind fields
- `URLFOR` is used to generate all links to records

#Performances

- Expensive calculation and data loading are lazy-loaded using JavaScript remoting and the `reRender` attribute
- The `actionRegion` tag is used where applicable to limit the size of the view state
- Both CSS and JavaScript are imported as static resources
- CSS resources are referred at the top of the page
- JavaScript resources are referred at the bottom of the page

#Security

- Text and merge field values for use in JavaScript are escaped using `{!JSENCODE(text)}` to prevent XSS vulnerabilities
- Text and merge field values for use in HTML are escaped using `{!HTMLENCODE(text)}` to prevent XSS vulnerabilities
- Text and merge field values for use in URLs are escaped using `{!URLENCODE(text)}` to prevent XSS vulnerabilities
