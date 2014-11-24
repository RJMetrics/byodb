# byodb
*challenge for engineering candidates: build a simple database*

Using any language you want, construct your own simple database that exposes the following HTTP REST interface:
 - `GET    /tables` - List tables
 - `GET    /tables/:table` - Retrieve the entire contents of `:table`
 - `GET    /tables/:table/:key` - Retrieve the contents of `:key` in `:table`
 - `POST   /tables/:table` - Expects a JSON map in the request body. Merges the contents of that map into `:table`, overwriting any existing keys.
 - `PUT    /tables/:table/:key` - Expects a JSON document in the request body. Sets the value of `:key` in `:table` to that document, overwriting any existing value.
 - `DELETE /tables/:table/:key` - Disassociates any value with `:key` in `:table`
 - `DELETE /tables/:table` - Empties all keys and values from `:table`
 - `DELETE /tables` - Empties all tables
 - `GET    /search?q=:query` - Returns all keys that match the regular expression `:query`

Note:  Don't just wrap an interface around mysql. We want you to build your own data storage and retrieval system.

Some things to think about:
 - How are you going to store the data? Which use cases are you optimizing for?
 - What is going to happen to the data when the service is restarted?  What about a crash?
 - How efficient is each of these operations?  Can you make them more efficient?
 - What are the proper HTTP status codes to return in the header of your responses?
 - Are there any other useful methods you would add to this interface?  As extra credit, implement one or more of these.

You should use whatever languages and frameworks you're most comfortable with **as long as your solution can be easily run from a Linux environment**. You can also use any open source software libraries that you'd like. Please submit a git repository URL or tarball that includes source code and a README file with documentation and instructions for building and running an instance of your database locally.
