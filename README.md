# Demo-of-C-coding
This is about a demonstration of coding with C++

For the following requirments:

1.The client should be able to connect to the server through a NamedPipe

  This demo is using Windows NamedPipes to implement.
  
2.The client should be able to make both sync and async calls to the server

 At client side, simply  a precompile option is set as
 #define ASYNCHRONOUSPIPE  //asnychronous or not
to control the communicating type.
  
3.The client should be able to send trivial data (strings, numbers) to the server

We can send/receive any bytes between server and client

4.The client should be able to create objects on the server (based on req-7 below), retrieve them, their attributes 
and call methods on them

Simply, the client can send command “1” to retrieve available classes with attributes and methods definition. Also,
clients can instantiate many objects for certain class and store them at server side. These objects are identified 
by unique ID. With one request, the client can commit a batch of calls to server, create or update objects, 
invoke methods as well as retrieve the execution result. Saved objects can be used to execute their methods
which may update themselves. Also, saved objects can be used as parameters to construct other objects. 
  
5.The server should be able to receive both sync/async connection requests from clients

The server is implemented with multi-thread and adaptive to both sync and async simultaneously.
  
6.The server should be able to store data provided by the client via NamedPipe in a reasonable data structure

 Rapidjson is used to transmit objects, remote-call requests and store objects in files.
  
7.The server should be able to register a custom class (w/ related functions, attributes) which can be used by the client (see req-4)

A config file named ClassListConfig.dat at server side is used to list the available classes of which details can be fetched by client.
  
8.The server should be able to store the custom objects created by the client for the custom class created in req-7

client can instantiate many objects for a class and store them at server side. These objects are identified by unique ID. 
  For every client there is a subdirectory to store their object files named class+objectID. Clients can add and update 
  their remote objects.
