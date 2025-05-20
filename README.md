# Tutorial 10 - Asynchronous Programming - Brodcast Chat Application

## Original code of broadcast chat

![farrel](/img/farrel.png)

![athalla](/img/athalla.png)

![muljawan](/img/muljawan.png)

![fam](/img/fam.png)

When a client sends a message, the server receives it and broadcasts it to all connected clients, including the sender. This occurs because the server keeps track of every connected client and continuously listens for incoming messages. Once a message is received, the server ensures it reaches all clients in the network, maintaining communication between them.

## Modifying the websocket port

![clientfail](/img/clientfail.png)
![serveroldport](/img/serveroldport.png)

As we can see above, when I changed the client port to 8080, the client expects to be connected to a websocket running on port 8080. On the other hand, the server (which I haven't changed the port just yet) still connected to a websocket running on port 2000. Because there's no websocket running on port 8080, the client encounters a ConnectionRefused error. This means that the client has attempted to connect several times to the websocket on port 8080 but the connection has never been successful.

![clientnewport](/img/clientnewport.png)
![servernewport](/img/servernewport.png)

After I changed the port of the server's websocket to match the client's port, now the application will run just fine as before.

## Small changes. Add some information to client

![latestclient](/img/latestclient.png)
![latestclient2](/img/latestclient2.png)
![latestserver](/img/latestserver.png)

At this stage, we are adding sender information for each client, including their IP address and port. This allows the client to identify who sent the message. To implement this change, the format of `bcast_tx.send` in `server.rs` needs to be modified.
