# Ordenamiento burbuja
```python
def ordenar_burbuja(lista):
    n = len(lista)
    for i in range(n - 1):
        for j in range(n - 1 - i):
            if lista[j] > lista[j + 1]:
                lista[j], lista[j + 1] = lista[j + 1], lista[j]
    return lista

entrada = input('Ingrese números separados por espacios: ')
numeros = entrada.split() # Usamos .splt para dividir lo que coloca el usuario en la entrada y la combierte en una lista de partes, separada por espacios

lista = []
for i in numeros:
    lista.append(int(i))

print(f'Lista original:, {lista}')
print(f'Lista ordenada:, {ordenar_burbuja(lista)}')
```
- Idea: compara pares de elementos adyacentes y los intercambia si están en el orden incorrecto, repitiendo el proceso hasta que no necesite mover ninguno mas.

- Complejidad temporal: en el peor caso es O(n²) porque hay dos bucles anidados. El externo corre n-1 veces y el interno corre n-1-i veces en cada vuelta, dando en total aproximadamente n(n-1)/2 comparaciones.

- Eficiencia para listas grandes: es ineficiente. Para 10.000 elementos hace cerca de 50 millones de comparaciones.por lo que concluimos que un algoritmo de Burbuja sirve para listas pequeñas o para aprender el concepto, pero no para uso real con datos grandes.
