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

_This file was generated by [verb-cli](https://github.com/assemble/verb-cli) on October 22, 2014._

[issues]: https://github.com/jonschlinkert/load-plugins/issues