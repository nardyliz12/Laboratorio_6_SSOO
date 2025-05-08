## Ejercicio 7: Scripts Básicos y Automatización

### 1. Crea un script llamado "backup.sh" que: 
- Reciba como parámetro un directorio 
- Cree un archivo tar.gz con el contenido de ese directorio 
- Coloque el archivo comprimido en ~/laboratorio/respaldo/ 
- Muestre un mensaje de éxito con el tamaño del archivo creado

#### Crear el script backup.sh
```
nano ~/laboratorio/scripts/backup.sh

#!/bin/bash

# Verificar si se proporcionó un directorio como argumento
if [ -z "$1" ]; then
    echo "Uso: $0 <directorio>"
    exit 1
fi

# Variables
DIR_ORIGEN="$1"
DIR_DESTINO=~/laboratorio/respaldo
FECHA=$(date +%Y-%m-%d_%H-%M-%S)
ARCHIVO_BACKUP="backup_${FECHA}.tar.gz"

# Crear respaldo
tar -czf "$DIR_DESTINO/$ARCHIVO_BACKUP" "$DIR_ORIGEN"

# Mostrar mensaje de éxito con tamaño del archivo creado
echo "Respaldo exitoso: $DIR_DESTINO/$ARCHIVO_BACKUP"
echo "Tamaño del archivo:"
du -h "$DIR_DESTINO/$ARCHIVO_BACKUP"
```
### 2. Prueba el script con diferentes directorios 
```
chmod +x ~/laboratorio/backup.sh
```
- Hacer el script ejecutable, Dar permisos de ejecución al script

### 3. Ejecutar pruebas con diferentes directorios
```
~/laboratorio/scripts/backup.sh ~/laboratorio/datos
```
![imagen](https://github.com/user-attachments/assets/41373e1d-31ca-4835-b2dc-3e8ee13692f1)

- Come se puede visualizar el respaldo se realizo correctamente.
  
### 4. Verificar los archivos creados
```
ls -lh ~/laboratorio/respaldo/
```
![imagen](https://github.com/user-attachments/assets/3f50b1eb-59a4-454b-98bd-da8752f69043)

- Todos los archivos crados se encuentran dentro de nuestro directorio.
