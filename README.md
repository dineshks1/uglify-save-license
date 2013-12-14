# uglify-save-license

Tiny license detector module for UglifyJS's `comments` option

## Installation

Install latest stable Node and run this command in the root of your project directory:

```
npm install --save-dev uglify-save-license
```

## Usage

### Use with [UglifyJS 2](https://github.com/mishoo/UglifyJS2)



### Use with [grunt-contrib-uglify](https://github.com/gruntjs/grunt-contrib-uglify)


## Example

### Gruntfile example

```coffeescript
module.exports = (grunt) ->
  'use strict'

  grunt.loadNpmTasks 'grunt-contrib-uglify'
  grunt.loadNpmTasks 'grunt-contrib-concat'
  grunt.loadNpmTasks 'grunt-contrib-clean'
  
  saveLicense = require 'uglify-save-license'

  grunt.initConfig
    uglify:
      target:
        options:
          preserveComments: saveLicense
        files: [
          expand: true
          flatten: true
          cwd: 'path/to/src'
          src: ["**/*.js"]
          dest: 'tmp/'
        ]

    concat:
      script:
        src: ['tmp/*.js']
        dest: 'path/to/build/app.js'

    clean:
      tmpfiles: ['tmp']

  grunt.registerTask 'default' [
    'uglify'
    'concat'
    'clean'
  ]
```

## License

Copyright (c) 2013 [Shinnosuke Watanabe](https://github.com/shinnn) All rights reserved.

Licensed under the [MIT license](http://opensource.org/licenses/mit-license.php).