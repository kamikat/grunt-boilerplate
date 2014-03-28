Grunt Frontend Boilerplate
==========================

Boilerplate project for fast creating a grunt based frontend workflow.

Setup
-----

Install grunt and grunt plugins with

    $ npm install

Install [SCUT](http://davidtheclark.github.io/scut/) with `bower`

    $ bower install

A **ruby** installation is required and install `sass` with gem (required by `grunt-contrib-sass`)

    $ gem install sass

Assets
------

Put assets in `asset` directory under the project root.

`asset` directory will be **merged** into build directory by grunt in build process.
(compiled unit have same name with asset shall overwrite that asset,
it's not recommended to have any asset that may has conflict with compiled unit)

**Known Issue**

- When using `grunt watch`, the compiled unit will not be guaranteed to overwrite the asset file

Options
-------

Options can be passed through environment variables

    $ SERVER_PORT=8020 grunt devserver # Run devserver at port 8020
    $ RELOAD_PORT=1337 grunt watch     # Run livereload server at port 1337 (default 35729)
    $ BUILD_ROOT="dist/" grunt         # Set build root to "dist/" (default "build/")

Tasks
-----

Boilerplate contains following grunt tasks

- gruntfile (jshint)

  Lint Gruntfile.js

- asset (copy)

  Copy assets to build directory.

- style (sass, autoprefixer)

  Build stylesheets with `node-contrib-sass` (ruby implementation).
  Native `node-sass` implementation is replaced becaused because it
  cannot met spec of SASS completely.

  Vendor prefixes are injected with `autoprefixer` task automatically,
  so please don't waste time writing vendor specific SASS/SCSS rules.

- script (jshint, copy)

  Copy javascript file to build directory after lint scripts.

- document (jade)

  Build all jade files from `src/` to html.

- clean

  Remove all contents in build directory.

- watch

  Daemon to automatically run tasks when source file changed.
  LiveReload server is enabled by default.
  See [documentation](https://github.com/gruntjs/grunt-contrib-watch#optionslivereload) for detail.

- devserver

  Run a server hosting static file service for development.

License
-------

(The MIT License)

