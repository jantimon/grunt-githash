# grunt-githash

> Grunt plugin to get the current githash

## Getting Started
This plugin requires Grunt.

If you haven't used [Grunt](http://gruntjs.com/) before, be sure to check out the [Getting Started](http://gruntjs.com/getting-started) guide, as it explains how to create a [Gruntfile](http://gruntjs.com/sample-gruntfile) as well as install and use Grunt plugins. Once you're familiar with that process, you may install this plugin with this command:

```shell
npm install grunt-githash --save-dev
```

Once the plugin has been installed, it may be enabled inside your Gruntfile with this line of JavaScript:

```js
grunt.loadNpmTasks('grunt-githash');
```

## The "githash" task

### Overview
In your project's Gruntfile, add a section named `githash` to the data object passed into `grunt.initConfig()`.

```js
grunt.initConfig({
  githash: {
    options: {
      // Task-specific options go here.
    },
    your_target: {
      // Target-specific file lists and/or options go here.
    },
  },
})
```

### Options

#### options.dir
Type: `String`
Default value: `'.'`

The root of the git repository

### Usage Examples

#### Default Options

In this example, the default options are used to get the git values.

```js
grunt.initConfig({
  githash: {
    main: {
      options: {},
    }
  },

  anotherTask: {
    options: {
      someProp: '<%= githash.main.hash %>'
    }
  }
})
```

#### Custom Options

In this example, we define the git repository location

```js
grunt.initConfig({
  githash: {
    main: {
      options: {
        // Git repository path:
        dir: 'builds'
      }
    }
  },

  anotherTask: {
    options: {
      someProp: '<%= githash.main.hash %>'
    }
  }
})
```

## Contributing
In lieu of a formal styleguide, take care to maintain the existing coding style. Add unit tests for any new or changed functionality. Lint and test your code using [Grunt](http://gruntjs.com/).

## Release History
_(Nothing yet)_

## License
Copyright (c) 2015 Jan Nicklas. Licensed under the MIT license.
