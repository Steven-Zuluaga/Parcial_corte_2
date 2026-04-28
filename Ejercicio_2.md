# Algoritmo de Polinimio de Taylor
```python
import math

def exp_taylor(x, n):

    if n <= 0:
        print("n debe ser un entero positivo")

    suma = 0
    for i in range(n):
        termino = x ** i / math.factorial(i)
        suma += termino
    return suma


x = float(input("Ingrese el valor de x: "))
n = int(input("Ingrese el número de términos n: "))

aproximacion = exp_taylor(x, n)
exacto = math.exp(x)

if n <= 0:
    print("Error: n debe ser positivo.")

else:
    aproximacion = exp_taylor(x, n)
    exacto = math.exp(x)

    print(f"e^{x} con {n} términos = {aproximacion:.2f}")
    print(f'math.exp({x})= {exacto:.2f}')
    print(f'Comparacion: {aproximacion == exacto}')
```
