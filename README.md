# load-plugins [![NPM version](https://badge.fury.io/js/load-plugins.png)](http://badge.fury.io/js/load-plugins)

> Load plugins for gulp, grunt, assemble, verb any node.js app that needs to load plugins from node_modules or local folders.

## Install
#### Install with [npm](npmjs.org)

```bash
npm i load-plugins --save
```

## Run tests

```bash
npm test
```

## Usage

### with gulp

```js
var plugin = plugins('gulp-*');

gulp.task('default', function () {
  gulp.src('test/*.js')
    .pipe(plugin.jshint());
    .pipe(plugin.mocha());
});
```

### with assemble

```js
var plugin = plugins('assemble-*');

assemble.task('default', function () {
  assemble.src('test/*.js')
    .pipe(plugin.jshint());
    .pipe(plugin.mocha());
});
```

## Options

See [resolve-dep](https://github.com/jonschlinkert/resolve-dep) for additional options.

### options.require

Pass a custom function for `require`ing files.

```js
plugins('gulp-*', {
  require: function(filepath) {
    // do stuff to filepath
  }
});
```

### options.camelize

Make plugin names camelcased. By default this is `false`.

### options.rename

Pass a rename function to change how plugins are named.

```js
plugins('my-plugins-*', {
  rename: function (filepath) {
    return path.basename(filepath);
  }
});
```

### options.omit

Omit strings from plugin names. This is a complement to the `.rename()` option, it's easiest to understand by way of example:

```js
plugins('gulp-*', {omit: 'gulp'});
```

Returns `{mocha: [Function]}` instead of `{'gulp-mocha': [Function]}`, and so on.

You may also pass an array of strings to omit, or use **braces**, e.g.:

```js
// note that the `omit` option doesn't work with full glob patterns, just braces
plugins('{foo,bar}-*', {omit: '{foo,bar}'});
```

## API


## Contributing
Pull requests and stars are always welcome. For bugs and feature requests, [please create an issue][issues].

## Author

**Jon Schlinkert**
 
+ [github/jonschlinkert](https://github.com/jonschlinkert)
+ [twitter/jonschlinkert](http://twitter.com/jonschlinkert) 

## License
Copyright (c) 2014 Jon Schlinkert, contributors.  
Released under the MIT license

***

_This file was generated by [verb-cli](https://github.com/assemble/verb-cli) on October 27, 2014._

[issues]: https://github.com/jonschlinkert/load-plugins/issues