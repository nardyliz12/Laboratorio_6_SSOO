## Desafío: Análisis de Logs del Sistema

### A. Crea un script llamado "analisis_logs.sh" que:  
- Busque en el directorio /var/log/ todos los archivos de log (terminados en .log)
- Identifique los 5 archivos de log más grandes
- Cuente las ocurrencias de la palabra "error" (ignorando mayúsculas/minúsculas) en cada uno
- Genere un informe en formato markdown en ~/laboratorio/datos/salida/informe_logs.md con:
  - Fecha y hora del análisis 
  - Tabla de archivos con: nombre, tamaño y número de errores
  - Los 3 últimos errores encontrados en el archivo con más errores
  - Muestre un resumen por pantalla

### Crear el script analisis_logs.sh
- Abrimos el terminal y editamos el archivo:
```
nano ~/laboratorio/scripts/analisis_logs.sh
```
- Luego, copiaamos este código en el editor:
```
#!/bin/bash

# Definir variables
LOG_DIR="/var/log/"
OUTPUT_FILE="$HOME/laboratorio/datos/salida/informe_logs.md"
FECHA=$(date "+%Y-%m-%d %H:%M:%S")

# Buscar archivos de log y ordenar por tamaño
LOGS=$(find $LOG_DIR -type f -name "*.log" -exec du -h {} + | sort -rh | head -5)

# Generar la tabla de archivos con nombre, tamaño y número de errores
echo "# Informe de Análisis de Logs" > $OUTPUT_FILE
echo "**Fecha del análisis:** $FECHA" >> $OUTPUT_FILE
echo "" >> $OUTPUT_FILE
echo "| Archivo | Tamaño | Número de errores |" >> $OUTPUT_FILE
echo "|---------|--------|------------------|" >> $OUTPUT_FILE

MOST_ERRORS=0
FILE_MOST_ERRORS=""

# Procesar cada archivo de log
while read line; do
    FILE_SIZE=$(echo $line | awk '{print $1}')
    FILE_NAME=$(echo $line | awk '{print $2}')
    ERROR_COUNT=$(grep -i "error" "$FILE_NAME" | wc -l)

    echo "| $FILE_NAME | $FILE_SIZE | $ERROR_COUNT |" >> $OUTPUT_FILE

    if [ "$ERROR_COUNT" -gt "$MOST_ERRORS" ]; then
        MOST_ERRORS=$ERROR_COUNT
        FILE_MOST_ERRORS=$FILE_NAME
    fi
done <<< "$LOGS"

# Obtener los últimos 3 errores del archivo con más errores
echo "" >> $OUTPUT_FILE
echo "**Últimos 3 errores del archivo con más errores ($FILE_MOST_ERRORS):**" >> $OUTPUT_FILE
echo '```' >> $OUTPUT_FILE
grep -i "error" "$FILE_MOST_ERRORS" | tail -3 >> $OUTPUT_FILE
echo '```' >> $OUTPUT_FILE

# Mostrar resumen en pantalla
echo "Análisis completado. Informe generado en: $OUTPUT_FILE"
echo "Archivos analizados:"
echo "$LOGS"
echo "Archivo con más errores: $FILE_MOST_ERRORS ($MOST_ERRORS errores)"
```
- Una vez tenemos el codigo dentro del terminal dentro de nano los guardamos presionando Ctrl + O, enter y Ctrl + X para salir y volver al terminal.

### Dar permisos de Ejecución
```
chmod +x ~/laboratorio/scripts/analisis_logs.sh
```
### Ejecutamos el script
- Corremos el script:
```
~/laboratorio/scripts/analisis_logs.sh
```
![imagen](https://github.com/user-attachments/assets/fbf30178-a7cc-4c8a-b6df-2f4083a450cb)

### Verificamos que el informe se ha generado
- Ejecutamos el siguiente comando
```
ls -lh ~/laboratorio/datos/salida/informe_logs.md
```
![imagen](https://github.com/user-attachments/assets/8084b09b-ac07-486e-b892-869f06f23ade)

- Si el archivo existe, puedes visualizar su contenido con:
```
cat ~/laboratorio/datos/salida/informe_logs.md
```
![imagen](https://github.com/user-attachments/assets/e2e0955b-3743-495f-8e71-07331552a31b)

- Como se puede visualizar ahi se genero el archivo de "informe_logs.md" en formato markdown.
  
![imagen](https://github.com/user-attachments/assets/605dc1f7-49c3-4905-9105-afda25107ff0)
