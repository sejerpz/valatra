Valatra is a web framework with a terrible name based on Ruby's Sinatra
framework.

```vala
var app = new Valatra.App();
app.port = 3333;

app.get('/', (req, res) => {
  /* 200 by default */
  res.status = 200;

  /* sets content-type, 'text/html' by default */
  res.type("text/plain");

  /* set whatever HTTP header */
  res.headers["MY_HEADER"] = "Hello!";

  res.setBody("Hello World!");

});

// this would be called for a request to '/user/john', or '/user/123', etc
app.get("/user/:id", (req, res) => {
  var id = req.params["id"];
  // do something with id...
});

app.post("/submit", (req, res) => {
  // if a POST was made to "/submit with a body of
  //"title=My+Awesome+Title", req.params["title"]
  // would return that
  req.params["title"];
});

app.start();
```


## dependencies
Valatra depends on gio-2.0 and gee-1.0. Compiling on valac 0.12.0

## building
As long as you have the dependencies fullfilled, building valatra is as easy as
running `make`. If you want to create a build with debugging symbols, run
`make debug`. To view the C code generated by Vala, run `make genc`.


## license
(MIT License)
Copyright (c) 2011 Erik Price

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

