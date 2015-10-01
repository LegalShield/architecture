# styleguide

## REST
Here is our [RESTful Guide](/restful-guide.md).

###Design Restful Routes First
The routes, request, and response for each endpoint should be thought out and designed first, then tested and coded. To help in this effort so that everyone can pair with each other and learn how to design great looking RESTful resource definitions, we will be using the following system:
- Each new change to this styleguide should be on it's own branch prefixed with your initials (ex: `dr-engage-flux-capacitor`)
- Make sure to merge master into your branch so you have the latest changes.
- Then, make a pull request for the branch. (Do not merge directly into master without a pull request!)
- Post the pull request on the engineering slack channel so someone can review it.
- Once it gets reviewed and approved (LGTM), if it's a single commit, merge it directly into master. If it's
 multiple commits, make sure to do a `git merge --squash`
- After you have successfully merged your branch into master, make sure to close your pull request and delete your branch from github if you no longer need it
- Try not to merge multiple changes into the same branch. Each should have it's own branch.

+ Javascript
  - [ES5](https://github.com/airbnb/javascript/tree/master/es5)
  - [Angular](https://github.com/johnpapa/angular-styleguide)
  - [Node.js](https://github.com/RisingStack/node-style-guide)
+ [Ruby](https://github.com/bbatsov/ruby-style-guide)
+ Objective-C
+ JAVA
  - [Code Architecture](/java/code-architecture.md)
  - [V2 API Endpoints](/java/v2-api-endpoints.md)
