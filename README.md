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

## Learn more

  * Official website: http://www.phoenixframework.org/
  * Guides: http://phoenixframework.org/docs/overview
  * Docs: https://hexdocs.pm/phoenix
  * Mailing list: http://groups.google.com/group/phoenix-talk
  * Source: https://github.com/phoenixframework/phoenix

### Adding pages
* Most of the action for this demo is in the web directory.
* To create a page define a route for it.
* web/router.ex
* get "/hello", HelloController, :index
* Our route specifies that we need a HelloPhoenix.HelloController module with an index/2 action.
* create web/controllers/hello_controller.ex
* add new view
* Create web/views/hello_view.ex




### Installing routes
