# Encuentra el mayor palíndromo

En este desafío, debes crear una función que encuentre el palíndromo más largo en una lista de palabras.

Recibirás un único parámetro: un array de palabras. Si no hay ningún palíndromo en la lista, la función debe devolver `null`. Si hay más de un palíndromo con la misma longitud máxima, debes devolver el primer palíndromo encontrado en la lista.

> Un palíndromo es una palabra que se puede leer de la misma manera tanto hacia adelante como hacia atrás.

Ejemplo 1:

```javascript
Input: findLargestPalindrome(["racecar", "level", "world", "hello"]);

Output: "racecar";
```

Ejemplo 2:

```javascript
Input: findLargestPalindrome(["Platzi", "javascript", "html", "css"]);

Output: null;
```

# Solución

```javascript
export function findLargestPalindrome(words) {
  let largest = "";
  words.forEach((word) => {
    const reverse = word.split("").reverse().join("");
    if (reverse === word) {
      if (word.length > largest.length) largest = word;
    }
  });
  return largest === "" ? null : largest;
}
```
