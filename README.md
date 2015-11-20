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
  - Legalshield API Docs: https://github.com/LegalShield/docs

##General Coding Guidelines
- Do not code defensively: http://danielroop.com/blog/2009/10/15/why-defensive-programming-is-rubbish/

##General Testing Strategies:

If time is a constraint, make sure to at least write feature tests for what you're trying to accomplish. Feature tests are the sweeping checks that make sure client requests get the proper response codes and bodies. 
- Ex. If you're adding a new endpoint to the API, add a feature test that includes a successful call to that endpoint and any appropriate unsuccessful calls to that endpoint. With any successful/unsuccessful scenarios that are created, make sure they mimic what reality is/will be. For example, if you're building a brand-new endpoint to get a list of resources, don't test the endpoint with query params (unless you're building that as well, of course). 
- If unit tests are skipped, there should be a chore/task to return to write unit tests once time allows (most likely while QA is occurring).

Proper testing should include unit tests as well, which are smaller, isolated checks against specific functions, classes, methods, etc. 
- Ex. If you are adding the new endpoint described above, you would add unit tests for any new helper methods you've added to help you get the results you wanted (if you add a find method on the resources, you'd want to test that find in isolation by mocking out database calls and anything else that is outside of that specific method - you'd test it by literally calling it off the resource you're working on). 
- You'll also want to test any presenters/row mappers that might be involved. 
- Feature tests plus unit tests should amount to a very thorough run through of essentially every piece of code you've added - if you have code that hasn't been tested indirectly through the feature test or directly through a unit test, you should patch that hole or see if that code is even necessary (testing helps point out extraneous code/ways to make code more efficient).
