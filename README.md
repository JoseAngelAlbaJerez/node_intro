

## Qué es Node.js?

Node.js es un entorno de ejecución de JavaScript basado en el motor V8 de Google Chrome. Permite ejecutar código JavaScript en el lado del servidor, lo que facilita la creación de aplicaciones web y de red escalables y de alto rendimiento.

### Repasar el uso de JavaScript necesario para usar Node.js:

#### Lexical Structure

- **Expressions**: Las expresiones en JavaScript son fragmentos de código que producen un valor. Pueden ser simples, como `5 + 3`, o más complejas, como una invocación de función o una asignación de variables.

    ```javascript
    5 + 3;
    ```

- **Data Types**: JavaScript tiene varios tipos de datos, incluyendo números, strings, booleanos, objetos, arrays, funciones, undefined, null y symbols.


    ```javascript
    let number = 10;
    let string = "Hola mundo";
    let boolean = true;
    let object = { key: "value" };
    function func() {}
    let undefinedVar;
    let nullVar = null;
    let symbol = Symbol("unique");
    ```

- **Classes**: En JavaScript, las clases son una forma de definir objetos y su comportamiento utilizando una sintaxis orientada a objetos. Fueron introducidas en ES6 y proporcionan una manera más clara y sencilla de trabajar con herencia y prototipos.

    ```javascript
    class Persona {
      constructor(nombre, edad) {
        this.nombre = nombre;
        this.edad = edad;
      }
      saludar() {
        console.log(`Hola, soy ${this.nombre}`);
      }
    }

    const persona1 = new Persona("Juan", 30);
    persona1.saludar();
    ```

- **Variables**: Las variables se utilizan para almacenar valores en JavaScript. Pueden ser declaradas con las palabras clave `var`, `let`, o `const`, siendo `const` para valores que no cambian y `let` para variables que pueden cambiar de valor.

    ```javascript
    let a = 5;
    const b = 10;
    ```

- **Functions**: Las funciones son bloques de código que pueden ser llamados para realizar una tarea específica. Pueden ser definidas utilizando la palabra clave `function` o mediante funciones flecha (`=>`) en ES6.

    ```javascript
    function sum(a, b) {
      return a + b;
    }

    const multiply = (a, b) => a * b;
    ```

- **this operator**: El operador `this` se refiere al objeto al que pertenece la función que está siendo ejecutada. Su valor depende de cómo se llama a la función y desde dónde se la llama.

    ```javascript
    const obj = {
      prop: "value",
      method() {
        console.log(this.prop);
      }
    };
    obj.method();
    ```

- **Arrow Functions**: Son una forma concisa de definir funciones en JavaScript, introducidas en ES6. Tienen una sintaxis más corta y un comportamiento diferente con respecto al valor de `this`.

    ```javascript
    const add = (a, b) => a + b;
    ```

- **Loops**: Los bucles (`for`, `while`, `do-while`) se utilizan para repetir una tarea hasta que se cumple una condición específica.

    ```javascript
    for (let i = 0; i < 5; i++) {
      console.log(i);
    }

    let i = 0;
    while (i < 5) {
      console.log(i);
      i++;
    }
    ```

- **Scopes**: El ámbito de una variable se refiere a dónde en el código puede ser accedida. JavaScript tiene ámbitos de función y ámbitos de bloque.

    ```javascript
    function outer() {
      let a = 5;
      console.log(a);
      function inner() {
        console.log(a);
      }
      inner();
    }
    outer();
    ```

- **Arrays**: Los arrays son estructuras de datos que permiten almacenar varios elementos bajo un solo nombre. Pueden contener cualquier tipo de datos y su longitud puede cambiar dinámicamente.

    ```javascript
    const array = [1, 2, 3, 4, 5];
    ```

- **Template Literals**: Son una forma de crear cadenas de texto más legibles y flexibles en JavaScript, introducidas en ES6. Permiten la interpolación de variables y expresiones dentro de cadenas de texto utilizando la sintaxis `${}`.

    ```javascript
    const name = "Juan";
    console.log(`Hola, mi nombre es ${name}`);
    ```

