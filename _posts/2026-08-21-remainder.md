---
layout: single
title: " Yo sólo quise aproximar ln(1/3) 🤷: el Resto de Schlömilch"
categories:
  - Matemáticas
tags:
  - Enseñanza de la Matemática
  - Análisis Matemático
  - Polinomio de Taylor
  - Aproximación
  - Cálculo Elemental
  - Bibliografía Matemática
---

# No me salió 🤔

Cierta tarde hace unos años estaba renovando mis ejemplos de Taylor para una clase y se me ocurrió uno bastante poco original aunque inofensivo: 

<div class="theorem">

<strong>Ejercicio: Aproximar $\ln(1/2)$:</strong><br>

Aproximar $\ln(1/2)$ mediante un polinomio de Taylor $P_{n}(x)$ para la función $f(x)=\ln(1-x)$ con centro $x_{0}=0$, encontrando $n\in\mathbf{N}_{0}$ tal que el error cometido sea menor que $10^{-3}$
</div>

La parte interesante obviamente es la de acotar el error y encontrar $n$, algo bastante estándar en estos ejercicios. **Usando la fórmula de Lagrange para el resto** tenemos: 

$$E_{n}(1/2)=\vert R_{n}(1/2)\vert=\left\vert\frac{f^{(n+1)}(c)}{(n+1)!}\left(\frac{1}{2}\right)^{n+1}\right\vert$$

donde $c\in(0,1/2)$. 

Las derivadas de $f(x)=\ln(1-x)$ son sencillas: 

$$f'(x)=-\frac{1}{1-x};\hspace{0.5cm}f''(x)=-\frac{1}{(1-x)^{2}};\hspace{0.5cm}...f^{(k)}(x)=-\frac{(k-1)!}{(1-x)^{k}};\hspace{0.5cm}$$

Así que todo va bien y nos queda: 

$$E_{n}(1/2)=\left\vert-\frac{n!}{(1-c)^{n+1}(n+1)!}\left(\frac{1}{2}\right)^{n+1}\right\vert=\frac{1}{(1-c)^{n+1}}\frac{1}{(n+1)2^{n+1}}$$

y ahora como: 

$$0<c<1/2\implies1-c>1/2\implies(1-c)^{-(n+1)}<2^{n+1}$$ 

y entonces $E_{n}(1/2)<1/(n+1)$ y listo, sale el $n$ que sea necesario para $10^{-3}$ o la precisión que uno quiera.  


Estaba contento con mi ejemplo, pero...algo me daba qué pensar: quedó demasiado *limpio* cuando se simplificó el $2^{n+1}$, ¿qué pasa si por ejemplo me muevo del $x=1/2$ un poco, digamos a $x=2/3$ para aproximar $\ln(1-2/3)=\ln(1/3)$? 

$$E_{n}(2/3)=\left\vert-\frac{n!}{(1-c)^{n+1}(n+1)!}\left(\frac{2}{3}\right)^{n+1}\right\vert=\frac{1}{(1-c)^{n+1}}\frac{2^{n+1}}{(n+1)3^{n+1}}$$

pero ahora: 

$$0<c<2/3\implies1-c>1/3\implies(1-c)^{-(n+1)}<3^{n+1}$$ 

y al acotar: 

$$E_{n}(2/3)=\frac{1}{(1-c)^{n+1}}\frac{2^{n+1}}{(n+1)3^{n+1}}<3^{n+1}\frac{2^{n+1}}{(n+1)3^{n+1}}=\frac{2^{n+1}}{n+1}$$

y esta expresión no tiende a 0 con $n$. La cota para $(1-c)^{-(n+1)}$ no se puede mejorar, así que tal como está, el ejercicio no me salió. 🤔

# Pensemos un poco (y llamemos a Chiappe)

