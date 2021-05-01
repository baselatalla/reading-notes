# How To Use EJS to Template Your Node Application

## Introduction

When creating quick on-the-fly Node applications, an easy and fast way to template our application is sometimes necessary.

Jade comes as the view engine for Express by default but Jade syntax can be overly complex for many use cases. EJS is one alternative does that job well and is very easy to set up. Let’s take a look at how we can create a simple application and use EJS to include repeatable parts of our site (partials) and pass data to our views.


File Structure
Here are the files we’ll need for our application. We’ll do our templating inside of the views folder and the rest is pretty standard Node practices.

![Screenshot_1](https://user-images.githubusercontent.com/55560502/116793879-2412d480-aad2-11eb-911a-fa0104a781c4.png)

package.json will hold our Node application information and the dependencies we need (express and EJS). server.js will hold our Express server setup, configuration. We’ll define our routes to our pages here


1. Node Setup
Let’s go into our package.json file and set up our project there.

![Screenshot_2](https://user-images.githubusercontent.com/55560502/116793886-28d78880-aad2-11eb-8e96-c2c88f3e26e3.png)

All we will need is Express and EJS. Now we have to install the dependencies we just defined. Go ahead and run:

![Screenshot_3](https://user-images.githubusercontent.com/55560502/116793892-2e34d300-aad2-11eb-952e-83bfc1800281.png)

With all of our dependencies installed, let’s configure our application to use EJS and set up our routes for the two pages we need: the index page (full width) and the about page (sidebar). We will do all of this inside our server.js file.

![Screenshot_4](https://user-images.githubusercontent.com/55560502/116793895-33921d80-aad2-11eb-8945-576cd071b6e7.png)

Here we define our application and set it to show on port 8080. We also have to set EJS as the view engine for our Express application using app.set('view engine', 'ejs');. Notice how we send a view to the user by using res.render(). It is important to note that res.render() will look in a views folder for the view. So we only have to define pages/index since the full path is views/pages/index.

2. Start Up our Server

Go ahead and start the server using:

![Screenshot_5](https://user-images.githubusercontent.com/55560502/116793898-3987fe80-aad2-11eb-9b5c-56fb8bf64008.png)

Now we can see our application in the browser at http://localhost:8080 and http://localhost:8080/about. Our application is set up and we have to define our view files and see how EJS works there.


3. Create the EJS Partials
Like a lot of the applications we build, there will be a lot of code that is reused. We’ll call those partials and define three files we’ll use across all of our site: head.ejs, header.ejs, and footer.ejs. Let’s make those files now.

![Screenshot_8](https://user-images.githubusercontent.com/55560502/116793903-43a9fd00-aad2-11eb-990c-83c09431925d.png)

![Screenshot_6](https://user-images.githubusercontent.com/55560502/116793905-44db2a00-aad2-11eb-8645-53081dda61a3.png)

![Screenshot_7](https://user-images.githubusercontent.com/55560502/116793906-4573c080-aad2-11eb-8ac2-05c011553104.png)


Add the EJS Partials to Views
We have our partials defined now. All we have to do is include them in our views. Let’s go into index.ejs and about.ejs and use the include syntax to add the partials.

Syntax for including an EJS Partial
Use <%- include('RELATIVE/PATH/TO/FILE') %> to embed an EJS partial in another file.

The hyphen <%- instead of just <% to tell EJS to render raw HTML.
The path to the partial is relative to the current file.

![Screenshot_9](https://user-images.githubusercontent.com/55560502/116793915-4f95bf00-aad2-11eb-81ae-edae159bb14f.png)

Now we can see our defined view in the browser at http://localhost:8080.

![Screenshot_10](https://user-images.githubusercontent.com/55560502/116793920-53c1dc80-aad2-11eb-8452-5c898688cbf2.png)

For the about page, we also add a bootstrap sidebar to demonstrate how partials can be structured to reuse across different templates and pages.

![Screenshot_11](https://user-images.githubusercontent.com/55560502/116793924-57edfa00-aad2-11eb-889c-5973f09e7ebd.png)

If we visit http://localhost:8080/about, we can see our about page with a sidebar!

![12](https://assets.digitalocean.com/articles/use-ejs-to-template-node-application/ejs-about.png)


Pass Data to Views and Partials
Let’s define some basic variables and a list to pass to our home page. Go back into your server.js file and add the following inside your app.get('/') route.

![Screenshot_12](https://user-images.githubusercontent.com/55560502/116793927-5cb2ae00-aad2-11eb-8550-e007eee0678e.png)


We have created a list called mascots and a simple string called tagline. Let’s go into our index.ejs file and use them.

Render a Single Variable in EJS
To echo a single variable, we just use <%= tagline %>. Let’s add this to our index.ejs file:

![Screenshot_13](https://user-images.githubusercontent.com/55560502/116793929-60463500-aad2-11eb-922e-26c9cdb64528.png)

Loop Over Data in EJS
To loop over our data, we will use .forEach. Let’s add this to our view file:

![Screenshot_14](https://user-images.githubusercontent.com/55560502/116793934-663c1600-aad2-11eb-98f9-fb5b7b19d26f.png)


Now we can see in our browser the new information we have added!

![15](https://assets.digitalocean.com/articles/use-ejs-to-template-node-application/ejs-rendered.png)


Pass Data to a Partial in EJS
The EJS partial has access to all the same data as the parent view. But be careful: If you are referencing a variable in a partial, it needs to be defined in every view that uses the partial or it will throw an error.

You can also define and pass variables to an EJS partial in the include syntax like this:

![Screenshot_15](https://user-images.githubusercontent.com/55560502/116793937-689e7000-aad2-11eb-94a1-c2950f905a38.png)

But you need to again be careful about assuming a variable has been defined.

If you want to reference a variable in a partial that may not always be defined, and give it a default value, you can do so like this:

![Screenshot_16](https://user-images.githubusercontent.com/55560502/116793941-6cca8d80-aad2-11eb-8231-58d5955bcdb3.png)

In the line above, the EJS code is rendering the value of variant if it’s defined, and default if not.



