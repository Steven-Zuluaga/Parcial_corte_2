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

print('Lista original:', lista)
print('Lista ordenada:', ordenar_burbuja(lista))
```
