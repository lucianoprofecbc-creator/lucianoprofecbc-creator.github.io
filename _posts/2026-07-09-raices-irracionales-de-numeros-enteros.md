---
layout: single
title: "Raíces Irracionales de Números Enteros"
categories:
  - Matemáticas
tags:
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

Una vez convencidos de que $\sqrt{2}$ es efectivamente un número *real* procedemos a probar que no es racional con un argumento por el absurdo. Intentar replicar esta idea para, por ejemplo, $\sqrt[3]{2}$ nos lleva a la famosa imposibilidad de *doblar el cubo* y en general, para la raíz de orden arbitrario, a las restricciones que impone la teoría de Galois a las de extensiones de cuerpos.   

Pero la demostración de la irracionalidad no tiene ninguna dificultad, aun cuando no *veamos* el número tan fácilmente en la recta. Generalicemos la idea conocida por todos al caso de una raíz $\ell -esima$ de un natural $m$. 

<div class="theorem">

<strong>Teorema (Irracionalidad de $\sqrt[\ell]{n}$).</strong>

Sean $n,\ell\in\mathbf{N}$. Entonces o bien existe $m\in\mathbf{N}$ tal que $n=m^{\ell}$ o bien $\sqrt[\ell]{n}\notin\mathbf{Q}$

</div>

<div class="proof" markdown="1">

<strong>Demostración.</strong>

Supongamos que $\sqrt[\ell]{n}\in\mathbf{Q}$, entonces $\exists a,b\in\mathbf{N}$ tales que $\sqrt[\ell]{n}=\frac{a}{b}$. El punto clave es asumir que $a$ y $b$ son coprimos, es decir que en el cociente, hemos *simplificado* todos los factores primos comunes (esto es inmediato usando el T.F.A.). Hecho ese supuesto, volvemos a la igualdad, ahora en la forma $b^{\ell}n=a^{\ell}$. 



</div>