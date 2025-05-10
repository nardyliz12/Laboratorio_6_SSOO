## Ejercicio 4: Redirección y Tuberías

### 1. Crear un archivo que contenga la lista de todos los procesos en ejecución 
```
ps aux > ~/laboratorio/todos_procesos.txt
cat ~/laboratorio/todos_procesos.txt # Para visualizar el resultado
```
![imagen](https://github.com/user-attachments/assets/34def319-b0f3-4584-b16a-db4b6a6564db)

- Para este caso, se utilizó el comando de "ps aux", que nos permite mostrar todos los procesos del sistema con detalles, tales como el usuario, CPU, memoria, etc, asimismo, la expresión ">" nos ayuda a redigir la salida al archivo, que en este caso es el archivo de "todos_procesos.txt".

### 2. Filtra los proccesos que pertenecen a tu usuario y guárdalos en archivo separado
```
grep '^nardy' ~/laboratorio/todos_procesos.txt > ~/laboratorio/procesos_usuario.txt

cat ~/laboratorio/procesos_usuario.txt
```
![imagen](https://github.com/user-attachments/assets/92840a78-54ad-48c9-88ef-f79590ce26de)

- En este caso la linea de comando utiliza "grep 'nardy'" como parte a mi usuario, ya que filtra las lineas que comienza (^) con mi nombre de usuario, asimismo, la presión > guarda el resultaso en el "archivo_usuario.txt".

### 3. Encontrar los 5 procesos que más memoria consumen y guárdarlos en "top_procesos.txt"

```
# Ordena por consumo de memoria (columna 4) y toma los primeros 5
sort -k4 -nr ~/laboratorio/todos_procesos.txt | head -n 5 > ~/laboratorio/top_procesos.txt

cat ~/laboratorio/top_procesos.txt

```
![imagen](https://github.com/user-attachments/assets/67bb03ea-8f95-4d78-a18b-a7dbe662c66c)

- Es comando utiliza "sort -k4 -nr" que ordenas por la columna 4 (memoria) en orden numérico inverso (-nr), de la misma manera "head -n 5" muestra solo las 5 líneas, y ese proceso se guarda en el archivo de "top_procesos.txt".

### 4. Crea un unico comando que cuente cuantos archivos hay en el directorio /etc

```
find /etc -type f 2>/dev/null | wc -l
```
![imagen](https://github.com/user-attachments/assets/2435a97d-1031-4e4f-8dcd-d7736b33b8be)

- En este caso utiliza el comando "find /etc -type f" que busca todos lo archivos (-type f) en /etc, asimismo, utiliza "2>/dev/null" que silencia errores (ej: permisos denegados), tambien usa "wc -l" que cuenta el númrero de líneas (archivos encontrados).






