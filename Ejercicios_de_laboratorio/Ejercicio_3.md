# Parte II
## Ejercicio 3: Búsqueda y FIltrado
### 1. Buscar todos los archivos con extensión ".txt" en el directorio de laboratorio y subdirectorios.
```
find ~/laboratorio -type f -name "*.txt" #Busca todos los archivos con extensión .txt
```

![imagen](https://github.com/user-attachments/assets/9def01a3-4a48-44f1-a998-df6e5b1bb32a)

- Como se visualiza el comando nos brinda todos los documentos que termien con ".txt", que en este caso serian 2 archivos, el archivo "datos1.txt" que se encuentra en el directorio de "entrada" y la copia de este mismo archivo, pero en el directorio de "respaldo".

### 2. Crear un archivo "numeros.txt" con números del 1 al 100 (uno por línea)
```
seq 1 100 > ~/laboratorio/numeros.txt # Para colocar los numeros en cada linea.
cat ~/laboratorio/numeros.txt #visualizar el resultado
```

![imagen](https://github.com/user-attachments/assets/59dc1ca3-fbce-4e80-a696-353d4d74d3db)

- Como se puede visualizar el comando nos ayuda colocar los numeros en cada linea que en este caso es del 1-100.

### 3. Encontrar todos los números pares en el archivo
```
grep -E '^[0-9]*[02468]$' ~/laboratorio/numeros.txt
```
![imagen](https://github.com/user-attachments/assets/57292df8-cb58-4460-9d08-f6249c651ea1)

- En este caso el comando junto a la operación que nos ayuda encontrar a todos aquellos números que son pares que van desde el 2-100.
```
^       # Coincide con el inicio de la línea
[0-9]*  # Coincide con cero o más (*) dígitos del 0 al 9
[02468] # Coincide con un ÚLTIMO dígito par (0, 2, 4, 6 u 8)
$       # Coincide con el final de la línea
```
### 4. Encontrar todos los números divisibles por 5
```
awk '($1 % 3 == 0)' ~/laboratorio/numeros.txt #Filtra líneas donde el número módulo 3 es 0
```
![imagen](https://github.com/user-attachments/assets/492798aa-2170-41a3-9be4-4fe415385d60)

- Utilizando el comando "awk" podemos encontrar todos aquellos números divisibles por 3, ya que este comando nos ayuda a flitrar las lineas, donde el número módulo de 3 es igual a 0.

### Cuenta cuántos números son divisibles por 5
```
grep -c -E "^[0-9]*[05]$" ~/laboratorio/numeros.txt
```
![imagen](https://github.com/user-attachments/assets/69bc62f6-1ed6-4f23-9ca9-8306c7185734)

- El comando "grep -E" se encarga de buscar patrones usando expresiones regulares y "grep -c" cuenta coincidencias como números terminados en 0 o 5, entonces el comando completo nos ayuda a contar cuantos números en total que son divisibles por 5, que en este caso son 20 números.

### Ordenar el archivo de mayor a menor y guardar el resultado en "numeros_ordenados.txt"

```
sort -nr ~/laboratorio/numeros.txt > ~/laboratorio/numeros_ordenados.txt
# Ver contenido de numeros_ordenados.txt
head ~/laboratorio/numeros_ordenados.txt  # Muestra los primeros 10 números ordenados
tail ~/laboratorio/numeros_ordenados.txt  # Muestra los últimos 10 números ordenados
```
![imagen](https://github.com/user-attachments/assets/c0181644-a87c-433c-97ba-795c2e04c55c)

- En este caso se utilizó el comando de "sort -nr" que ordena numéricamente (-n) en orden reverso (-r), que es lo que nos pide el ejercicio de ordenar los números de mayor a menor, que en este caso inicia desde 100 y termina en 1 guardandolo en el archivo de "numeros_ordenados.txt.

![imagen](https://github.com/user-attachments/assets/77d11c36-74ca-4c3d-9431-3d07092b168e)


 






