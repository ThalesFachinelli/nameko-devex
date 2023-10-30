### Question 1: Why is performance degrading as the test runs longer ?

The longer the tests run, more data is inserted in the database therefore more serialization/deserialization of data has to be performed and as the enviroment is set to use Marshmallow performance tends to degrade more and more as the tests run. This is due to the fact that Marshmallow is basically because when you serialize an object through Marshmallow it iterates through all the fields it knows about, then does a ton of reflection to extract the field from the input object. One way to mitigate this problem is to generate a serialization method at runtime that assumes the incoming object complies with the schema, falling back to the original Marshmallow code if it doesn’t as Toasted Marshmallow does.

### Question 2: How do you fix it ?

Use another serialization framework like Toasted Marshmallow.