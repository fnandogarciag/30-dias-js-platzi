# Implementa singleton en un chat

En este desafío, tendrás que aplicar el patrón de diseño Singleton en un Chat.

Tu objetivo es crear la lógica en la clase Chat para garantizar que exista una única instancia de la clase en todo momento.

Además, la clase Chat deberá contener los siguientes métodos:

- `sendMessage(message)`: Este método debe permitir enviar un mensaje a todos los usuarios en la lista, accediendo al método `receiveMessage` de cada instancia de usuario.

- `addUser(user)`: Este método debe agregar un nuevo usuario a la lista, verificando que sea una instancia de la clase `User` (el código de esta clase la puedes ver dentro del sistema de archivos del playground).

- `removeUser(name)`: Este método te permitirá eliminar un usuario de la lista por su nombre.

Ejemplo 1:

```javascript
Input:
const chat1 = new Chat();
const chat2 = new Chat();

console.log(chat1 === chat2)

Output: true
```

Ejemplo 2:

```javascript
Input:
const chat = new Chat();
const user1 = new User("Pepito");
const user2 = new User("Juanito");
chat.addUser(user1);
chat.addUser(user2);

chat.sendMessage("Nunca pares de aprender!");

console.log(user1.messages)
console.log(user2.messages)

Output:
["Nunca pares de aprender!"]
["Nunca pares de aprender!"]
```

# Solución

```javascript
import { User } from "./user";

export class Chat {
  users = [];
  constructor() {
    if (!Chat.instance) {
      Chat.instance = Object.freeze(this);
    }
    return Chat.instance;
  }
  sendMessage(message) {
    this.users.forEach((user) => user.receiveMessage(message));
  }
  addUser(user) {
    if (user instanceof User) this.users.push(user);
  }
  removeUser(name) {
    const index = this.users.findIndex((user) => user.name === name);
    if (index !== -1) this.users.splice(index, 1);
  }
}
```
