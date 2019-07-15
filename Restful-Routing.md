## Question 3
What is REST-ful routing?
A RESTful route is a route that provides mapping between HTTP verbs (get, post, put, delete, patch) to controller CRUD actions (create, read, update, delete). Instead of relying solely on the URL to indicate what site to visit So, a RESTful route depends on the HTTP verb and the URL.

What this means is that when our application receives an HTTP request, it introspects on that request and identifies the HTTP method and URL, connects that with a corresponding controller action that has that method and URL, executes the code in that action, and determines which response gets sent back to the client.

RESTful routes
/**
 * Auto generate RESTful url routes.
 *
 * URL routes:
 *
 *  GET    /users[/]        => user.list()
 *  GET    /users/new       => user.new()
 *  GET    /users/:id       => user.show()
 *  GET    /users/:id/edit  => user.edit()
 *  POST   /users[/]        => user.create()
 *  PATCH  /users/:id       => user.update()
 *  DELETE /users/:id       => user.destroy()
 *
 * @param {Object} options
 *  - {Object} app, must impl `app.get(), app.post(), app.patch(), app.delete()`.
 *  - {String} name, resource's name. like `users, posts, tweets`.
 *  - {Object} controller, controller module contains `CRUD List` methods.
 *  - {String} [baseURL], default is '/'. e.g.: '/posts/:pid/'
 */
function restfulRouter(app, name, mod);
Usage
var restful = require('restful-router');
var connect = require('connect');
var urlrouter = require('urlrouter');
var user = require('./controllers/user');
var foo = require('./controllers/foo');

var server = connect(
  connect.query(),
  connect.bodyParser(),
  urlrouter(function (app) {
    app.get('/', function (req, res) {
      res.end('hello world');
    });

    /**
     * Users REST API
     *
     * GET    /users     => list()
     * GET    /users/:id => show(req.params.id)
     * POST   /users     => create()
     * PATCH  /users/:id => update(req.params.id)
     * DELETE /users/:id => delete(req.params.id)
     */
    restful({
      app: app,
      name: 'users',
      controller: user
    });

    /**
     * Foos REST API
     *
     * GET /users/:uid/foos/:date => show(req.params.uid, req.params.date)
     */
    restful({
      app: app,
      key: 'date',
      baseURL: '/users/:uid',
      name: 'foos',
      controller: foo,
    });

  })
).listen(3000);
