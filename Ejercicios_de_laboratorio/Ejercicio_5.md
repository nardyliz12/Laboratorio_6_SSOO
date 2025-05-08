## Ejercicio 5: Permisos y Usuarios

### 1. Crear un directorio "privado" en el directorio de laboratorio 
```
mkdir ~/laboratorio/privado
```
![imagen](https://github.com/user-attachments/assets/1114fa85-ed00-45e6-9743-084c4025a015)

- Con el comando "mkdir" se creo el directorio "privado" en el directorio de "laboratorio"

### 2. Crea un archivo "confidencial.txt" dentro de este directorio
```
touch ~/laboratorio/privado/confidencial.txt
ls ~/laboratorio/privado
```

![imagen](https://github.com/user-attachments/assets/2398daf5-d46c-41aa-bba5-5ca2faa5c070)

- Comando "touch" se creo correctamente el archivo "confidencial.txt", dentro del direcotrio "privado".

### 3. Configura permisos para que: solo tú puedas leer y escribir el archivo (no ejecutar), nadie más pueda hacer nada con él
```
chmod 600 ~/laboratorio/privado/confidencial.txt
```
- En este comando 600 en permisos significa que el dueño eres (tú) donde 6 (lectura 4 + escritura 2), asimismo, tiene grupo y otros, donde 0 significa (ningún permiso), en pocas palabras significa que el propietario tiene permiso de lectura y escritura, nadie más puede acceder.

### 4. Crea un directorio "compartido" que cualquiera pueda leer, pero sólo tú modificar
```
mkdir ~/laboratorio/compartido
chmod 755 ~/laboratorio/compartido
```
- En este comando 755 en permisos significa: Dueño (tú) es igual a 7 donde (lectura 4 + ejecución 2 + ejecución 1), también, grupos y otros es igual a 5 donde (lectura 4 + ejecución 1, pero sin escritura), en pocas palabras significa que el propietario tiene permisis de lectura, escritura y ejecución, otros pueden leer y ejecutar, pero no modificar.
  
### 5. Verifica los permisos utilizando ls -la
```
ls -la ~/laboratorio/privado/confidencial.txt
ls -ld ~/laboratorio/compartido
```

![imagen](https://github.com/user-attachments/assets/e1c51b85-418c-410d-a547-333673ca725b)

- Del resultado podemos rescatar lo siguiente, se puede visualizar que en le archivo "confidencial.txt" aparece "-rw--------" eso signifia que solo el dueño tiene el derecho de acceder a la lectura (r) y escritura (w). Asimismo, el caso "compartido" aparece "drwxr-xr-x", que significa que el dueño "rwx" puede acceder a la lectura, escritura y ejecución, mientras, que en grupo y otros esta "r-x" que significa que solo es para lectura y ejecución sin escritura.

- **Notas clave:**
  - **Permisos numéricos:**

    - 600 (archivo): Solo tú puedes leer/modificar.

    - 755 (directorio): Todos pueden listar/entrar, pero solo tú crear/eliminar archivos.
      
  - **Ejecución en directorios:**

    - El permiso x en directorios permite "entrar" al directorio (no es lo mismo que en archivos).
  - **Verificación:**
    - ls -la muestra permisos en formato letras (ej: rwx).

    - ls -ld verifica permisos del directorio (no su contenido).


