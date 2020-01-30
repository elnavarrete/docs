---
layout: post
author: erik
title: Cómo extraer texto de un documento por consola
categories: Programación, Linux, Consola
---


Para obtener el número de línea de una palabra que se quiera buscar
```
cat archivo | grep 'textoBuscado' -n


Para obtener un tramo de texto del documento original
```
sed -n '#_inicial, #_final p' archivo > salida


Otra forma es utilizando ***awk***
```
awk 'NR>=#_inicial && NR<=#_final' archivo > salida




