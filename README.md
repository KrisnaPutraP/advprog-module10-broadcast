# Tutorial 10 - Asynchronous Programming - Brodcast Chat Application

## Original code of broadcast chat

![farrel](/img/farrel.png)

![athalla](/img/athalla.png)

![muljawan](/img/muljawan.png)

![fam](/img/fam.png)

When a client sends a message, the server receives it and broadcasts it to all connected clients, including the sender. This occurs because the server keeps track of every connected client and continuously listens for incoming messages. Once a message is received, the server ensures it reaches all clients in the network, maintaining communication between them.