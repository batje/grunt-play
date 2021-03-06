# grunt-play

## Getting Started

This plugin requires Grunt `~0.4.0`

```shell
npm install grunt-play --save-dev
```

One the plugin has been installed, it may be enabled inside your Gruntfile with this line of JavaScript:

```js
grunt.loadNpmTasks("grunt-play");
```

## The "play" task

### Overview

In your project's Gruntfile, add a section named `play` to the data object passed into `grunt.initConfig()`.

```js
grunt.initConfig({
  play: {
    fanfare: {
      sound: "fanfare", // There are 2 default sounds included: fanfare or beep. overrides "file"
      file: "./sounds/fanfare.mp3", // Path is relative to your project
      player: "afplay" // Overrides the automatic player detection
    }
  }
});
```

### Usage Examples

#### Example Gruntfile

```js
module.exports = function(grunt) {
  "use strict";

  grunt.initConfig({
    jshint: {
      all: ["tasks/**/*.js"],
      options: {
        jshintrc: ".jshintrc"
      }
    },
    watch: {
      scripts: {
        files: ["tasks/**/*.js"],
        tasks: ["jshint", "play:fanfare"]
      }
    },
    play: {
      fanfare: {
        file: "./sounds/fanfare.mp3"
      }
    }
  });

  // Actually load this plugin's task(s).
  grunt.loadTasks("tasks");

  // These plugins provide necessary tasks.
  grunt.loadNpmTasks("grunt-contrib-jshint");
  grunt.loadNpmTasks("grunt-contrib-watch");

  // By default, lint and run all tests.
  grunt.registerTask("default", ["jshint", "play"]);
};
```

## thanks

i love DQ :)

## Release History

2013-03-27   v0.0.1   initial release
