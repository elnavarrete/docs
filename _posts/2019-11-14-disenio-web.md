---
layout: post
author: erik
title: Notas para una buena maquetación WEB
categories: Programación, Web
---

Los valores predefinidos que se debería utilizar al inicio de un css serán:

+ Asignar a todo el documento un box-sizing
```css
* {
  box-sizing: border-box;
}
```

+ Para centrar elementos:
    + Horizontal
        + Para elementos inline -> **text-align: center**
        + Para centrar bloque -> **margin: X auto;** (el elemento debe tener una anchura definida)
    + Vertical
        + Para elementos inline es preferible con FLEX
	+ Para elementos en bloque ->
	  ```
		position: absolute;
		top: 50%;
		transform: translateY(-50%);
	  ```

+ Propiedad **position**:
    + **fixed**: para mantener un elemento en un posición fija
    ```css
        footer {
	 bottom: 0px;
	 position: fixed;	// mantendrá el footer al final de la vista pantalla
	}
    ```
    + **sticky**: cuando llega a su posición se aplica sus propiedades
    ```css
	position: sticky;
	top: 0px; // se aplica cuando llega al elemento
	z-index: 10;
    ```
