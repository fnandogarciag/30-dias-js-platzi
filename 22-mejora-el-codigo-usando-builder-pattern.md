# Mejora el código usando builder pattern

En este desafío, te proponemos utilizar el patrón builder para construir un objeto "auto".

Actualmente, la construcción de un auto en el código es confusa y difícil de leer.

```javascript
const car = new CarBuilder(2021, "Model X", "Tesla", "Red", 5000, false);
```

Tu tarea será implementar el patrón builder para lograr una construcción más clara y legible.

Ejemplo:

```javascript
Input:
const car = new CarBuilder()
  .setYear(2021)
  .setModel("Model X")
  .setBrand("Tesla")
  .setColor("Red")
  .setPrice(50000)
  .setIsAvailable(false)
  .build()

Output: {
  year: 2021,
  model: "Model x",
  brand: "Tesla",
  color: "Red",
  price: 50000,
  isAvailable": false
}
```

# Solución

```javascript
export class CarBuilder {
  year = 0;
  model = "";
  brand = "";
  color = "";
  price = 0;
  isAvailable = false;
  setYear(year) {
    this.year = year;
    return this;
  }
  setModel(model) {
    this.model = model;
    return this;
  }
  setBrand(brand) {
    this.brand = brand;
    return this;
  }
  setColor(color) {
    this.color = color;
    return this;
  }
  setPrice(price) {
    this.price = price;
    return this;
  }
  setIsAvailable(isAvailable) {
    this.isAvailable = isAvailable;
    return this;
  }
  build() {
    return {
      year: this.year,
      model: this.model,
      brand: this.brand,
      color: this.color,
      price: this.price,
      isAvailable: this.isAvailable,
    };
  }
}
```
