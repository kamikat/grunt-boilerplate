Grunt Frontend Boilerplate
==========================

Boilerplate project for fast creating a grunt based frontend workflow.

Setup
-----

Install grunt and grunt plugins with

    $ npm install

Install [SCUT](http://davidtheclark.github.io/scut/) with `bower`

    $ bower install

Asset
-----

Put asset in `asset` directory under the project root.

`asset` directory will be **merged** into build directory by grunt in build process.
(compiled unit have same name with asset shall overwrite that asset,
it's not recommended to have any asset that may has conflict with compiled unit)

**Known Issue**

- When using `grunt watch`, the compiled unit will not be guaranteed to overwrite the asset file

Option
------

Options can be passed through environment variables

    $ SERVER_PORT=8020 grunt devserver # Run devserver at port 8020
    $ RELOAD_PORT=1337 grunt watch     # Run livereload server at port 1337 (default 35729)
    $ BUILD_ROOT="dist/" grunt         # Set build root to "dist/" (default "build/")

