# Installation using Homebrew

You may already have MongoDB installed on your system, let's check by typing `mongod` in terminal (note the lack of a "b" at the end").

If you receive an error, lets use _Homebrew_ to install MongoDB:

1. Update Homebrew's database (this might take a bit of time)  
   `brew update`
2. Then install MongoDB  
 `brew install mongodb`

MongoDB by default will look for data in a folder named `/data/db`. We would have had to create this folder, but Homebrew did it for us (hopefully).

#### Start Your Engines!

`mongod` is the name of the actual database server process. The installation of MongoDB does not set mongoDB to start automatically. A common source of errors when starting to work with MongoDB is forgetting to start the database server.

To start the database server, type `mongod` in terminal.

Press `control-c` to stop the server. **Don't just shut the terminal window.**

MongoDB installs with a client app, a JavaScript-based shell, that allows us to interact with MongoDB directly. To enter the shell open __another__ terminal window and type:

 `mongo`

> NOTE! Because `mongod` is a __server__ an we're accessing it as a __client__ we're communicating via __ports__ so we can run our commands from any directory.

The app will load and the prompt will change to `>`.

List the shell's available commands: `> help`.
