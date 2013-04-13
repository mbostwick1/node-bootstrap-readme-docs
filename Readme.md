
# Node Bootstrap Readme Docs <sup>[![Version Badge](http://vb.teelaun.ch/getprove/node-bootstrap-readme-docs.svg)](https://npmjs.org/package/readme-docs)</sup>

Generate a sexy docs page with Node, Connect or Express, Twitter Bootstrap, and your Github repo's Readme.md file.

Check out an example generated page at <https://getprove.com/docs> and its respective [Readme.md](https://github.com/getprove/prove-api/blob/master/Readme.md).


## Index

* [How it Works](#how-it-works)
* [Format](#format)
* [Examples](#examples)
* [Contributors](#contributors)
* [License](#license)


## How it Works

Express and Connect expose `app.settings` as `settings` in your views.

This module populates `app.settings.readmeDocs` with an object of readme's.

Simply require this module, then implement it with route middleware:

```js
var express = require('express')
  , express = express()
  , readmeDocs = require('readme-docs')(app)
app.set('view engine', 'jade')
app.get('/docs', readmeDocs('user', 'repo'), function(req, res, next) {
  res.render('docs')
})
app.listen(3000)
```

You can use any templating language, here are a few example implementations:

**Jade**:

```jade
ul
  != settings.readmeDocs.user.repo.nav
```

**EJS**:

```ejs
<ul>
  <%= settings.readmeDocs.user.repo.body %>
</ul>
```

These examples both output the following HTML when rendered:

```html
<ul>
  <li><a href="#how-it-works">How it Works</a></li>
  <li><a href="#format">Format</a></li>
  <li><a href="#examples">Examples</a></li>
  <li><a href="#contributors">Contributors</a></li>
  <li><a href="#license">License</a></li>
</ul>
```


## Format

Your `Readme.md` file should contain the following format:

```md

# Docs

Some description of your awesome API.

## Index

* [First Link](#first-link)
* [Second Link](#second-link)
* [Third Link](#third-link)

## First Link

Some stuff goes here for the first link.

## Second Link

Some stuff goes here for the second link.

## Third Link

Some stuff goes here for the third link.

```

## Examples

See the [examples](https://github.com/getprove/node-bootstrap-readme-docs/tree/master/server) folder for an Express &amp; Jade example.


## Contributors

* Nick Baugh <niftylettuce@gmail.com>


## License

The MIT License

Copyright (c) 2013- Prove <support@getprove.com> (https://getprove.com)

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.


