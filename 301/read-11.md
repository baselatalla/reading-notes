# How To Use EJS to Template Your Node Application

## Introduction

When creating quick on-the-fly Node applications, an easy and fast way to template our application is sometimes necessary.

Jade comes as the view engine for Express by default but Jade syntax can be overly complex for many use cases. EJS is one alternative does that job well and is very easy to set up. Let’s take a look at how we can create a simple application and use EJS to include repeatable parts of our site (partials) and pass data to our views.


File Structure
Here are the files we’ll need for our application. We’ll do our templating inside of the views folder and the rest is pretty standard Node practices.

>>>>>>>1

package.json will hold our Node application information and the dependencies we need (express and EJS). server.js will hold our Express server setup, configuration. We’ll define our routes to our pages here


1. Node Setup
Let’s go into our package.json file and set up our project there.

>>>>>>2

All we will need is Express and EJS. Now we have to install the dependencies we just defined. Go ahead and run:

>>>>>3

With all of our dependencies installed, let’s configure our application to use EJS and set up our routes for the two pages we need: the index page (full width) and the about page (sidebar). We will do all of this inside our server.js file.

>>>>>>>4

Here we define our application and set it to show on port 8080. We also have to set EJS as the view engine for our Express application using app.set('view engine', 'ejs');. Notice how we send a view to the user by using res.render(). It is important to note that res.render() will look in a views folder for the view. So we only have to define pages/index since the full path is views/pages/index.

2. Start Up our Server

Go ahead and start the server using:

>>>>>>>>>5

Now we can see our application in the browser at http://localhost:8080 and http://localhost:8080/about. Our application is set up and we have to define our view files and see how EJS works there.


3. Create the EJS Partials
Like a lot of the applications we build, there will be a lot of code that is reused. We’ll call those partials and define three files we’ll use across all of our site: head.ejs, header.ejs, and footer.ejs. Let’s make those files now.

>>>>>>6

>>>>>>>7

>>>>>>8

Add the EJS Partials to Views
We have our partials defined now. All we have to do is include them in our views. Let’s go into index.ejs and about.ejs and use the include syntax to add the partials.

Syntax for including an EJS Partial
Use <%- include('RELATIVE/PATH/TO/FILE') %> to embed an EJS partial in another file.

The hyphen <%- instead of just <% to tell EJS to render raw HTML.
The path to the partial is relative to the current file.

>>>>>>9

Now we can see our defined view in the browser at http://localhost:8080.

>>>>>10

For the about page, we also add a bootstrap sidebar to demonstrate how partials can be structured to reuse across different templates and pages.

>>>>11

If we visit http://localhost:8080/about, we can see our about page with a sidebar!

![12](https://assets.digitalocean.com/articles/use-ejs-to-template-node-application/ejs-about.png)


Pass Data to Views and Partials
Let’s define some basic variables and a list to pass to our home page. Go back into your server.js file and add the following inside your app.get('/') route.

>>>>>12


We have created a list called mascots and a simple string called tagline. Let’s go into our index.ejs file and use them.

Render a Single Variable in EJS
To echo a single variable, we just use <%= tagline %>. Let’s add this to our index.ejs file:

>>>>13

Loop Over Data in EJS
To loop over our data, we will use .forEach. Let’s add this to our view file:

>>>>14


Now we can see in our browser the new information we have added!

![15](https://assets.digitalocean.com/articles/use-ejs-to-template-node-application/ejs-rendered.png)


Pass Data to a Partial in EJS
The EJS partial has access to all the same data as the parent view. But be careful: If you are referencing a variable in a partial, it needs to be defined in every view that uses the partial or it will throw an error.

You can also define and pass variables to an EJS partial in the include syntax like this:

>>>>>15

But you need to again be careful about assuming a variable has been defined.

If you want to reference a variable in a partial that may not always be defined, and give it a default value, you can do so like this:

>>>>>16

In the line above, the EJS code is rendering the value of variant if it’s defined, and default if not.



