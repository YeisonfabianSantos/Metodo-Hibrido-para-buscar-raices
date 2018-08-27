# Metodo-Hibrido-para-buscar-raices

# Metodo de Brent-Dekker
# autor: Yeison Santos
# codigo para resolver ecuaciones algebraicas 
import numpy as np 
import matplotlib.pyplot as plt 
import math as m


x=np.linspace(0,9,100)
plt.plot(x,np.cos(x)**5+60*np.sin(3*x),x,x**2)       # graficamos la funcion ha resolver 

# Reescribimos la funcion para buscaqueda de raices (ceros de funciones)
def f(x):
    """Ecuacion no lineal.
    """
    return np.cos(x)**5+60*np.sin(3*x)-x**2

# Buscamos una solucion de acuerdo a la grafica obtenida anteriormente en el intervalo de 3 ha 4

from scipy.optimize import brentq      # por defecto ya viene implementado en python
sol1=brentq(f,3.0,4.0)
print (sol1)         #3.082978831374583

# Buscamos la siguiente raiz, por el metodo de newton.

from scipy.optimize import newton
sol2=newton(f,2.0)
print (sol2)         #2.1195930167624204
