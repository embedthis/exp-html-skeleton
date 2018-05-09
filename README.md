exp-html-skeleton
===

Expansive HTML skeleton plugin.

This provides:

 * Configuration for Expansive plugins: 
    * [exp-css](https://github.com/embedthis/exp-css) for CSS files
    * [exp-less](https://github.com/embedthis/exp-less) for Less files
    * [exp-j](https://github.com/embedthis/exp-js) for script files
 * Default layout 
 * Default partials for header, navigation and footer
 * Starter home page

### To install:

    pak install exp-html-skeleton

### Description

The HTML skeleton is a basic starter skeleton for Expansive. It provides a default layout, partial pages and is configured to use Less stylesheets. Extensions are installed to process less stylesheets and minify scripts.

The skeleton is configured for a "debug" and "release" mode of operation via the "mode" property in package.json. By default, debug mode will disable minification and mangling of scripts.

### Configure

#### expansive.json

* less.dependencies &mdash; Explicit map of dependencies if not using "stylesheet". 
* less.enable &mdash; Enable the less service to process less files.
* less.files &mdash; Array of less files to compile.
* less.stylesheet &mdash; Primary stylesheet to update if any less file changes.
    If specified, the "dependencies" map will be automatically created. 
* css.prefix &mdash; Enable running autoprefixer on CSS files to handle browser specific extensions.
* css.minify &mdash; Enable minifying CSS files.
* js.enable &mdash; Enable minifying script files.
* js.files &mdash; Array of files to minify. Files are relative to 'source'.
* js.compress &mdash; Enable compression of script files.
* js.mangle &mdash; Enable mangling of Javascript variable and function names.
* js.dotmin &mdash; Set '.min.js' as the output file extension after minification. Otherwise will be '.js'.

```
{
    services: {
        'less': {
            enable: true,
            files: [ '!**.less', '**.css.less' ]
            stylesheet: 'css/all.css',
            dependencies: { 'css/all.css.less' : '**.less' },
        },
        'css': {
            prefix: true,
            minfiy: true,
        },
        'js': {
            enable:     true,
            files:      null,
            compress:   true,
            mangle:     true,
            dotmin:     false,
        }
    }
}
```

### Get Pak from

[https://www.embedthis.com/pak/](https://www.embedthis.com/pak/)
