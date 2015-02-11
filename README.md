# grunt-githash

> Grunt plugin to get the current git hash, git branch and git tag

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

### Available values

#### githash.{target}.branch
Type: `String`
Value: branch name

#### githash.{target}.tag
Type: `String`
Value: tag name

#### githash.{target}.hash
Type: `String`
Value: the full hash value

#### githash.{target}.short
Type: `String`
Value: the short git hash value

### Usage Examples

#### Default Options

In this example, the default options are used to get the git status.

```js
grunt.initConfig({
  githash: {
    main: {
      options: {},
    }
  },

   anotherTask: {
     options: {
       exampleOptions1: '<%= githash.main.hash %>',
       exampleOptions2: '<%= githash.main.hash %> <%= githash.main.tag %> <%= githash.main.branch %>',
       exampleOptions3: '<%= githash.main.short %>'
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

## License
Copyright (c) 2015 Jan Nicklas. Licensed under the MIT license.
