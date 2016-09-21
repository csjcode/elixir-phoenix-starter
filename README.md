# HelloPhoenix

Basic app starts with following instructions:
http://www.phoenixframework.org/docs/up-and-running

To start your Phoenix app:

  * Install dependencies with `mix deps.get`
  * Create and migrate your database with `mix ecto.create && mix ecto.migrate`
  * Install Node.js dependencies with `npm install`
  * Start Phoenix endpoint with `mix phoenix.server`

Now you can visit [`localhost:4000`](http://localhost:4000) from your browser.

Ready to run in production? Please [check our deployment guides](http://www.phoenixframework.org/docs/deployment).

### Adding pages - http://www.phoenixframework.org/docs/adding-pages
* Most of the action for this demo is in the web directory.
* To create a page define a route for it.
* web/router.ex
* get "/hello", HelloController, :index
* Our route specifies that we need a HelloPhoenix.HelloController module with an index/2 action.
* create web/controllers/hello_controller.ex
* Add new view
* Create web/views/hello_view.ex
* Next we have to add a template, Phoenix uses is EEx, which stands for Embedded Elixir. Template files have the .eex file extension
* web/templates/hello/index.html.eex
* this is rendered automatically into the application layout - web/templates/layout/app.html.eex
* Add another router
* get "/hello/:messenger", HelloController, :show
* The atom :messenger is in the path. Phoenix will takes taht param and passes a Map with the key messenger pointing to that value to the controller.
* http://localhost:4000/hello/Ferrari, the value of ":messenger" will be "Ferrari".
* At web/controllers/hello_controller.ex, edit that file and add a show action
* def show(conn, %{"messenger" => messenger}) do  render conn, "show.html", messenger: messenger end
* the keys to the params map will always be strings
* create Template web\templates\hello\show.html.eex
* Add this into the template <%= @messenger %>

### Router summary (basic principles, no code in this section)

* Routes which begin with an HTTP verb name expand to a single clause of the match function.
* Routes which begin with 'resources' expand to 8 clauses of the match function.
* Resources may restrict the number of match function clauses by using the only: or except: options.
* Any of these routes may be nested.
* Any of these routes may be scoped to a given path.
* Using the as: option in a scope can reduce duplication.
* Using the helper option for scoped routes eliminates unreachable paths.

### Installing routes

* The name you gave your application will appear instead of HelloPhoenix for both the router module and controller name.
* Phoenix provides a great tool for investigating routes in an application, the mix task phoenix.routes. $ mix phoenix.routes
* in web/router.ex  - resources "/users", UserController
* mix phoenix.routes
* Let's say we have a read-only posts resource. We could define it like this: resources "/posts", PostController, only: [:index, :show]
* Running $ mix phoenix.routes shows that we now only have the routes to the index and show actions defined.
* if we have a comments resource, and we don't want to provide a route to delete one: resources "/comments", CommentController, except: [:delete]
* 


### Learn more

  * Official website: http://www.phoenixframework.org/
  * Guides: http://phoenixframework.org/docs/overview
  * Docs: https://hexdocs.pm/phoenix
  * Mailing list: http://groups.google.com/group/phoenix-talk
  * Source: https://github.com/phoenixframework/phoenix
