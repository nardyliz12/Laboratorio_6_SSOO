## Ejercicio 2: Visualización y Edición Básica 

### 1.Crear un archivo "registro.log" con al menos 20 lineas.
```
touch ~/laboratorio/datos/registro.log # Crear el archivo en el directorio de "datos".
nano ~/laboratorio/datos/registro.log #Para colocar las 20 lineas de texto dentro del archivo
```
|              |         |
|---------------|-----------|
|![imagen](https://github.com/user-attachments/assets/59d2fff3-9d77-45fb-b021-b6c5c052f5e3)|![imagen](https://github.com/user-attachments/assets/3e22a659-c028-4527-be76-7f10b5314641)|

- Para visualizar el contenido completo
```
cat ~/laboratorio/datos/registro.log 
```
![imagen](https://github.com/user-attachments/assets/a7cc4a91-f685-451a-acf5-ec04bd7e3d03)

- Como se puede visualzar se ve todo el texto ingresado en el archivo de "registro.log"

### 2. Visualizar las primeras 5 lineas del archivo de "registro.log"
```
head -n 5 ~/laboratorio/datos/registro.log
```
![imagen](https://github.com/user-attachments/assets/68368070-f63b-4aab-91ca-e0610b32909b)

- Tal como se muestra en la iamgen solo muestra las 5 primeras lineas de todo el texto.

### 3. Visualizar las últimas 3 lineas del archivo "registro.log"
```
tail -n 3 ~/laboratorio/datos/registro.log
```
![imagen](https://github.com/user-attachments/assets/6bb1926f-5066-4cd0-b994-880a04ef40ac)

- En este caso podemos observar que se muestras las lineas finales del texto, pero al ser la ultima linea algo extensa aparenta com si fuera de 4 lineas, pero no lo que en si esta mostrando son las 3 últimas líneas del todo el texto.

### 4. brir el archivo con nano (o vim) y agregar una linea al inicio que diga "#ARCHIVO DE REGISTRO"

```
nano ~/laboratorio/datos/registro.log # agreamos el texto requerido
```
![imagen](https://github.com/user-attachments/assets/37db8d15-0d82-45b9-9294-e659bca3de7c)

- En este caso podemos visualizar el panel para hacer la agregación del texto requerido, una vez hayamos hecho el cambio, ponemos "Ctrl + 0", luego "enter", para finalmente colocar "Ctrl + X" para salir y regresar al terminal.

### 5. Visualiza el archivo completo para vereficar los cambios
```
cat ~/laboratorio/datos/registro.log # Para visualizar los cambios 
```
![imagen](https://github.com/user-attachments/assets/04b22174-4280-4d4f-b07d-1c6086a085d4)

- Como se puede visualizar se realizó el cambio correspondiente a nuestro archivo "registro.log".



