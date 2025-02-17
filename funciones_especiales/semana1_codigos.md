---
author: " "
subject: Funciones especiales - Semana 1
jupytext:
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.16.7
kernelspec:
  display_name: Python 3
  name: python3
downloads:
  - file: ./semana1_codigos.md
    title: semana1_codigos.md
  - file: ./semana1_codigos.ipynb
    title: semana1_codigos.ipynb
---

:::{attention} Ejecútame
🐁 ¡Este notebook es ejecutable! 
:::
+++ {"id": "dWH7LKhcvSSh"}

# Códigos

+++ {"id": "QVOmENgNEMK2"}

## Polinomios de Legendre

```{code-cell} ipython3

#| label: legendre
#| placeholder: ./polinomios_legendre.png
import numpy as np
from scipy.special import legendre  # Función de Legendre de grado n
import matplotlib.pyplot as plt  # biblioteca de visualización de datos
plt.rcParams.update({'font.size': 16})

x = np.linspace(-1, 1, 100)
markers = ['o', 's', 'D', '^', 'v']  # Lista de marcadores

plt.figure(figsize=(10, 6))
for i in range(5):
    plt.plot(x, legendre(i)(x), label=f'$P_{i}(x)$', marker=markers[i], markevery=10)
plt.xlabel('x')
plt.ylabel(f'$P_n(x)$')
#plt.title('Polinomios de Legendre')
plt.grid(True)
plt.legend()
plt.show()
```

```{code-cell} ipython3

#| label: legendre-2
#| placeholder: ./polinomios_legendre-2.png
import numpy as np
import matplotlib.pyplot as plt
plt.rcParams.update({'font.size': 16})
from scipy.special import legendre

# Parámetros
l_max = 4  # Máximo orden de polinomios de Legendre
theta = np.linspace(0, np.pi, 100)  # Valores de theta (ángulo polar)
markers = ['o', 's', 'D', '^', 'v']  # Lista de marcadores
# Calcular y graficar los primeros polinomios de Legendre
plt.figure(figsize=(10, 6))
for l in range(l_max + 1):
    P_l = legendre(l)
    plt.plot(np.degrees(theta), P_l(np.cos(theta)), label=f'$P_{l}(\\cos \\theta)$', marker=markers[l], markevery=10)

plt.xlabel('$\\theta$ (grados)')
plt.ylabel('$P_{l}(\\cos \\theta)$')
#plt.title('Polinomios de Legendre')
plt.legend()
plt.grid(True)
plt.show()
```

```{code-cell} ipython3

#| label: latex-legendre
import numpy as np
from scipy.special import legendre

# Crear el polinomio a partir de los coeficientes
for i in range(5):
    # Obtener los coeficientes del polinomio de Legendre
    coef = legendre(i).coefficients
    # Crear el polinomio en formato LaTeX
    poly_latex = " + ".join([f"{coef[j]:.2f}x^{i-j}" for j in range(i+1)])
    # Imprimir el polinomio en formato LaTeX
    print(f"Polinomio de Legendre de orden {i}:")
    print(f"${poly_latex}$")
    print()
```


## Polinomos asociados de Legendre

```{code-cell} ipython3

#| label: legendre-asociados
#| placeholder: ./polinomios_legendre_asociados.png
import numpy as np
import matplotlib.pyplot as plt
plt.rcParams.update({'font.size': 16})
from scipy.special import lpmv

# Definición del rango de x
markers = ['o', 's', 'D', '^', 'v']  # Lista de marcadores
x = np.linspace(-1, 1, 100)
l=3
m=-1
# Calcular el polinomio asociado de Legendre
markers = ['o', 's', 'D', '^', 'v']  # Lista de marcadores
plt.figure(figsize=(10, 6))
# Graficar el polinomio
for m in range(l+1):
  P_lm = lpmv(m, l, x)
  plt.plot(x, P_lm, label=f'$P_{l}^{m} (x)$', marker=markers[m], markevery=10)
plt.xlabel('x')
plt.ylabel(f'$P_l^m(x)$')
#plt.title(r'Polinomio asociado de Legendre de $P_l^m$')
plt.legend()
plt.grid(True)
plt.show()
```

## Armónicos esféricos

```{code-cell} ipython3
#| label: armonicos-esfericos
#| placeholder: ./armonico-esferico.png
import numpy as np
import matplotlib.pyplot as plt
import scipy.special as sp
from mpl_toolkits.mplot3d import Axes3D

# Parámetros del armónico esférico
l = 3  # Número cuántico angular
m = 2  # Número cuántico magnético

# Crear una malla en coordenadas esféricas
theta = np.linspace(0, np.pi, 100)  # Ángulo polar
phi = np.linspace(0, 2*np.pi, 100)  # Ángulo azimutal
theta, phi = np.meshgrid(theta, phi)

# Evaluar el armónico esférico
Y_lm = sp.sph_harm_y(m, l, phi, theta)

# Convertir a coordenadas cartesianas para graficar
r = np.abs(Y_lm)  # Magnitud del armónico esférico
x = r * np.sin(theta) * np.cos(phi)
y = r * np.sin(theta) * np.sin(phi)
z = r * np.cos(theta)

# Graficar en 3D
fig = plt.figure(figsize=(8, 6))
ax = fig.add_subplot(111, projection='3d')
ax.plot_surface(x, y, z, facecolors=plt.cm.viridis(r / r.max()), edgecolor='k', alpha=0.7)

# Configuración del gráfico
ax.set_xlabel('X')
ax.set_ylabel('Y')
ax.set_zlabel('Z')
ax.set_title(rf'Armónico Esférico $|Y_{l}^{m}(\theta, \varphi)|$')

plt.show()
```

