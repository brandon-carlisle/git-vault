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

What if we want 