# grunt

A task-based command line build tool for JavaScript projects

# install

    $ npm install -g grunt

# init (built-in task)

Generate project scaffolding from a predefined template.

Unlike other tasks, init should only ever be run once for a project. Typically,
it is run at the very beginning before work has begun, but it can be run later

# overriding prompt defaults

`~/.grunt/tasks/init/defaults.json`

    {
      "author_name": "Pau Fracés"
    , "author_email": "pfraces@gmail.com"
    , "licenses": "GPL"
    }

# overriding template directory

You can override things for a given init template with these paths

* `~/.grunt/tasks/init/TEMPLATE.js`
* `~/.grunt/tasks/init/TEMPLATE/rename.json`
* `~/.grunt/tasks/init/TEMPLATE/root/`

## Renaming or excluding template files

If, for some reason, you want to rename or exclude files, you can edit 
rename.json which describes a map of sourcepath to destpath values. The 
sourcepath must be the path of the file-to-be-copied relative to the `root/` 
folder, but the destpath value can contain `{% %}` init templates, as in any 
init file, and describes what the destination path will be

* If `false` is specified for the destpath the file will not be copied.
* The `rename.json` file is merged using `grunt.task.readDefaults` so it 
  overrides built-in values.

# The grunt.js file, aka "gruntfile"

Each time grunt is run, it looks in the current directory for a file named 
grunt.js. If this file is not found, grunt continues looking in parent 
directories until that file is found. This file is typically placed in the root
of your project repository, and is a valid JavaScript file comprised of these 
parts:

* Project configuration
* Loading grunt plugins or tasks folders
* Tasks and helpers

This is an example of a very basic sample grunt.js gruntfile that does all 
three of these things.

    module.exports = function(grunt) {

      /**
      * # Project configuration.
      *
      * Each grunt task relies on configuration information defined in an
      * object passed to the `grunt.initConfig` method. 
      */
      grunt.initConfig({

        **
        * For example, this basic config defines a list of files to be linted 
        * when the lint task is run on the command line via `grunt lint`.
        */
        lint: {
          all: ['grunt.js', 'lib/**/*.js', 'test/**/*.js']
        },
        jshint: {
          options: {
            browser: true
          }
        }
      });

      /**
      * # Loading grunt plugins or tasks folders
      *
      * While you can define tasks and helpers in your gruntfile, you can also 
      * load tasks from external sources.
      *
      * Load tasks and helpers from the "tasks" directory, relative to
      * grunt.js.
      */
      grunt.loadTasks('tasks');

      /**
      * Load tasks and helpers from the "grunt-sample" Npm-installed grunt
      * plugin.
      */
      grunt.loadNpmTasks('grunt-sample');

      /**
      * # Tasks and helpers
      *
      * The easiest way to define the default task is to create an alias task.
      *
      * In the following example, a default task is defined that, when invoked
      * by specifying `grunt` or `grunt default` on the command line, will
      * execute the `lint`, `qunit`, `concat` and `min` tasks in-order. It
      * behaves exactly as if `grunt lint qunit concat min` was run on the
      * command line.
      */
      grunt.registerTask('default', 'lint qunit concat min');
    };

## Project configuration.

    grunt.initConfig({
      // Project metadata, used by some directives, helpers and tasks.
      meta: {},
      // Lists of files to be concatenated, used by the "concat" task.
      concat: {},
      // Lists of files to be linted with JSHint, used by the "lint" task.
      lint: {},
      // Lists of files to be minified with UglifyJS, used by the "min" task.
      min: {},
      // Lists of files or URLs to be unit tested with QUnit, used by the
      // "qunit" task.
      qunit: {},
      // Configuration options for the "server" task.
      server: {},
      // Lists of files to be unit tested with Nodeunit, used by the "test"
      // task.
      test: {},
      // Configuration options for the "watch" task.
      watch: {},
      // Global configuration options for JSHint.
      jshint: {},
      // Global configuration options for UglifyJS.
      uglify: {}
    });

## Loading grunt plugins or tasks folders

Loading externally defined tasks and helpers in this way is preferred to
loading them via the analogous --tasks and --npm command-line options. This is
because when tasks are created or loaded in the grunt.js gruntfile, the tasks
effectively become part of the project and will always be used (provided they
are available) whenever grunt is run.

## Tasks and helpers

You are not required to define tasks in your project gruntfile, because grunt
provides a number of built-in tasks. That being said, until you define a
`default` task, grunt will not know what to do when you run it just as grunt
without specifying any tasks, because grunt does not provide a default 
`default` task.

Choose the default tasks that make the most sense for your project. If you find
yourself commonly executing other groups of tasks, create as many named aliases
as you need!

# references

* https://github.com/gruntjs/grunt/blob/master/docs/toc.md
* https://github.com/gruntjs/grunt/blob/master/docs/getting_started.md
* https://github.com/gruntjs/grunt/blob/master/docs/task_init.md
* https://github.com/gruntjs/grunt/blob/master/docs/api.md
