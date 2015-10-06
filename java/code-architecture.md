#JAVA Code Architecture


##Models
+ Maps data and methods for a single business unit
+ **(Java POJO objects + DAO)** - Get rid of [Anemic Model Anti-Pattern](http://www.martinfowler.com/bliki/AnemicDomainModel.html) (Read more in this article by Martin Fowler)
+ Does not directly correlate to REST endpoints (Keep implementation separate from endpoints)


##Controllers
+ Get request parameters and pass to Business Logic (In Services or Models)
+ Pass output to Presenter to return a response (Views that turn Java objects into JSON) -> Output JSON

##Views/Presenter
+ This takes the Java representation and converts it to a JSON representation
+ This step is pretty much what Jackson does in the response