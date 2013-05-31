---
title: Movimientos en Terminal.app
excerpt: Cómo mejorar la experiencia de usuario con Terminal.app.
tags: mac, sysadmin
date: 2006-07-11 14:21
slug: movimientos-en-terminal-app
author: Francisco Pinto
layout: post
location: Málaga, Spain
image:
color:
---

Cuando uno está tan acostumbrado a usar un terminal y se encuentra que Terminal.app no es demasiado sofisticado, se pregunta cómo es posible que hayan descuidado tanto este tema en un sistema operativo tipo *NIX. El movimiento entre palabras o ir al principio/final de la línea de comandos, al menos en mi iBook, es tedioso.

La aplicación Terminal.app tiene un cuadro de preferencias al que se accede con **Terminal -> Ajustes de ventana**. Dentro del apartado **Teclado** viene el mapeo de teclado que utiliza Terminal. En todas las aplicaciones de Mac OS X, la combinación Opción+Izquierda (⌥←) lleva al principio de la palabra anterior. Para ello, sólo hay que Añadir una combinación como la siguiente:

**Tecla: cursor a la izquierda**

	- Modificador: opción
	- Acción: enviar sentencia a la shell: \033b

La sentencia *\033b* se consigue pulsando una vez **escape** y la letra **b**. Si se quiere mapear también la misma opción pero para avanzar a la palabra siguiente, habrá que sustituir la combinación por la de la tecla derecha y la sentencia pulsando **escape** y la letra **f**:

**Tecla: cursor a la derecha**

	- Modificador: opción
	- Acción: enviar sentencia a la shell: \033f

Tener la posibilidad de moverse de principio a fin de la línea de comandos es también muy útil a la hora de corregir errores o aprovechar líneas introducidas anteriormente. En este caso, la combinación estándar de las aplicaciones de Mac OS X es Control+Izquierda (⌃←) para ir al inicio de la línea:

**Tecla: cursor a la izquierda**

	- Modificador: control
	- Acción: enviar sentencia a la shell: \001

La sentencia *\001* se consigue pulsando Control+A (⌃A). Si se quiere mapear también la misma opción pero para ir al final de la línea, habrá que sustituir la combinación por la de la tecla derecha y la sentencia por Control+E  (⌃E):

**Tecla: cursor a la derecha**

	- Modificador: control
	- Acción: enviar sentencia a la shell: \005

Otra combinación de teclado que no se corresponde con la del resto del sistema es la de suprimir hacia delante, que se consigue con **Fn+Borrar**, reproduciendo en su lugar una virigulilla (~). En este caso, la combinación de teclado sí está ya creada en el listado, en la línea **Suprimir** (borrar hacia delante). Tan sólo hay que **Editar** dicha línea y cambiar la sentencia de *\033[3~* a *\004*. La sentencia \004 se consigue pulsando Control+Opción+D (⌃⌥D).

Para guardar los cambios se debe pulsar sobre Usar estos ajustes por omisión. Además, si se pretende realizar una búsqueda en el historial de líneas introducidas, basta con pulsar **Control+R** e introducir alguna cadena de caracteres para que la encuentre.

Con esto y cambiando el esquema de color a [Solarized](http://ethanschoonover.com/solarized) ya estamos más cerca de tener algo parecido a una terminal de verdad.
