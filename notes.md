# Design notes

- user visits react app
- asks express API for some data
- express pulls info out of mongoDB database
- sends info back to react app

## Instructor notes on tech

- Node: javascript runtime used to execute code outside of browser
- Express: library that runs node runtime. Helpers make HTTP/writing servers traffic easier

node listens to port, when HTTP request comes in it
node takes information from HTTP request, hand off to express
express looks at request, decides which bit of logic will handle/respond to incoming request
express has route handlers, asks for specific service (authenticating, logging out a user, create a new survey)
express processes incoming request, generates outgoing response
response sent back to node process, node responds with response we author

`app.get('/', (req, res) => {
  res.send({ hi: 'there' });
});

app.listen(5000);`

- app object represents underlying express server
- app.get function creates a new route handler
  - app.get => get info
  - app.post => send info
  - app.put => update all properties of something
  - app.delete => delete info
  - app.patch => update some properties of something
- forward slash is for route portion of handler, if anyone visits that route do this
- 'req' shorthand for incoming request
- 'res' shorthand for response, data sent back to request
- body of arrow function, sends back json in this case
- .listen(5000) tells node to allow traffic to flow in on this port