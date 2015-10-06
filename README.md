# Styleguide

##Contributing
- Each new change to this styleguide should be on it's own branch prefixed with your initials (ex: `dr-new-user-endpoint`)
- Then, make a pull request for the branch. (Do not merge directly into master without a pull request!)
- Post the pull request on slack so someone can review it.
- Once approved (LGTM), merge it directly into master. If it's multiple commits, make sure to do a `git merge --squash`
- After merging your branch into master, close your pull request and delete your branch from github if you no longer need it

##[REST Guide](/restful-guide.md)

##Language Specific Guides
+ Javascript
  - [ES5](https://github.com/airbnb/javascript/tree/master/es5)
  - [Angular](https://github.com/johnpapa/angular-styleguide)
  - [Node.js](https://github.com/RisingStack/node-style-guide)
+ [Ruby](https://github.com/bbatsov/ruby-style-guide)
+ Objective-C
+ JAVA
  - The old AO Web Services endpoints are called V1
  - The new Restful Api is called V2, below are how to write for this new api.
  - [Code Architecture](/java/code-architecture.md) - Best practices for writing code in Java 
  - [V2 API Endpoints](/java/v2-api-endpoints.md) - The RESTful routes, request, and response for each endpoint should be thought out and designed first here.
