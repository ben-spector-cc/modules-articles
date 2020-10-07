# JavaScript Environments

## Tools used and referenced in this article

* Text Editors (I recommend the text editors [Sublime 3](https://www.sublimetext.com/3) or [VS Code](https://code.visualstudio.com/download))
* [Node.js](https://nodejs.org/en/download/)
* Computer Terminal

## Runtime Environments

**A runtime environment is where your program will be executed.** This article covers the two JavaScript runtime environments: 
1. the Node.js runtime environment;
2. a browser's runtime environment.


The most common place where JavaScript code is executed is in a browser. For example, you could create a file called **my_website.html** and put the following HTML code inside:

```html
<!-- my_website.html -->
<html>
    <body>
        <h1> My Website </h1>
        <script> window.alert("Hello World"); </script>
    </body>
</html>
```

Open your favorite browser and open up this file by going to File > Open > **my_website.html**. 

Upon loading, the embedded `<script></script>` will execute and the `window.alert()` function creates a pop-up box in your browser with the text `"Hello World"`. How is this possible? Where did the `window.alert()` function come from and how can it control your browser?

The answer is that we are executing this code in the _browser's runtime environment_. The `window.alert()` function is built into this environment and any program executed in a browser has access to this function. In fact, the `window` object applications running in a browser access to a huge amount of data and functionality relating to the open browser window beyond just `alert()`.

> Try replacing `window.alert()` with `window.prompt()` or `window.confirm()`

Applications created for and executed in the browser are known as _front-end_ applications. For a long time, JavaScript code could only be executed in a browser. In order to create `back-end` applications that could run on a computer _without_ a browser, you would need to use other programming languages such as Java or PHP.

In 2009, the _Node.js runtime environment_ was created for the purpose of executing JavaScript code without a browser, thus enabling programmers to create _full-stack_ (front-end and back-end) applications entirely in the JavaScript language. 

Node.js is an entirely new runtime environment, meaning that browser-environment-related data values and functions, like `window.alert()`, can't be used. Instead, the Node.js runtime environment gives applications access to a variety of features unavailable in a browser, such as access to the server's file system, database, and network.

For example, suppose we created a file called **my-app.js**. We can check to see the directory that this file is located in using the Node.js runtime environment variable `process`:

```js
// my-app.js
window.alert("process.env.PWD");
```

`process` is an object containing data relating to the JavaScript file being executed. `process.env` contains environment variables such as `process.env.PWD` which contains the current working directory (and stands for "print working directory"). 

To execute the JavaScript code in this file, we can open up a terminal and run:

```sh
$ node my-app.js
/path/to/working/directory
```

So, as you can see, depending on _where_ your javascript code is executed, different data values and functions will be available. As you build your JavaScript application, consider what features it will include:
* Does it have a user-facing component that is accessed via the browser? 
* Will you need access to file systems and/or databases?
* [any other questions?]

Answering these questions will help you determine whether or not you are building a front-end, back-end, or full-stack application, and which environment variables you will have access to.
