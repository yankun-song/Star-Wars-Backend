# Star-Wars-Backend
## Server
For the _server_ directory, we have the following directories/ files.

- **server.js**

    In this file, we may do the following things:
    1. Require/ import routers from other files
    2. Parsing request body
    3. Handle requests for static files
    4. Define route handlers
    5. Define route handler to respond with main app
    6. Catch-all route handler for any requests to an unknown route
    7. Configure global error handler
    8. Start server


- **routes**

    In this folder, we have some routers defined. In each router file, we will import controllers, use them as middlewares, and return a response.
    Take character.js as an example. We declare the actions to take once receiving a DELETE request from the endpoint "/id", like "/21". This is an example of route parameter.
```js
router.delete(
  "/:id",
  characterController.deleteCharacter,
  fileController.deleteCharacter,
  (req, res) => {
    return res.status(200).json(res.locals.deletedCharacter);
  }
);
```

- **controllers**

    In this folder, we have some controllers defined. In each controller file, we declare an empty object, then assign new methods to it. For the _characterController_, we can create/ update/ delete. In each method of controller(aka _middleware_), we may extract information from the _request_, and process the data. We either return _next()_, which means we will execute the next middleware, or return _next(error)_, which means we return an error messgae and will not execute the following middlewares.
    
- **data**

    When doing this project, we didn't have a database. All the character data are store here.
    
- **utils**
--------
[Codesmith Tutorial](https://github.com/yankun-song/unit-9-express)
