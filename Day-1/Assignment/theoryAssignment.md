### What is Emmet?
Editor Plugin used for text editors that provides abbreviations which convert to code blocks
---
### What is CDN? Why do we use it?
Content Delivery Network is used to provide content to users. It is designed to reduce network latency by placing servers close to the actual users, All servers are inter-connected and disterbuted geographically to provide high performance.
---
### Why is React known as React?
rendering "reactive" to changing inputs
---
### What is crossorigin in script tag?
- Integrity - defines the hash value of a resource (like a checksum) that has to be matched to make the browser execute it. The hash ensures that the file was unmodified and contains expected data. This way browser will not load different (e.g. malicious) resources. Imagine a situation in which your JavaScript files were hacked on the CDN, and there was no way of knowing it. The integrity attribute prevents loading content that does not match.

- Cross-Origin Resource Sharing (CORS) is an HTTP-header based mechanism that allows a server to indicate any origins (domain, scheme, or port) other than its own from which a browser should permit loading resources.
- For security reasons, browsers restrict cross-origin HTTP requests initiated from scripts. For example, XMLHttpRequest and the Fetch API follow the same-origin policy. This means that a web application using those APIs can only request resources from the same origin the application was loaded from unless the response from other origins includes the right CORS headers.
- crossorigin - defines options used when the resource is loaded from a server on a different origin
- crossorigin can be set to either “anonymous” or “use-credentials”. Both will result in adding origin: into the request. The latter however will ensure that credentials are checked. No crossorigin attribute in the tag will result in sending a request without origin: key-value pair.
---
### What is diference between React and ReactDOM

- React library is responsible for creating views 
- React has the core tools intended to be shared by React on different platforms (e.g. React Native).
- ReactDOM library is responsible to actually render UI in the browser.
- React-DOM is a library which glues React to the browser DOM
---
### What is difference between react.development.js and react.production.js files via CDN?

The development build is used - as the name suggests - for development reasons. You have Source Maps, debugging and often times hot reloading ability in those builds. The production build, on the other hand, runs in production mode which means this is the code running on your client's machine.


###  What is async and defer?
both are boolean attributes that are used along with script tag used to load external scripts efficiently

- HTML Parsing (<script src="" />)
    While Parsing HTML, if the Parser encounters script tag, it pauses the parsing, fetches the script, executes it, then resumes the parsing, meaning JS is blocking the parsing of HTML.

- HTML with async (<script async src="" />)
    While Parsing HTML, if the Parser encounters script tag, it fetches the script asynchronously and the parsing continues, when the fetching is complete, the parsing stops, script execution is done then parsing continues. 

- HTML Parsing with Defer (<script defer src="" />)
    While Parsing HTML, if the Parser encounters script tag, it fetches the script asynchronously, and parsing continues. Scripts are only executed when the HTML parsing is completed. 
    
- async does not gurantee order of execution of scripts, if there is a dependency on scripts it may cause braking of code.
- defer maintains the order of execution and only executes them when html parsing is completed.