## Using REPL

In the terminal, we open the Node REPL, by using the node keyword. We can then write any JavaScript we want in here:

![[Code_Aq19fb5RbX.png]]

We can exit this REPL, we can use .exit, and CTRL D.

If we want to see all the global variable that are available in node, while in the REPL, we can press tab:

![[Code_lzGptFp0Ky.png]]

We can use the underscore to use the previous value:

![[Code_ZYIKRHjjUb.png]]

[More info here]()

## Using Modules

Let's say we wanted to read and write files to the file system. In order to do that in Node, we need to use what is called a node module. A module basically adds extra functionality to node.

In the case of reading files, we would use the fs (file system) module.

How can we use these modules? We can 'require' them into our file and then store the result into a variable.

![[Code_uvQVhTXIEC.png]]

## Reading and Writing files

Reading the text from a txt file: 

![[Code_rvHiljLHc6.png]]

Writing a new file to the file system: 

![[Code_IcZIpdn24y.png]]

## Reading and Writing files asynchronously 

We can use the asynchronous version, readFile:

![[Code_gt9DNowbb8.png]]

What if we want another readFile that depends of the first readFile? We can use callbacks (this will cause callback hell, but will be solved later with async/await):

![[Code_23B9wAIupi.png]]

## Creating a simple web server

When we build our server, we do two things:
1) We create the server
2) We start the server to listen for incoming requests

We make the server using createServer, which takes in a callback function which will be called every time a request is made to the server. It also gets called with two arguments, the request and the response:

![[Code_heViIQHVtZ.png]]

We can then start listening to requests on the server using the listen method which will be on the server after making it with createServer. The listen method will take three arguments - the port on which we want the server to listen to, the IP address of where we want to run the server and then a callback function that will be called when the server starts to listen.

![[Code_X0ME8tmiSu.png]]

## Routing

In small apps, we can do our own routing (in larger / production apps we could use Express). This just means, based on the 