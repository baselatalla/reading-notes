## Node.js For Beginners. Deploy Your Blog to Heroku

Error pages are not what typically appear on your screen when you're surfing the web, but when it happens it's so annoying! To see how servers work from within, we will build a simple web server by ourselves. We will use Node.js as a server part technology for that task. Then we'll use Heroku cloud application platform to turn this local server into a world wide server.


We will use Node.js for our project. Node.js is an open source, cross-platform runtime environment, which allows you to build server-side and networking applications. It's written in JavaScript and can be run within the Node.js runtime on any platform. First of all, of course, you need to install it. You'd better check the download page for more details. I'll wait until you finish, so don't worry. Is it done? Great! Now you can create your first web server. And it will be one of the easiest tasks in your life.

First of all, we need to create a JavaScript file. Let's name it server.js:

![1](https://user-images.githubusercontent.com/55560502/115961208-0ec00800-a51e-11eb-8ab9-08a672caa04c.png)


It's simple. It's tiny. But it's a server! Let's make sure it's working. Run at your terminal:

*_node server.js_*

Then check it in your browser. Your new server's address, as you may guess, is http://localhost:3000/ Mine is working. How about yours? Hope, it's working too.

![2](http://i.imgur.com/idykoj7.png)

Now, to be sure it's a web server and not just a piece of code that returns a single line of text, we'll use it as a server! You can check it with your smartphone. Let's suppose, your laptop's IP address within your local network is 192.168.1.101. You can connect to your server through the 3000th port (for this particular example) by typing http://192.168.1.101:3000/ in your browser. Works well in my case:

![3](http://i.imgur.com/emlOrX0.png)


Well, it is a server! And we have evidence. What you got here is your own client-server model, which can fit in your bag! Take it any place you want! It will be a good idea to deploy our server online, so everyone could see it.

But you should notice something, before we go further. Let's look more closely at our first Node server. This is an example of how Node provides you with non-blocking and event-driven behavior. Let me explain:

![2](https://user-images.githubusercontent.com/55560502/115961212-167fac80-a51e-11eb-9f45-84baad8a774f.png)



This code performs a request for some resource. When the response comes back, an anonymous function is called. It contains the argument data, which is the data received from that request.

So, Node allows you to use the so-called event loop, which works faster because of non-blocking behavior. For example, nginx uses an event loop with asynchronous I/O. That's why it's fast as hell!


### Make it worldwide


Works fine. But it works locally. WWW is for "World Wide Web" and we will turn your local server into a world wide server. We'll use Heroku cloud application platform for this. Heroku is a cloud platform as a service (cool long-bearded programmer guys call such type of things "PaaS"). It allows you to deploy your web server, so everyone could see how awesome you are as a web developer. First of all, you need to create an account on developer's site and install Heroku. This is not so hard. Just follow the instructions. There is also instruction on Heroku's site that can explain you how to run your first simple web server, which returns you the "Hello, World!" string. You can try it, but I think that it will be more interesting if we build our own web server from scratch. Sounds exciting, huh?

## First step after Heroku installation is to log in to the system from your computer:

*_heroku login_*

We will leave Heroku for now. But we'll need it soon after we build our server.

* Now, the creation. It will be a simple blog with basic functionality. It will show you requested web pages and the error page in case of an error.

Create your project directory. And then create the server.js file inside of it.

First of all, let's declare some variables:

*var http = require("http");*
*var fs = require("fs");*
*var path = require("path");*
*var mime = require("mime");*

The first one will give you the key to Node's HTTP functionality. The second one is for possibility to interact with the file system. The third one allows you to handle file paths. The last one allows you to determine a file's MIME-type. And it's not a part of Node.js, so we need to install third-party dependencies before using it. We need to create the package.json file for that purpose. It will contain project related information, such as name, version, description, and so on. For our project we will use MIME-types recognition, because it's not enough to just send the contents of a file when you use HTTP. You also need to set the Content-Type header with proper MIME-type. That's why we need this plug-in.

Create the package.json file and fill it with proper information. Here's mine:

package.json
{
  "name" : "blog",
  "version" : "0.0.1",
  "description" : "My minimalistic blog",
  "dependencies" : {
    "mime" : "~1.2.7"
  }
}

There are "name", "version", "description", and "dependencies" fields in it. The syntax is simple, as you can see. We added our "mime" plug-in and now it's time to download it. We'll use built-in Node Package Manager. Just run:

*_npm install_*

It will create node_modules folder and place all the files inside of it. So, we resolve our dependencies and can return to our code.

We will now create send404() function. It will handle the sending of 404 error, which usually appears when requested file doesn't exist:


function send404(response) {
  response.writeHead(404, {"Content-type" : "text/plain"});
  response.write("Error 404: resource not found");
  response.end();
}


Nothing sophisticated with this one. It returns plain text when server can't find a page.

* Now we will define sendPage() function. It first writes the header and then sends the contents of the file:

function sendPage(response, filePath, fileContents) {
  response.writeHead(200, {"Content-type" : mime.lookup(path.basename(filePath))});
  response.end(fileContents);
}
Notice the way we handle the MIME-types.

* Now we'll define how our server will handle responses. This function will return the content of the requested file or the 404 error otherwise:

handler.js
function serverWorking(response, absPath) {
  fs.exists(absPath, function(exists) {
    if (exists) {
      fs.readFile(absPath, function(err, data) {
        if (err) {
          send404(response)
        } else {
          sendPage(response, absPath, data);
        }
      });
    } else {
      send404(response);
    }
  });
}

* And now it's time to create the HTTP server:

create-server.js

var server = http.createServer(function(request, response) {
  var filePath = false;

  if (request.url == '/') {
    filePath = "public/index.html";
  } else {
    filePath = "public" + request.url;
  }

  var absPath = "./" + filePath;
  serverWorking(response, absPath);
});

Now we need to start our server. And here's the tricky part. Do you remember how we told the server to listen to the 3000th port in our first example? No? I'll remind you:

*_http.createServer(<some code here>).listen(3000)_*

We can do it when we run our server locally. But Heroku sets a dynamically assigned port number to your app. That's why we need to handle all this mess with ports as it’s shown below:

*_var port_number = server.listen(process.env.PORT || 3000);_*

You can use the port_number variable later. For example, in console.log() function to tell the user, which port is used. This is your homework for tomorrow.

That's all we need to run our simple web server. Now it's time to create some content. We'll create the public folder and two folders inside of it: stylesheets and images. We'll put all our HTML files into the public folder.The stylesheets folder is for CSS files. And the images one is for pictures.

We need to create the index.html file. It will determine our blog's exterior. Here's the code:

![3](https://user-images.githubusercontent.com/55560502/115961220-1da6ba80-a51e-11eb-9455-d2e96aab3ac4.png)


Here you can see how the main page looks like: 

![5](http://i.imgur.com/3pSODQH.png)


To start your server locally run:

*_node server.js_*


And then click the first link:

![5](http://i.imgur.com/6Z9OxuV.png)


![5](http://i.imgur.com/iQBQKdM.png)



## It's Heroku time!


Open your terminal within your project folder. For my Linux it's:

_*cd /path/to/my/project*_

Then run:

_*git init*_

Empty Git repository will be initialized in .git/ folder.

Then run:

_*git add .*_

This command allows Git to track your files changes.

Now commit your files to the initialized Git repo:

*_git commit -m "Simple server functionality added"_*

We'll create our first Heroku application now:

_*heroku create*_

Heroku will generate a random name for your application. In my case it's enigmatic-citadel-9298. Don't worry. You can change it later.

Now we can deploy our project. Every Heroku app starts with no branches and no code. So, the first time we deploy our project, we need to specify a remote branch to push to:

_*git push heroku master*_

The application is now deployed. Ensure that at least one instance of the app is running:

_*heroku ps:scale web=1*_

And now, before we open it, it's time to choose a proper name for our first creation. I called it myfirstserver:

_*heroku apps:rename myfirstserver*_

Everything is done. You can try it now:

*_heroku open_*

This command will open your Heroku project in your web browser. In this particular case, server address is https://myfirstserver.herokuapp.com/. Now you can share your first web application with any person you want.

Looking back

We've built our own web server using less than 50 lines of code. Not so hard, if you ask me. It's pretty simple, yes. But you can see, how average server works. It was a simple task. But you can combine Node.js with different technologies, such as CSS3 and HTML5, then spice it with some JavaScript functionality. There is really a lot of libraries and frameworks to take a look at. Personally I started to dig into Webix, it's a relatively new library and is developed by a small software company from Eastern Europe. Samples of apps made with the library and Node.js: CRM and task planner. Seems like you can create anything with the right client-side framework and Node.js.

And, talking about Node.js as a technology...

...it will make your DIRTy job for you.
There is an acronym created to describe such type of applications Node.js was created for. It's DIRT. It means Data-Intensive Real-Time applications. Node allows a server to handle a lot of connections and work with a number of requests at the same time. And you don't need much memory for that. It's designed to be responsive and fast. Just like your web browser! So, it's useful when you need to create an application that will be able to respond instantly to a large number of users. And Node was built from scratch to provide you with such a functionality.



