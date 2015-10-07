# RESTful Patterns

If you need more information, please feel free to read the references listed below.


## Design First
The routes, request, and response for each endpoint should be designed, then tested and coded.

## Designing For REST Resources
+ Collection ( Ex: `/v2/plans` )
	- GET - **List** or **Index** an array of elements that belong to this collection. (Ex: `[ {id:"1", ...}, {id:"2", ...}]`)
	- POST - **Create** a new entry in the collection. 
	- PUT - **Not Used** 
	- PATCH - **tbd**
	- DELETE - **Delete the entire collection**
+ Element (Ex: `/v2/plans/12345`)
	- GET - **Retrieve** a representation of this element from the collection
	- PUT - **Replace** or **Create** (**Upsert**) the element into the collection
	- PATCH - **Partially Modify** the fields in this element
	- POST - **Not Used**
	- DELETE - **Delete** this element

# References

1) [Best Practices for Designing a Pragmatic RESTful API](http://www.vinaysahni.com/best-practices-for-a-pragmatic-restful-api)

2) [REST on Wiki](https://en.wikipedia.org/wiki/Representational_state_transfer)

