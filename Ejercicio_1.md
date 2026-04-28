# Algoritmo de Euclides y Metodo ingenuo
```python
#Euclides
def mcd(a, b):

    while b != 0:
        residuo = a % b
        a = b
        b = residuo
    return a

#Metodo ingenuo
def mcd_ingenuo(a, b):

    n_encontrado = 1
    for i in range(1, min(a, b) + 1):
        if a % i == 0 and b % i == 0:
            n_encontrado = i
    return n_encontrado

a = int(input('Ingrese el primer número entero positivo: '))
b = int(input('Ingrese el segundo número entero positivo: '))

if a <= 0 or b <= 0:
    print('Error: ambos números deben ser enteros positivos.')
else:
    r1 = mcd_ingenuo(a, b)
    r2 = mcd(a, b)

    print(f'Ingenuo:   MCD({a}, {b}) = {r1}')
    print(f'Euclides:  MCD({a}, {b}) = {r2}')
    print(f'COmparacion:  {r1 == r2}')
```

- Idea:
Se basa en la propiedad de MCD(a, b) = MCD(b, a mod b).
El residuo siempre es menor que b por lo que en cada iteración el problema se hace más pequeño hasta llegar a 0.

- Interaciones:
En cada paso del while, el valor de a toma el valor anterior de b, y b toma el residuo de la división a mod b. 
Como el residuo siempre es estrictamente menor que b, los valores van disminuyendo paso a paso. 
Por ejemplo para MCD(48, 18): en la primera iteración se obtiene residuo 12, en la segunda residuo 6, 
y en la tercera residuo 0, momento en que el algoritmo retorna 6 como resultado.

- Porque termina:
El algoritmo termina porque la secuencia de residuos va disminuyendo y siempre es mayor o igual a cero. 
Al estar limitada a ser inferior a cero e ir disminuyendo, inevitablemente llega a cero en un número finito de pasos. 
Cuando b vale 0, el valor acumulado en a es el MCD y se retorna.

