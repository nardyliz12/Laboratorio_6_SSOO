# Parte  III
## Ejercicio 6: Procesos y Monitoreo

### 1. Ejecuta un comando ping a google.com en segundo plano, redirigiendo su salida a "ping_log.txt"
```
ping google.com > ~/laboratorio/ping_log.txt 2>&1 &
jobs -l  # Muestra procesos en segundo plano con sus PIDs (verificación)
```
![imagen](https://github.com/user-attachments/assets/0d77f2e9-6b00-40c9-b7ac-9dfa93cfc77a)

- En este comando ">" redirige la salida estándar al archivo, asimismo, "2>&1" redirige errores (stderr) a la salida estándar (stdout) y "&" ejecuta el proceso en segundo plano.

### 2. Ejecuta el comando top y aprende a : Ordenar procesos por uso de CPU, Memoria, y filtrar para ver solo tus procesos
```
P (Shift + p)	Ordena por porcentaje de CPU (descendente).
M (Shift + m)	Ordena por uso de memoria (descendente).
u + nombre_usuario	Muestra solo procesos de tu usuario.
```

![imagen](https://github.com/user-attachments/assets/2f64a7a9-d9c9-459a-b1cd-a9902ee3df94)

### 3. Identifica el PID del proceso ping que iniciaste y termínalo correctamente
```
# Encuentra el PID del proceso ping (opción 1)
pgrep -f "ping google.com"

# Opción 2 (lista todos los procesos de ping):
ps aux | grep "ping google.com"

# Termina el proceso (reemplaza [PID] con el número real):
kill 9961
```
![imagen](https://github.com/user-attachments/assets/5b742540-5326-4544-b153-faa3ed74966a)

### 4. Verifica que el archivo de log contiene información
```
cat ~/laboratorio/ping_log.txt
```
![imagen](https://github.com/user-attachments/assets/b08bb216-fdb1-4178-b083-6901aa8a45f1)
![imagen](https://github.com/user-attachments/assets/218bb665-88fd-4837-a1ae-9d92bcfb1003)

-De acuerdo a todo lo visto sabemos que "ping" no se detiene, para ello usamos "kill [PID] para forzar la terminación, con ello concluimos que terminamos el proceso correctamente.
