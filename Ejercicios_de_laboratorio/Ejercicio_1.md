## EJERCICIO 1: Navegación y Gestión de Archivos

Uno de los primeros pasos es crear la estructura de nuestro directorio que viene a ser de la siguiente forma:
```
~/laboratorio/ 
|---- datos/ 
|        |-----entrada/ 
|        |-----salida/ 
|-----scripts/ 
|-----respaldo 
````
Para ello en el terminal usamos los sigueintes comandos de linux.

```
#Crear la estructura del directorio
mkdir -p ~/laboratorio/datos/entrada 
mkdir -p ~/laboratorio/datos/salida 
mkdir -p ~/laboratorio/scripts 
mkdir -p ~/laboratorio/respaldo

#Verificar que los direcotrios se han creado corectamente
ls -R ~/laboratorio
```

![imagen](https://github.com/user-attachments/assets/d4d7f96c-4760-4ee5-b32d-7157352b7df9)

- Ahi podemos visualizar que nuestro directorio se ha creado correctamente.

|Direcotrio "laboratorio" |Directorrio "entrada" | 
|--------------------|------------------------------|  
|![imagen](https://github.com/user-attachments/assets/e49f81aa-3f5d-4410-86fd-892a31e91e17) |![imagen](https://github.com/user-attachments/assets/5902a801-5529-4702-a831-4f3b84fa7ed0)|

### 1. Navegar entre los diferentes directorios:
```
cd ~/laboratorio/datos/entrada  # Cambiar al directorio "entrada"
cd ~/laboratorio/respaldo       # Cambiar al directorio "respaldo"
cd ~/laboratorio                # Cambiar al directorio raíz del laboratorio
```
### 2. Crear tres archivos de texto vacios en el directorio de "entrada":
```
# Crear archivos en "entrada"
touch ~/laboratorio/datos/entrada/datos1.txt
touch ~/laboratorio/datos/entrada/datos2.txt
touch ~/laboratorio/datos/entrada/config.cfg

# Verificar los archivos creados
ls -la ~/laboratorio/datos/entrada/   # Mostrar contenido de entrada
```
![imagen](https://github.com/user-attachments/assets/e6286c8c-edd0-417d-ae9a-115a82a58ac4)

- Se puede evidenciar que los archivos de "datos1.txt, datos2.txt y config.cfg" se han creado correctamente en el directorio de entrada.

### 3. Copiar "datos1.txt al directorio "respaldo"
```
cp ~/laboratorio/datos/entrada/datos1.txt ~/laboratorio/respaldo/
ls -la ~/laboratorio/respaldo/        # Mostrar contenido de respaldo
```
![imagen](https://github.com/user-attachments/assets/5bc3e696-1cb7-48bf-94ea-7444c74b9905)

- En este caso también se puede observar que el archivo "datos1.txt" se ha copiado en el directorio de "respaldo".

![imagen](https://github.com/user-attachments/assets/1a3bf81e-1b22-40a6-b350-7ab0023279e8)

### 4. Mover "config.cfg" al directorio raíz del laboratorio:
```
mv ~/laboratorio/datos/entrada/config.cfg ~/laboratorio/

# Verificar cambios
ls -la ~/laboratorio/            # Debe mostrar "config.cfg" en el directorio raíz
```
![imagen](https://github.com/user-attachments/assets/3c7dc2e1-977c-48ff-83be-5768f54ee0f5)

- Seguidamente podemos ver que el archivo "config.cfg" se ha movido al directorio raíz que es "laboratorio".

### 5. eliminar "datos2.txt:
```
rm ~/laboratorio/datos/entrada/datos2.txt
ls -la ~/laboratorio/datos/entrada/ # "datos2.txt" ya no debe aparecer
```
![imagen](https://github.com/user-attachments/assets/95c0ac1d-d1fc-4545-ad5a-97330ee71d04)

- Como se puede visualizar el archivo "datos2.txt" ha desaparecido de nuestro directorio de "entrada".




![imagen](https://github.com/user-attachments/assets/c2fa656c-5cb7-4cc8-a336-5cccb8d50632)







