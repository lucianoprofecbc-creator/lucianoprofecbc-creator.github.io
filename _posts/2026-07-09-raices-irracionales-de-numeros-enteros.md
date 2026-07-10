---
layout: single
title: "Raíces Irracionales de Números Enteros"
categories:
  - Matemáticas
tags:
  - Pre-Calculo
  - Enseñanza de la Matemática
  - Álgebra
  - Números
  - Irracionalidad
  - Teoría de Números
---

## Demostración Clásica 

Todos hemos visto (y probablemente enseñado) en los cursos de pre-cálculo, una demostración de la irracionalidad de $\sqrt{2}$. Yo recuerdo verla en los viejos apuntes del CBC, de Guillermo Hansen, y en los de J. C. Pedraza también. La idea básica es muy sencilla y sólo usa el Teorema Fundamental de la Aritmética (T.F.A) y un argumento por el absurdo. 

Desde el punto de vista puramente algebráico (más bien aritmético) el hecho de que el radicando sea 2 y la raíz sea cuadrada no juegan ningún rol demasiado especial, como vamos a ver. 

Desde el punto de vista pedagógico, sin embargo, $\sqrt{2}$ es particularmente bueno porque se puede mostrar antes que nada que $\sqrt{2}$ efectivamente *existe*. Esta demostración de existencia es una construcción elemental con regla y compás que permite ubicar un segmento de longitud $\sqrt{2}$ en la recta a partir de una utilización inteligente del Teorema de Pitágoras. 

<p align="center">
  <img src="{{ '/assets/images/posts/raices/sqrt2.svg' | relative_url }}" alt="Construcción geométrica de raíz de 2">
</p>

Una vez convencidos de que $\sqrt{2}$ es efectivamente un número *real* procedemos a probar que no es racional con un argumento por el absurdo. Intentar replicar la construcción geométrica para, por ejemplo, $\sqrt[3]{2}$ nos lleva a la famosa imposibilidad de *doblar el cubo* y en general, para la raíz de orden arbitrario, a las restricciones que impone la teoría de Galois a las extensiones de cuerpos.   

Pero la demostración de la irracionalidad no tiene ninguna dificultad, aun cuando no *veamos* el número tan fácilmente en la recta. Generalicemos la idea conocida por todos al caso de una raíz $\ell -esima$ de un natural $m$. 

<div class="theorem">

<strong>Teorema (Irracionalidad de $\sqrt[\ell]{n}$).</strong>

Sean $n,\ell\in\mathbf{N}$. Entonces o bien existe $m\in\mathbf{N}$ tal que $n=m^{\ell}$ o bien $\sqrt[\ell]{n}\notin\mathbf{Q}$

</div>

<div class="proof" markdown="1">

<strong>Demostración.</strong>

Supongamos que $\sqrt[\ell]{n}\in\mathbf{Q}$, entonces $\exists a,b\in\mathbf{N}$ tales que $\sqrt[\ell]{n}=\frac{a}{b}$. El punto clave es asumir que $a$ y $b$ son coprimos, es decir que en el cociente, hemos *simplificado* todos los factores primos comunes (esto es inmediato usando el T.F.A.). 

Hecho ese supuesto, volvemos a la igualdad, ahora en la forma: $b^{\ell}n=a^{\ell}$. Esta igualdad implica que $b^{\ell}$ divide a $a^{\ell}$ y al mismo tiempo son coprimos (porque $a$ y $b$ lo son), por lo que $b^{\ell}$ tiene que ser 1 y entonces $n=a^{\ell}$ o llamando $a=m$ tenemos $n=m^{\ell}$.  

</div>

Nótese que ni siquiera fue necesario un argumento por el absurdo para el caso general. Ahora es sencillo mostrar la irracionalidad de ciertos casos, por ejemplo de las raíces de números primos: $\sqrt[\ell]{p}\in\mathbf{Q}\iff p=m^{\ell}$ con $m\in\mathbf{N}$, pero si $p$ es primo esto sólo puede pasar si $p=m$ y $\ell=1$, así que $\sqrt[\ell]{p}\notin\mathbf{Q}$ si $\ell\geq2$. 

## Demostración Artesanal 

Existe una demostración alternativa de la irracionalidad de $\sqrt{2}$ que vi una vez en Twitter y uso en mis cursos de pre-cálculo, generalizándola a $\sqrt{n}$. 

Esta demostración tiene la ventaja de usar solamente la función *parte entera inferior* (*floor*) y el buen ordenamiento de los naturales. Sirve, más que nada, como una forma de mostrar la utilidad de la función *floor* en el comienzo de cursos elementales. 

El principal problema de dicha demostración es que si bien resulta inmediato para $\sqrt{n}$, no se extiende de manera trivial a $\sqrt[\ell]{n}$ como la demostración que usa el T.F.A. El motivo es que el paso clave de la demo ([📄 PDF completo en Zenodo](https://doi.org/10.5281/zenodo.21249890)) usa el hecho de que $\sqrt{n}*\sqrt{n}=n\in\mathbf{N}$, y eso no lo podemos replicar en el caso general. 

## Comentarios Finales

Una sensación que deja este sencillo análisis es que *casi todas las raíces son irracionales* y a uno le surge la natural curiosidad del *por qué* 🤔. 

La respuesta seguramente es obvia para quien tiene un conocimiento cabal de la teoría de cuerpos y de la teoría de Galois y algún día me gustaría poder decir que yo soy esa persona. 

Por el momento digamos que es una cuestión tan interesante que se puede plantear al comienzo de un curso de pre-cálculo (incluso pre-universitario) y conectar con temas matemáticos profundos. 

Bueno, hasta que los moleste luego. 

L.A.P. 