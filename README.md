# ✨ ES6: Maps

### 👉 Ver [todas las notas](https://github.com/undefinedschool/notes)

## _tl;dr_

- Es un tipo de estructura de datos
- Nos permite almacenar la información en pares _clave-valor_
- **Las claves son únicas**, no se repiten => no tenemos pares _clave-valor_ que se repitan

## ¿Para qué sirven? ¿Por qué usarlos?

![](http://www.radiozero.cl/static/2016/10/britney.jpg)

- Usamos _Map_ principalmente para búsquedas rápidas (de valores asociados)

## Ventajas de usar ES6 Map sobre Object

- Si usamos objetos como _diccionarios_, estamos limitados por los tipos de valores que podemos tener como claves: sólo podemos usar valores que sean válidos como nombres de propiedades (_number_ o _string_)
- **En un _Map_ puedo usar cualquier tipo de valor como clave** (incluyendo objetos y funciones)
- En los objetos, el orden de las propiedades/claves no está garantizado (depende de la implementación del engine). Sólo porque agreguemos pares _clave-valor_ en cierto orden, no implica que van a permanecer en ese orden cuando las iteremos
- **En un _Map_, el orden en el que agregamos las claves se mantiene**
- Podemos obtener el tamaño de un _Map_ fácilmente, usando la propiedad `size`
- Un _Map_ puede ser iterado directamente
- **_Map_ nos provee de ciertos métodos para, entre otras cosas, poder iterar las claves** (ej: `forEach`)
- Pueden ver otras diferencias con más detalle [acá](https://medium.com/front-end-weekly/es6-map-vs-object-what-and-when-b80621932373)
- Un _Map_ puede tener ventajas de _performance_ en casos donde agreguemos/saquemos pares _clave-valor_ con frecuencia

## Uso

### Crear un nuevo `Map`

```js
// crear un nuevo map/diccionario con los pares {"a" => 1, "b" => 2}
const m = new Map();

m.set('a', 1);
m.set('b', 2);
```

### Obtener el tamaño

```js
// obtener el tamaño (cantidad de pares mapeados) del diccionario
m.size;
```

### Borrar/resetear todas las entradas del `Map`

```js
m.clear();
```

### Eliminar un par

```js
m.delete('a'); // true
m.delete('c'); // false (la clave 'c' no existe en el map)
```

### Obtener el valor mapeado a una clave

```js
m.get('a'); // 1
m.get('z'); // undefined (la clave 'z' no existe en el map)
```

### Preguntar si una clave existe

```js
m.has('a'); // true
m.has('z'); // false
```

### Iterar las claves

```js
m.forEach((key, value) => console.log(`key: ${key} => value: ${value}`));
```

```js
// también podemos usar for.. of

for(const [key, value] of m) {
  console.log(`${key} = ${value}`);
}
```

### Construir un `Map` a partir de un `Array`

```js
// para que funcione, cada elemento del array debe ser un par
const arr = [['a', 1], ['b', 2]];
const m = new Map(arr);
```

Etc... [Ver más en MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map)
