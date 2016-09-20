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
*

### Installing routes

### Learn more

  * Official website: http://www.phoenixframework.org/
  * Guides: http://phoenixframework.org/docs/overview
  * Docs: https://hexdocs.pm/phoenix
  * Mailing list: http://groups.google.com/group/phoenix-talk
  * Source: https://github.com/phoenixframework/phoenix
