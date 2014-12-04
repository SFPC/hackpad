# [Node.js](http://www.nodejs.org) workshop

**By [Jonas Jongejan](/ep/profile/DSJ4bUjGZcw) !**

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_KKyn3DpwfBN_p.252083_1413917211609_undefined)

**Overview**

Node is Chrome's implementation of Javascript, taken off the browser and used in the world as a full, general purpose language. 

It's easy for communication and other more general network, web functions and it has a very good system to handle different types of logic.

In its simplest form, it can be used in terminal just like you would on the console:

*   console.log("Hola")
*   > Hola
*

To make an application in Node.js we'll create a new file, such as app.js within a folder:

*   appfolder
*   -> app.js
*

To run the application, simply do:

*   node app.js

**Modules**

What makes Node.js interesting is the vast quantity of modules for it, that we'll manage using _npm,_ or Node Package Manager. npm comes with the common node setup, and it's a tool to easy install modules (of which there are > 100k now). 

To install a module, we'll simply do:

*   npm install moment.js

For Node applications, the standard is to install modules locally within the application folder, so that it's easy to share and transport and minimize dependency issues.

To include a module that we've installed to the application, we'll use 'require'.

*   * ones with 'npm' will be specific to node

*   var moment = require('moment');  // this includes your modules
*   console.log(moment())

**package.json:**

Package.json is a file that describes the structure of the current application and its dependencies. It describes the modules its uses and it will inform the requirements when the application is run in an environment that is different from the original one. 

Using:

*   npm install moments.js --save

This will write the dependency moment.js (and whatever else it already has) in _package.json_, so that it's included in its dependencies descriptions. Need to type "--save" in terminal in order to include new modules that extend node.

*   {
*       "dependencies" : {
*           "moment": "^2.8.3",
*           "superb": "^1.0.4"
*       }
*   }

This is so, so that when you deliver, share, deploy or whatever you do with a node app, you don't include the dependencies but there is a structured documentation of the environment in which it runs.

package.json will often include all sorts of information, such as license, author, etc.

**Uses**

Node is very often used to create web services, for server programming and other stuff.
<undefined><li>**Web applications: Express.js as example**</li></undefined>

[Express.js](http://expressjs.com/) is a web framework for Node. It has a variety of uses, such as server utilities. It is thought to provide basic serving roots, '_when you receive this kind of request, return this shit'-_ type of behavior

For example (from Express.js site):

*   // When app gets a GET with no additional info,
*       send back: "Hello World"
*   app.get('/', function (req, res) {
*     res.send('Holaquetal!')
*   });
*     
*   // We create the server, and make it listen to port 3000
*   var server = app.listen(3000, function () {
*     var host = server.address().address
*     var port = server.address().port
*     console.log('Example app listening at [](http://%s:%s)http://%s:%s', host, port)
*   });

As a server programming tool, it can take URI parameters, manipulate them in the server and return them to the client.
<undefined><li>**Other interesting modules**</li></undefined>

[node-slack](https://github.com/xoxco/node-slack): communicate with Slack's api, make bots and other fun stuff

**Host a Node.js app in a public serving server -> HEROKU!**

[](https://www.heroku.com/)https://www.heroku.com/

It's a very simple hosting service, hosting servers where to upload applications in Node (and Python, RoR, whateva) and have it run. In its free version, it's created for simply proof-of-concept applications and testing, but projects can be scaled to production in premium versions of it.

Heroku requieres a config file called Procfile with a specific form to inform the server on how to run, and some port configuration and so on. In its most basic form:

*   web: node app.js

Yeah.

-> DO THIS: So to make this work, we'll first install [Heroku command line tools](https://devcenter.heroku.com/articles/getting-started-with-nodejs#set-up) (there's a set of tool from Heroku you can install). 

Then to push it to the Heroku git server, we'll first create a git repo in Heroku in our folder.

*   heroku create

And finally commit and push changes to the server:

*   git push keroku master

So it really is very simple to get something running on a server in Node that allows communication between machines and a server and so on (look at examples with [](http://socket.io/))http://socket.io/).

Can connect / interact with twitter too:

[](https://www.npmjs.org/package/node-twitter)https://www.npmjs.org/package/node-twitter

Extra reference for Twitter and Node, bots!  -> [](http://www.apcoder.com/2013/10/03/twitter-bot-20-minutes-node-js/)[http://www.apcoder.com/2013/10/03/twitter-bot-20-minutes-node-js/](http://www.apcoder.com/2013/10/03/twitter-bot-20-minutes-node-js/)

Node is a way to work with different APIs

**Database utilities**

Node has very good support for database systems such as PostgreSQL (Redshift) or NoSQL (MongoDB), but it can work with anything. 

**More modules**

Awesome curated list of packages -> [](https://github.com/sindresorhus/awesome-nodejs)https://github.com/sindresorhus/awesome-nodejs

**References**

[](http://www.nodejs.org)http://www.nodejs.org

[](http://nodeschool.io/)[http://nodeschool.io/](http://nodeschool.io/)

[](https://devcenter.heroku.com/articles/node-best-practices)[https://devcenter.heroku.com/articles/node-best-practices](https://devcenter.heroku.com/articles/node-best-practices)