# Sockets

In the client, you can use&#x20;

```
const socket = useSocket(namespace);

socket.on('event', () => null);
socket.emit('event', 'toServer');
```



in the server, you can create a route handler in the api directory

```
export default function Route (instance) {
    instance.socket('namespace', {}, handler);
    
    async function handler(socket) {
        socket.on('event', () => null);
    }
}
```



