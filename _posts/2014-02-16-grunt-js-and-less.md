---
layout: post
category : posts
title: Grunt: Building LESS into CSS
tags : [node.js, grunt, beginner, tutorial, less]
---

How do you build LESS into CSS? How do you build it minified? How can you build it in your development environment?

These are the common scenarios when working with LESS and they are easily solved with Grunt.

In the past, we used grunt-recess, because that's what Bootstrap was using. Apparently, the owner of that repository hasn't kept up with the updates with LESS (most notably LESS 1.4 extend functionality), so we have stopped using it. (I think he's going to maintain his recess code for Gulp, which is also a useful build tool, but a bit different from what we need in some cases).

Now, I suggest using [grunt-contrib-less][1].

The set up is simple if you've set up your Gruntfile.js

Install using the node package manager from your command line and normally you'll want to save the version information as well (using the --save-dev):

`npm install grunt-contrib-less --save-dev`    

Then, add the configuration (which is really just javascript data):

```js
var watchFilesLess = 'Web/assets/style/**/*.less'; 

grunt.initConfig({
    pkg : grunt.file.readJSON('package.json'),
    // Watch for auto compiling.
    watch : {
        filesLess : { // name of the watch for our less files.
            files : [watchFilesLess],
            tasks : ['less:dev'],
            options : {
                spawn : false
            }
        }       
    },
    less: {
        dev: {
            options: {
            },
            files: {
                'Web/assets/style/site.css': 'Web/assets/style/site.less'
            }
        },
        production: {
            options: {
                cleancss: true // compress using clean-css
                // Could also use the default: compress: true
            },
            files: {
                'Web/assets/style/site.min.css': 'Web/assets/style/site.less'
            }
        }
    },
    ...
});
```    

Define the tasks:

`grunt.loadNpmTasks('grunt-contrib-less');`
    

I normally run the task as part of my default, meaning that when I type 'grunt' on the command-line, it will run. Order is important here, and my 'less' should be before my 'watch'.

`grunt.registerTask('default', ['less:production', 'watch']);`
    

Then, I have a task for just building the css, which is run on the command-line by typing: grunt css

`grunt.registerTask('css', ['less:production']); // just build`

 [1]: https://github.com/gruntjs/grunt-contrib-less