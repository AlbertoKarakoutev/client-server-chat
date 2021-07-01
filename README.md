# client-server-chat

# Server
A Java Spring server handling incoming connections to the chat. The Controller handles the endpoints for the tasks and the Service executes them.
Start the server by running the ChatServerApplication.java file.

## Methods
 
```java
List<String> getAcviteUsers()
```
Retrieves a list with all currently logged in users from the resources directory.


  
  
```java
boolean login() 
```
@PostMapping
Logs in the user by recording his username and IP address in the active users file. This will also allow the user to priceed to the main GUI of the chat. If the method returns true, the login has been successful, e.g. no one has that username, no file errors have happend etc.



```java
boolean logout()
```
@PostMapping
Logs out the user by removing his entry from the ective users files. Thie will close the application. Returns true if no errors.


```java
void sendMessage()
```
@PostMapping
The server receives the message, username of the sender, the date and time and the list of people to send the message to. The server send the message to the active users from the receivers list through sockets.


## Client

The client has a textarea for writing, showing and a send button. When the user sends a message vie ```sendMessage()```, it is sent to the server throuth the HttpClient with the message and other data as the request body. The server then distributes the message and all receivers' chat boxes are updated with the new information.
