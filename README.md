[Versión 0.6.2]: #
# velcpu - Modificador automático y fijo de la velocidad de la CPU

Este script echo en bash es un wrapper de cpupower para modificar la velocidad del procesador. Puede elegirse una frecuencia fija o optimizar el rendimiento para un techo máximo de temperatura.

---
## Estado del proyecto
- Actualmente funciona sin problemas.
- Quedan ideas para añadir y mejorar detalles.

---
## Instalación
No requiere instalación

### Lenguaje
- Bash

### Dependencias
Sí, tiene dependencias de:
- cpupower (Debian/Ubuntu)

### Sistemas operativos compatibles
Probado en:
- Debian

---
## Uso
- Solo se puede usar una opción por cada ejecución, son excluyentes
- El 0% de frecuencia es la frecuencia base del procesador

### Opciones de ejecución
**./velcpu**
>-> El programa muestra

>- Las distintas opciones de uso
>- Las instancias en segundo plano del programa
>- Rango de frecuencias de la CPU del ordenador
>- Ejemplos de uso.

**./velcpu -l 3**

**./velcpu -l 30**
>-> La opción -l configura una velocidad fija (porcentaje)
    -Entre 0-9 establece la frecuencia desde el 0% hasta el 90%
    -Entre 10-100 establece la frecuendia desde el 10% hasta el 100%

**./velcpu -f 14**

**./velcpu -f 1400000**
>-> La opción -f configura una velocidad fija (frecuencia)
    -Entre la frecuencia mínima y máxima de tu procesador en kHz, establece esa frecuencia
    -Se puede elegir introducir en kHz o en centenas de kHz: 1,4GHz = 14

**./velcpu -c**
>-> Regulación automática (versión gráfica)
    -Techo máximo de temperatura de 85 grados centígrados.
    -Modo gráfico, para ejecutar en segundo plano usar opción -d
    -Actualización cada 0.5 segundos (variable "refresco")
    -Si se acerca a la temperatura límite desconecta los hilos del procesador.
    -Objetivo: rendimiento máximo sin sobrepasar la temperatura

**./velcpu -d**
>-> Regulación automática (versión en segundo plano)
    -Idéntica a la opción -c pero sin mostrar nada.
    -Se ejecuta automaticamente en segundo plano, independente de la terminal.

**./velcpu -dk**
>-> Mata a los procesos en segundo plano
    -Útil para eliminar los procesos lanzados con la opción -d
    -Se pueden ver los activos ejecutando "./velcpu"
    -Mantiene la última configuración que dejó el proceso en segundo plano.
    -Objetivo: eliminar el proceso manteniendo la configuración que ha dejado.

**./velcpu -r**
>-> Resetea configuraciónes y procesos en segundo plano.
    -Mata a los procesos en segundo plano
    -Resetea las frecuencias y los hilos originales
    -Objetivo: Mata el proceso y resetea todas las configuraciones de la CPU


### Ejemplo de uso

    velcpu             >> Informació
    velcpu -l 3        >> Límit al 30%
    velcpu -l 30       >> Límit al 30%
    velcpu -f 14       >> Límit a 1.4GHz
    velcpu -f 1400000  >> Límit a 1.4GHz
    velcpu -c          >> Regulació automatica
    velcpu -d          >> Reg. Autom. segon plà
    velcpu -dk         >> Mata segon plà
    velcpu -r          >> Deixa frec de fabrica

---

## Recomendación
Para un uso mas ágil se puede crear una carpeta para script de forma que todos los que se añadan se puedan llamar desde la propia terminal como cualquier otro comando.

Esto se puede conseguir añadiendo a ~/.bashrc la línea:

>export PATH=$PATH:/ruta/a/carpeta/con/scripts

---
## Licencia
Este proyecto está licenciado bajo GPLv2 - consulta el archivo LICENSE para más detalles.

---
## Autor
    [Alex](github.com/4lexKy)
---
