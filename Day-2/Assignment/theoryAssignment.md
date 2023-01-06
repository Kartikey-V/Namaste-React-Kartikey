# What is 'NPM'
- It is a library used to manage Node Packages/Dependencies for us.
- Online Repo for open source node projects, people publish their libraries on npm and others can use it
- package installation, version management and dependency management.

# What is `Parcel/Webpack`? Why do we need it?
- Parcel is a beast,module bundler which bundles the code, it performs a lot of functions
- combine multiple js files into one js file, piece together different dependencies 
- Loader-> pre process files other than js, add Module/rules/test Regex then module/rules/test/use to process scss to regular css to js then inject in browser.
# what is `.parcel-cache`?
- it is the storage used by parcel to keep track of changes when the project is build so that whenever rebuilding it, it doesnt to re parse and re analyze from scratch. 
# What is `npx`?
- npx is the command to execute node packages
- npm doesnt run packages
- runs a command of a package without installing it explicitly.
- What is difference between `dependencies` vs `devDependencies`
- dependencies are packages which the project requires in order to run it, meaning the project is dependent on the libraries.
- devDependencies are deps which are required only during development
- devDependencies are isntalled by providing 
```npm i -D package-name``` or 
```npm i --save-dev```
# What is `Tree Shaking` ?
- Removal of dead code
- it uses the import and export statements to identify which code is to be removed or not. 
- Module bundler like webpack automatically remove daead code when bundling multiple js files into a single file
# What is Hot Module Replacement?
- it allows modules to be updated at runtime without needing a full refresh.
- it helps retain application state which is lost during full reload
- The following steps allow modules to be swapped in and out of an application:
    - The application asks the HMR runtime to check for updates.
    - The runtime asynchronously downloads the updates and notifies the application.
    - The application then asks the runtime to apply the updates.
    - The runtime synchronously applies the updates.
# List down your favourite 5 superpowers of Parcel and describe any 3 of them in your own words.
- Hot Reloading: 
- superfast
- lazy dev build
- multi core
- caching
- production optimization: tree shaking, minification, image optimizatioin, compression, code splititng, content hashing
# What is `.gitignore`? What should we add and not add into it?
- .gitignore file tells git which files need not be tracked for uploading on github or online repo. 
- We should add all files which can be again generated in gitignore like nodemodules, cache etc.
# What is the difference between `package.json` and `package-lock.json`
- package-lock is a mechanism to capture the exact dependency tree installed at any point in time. This helps with collaboration across different environments in which you want everyone fetching dependencies for a specific version of your project to fetch the same tree.
- Do you need both package-lock.json and package.json? No.
- Do you need the package.json? Yes.
- Can you have a project with only the package-lock.json? No.
- The package.json is used for more than dependencies - like defining project properties, description, author & license information, scripts, etc. The package-lock.json is solely used to lock dependencies to a specific version number.
- when each is invoked: package.json is generated when "npm init" is run, package-lock.json is created when a package is installed in the project.

# Why should I not modify `package-lock.json`?
- don’t change package-lock.json directly. That’s being handled automatically by NPM. It reflects changes made to package.json to package-lock.json and keeps it up to date.
- npm update will read package.json to find any dependencies that can be updated. Subsequently, it will construct a new dependency tree and update the package-lock.json as well.
# What is `node_modules` ? Is it a good idea to push that on git?
- node_modules folder contains the code for all the dependencies which npm installed.
- it should not be pushed on git as it can easily be rebuild by using npm install

# What is the `dist` folder?
- dist or distributable folder contains the final static files ready for deployment. it contains the minimized files

- public means the web accessible root of the site. Basically whatever is in that folder can be opened from browser address bar. Server won't provide user access to files outside public

- build is where compiled version of assets are placed when you run npm build. This is what will get delivered to user

- src (short for "source") contains your working files that will be used later to create the build

# What is `browserlists`
- Browserslist is a tool that allows specifying which browsers should be supported in your frontend app by specifying "queries" in a config file
- transpilers/bundlers know what browsers you want to support, so they can "group" browsers in different categories and generate separate bundles