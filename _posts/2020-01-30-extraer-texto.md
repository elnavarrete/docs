---
layout: post
author: erik
title: Cómo extraer texto de un documento por consola
categories: Programación, Linux, Consola
---


<<<<<<< HEAD
## Para obtener el número de línea de una palabra que se quiera buscar
```
cat archivo | grep 'textoBuscado' -n
```

## Para obtener un tramo de texto del documento original
```
sed -n '#_inicial, #_final p' archivo > salida
```

## Otra forma es utilizando **awk**

```
awk 'NR>=#_inicial && NR<=#_final' archivo > salida
``
=======
Para obtener el número de línea de una palabra que se quiera buscar
```
cat archivo | grep 'textoBuscado' -n


Para obtener un tramo de texto del documento original
```
sed -n '#_inicial, #_final p' archivo > salida


Otra forma es utilizando ***awk***
```
awk 'NR>=#_inicial && NR<=#_final' archivo > salida

>>>>>>> 02719499cf4a57125236b80f6e66bff34fdd4be8