- **Strict Mode**: Modo estricto es una forma de escribir código más seguro y eficiente en JavaScript. Se activa con la declaración `"use strict";`. Ayuda a evitar errores comunes y a hacer el código más optimizable para los motores de JavaScript.

    ```javascript
    "use strict";
    ```

- **ECMAScript 2015 (ES6) and beyond**: ES6 es una versión importante de JavaScript que introdujo muchas características nuevas, como clases, funciones flecha, let y const, entre otras. Desde entonces, nuevas versiones de ECMAScript han seguido introduciendo nuevas funcionalidades y mejoras al lenguaje.

    ```javascript
    class Persona {
      constructor(nombre) {
        this.nombre = nombre;
      }
      saludar() {
        console.log(`Hola, soy ${this.nombre}`);
      }
    }
    ```
### Define "Asynchronous Programming" y sus conceptos principales:

#### Asynchronous Programming and Callbacks

Las funciones asíncronas permiten que otras operaciones se ejecuten mientras se espera una tarea específica. Los callbacks son funciones que se pasan como argumentos a otras funciones y se llaman cuando se completa una tarea asíncrona. Son una forma común de manejar la asincronía en JavaScript.

```javascript
function doAsyncTask(callback) {
  setTimeout(function() {
    console.log("Tarea asíncrona completada");
    callback();
  }, 2000);
}

function callbackFunction() {
  console.log("Callback ejecutado");
}

console.log("Iniciando tarea asíncrona...");
doAsyncTask(callbackFunction);
console.log("Tarea asíncrona en progreso...");

```

#### Timers

En JavaScript, puedes usar setTimeout() y setInterval() para programar tareas para que se ejecuten en el futuro. Esto es útil para implementar retrasos o ejecutar tareas de forma periódica.

> setTimeout()
La función setTimeout() se utiliza para ejecutar una función después de un cierto período de tiempo especificado, expresado en milisegundos.

```javascript
setTimeout(function() {
  console.log("¡Hola, después de 1 segundo!");
}, 1000);

```
> setInterval()
La función setInterval() se utiliza para ejecutar una función repetidamente cada cierto período de tiempo especificado, expresado en milisegundos.

```javascript
let contador = 0;
setInterval(function() {
  contador++;
  console.log("Contador:", contador);
}, 1000);

```

#### Promises

Las promesas son objetos que representan la eventual finalización (o falla) de una operación asíncrona, y su resultado. Permiten un manejo más limpio y encadenado de operaciones asíncronas en comparación con los callbacks.

```javascript
// Promises
const promise = new Promise((resolve, reject) => {
  setTimeout(() => {
    resolve("¡Hola, después de 1 segundo!");
  }, 1000);
});
promise.then((value) => {
  console.log(value);
});
```

#### Async and Await

Introducido en ES2017, async y await son palabras clave que simplifican el manejo de operaciones asíncronas. Permiten escribir código asíncrono de una manera más similar a código síncrono, lo que lo hace más fácil de leer y entender.

```javascript
// Async/Await
async function greet() {
  const message = await promise;
  console.log(message);
}
greet();
```

#### Closures

 Un cierre (closure) es la combinación de una función y el ámbito en el que se declaró la función. Los cierres permiten acceder a variables externas desde una función interna, incluso después de que la función externa haya terminado de ejecutarse. Son útiles en el manejo de callbacks y promesas.

```javascript
 function outer() {
  let outerVar = "outer";
  function inner() {
    console.log(outerVar);
  }
  return inner;
}

const innerFunc = outer();
innerFunc();
```

#### The Event Loop

El bucle de eventos es el mecanismo que permite que JavaScript maneje las operaciones asíncronas de manera eficiente. Permite que el programa siga ejecutándose mientras espera que se completen las operaciones asíncronas, evitando bloqueos y manteniendo la capacidad de respuesta del programa.
```javascript
console.log("Inicio");
setTimeout(() => {
  console.log("Dentro del setTimeout");
}, 0);
console.log("Fin");
```