Lo primero que a uno se le ocurre es "*tal vez no converja a 0 el error*" pero es fácil descartar esa posibilidad. La función $f(x)=\ln(1-x)$ se puede desarrollar en serie de potencias centrada en $x_{0}=0$ sin ninguna dificultad porque es la integral de $f'(x)=\dfrac{-1}{1-x}$ que tiene un desarrollo válido en $(-1,1)$ por la serie geométrica: 

$$\frac{-1}{1-x}=-\sum_{n=0}^{+\infty}x^{n}\implies\ln(1-x)=-\sum_{n=0}^{+\infty}\frac{x^{n+1}}{n+1}$$

y el radio de convergencia se mantiene, así que obviamente $R_{n}(x)\xrightarrow[n\rightarrow+\infty]{}0$ para cada $x$ en $(-1,1)$.

El problema tiene que ser entonces la propia fórmula de Lagrange para el resto que no permite acotar de manera más precisa con la información del $c\in(0,2/3)$. 

En el momento en que me dí cuenta de eso hice lo que haría cualquiera en esa situación, preguntarle a [Germán Chiappe](https://www.researchgate.net/profile/German-Chiappe), quien me recordó algo que alguna vez había leido pero por falta de uso ya recordaba muy vagamente: "*las otras formas del resto de Taylor a veces pueden ser útiles, fijate con la forma de Cauchy o la forma integral*". Como de manera habitual, Chiappe tenía razón, de hecho con ambas formas sale de manera muy similar. 

Mostrémoslo con la forma de Cauchy, la acotación con la forma integral es prácticamente la misma. La fórmula para el resto según Cauchy, que saqué del tomo 1 del libro de Courant & John es: 

$$R_{n}=\frac{h^{n+1}}{n!}(1-\theta)^{n}f^{(n+1)}(x_{0}+\theta h)$$

donde $h=x-x_{0}$ y $\theta$ es un número desconocido entre 0 y 1. Nótese una omisión que he hecho, como hacen Courant & John, que es la dependencia de $R_{n}$ con $x$, algo que es puramente notacional (porque usamos $h$) pero deliberado por algo más práctico que veremos abajo. 

Volviendo a nuestro caso de interés, como tenemos $x_{0}=0$, $x=2/3$ entonces $h=2/3$ y además vimos que $f^{k}(x)=-\dfrac{(k-1)!}{(1-x)^{k}}$, resulta: 

$$|R_{n}|=\left\vert\frac{(2/3)^{n+1}}{n!}(1-\theta)^{n}\frac{-n!}{(1-(2/3)\theta)^{n+1}}\right\vert=$$

$$=\left(\frac{2}{3}\right)^{n+1}\left(\frac{1-\theta}{1-(2/3)\theta}\right)^{n}\frac{1}{1-(2/3)\theta}$$

Como $\theta\in(0,1)$ el factor $\dfrac{1}{1-(2/3)\theta}$ está en $(0,3)$. Por otro lado el factor $\dfrac{1-\theta}{1-(2/3)\theta}$ es también fácil de acotar porque es una función continua en [0,1] y es estrictamente decreciente (es una homográfica elemental), tomando su valor máximo de 1 cuando $\theta=0$. 

Con todo esto queda: $\vert R_{n}\vert<3\left(\frac{2}{3}\right)^{n+1}$ *et voilà* como dirían Cauchy y Chiappe que son franceses. 

# Y Ahora Pasemos a Molestar

Gran triunfo de la forma de Cauchy y todos estamos felices, pero me quedé pensando 🤔🤔🤔🤔🤔 ¿dónde se pierde la información al usar la forma de Lagrange?

Estuve mirando el Courant & John (el Cap. 5 del Tomo 1) y no arribé a ninguna conclusión muy evidente. Como ya se me había hecho tarde para preguntarle de nuevo a [Germán Chiappe](https://www.researchgate.net/profile/German-Chiappe) le pregunté a Gemini y en principio me sanateó. 

Me di cuenta de que me tiró fruta porque me dijo algo que yo ya había pensado y descartado mientras leía el Courant, y era que la forma integral usaba más información de la función al *promediar* con el TVM integral. Pero eso no era cierto por un lado porque el TVM integral justamente dice lo contrario y es que esa info se concentra en el desconocido $c$ al igual que en el TVM diferencial. Por otro, sencillamente, porque la forma de Cauchy no pasa por la integral y de todas formas hizo lo que Lagrange no pudo.  

Así que le dije eso a Gemini y se ve que se ofendió porque hizo algo que yo hago siempre que alguien me pregunta algo: me mandó a leer el Rey Pastor. Concretamente me dijo que busque la *forma de Schlömilch*, algo que efectivamente estaba en el libro, y está bueno pero no tan bueno como lo que sigue. 

Así como al pasar, me tiró también una referencia **BUENÍSIMA** que yo **NO** conocía (rarísimo, yo conozco todo 🤌 😂😂😂): *buscá el libro de Fikhtengol'ts, The Fundamentals of Mathematical Analysis (vol.1)*. 

Lo fui a buscar y ya un primer vistazo me dio una buena sensación: está traducido del ruso por Ian Sneddon (es de 1965 el libro). Que un tipo que escribe libros buenos, concisos y elegantes como Sneddon se haya tomado el trabajo de traducir dos tomos de más de 500 páginas de un libro de análisis bastante introductorio, *por algo debe ser*, me dije.

Dicho y hecho, el libro de Fikhtengol'ts está buenísimo: extremadamente claro, muy elegante pero sin galerazos, y lleno de pequeñas observaciones inteligentes y profundas, como este blog (😂) pero en serio. Me gustaría hablar largo y tendido del mismo, pero no quiero spoilear, vayan, lean y disfruten. 

# La Forma General de Schlömilch para el Resto

Sí voy a spoilear lo que tiene que ver con el resto de aproximar por Taylor porque al fin y al cabo a eso vinimos. 

El *truco* para encontrar todas las formas juntas del resto que usa Fikhtengol'ts es básicamente el mismo que está en el Courant & John, pero lo hace con una elegante parsimonia muy propia de todo su tratado. 

Recordemos la definición de resto de aproximar $f(x)$ por $P_{n}(x)$:

$$R_{n}(x)=f(x)-P_{n}(x)=$$

$$=f(x)-f(x_{0})-f'(x_{0})(x-x_{0})-\frac{f''(x_{0})}{2}(x-x_{0})^{2}-\cdots-\frac{f^{n}(x_{0})}{n!}(x-x_{0})^{n}$$

En esta fórmula, $x_{0}$ está fijo y $x$ varía en algún entorno del mismo. Ahora bien, cuando estamos tratando con el resto de Taylor, el supuesto típico para que nos salga una fórmula compacta y elegante como la de Lagrange, la de Cauchy, etc., es que las derivadas de $f(x)$ hasta orden $n+1$ existen y son continuas en algún $[x_{0}-\delta,x_{0}+\delta]$. 

Pensado así, podemos fijar un $x$ en dicho entorno y *variar $x_{0}$*, o sea que el centro sea $t$ con $t\in[x_{0}-\delta,x_{0}+\delta]$, computando un nuevo $P_{n}$ para cada $x_{0}$, es decir pensamos en la función: 

$$\phi(t)=f(x)-f(t)-f'(t)(x-t)-\frac{f''(t)}{2}(x-t)^{2}-\cdots-\frac{f^{n}(t)}{n!}(x-t)^{n}$$

de manera que $\phi(x)=0$ y $\phi(x_{0})=R_{n}(x)$.

Atentos que acá viene la primera magia (Courant también la usa, bien ahí el gringo). Observemos que, al derivar en $t$: 

$$\left(\frac{f^{k}(t)(x-t)^{k}}{k!}\right)'=\frac{f^{k+1}(t)(x-t)^{k}}{k!}-\frac{f^{k}(t)(x-t)^{k-1}}{(k-1)!}$$

pero también: 

$$\left(\frac{f^{k+1}(t)(x-t)^{k+1}}{(k+1)!}\right)'=\frac{f^{k+2}(t)(x-t)^{k}}{(k+1)!}-\frac{f^{k+1}(t)(x-t)^{k}}{k!}$$

y entonces cuando calculamos $\phi'(t)$ se nos anulan todos los términos al sumar, excepto el último: 

$$\phi'(t)=-\frac{f^{n+1}(t)(x-t)^{n}}{n!}$$ 

Y en este punto Courant & John utilizan este resultado para las modestas fórmulas de Cauchy y Lagrange pero Fikhtengol'ts tira la Magia \#2. 

Usemos el Teorema del Valor Medio de Cauchy para $\phi(t)$ y para **cualquier** función $\psi(t)$ continua en  $[x_{0}-\delta,x_{0}+\delta]$ con derivada no nula en el interior del intervalo. Nos queda: 

$$\frac{\phi(x_{0})-\phi(x)}{\psi(x_{0})-\psi(x)}=\frac{\phi'(c)}{\psi'(c)}$$

$$\implies \phi(x_{0})-\phi(x)=(\psi(x_{0})-\psi(x))\frac{\phi'(c)}{\psi'(c)}$$

para algún $c$ entre $x_{0}$ y $x$.

Pero recordemos que $\phi(x)=0$, $\phi(x_{0})=R_{n}(x)$ y que $\phi'(t)=-\dfrac{f^{n+1}(t)(x-t)^{n}}{n!}$ , o sea que: 

$$\boxed{R_{n}(x)=-\frac{\psi(x_{0})-\psi(x)}{\psi'(c)}\frac{f^{n+1}(c)(x-c)^{n}}{n!}}$$

**Y esta es la verdad de la milanesa: la elección de la $\psi(t)$ es la clave**. Elijamos $\psi(t)=(x-t)^{n+1}$ y nos queda $\psi'(c)=-(n+1)(x-c)^{n}$, $\psi(x_{0})=(x-x_{0})^{n+1}$, $\psi(x)=0$ así que:

$$R_{n}(x)=-\frac{(x-x_{0})^{n+1}}{-(n+1)(x-c)^{n}}\frac{f^{n+1}(c)(x-c)^{n}}{n!}=\frac{f^{n+1}(c)}{(n+1)!}(x-x_{0})^{n+1}$$

la forma de Lagrange!!! 

Para obtener la forma de Cauchy elegimos $\psi(t)=(x-t)$, llamamos a $c=x_{0}+\theta(x-x_{0})$ y etc. 

La **Forma de Schlömilch** propiamente dicha no es esta tan general que está en el libro de Fikhtengol'ts, sino la que figura en el libro de Rey Pastor (§39-2): 

$$R_{n}(x)=\frac{f^{n+1}(x_{0}+h\theta)}{n!p}h^{n+1}(1-\theta)^{n+1-p}$$

que incluye a Lagrange ($p=n+1$) y Cauchy ($p=1$) como casos particulares. Se obtiene simplemente con  $\psi(t)=(x-t)^{p}$, para $p=1,2,...,n+1$. 

**O sea que la elección de $\psi(t)$ esconde el trade-off entre la simpleza de la fórmula y la información que se pierde/gana**. La forma de Lagrange la elegimos todos porque es extremadamente sencilla de recordar (es casi un término más del polinomio) y funciona casi siempre. La de Cauchy es más fea pero como dice Fikhtengol'ts *"a veces ese factor $(1-\theta)^{n}$ puede ser útil"*, como vimos en nuestro ejemplo inicial del $\ln(1/3)$. 

Bueno, no sé que tanto interés tendrá el lector en las fórmulas para el resto de aproximar por Taylor, pero sin duda este post tiene un aporte positivo para toda la gente de bien que es la sugerencia bibliográfica del tratado de Fikhtengol'ts, de nada 😂. 

Hasta que los moleste luego! 

L. A. P

