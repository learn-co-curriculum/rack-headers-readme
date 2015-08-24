# Headers

Headers are specifications passed along in the response that are essential for setting up the Rack environment.

### HTTP and headers

In order to understand the structure, we'll use HTTP protocols for simplicity. Everything you see in your browser, for example, is transferred via HTTP. Navigating the web is essentially a large series of HTTP requests and responses, and these are transported by HTTP headers in your metadata.

### Live HTTP Headers
If you're using Firefox or Chrome, you can use the [Live HTTP Headers](https://chrome.google.com/webstore/detail/live-http-headers/iaiioopjkcekapmldfgbebdclcnpgnlo?hl=en) extension to see what these HTTP Headers look like. Once you enable it to capture your requests and responses, you can click on a logged request/response and see the corresponding HTTP Headers.

### Rack Header
Rack uses these headers to set up the environment in accordance with the HTTP standard. The header is simply a hash that contains these header elements. For example, the following is a Rack response for a `ResponseTimer` Rack app:

```ruby
class ResponseTimer
  def intialize(app)
    @app = app
  end

  def call(env)
    [200, {"Content-Type" => "text/html"}, "Hello World!"]
  end
end
```

The header in this response is `{"Content-Type" => "text/html"}`. This is simply saying that the content type of this response is `text/html`, and this will render the body `Hello World!` in the HTML text formatting language.

### Resources
- [Rack Middleware](http://asciicasts.com/episodes/151-rack-middleware)
- [Rack from the Beginning](http://hawkins.io/2012/07/rack_from_the_beginning/)
