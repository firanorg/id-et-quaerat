# **@firanorg/id-et-quaerat.js** for Node.js

[![Subscribe](https://img.shields.io/badge/%20subscribe%20-%20mailchimp%20-blue.svg )](http://eepurl.com/cGRggH)
[![Downloads](https://img.shields.io/npm/dm/@firanorg/id-et-quaerat.svg)](https://npm-stat.com/charts.html?package=@firanorg/id-et-quaerat)
[![Status](https://github.com/firanorg/id-et-quaerat/workflows/tests/badge.svg)](https://github.com/firanorg/id-et-quaerat/actions) [![Dependencies status](https://david-dm.org/franciscop/@firanorg/id-et-quaerat/status.svg)](https://david-dm.org/franciscop/@firanorg/id-et-quaerat)

Powerful @firanorg/id-et-quaerat for Node.js that just works so **you can focus on your awesome project**:

```js
// Include it and extract some methods for convenience
const @firanorg/id-et-quaerat = require('@firanorg/id-et-quaerat');
const { get, post } = @firanorg/id-et-quaerat.router;

// Launch @firanorg/id-et-quaerat with options and a couple of routes
@firanorg/id-et-quaerat({ port: 8080 }, [
  get('/', ctx => 'Hello world'),
  post('/', ctx => {
    console.log(ctx.data);
    return 'ok';
  })
]);
```

<blockquote class="external">
  <p>Simplicity is a great virtue but it requires hard work to achieve it and education to appreciate it. And to make matters worse: complexity sells better.</p>
  <cite>― Edsger W. Dijkstra</cite>
</blockquote>


## Getting started

There's a [whole tutorial on getting started for beginners](https://@firanorg/id-et-quaeratjs.io/tutorials/getting-started/) but the quick version is to first install `@firanorg/id-et-quaerat` as a dependency:

```bash
npm install @firanorg/id-et-quaerat
```

> Server requires **Node.js 7.6.0** or newer. **Node.js 8.x.y** LTS is recommended.

Then you can create a file called `index.js` with this code:

```js
// Include the @firanorg/id-et-quaerat in your file
const @firanorg/id-et-quaerat = require('@firanorg/id-et-quaerat');
const { get, post } = @firanorg/id-et-quaerat.router;

// Handle requests to the url "/" ( http://localhost:3000/ )
@firanorg/id-et-quaerat([
  get('/', ctx => 'Hello world!')
]);
```

Execute this in the terminal to get the @firanorg/id-et-quaerat started:

```bash
node .
```

And finally, open your browser on [localhost:3000](http://localhost:3000/) and you should see 'Hello world!' on your browser.



## Documentation

The library is documented here:

<strong><a class="button" href="https://@firanorg/id-et-quaeratjs.io/documentation/">Full Documentation</a></strong>

> [**Subscribe here**](http://eepurl.com/cGRggH) to receive tutorials when released. Tutorials are *good for learning* while the documentation is good for reference/quick use *once you know the basics*.

You can also download the repository and try the examples by browsing to them and `node .` inside each of them in `/examples`.



## Use cases

The package `@firanorg/id-et-quaerat` is great for many situations. Let's see some of them:


### Small to medium projects

Everything works out of the box, you get great support for most features and you can easily tap into Express' middleware ecosystem. What's not to love?

Some of the included features: body and file parsers, cookies, sessions, websockets, Redis, gzip, favicon, csrf, SSL, etc. They just work so you will save a headache or two and can focus on your actual project. Get a simple form going:

```js
const @firanorg/id-et-quaerat = require('@firanorg/id-et-quaerat');
const { get, post } = @firanorg/id-et-quaerat.router;
const { render, redirect } = @firanorg/id-et-quaerat.reply;

@firanorg/id-et-quaerat(
  get('/', () => render('index.pug')),
  post('/', ctx => {
    console.log(ctx.data);
    return redirect('/');
  })
);
```



### API design

From the flexibility and expressivity of the bundle, designing APIs is a breeze:

```js
// books/router.js
const { get, post, put, del } = require('@firanorg/id-et-quaerat/router');
const ctrl = require('./controller');

module.exports = [
  get('/book', ctrl.list),
  get('/book/:id', ctrl.item),
  post('/book', ctrl.create),
  put('/book/:id', ctrl.update),
  del('/book/:id', ctrl.delete)
];
```



### Real time

Websockets were never this easy to use! With socket.io on the front-end, you can simply do this in the back-end to handle those events:

```js
// chat/router.js
const { socket } = require('@firanorg/id-et-quaerat/router');
const ctrl = require('./controller');

module.exports = [
  socket('connect', ctrl.join),
  socket('message', ctrl.message),
  socket('disconnect', ctrl.leave)
];
```



## Author & support

This package was created by [Francisco Presencia](http://francisco.io/) but hopefully developed and maintained by many others. See the [the list of contributors here](https://github.com/firanorg/id-et-quaerat/graphs/contributors).

You can also [sponsor the project](https://@firanorg/id-et-quaeratjs.io/sponsor), get your logo in here and some other perks with tons of ♥
