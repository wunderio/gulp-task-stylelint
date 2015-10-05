Gulp task stylelint
=================

> A gulp task used for linting css files. It uses [stylelint](https://github.com/stylelint/stylelint) since it is based on postcss and is pluggable like ESLint.

## Installation
```sh
npm install --save-dev wunderkraut/gulp-task-stylelint
```

## Usage

### Basic usage

You can find a list of all supported rules here: <https://github.com/stylelint/stylelint/blob/master/docs/rules.md>

```js
// Require gulp.
var gulp = require('gulp')

// Require task module and pass gulp to provide the gulp tasks.
require('gulp-task-stylelint')(gulp)
```

### Advanced usage
You can also pass a configuration to the task. This allows you to overwrite the default configuration and provide other configuration like a base path for your files.

#### gulpfile.js
```js
var gulp = require('gulp')
var gulpConfig = require('./gulpconfig')

// Just pass the configuration object as second parameter.
require('gulp-task-stylelint')(gulp, gulpConfig)
```

#### gulpconfig.js
```js
var path = require('path');

module.exports = {
  // Basic configuration.
  basePath: '.',

  // Overwrite default configurations.
  stylelint: {
      src: path.join('some', 'source', 'folder', '**', '*.css'),
      rules: {
        // Basics
        'indentation': [2, 2],
        'value-no-vendor-prefix': [2],
        'rule-trailing-semicolon': [2, 'always'],

        // Avoid accidental overrides
        'rule-no-shorthand-property-overrides': 2

        // Full rule documentation can be found here:
        // https://github.com/stylelint/stylelint/blob/master/docs/rules.md
      }
    }
}
```

## Contributing

Pull requests and stars are always welcome. For bugs and feature requests, [please create an issue](https://github.com/wunderkraut/gulp-task-boilerplate/issues/new).
