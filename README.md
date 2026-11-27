# Simulaciones estocásticas

Notebooks en Python para simular procesos estocásticos, desde números pseudoaleatorios hasta ecuaciones diferenciales estocásticas con reflexión en dominios acotados.

## Contenido

| Notebook | Tema |
|---|---|
| `Simulación_del_movimiento_Browniano_estándar.ipynb` | Números pseudoaleatorios, simulación Monte Carlo basada en la ley de los grandes números (estimación de $\mathbb P(Z>c)$) y trayectorias del movimiento browniano estándar. |
| `Simulación_de_la_Integral_de_Ito.ipynb` | Aproximación de la integral de Itô $\int_0^T W_t\,dW_t$ y de integrales de procesos simples adaptados. |
| `euler_maruyama.ipynb` | Método de Euler–Maruyama para simular ecuaciones diferenciales estocásticas, con animación de las trayectorias. |
| `RSDE.ipynb` | Ecuaciones diferenciales estocásticas reflejadas (RSDE): un browniano 2D proyectado sobre un cuadrado fijo y sobre un cuadrado móvil $G(t)=G+C(t)$. |
| `Simulaciones_Presentación.ipynb` | Simulaciones de la presentación: RSDE en un pasillo y en un dominio en forma de L, tiempo de salida $\tau$ según la intensidad del ruido $\sigma$, y animaciones. |

## Idea central

Las RSDE se simulan con un esquema de Euler–Maruyama proyectado:

$$
X_{n+1} = P_G\big\{X_n + b(t_n, X_n)\,\Delta t + \sigma(t_n, X_n)\,\Delta W_n\big\},
\qquad \Delta W_n = \sqrt{\Delta t}\,Z_n,\quad Z_n\sim\mathcal N(0, I),
$$

donde $P_G$ es la proyección sobre el conjunto $G$. Cuando el paso libre sale del dominio, la proyección lo devuelve al punto más cercano de la frontera.

## Requisitos

- Python 3
- `numpy`
- `matplotlib`

Las animaciones usan `matplotlib.animation` y se muestran en el notebook con `IPython.display.HTML`.

## Uso

Cada notebook se puede abrir en Google Colab desde GitHub y ejecutar de principio a fin. Algunos experimentos con muchas trayectorias, como el cálculo de $\tau$ para varios valores de $\sigma$, pueden tardar varios minutos.

## Autor

Marco Pérez D., Universidad de O'Higgins.
