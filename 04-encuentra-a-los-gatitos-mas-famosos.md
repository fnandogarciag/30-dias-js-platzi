# Encuentra a los gatitos más famosos

En este desafío, debes encontrar al gatito más famoso con base en su número de seguidores.

Recibirás un array de objetos que incluirán las siguientes propiedades:

- `name`: nombre del gatito.
- `followers`: un array de números, donde cada uno representa los seguidores de cada red social.

Tu tarea es devolver un array con los nombres de los gatos que tienen solo el mayor número de seguidores. Si hay dos o más gatos con el mismo número máximo de seguidores, deberás incluirlos en el array de resultado, manteniendo el orden en el que aparecen en el array de entrada.

Tendrás inputs y outputs como los siguientes 👇

Ejemplo 1:

```javascript
Input: findFamousCats([
  {
    name: "Luna",
    followers: [500, 200, 300],
  },
  {
    name: "Michi",
    followers: [100, 300],
  },
]);

Output: ["Luna"];
```

Ejemplo 2:

```javascript
Input: findFamousCats([
  {
    name: "Mimi",
    followers: [320, 120, 70],
  },
  {
    name: "Milo",
    followers: [400, 300, 100, 200],
  },
  {
    name: "Gizmo",
    followers: [250, 750],
  },
]);

Output: ["Milo", "Gizmo"];
```

# Solución

```javascript
export function findFamousCats(cats) {
  let maxFollowers = 0;
  let famousCats = [];
  cats.forEach((cat) => {
    const followers = cat.followers.reduce((sum, num) => sum + num, 0);
    if (followers > maxFollowers) {
      maxFollowers = followers;
      famousCats = [];
    }
    if (followers >= maxFollowers) famousCats.push(cat.name);
  });
  return famousCats;
}
```
