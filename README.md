# Meteor BackboneCoffee Template

Simple [Meteor](https://github.com/meteor/meteor) seed repo with some core smart packages, starter files, & basic folder structure.

Usage:
```
git clone http://github.com/Whoaa512/backbone-coffee-meteor-seed.git [project-name]
cd [project-name]
meteor update
meteor
```


Comes with the following core smart packages already install:

* `autopublish`
* `insecure`
* `preserve-inputs`
* `coffeescript`
* `bootstrap`
* `less`
* `backbone`
* `jquery`
* `underscore`


##Where should I put my files?

The example apps in meteor are very simple, and don’t provide much insight. Here’s my current thinking on the best way to do it: (any suggestions/improvements are very welcome!)

```bash
lib/                       # <- any common code for client/server.
lib/environment.js         # <- general configuration
lib/methods.js             # <- Meteor.method definitions
lib/external               # <- common code from a third party
## Note that js files in lib folders are loaded before other js files.

models/                    # <- definitions of collections and methods on them (could be collections/)

client/lib                 # <- client specific libraries (also loaded first)
client/lib/environment.js  # <- configuration of any client side packages
client/lib/helpers         # <- any helpers (handlebars or otherwise) that are used often in view files

client/application.js      # <- subscriptions, basic Meteor.startup code.
client/index.html          # <- toplevel html
client/index.js            # <- and its JS
client/views/<page>.html   # <- the templates specific to a single page
client/views/<page>.js     # <- and the JS to hook it up
client/views/<type>/       # <- if you find you have a lot of views of the same object type
client/stylesheets/        # <- css / styl / less files

server/publications.js     # <- Meteor.publish definitions
server/lib/environment.js  # <- configuration of server side packages

public/                    # <- static files, such as images, that are served directly.

tests/                     # <- unit test files (won't be loaded on client or server)
```

For larger applications, discrete functionality can be broken up into sub-directories which are themselves organized using the same pattern. The idea here is that eventually module of functionality could be factored out into a separate smart package, and ideally, shared around.

```bash
feature-foo/               # <- all functionality related to feature 'foo'
feature-foo/lib/           # <- common code
feature-foo/models/        # <- model definitions
feature-foo/client/        # <- files only sent to the client
feature-foo/server/        # <- files only available on the server
```


## Need more smart packages?
You can optionally add a `packages` folder to your root directory where you can clone down repos of [Meteorite smart packages](http://atmosphere.meteor.com). No Meteorite needed!

[Original repo](https://github.com/nickjanssen/meteor-template) by @nickjanssen.

Folder structure based from @oortcloud's [Unofficial Meteor FAQ](https://github.com/oortcloud/unofficial-meteor-faq/blob/master/README.md#where-should-i-put-my-files).

MIT License
