# Sending form data

Once the form data has been validated on the client-side, it is okay to submit the form. And, since we covered validation in the previous article, we're ready to submit! This article looks at what happens when a user submits a form — where does the data go, and how do we handle it when it gets there? We also look at some of the security concerns associated with sending form data.

## Client/server architecture

At it's most basic, the web uses a client/server architecture that can be summarized as follows. a client (usually a web browser) sends a request to a server (most of the time a web server like Apache, Nginx, IIS, Tomcat, etc.), using the HTTP protocol. The server answers the request using the same protocol.

![1](https://developer.mozilla.org/en-US/docs/Learn/Forms/Sending_and_retrieving_form_data/client-server.png)

An HTML form on a web page is nothing more than a convenient user-friendly way to configure an HTTP request to send data to a server. This enables the user to provide information to be delivered in the HTTP request.

## On the client side: defining how to send the data

The <form> element defines how the data will be sent. All of its attributes are designed to let you configure the request to be sent when a user hits a submit button. The two most important attributes are action and method.


## The method attribute
The method attribute defines how data is sent. The HTTP protocol provides several ways to perform a request; HTML form data can be transmitted via a number of different methods, the most common being the GET method and the POST method

To understand the difference between those two methods, let's step back and examine how HTTP works. Each time you want to reach a resource on the Web, the browser sends a request to a URL. An HTTP request consists of two parts: a header that contains a set of global metadata about the browser's capabilities, and a body that can contain information necessary for the server to process the specific request.

## The GET method
The GET method is the method used by the browser to ask the server to send back a given resource: "Hey server, I want to get this resource." In this case, the browser sends an empty body. Because the body is empty, if a form is sent using this method the data sent to the server is appended to the URL.

# A special case: sending files
Sending files with HTML forms is a special case. Files are binary data — or considered as such — whereas all other data is text data. Because HTTP is a text protocol, there are special requirements for handling binary data.

## The enctype attribute
This attribute lets you specify the value of the Content-Type HTTP header included in the request generated when the form is submitted. This header is very important because it tells the server what kind of data is being sent. By default, its value is application/x-www-form-urlencoded. In human terms, this means: "This is form data that has been encoded into URL parameters."

If you want to send files, you need to take three extra steps:

Set the method attribute to POST because file content can't be put inside URL parameters.
Set the value of enctype to multipart/form-data because the data will be split into multiple parts, one for each file plus one for the text data included in the form body (if text is also entered into the form).
Include one or more <input type="file"> controls to allow your users to select the file(s) that will be uploaded.

## We can modify fields in FormData with methods:

formData.append(name, value) – add a form field with the given name and value,
formData.append(name, blob, fileName) – add a field as if it were <input type="file">, the third argument fileName sets file name (not form field name), as it were a name of the file in user’s filesystem,
formData.delete(name) – remove the field with the given name,
formData.get(name) – get the value of the field with the given name,
formData.has(name) – if there exists a field with the given name, returns true, otherwise false
A form is technically allowed to have many fields with the same name, so multiple calls to append add more same-named fields.
There’s also method set, with the same syntax as append. The difference is that .set removes all fields with the given name, and then appends a new field. So it makes sure there’s only one field with such name, the rest is just like append:
formData.set(name, value),
formData.set(name, blob, fileName).
Also we can iterate over formData fields using for..of loop:


# Summary

FormData objects are used to capture HTML form and submit it using fetch or another network method.
We can either create new FormData(form) from an HTML form, or create a object without a form at all, and then append fields with methods:
formData.append(name, value)
formData.append(name, blob, fileName)
formData.set(name, value)
formData.set(name, blob, fileName)
Let’s note two peculiarities here:
The set method removes fields with the same name, append doesn’t. That’s the only difference between them.
To send a file, 3-argument syntax is needed, the last argument is a file name, that normally is taken from user filesystem for <input type="file">.
Other methods are:
formData.delete(name)
formData.get(name)
formData.has(name)

* high quality frameworks that make handling forms easier, such as:
  * Django for Python
  * Express for Node.js.
  * Laravel for PHP.
  * Ruby On Rails for Ruby

