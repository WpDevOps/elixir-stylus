## Usage

This WpDevOps Elixir extension allows you to compile Stylus.

## Installation

First, pull in the extension through NPM.

```
npm install --save-dev @wpdevops/elixir-stylus
```

That's it! You're all set to go!

## Usage

Assuming you write...

```js
elixir(function(mix) {
   mix.stylus('app.styl');
});
```

...this will compile your `assets/stylus/app.styl` file to `./dist/css/app.css`.

If you'd like to set a different output directory, you may pass a second argument to the `stylus()` method, like so:

```js
mix.stylus('app.styl', './dist/scripts/styles.css')
```

Finally, if you want to override the Stylus plugin options, you may pass an object as the third argument.

```js
mix.stylus('app.styl', null, {});

// See options at: https://www.npmjs.com/package/gulp-stylus#options
```

## PostCSS

This extension includes a PostCSS adapter out of the box, as well as support for the incredibly impressive [Lost](https://github.com/peterramsing/lost) grid system. Check out the documentation in that link, and immediately start using it in your projects with this extension. Zero setup. :)

If there are other PostCSS plugins you want to pull in, you may use the third argument to `mix.stylus()` - 

```js
var postStylus = require('poststylus'); // npm install --save-dev poststylus

mix.stylus('app.styl', null, {
   use: [postStylus(['lost', 'postcss-position'])] // npm install --save-dev postcss-position
});
```

---

This package was originally ([laravel-elixir-stylus](https://github.com/JeffreyWay/laravel-elixir-stylus)) 
written by [Jeffrey Way](https://github.com/JeffreyWay)