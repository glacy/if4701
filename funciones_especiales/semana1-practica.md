---
title: Ejercicios
description: Ejercicios
short_title: Ejercicios
author: " "
tags: []
subject: Funciones especiales - Semana 1
keywords: []
exports:
  - format: pdf
    template: arxiv_two_column
    output: ./semana1-practica.pdf
# downloads:
#   - file: ./semana1-practica.md
#     title: semana1-practica.md
#   - file: ./semana1-practica.pdf
#     title: semana1-practica.pdf
# abstract: asdsdasdadasdasdasda
# kernelspec:
#   name: python3
#   display_name: "Python 3"
---

:::{hint} Instrucciones
Resuelva de forma razonada cada uno de los siguientes ejercicios. Use esquemas y dibujos si lo considera necesario. Debe incluir los cálculos
y procedimientos que le llevan a su respuesta.
:::

```{exercise}
:label: EDOs
Con base en la información de [](#tab-sturm-liouville) y la [Ecuación %s](#eq-sturm-liouville), escriba explícitamente la EDO 
1. de Legendre
2. asociada de Legendre
3. de Bessel
4. de Hermite
```

```{exercise}
:label: ex2

Escriba explícitamente las siguientes funciones:

1.  $P_{10}(x)$

2.  $P^2_4(x)$

3.  $Y_3^2(\theta,\varphi)$

4.  $[Y_3^{1}(\theta,\varphi)]^*$
```



```{exercise}
:label: ex5
Grafique $V(r, \theta) = \frac{GM}{r} \left( 1 - \frac{R^2}{r^2} P_2(\cos \theta) \right)$.
```

```{exercise}
:label: ex3
La solución a la ecuación de Laplace en coordenadas esféricas está dada por
    $$v(r, \theta, \varphi) = \sum_{l=0}^{\infty} \sum_{m=-l}^{l} (A_{lm} r^l + B_{lm} r^{-l-1}) P_l^m(\cos \theta) e^{im\varphi}$$

En una situación con simetría axial, $m=0$.

Considere una esfera conductora hueca de radio $a$ colocada en el origen. Si una de las mitades de su superficie se encuentra cargada
a un potencial $v_0$ y la otra mitad a potencial cero, las condiciones de frontera son
$$
v(a,\theta,\varphi)= \left\{\begin{matrix}
v_0 & \text{para } & 0<\theta<\pi/2\\
0 & \text{para } & \pi/2<\theta<\pi
\end{matrix} \right.
$$

Dentro de la esfera ($r<a$), la solución debe ser finita, de manera que $B_l=0$ para todo $l$ y se debe cumplir que
$$A_la^l=\frac{2l+1}{2}v_0\int_0^1 P_l(\mu)d\mu.$$

Similarmente, fuera de la esfera ($r>a$), la solución debe ser finita, de manera que $A_l=0$ para todo $l$ y se debe cumplir que
$$B_la^{-(l+1)}=\frac{2l+1}{2}v_0\int_0^1 P_l(\mu)d\mu.$$ Usando la relación de recurrencia $$(1-x^2)P^\prime_l(x)=lP_{l-1}-lxP_l(x)$$ y
la relación (referente a la ecuación de Sturm-Liouville) $$(\lambda_n-\lambda_m)\int_{x_1}^{{x_2}}\rho y_n y_m dx=\left[ y_npy^\prime_m-y_mpy^\prime_n\right]^{x_2}_{x_1}$$

escriba la solución $v(r,\theta,\varphi)$, tanto para dentro como para afuera de la esfera.
```




