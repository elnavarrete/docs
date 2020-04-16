---
layout: post
author: erik
title: Cómo extraer texto de un documento por consola
categories: Programación, Linux, Consola
---

## Para obtener el número de línea de una palabra que se quiera buscar
```sh
cat archivo | grep 'textoBuscado' -n
```

## Para obtener un tramo de texto del documento original
```sh
sed -n '#_inicial, #_final p' archivo > salida
```

## Otra forma es utilizando **awk**

```sh
awk 'NR>=#_inicial && NR<=#_final' archivo > salida
```

## Un pequeño buscador dentro de logs
Recibe dos paŕametros: dato a buscar y el nombre del archivo en el que se quiere buscar.

Regresará las primeras 1000 líneas después de encontrar el elemento buscado.
~~~sh
#! /bin/bash

data=$1
file=$2

if [ -s $file ] && [ -f $file ]  # comprueba que no vacío y que sea un archivo
	then
		read -p"Cuántas líneas?: " nLinea
		if [ -z $nLinea ]
		then
			nLinea=1000
		fi

		nInicio=0

		IFS=$':'	#para establecer el separador de lineas
		for line in `cat $file | grep -m1 -n $data -o`
		do
			nInicio=$line
			break  #sale con el número de línea
		done
		nLinea=$(expr $nLinea + $nInicio)
		output=$(sed -n "$nInicio,$nLinea p" $file)
		echo $output > $file.out
		echo "END"
	else
		echo "ERROR: comprobar archivo"
fi
~~~

