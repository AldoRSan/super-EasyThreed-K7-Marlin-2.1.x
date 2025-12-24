# super-EasyThreed-K7-Marlin-2.1.x

actualización completa para la EasyThreed K7

basado en el gran trabajo de schmttc para las impresoras EasyThreed con placas et4000+ y en su documentación y esquemas proporcionados en
https://github.com/schmttc/EasyThreeD-K7-STM32

Actualizado a Marlin 2.1.X bugfix (oct 2025)

Este firmware está pensado para usarse junto con mis modificaciones para la EasyThreed K7, con el objetivo de reconstruir completamente la EasyThreed K7 para utilizar motores paso a paso reales y un hotend adecuado.
Los archivos STL y las imágenes de referencia pueden encontrarse en Printables, y los archivos originales en Tinkercad.

Este mod asume que estás usando al menos:

-Nema 17 como motores paso a paso para todos los ejes y el extrusor.

-fuente de alimentación de 12V 10A.

-endstops para todos los ejes.

-sin autonivelado.

-cama caliente (opcional).

-extrusor Titan Bowden.

-hotend MK8.

Funciones incluidas
-Autotune MPC para el hotend, mejor que PID y más estable.
-Funcionalidad mejorada de los 4 botones de nivelación, el botón Home y el interruptor de feed/retract.
-Linear Advance e Input Shaping habilitados por defecto.
-Cama caliente habilitada; establecer en cero en el slicer si no está instalada.
-Pausa avanzada y comando M600 habilitados para cambio de filamento a mitad de impresión.

Comportamiento de los botones:
Botón PRINT
  Estado inactivo:
     -Pulsación corta: imprime el último archivo de la tarjeta SD
     -Pulsación larga: eleva el cabezal de impresión 2 cm

  Impresión activa:
     -Pulsación corta: pausa y mueve la boquilla a una zona segura
     -Pulsación larga: cancela el trabajo de impresión actual

  Pausado / esperando M600:
     -Pulsación corta: reanuda la impresión

Botones FEED / RETRACT:
  Estado inactivo:
 -precalienta la boquilla a 220 °C y carga/descarga filamento

  Impresión activa:
 -deshabilitados durante la impresión

  Pausado:
 -precalienta la boquilla a 220 °C y carga/descarga filamento, para cambios manuales de filamento

Botón Home.
  Estado inactivo:
  -Pulsación corta: home de todos los ejes (esquina 1 para nivelación)
  -Pulsación larga: realiza autotune de temperatura del hotend (M306)

  Impresión activa:
  -cicla la velocidad de impresión entre 100%, 125%, 160% y 200% usando M220.

Botones de nivelación:
-Botón 1:
-Inactivo: mueve el cabezal a una zona segura
-Imprimiendo: aumenta el flujo +5%

-Botón 2:
-Inactivo: mueve a la esquina 2 para nivelación
-Imprimiendo: reduce el flujo -5%

-Botón 3:
-Inactivo: mueve a la esquina 3 para nivelación
-Imprimiendo: aumenta la temperatura +5 °C

-Botón 4:
-Inactivo: mueve a la esquina 4 para nivelación
-Imprimiendo: reduce la temperatura -5 °C


Instalación:
El bootloader de la placa es propietario de MKS y lee un archivo binario de firmware llamado mksLite.bin desde la tarjeta SD al arrancar.

Copia mksLite.bin a la tarjeta SD y reinicia la impresora
Después de un corto tiempo (<30 s), el firmware se escribe en la placa y mksLite.bin en la tarjeta SD se renombra a mksLite.CUR
////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
complete upgrade for the EasyThreed k7

based on the great work of schmttc for the EasyThreed printers with et4000+ boards and his documentation and schematics provided on https://github.com/schmttc/EasyThreeD-K7-STM32

Updated to Marlin 2.1.X bugfix (oct 2025)

This firmware is intended to be used with my EasyThreed K7 mods to completely rebuild the easythreed k7 to use real stepper mottors and hotend. Stl files and reference images can be found on printables and the original files on thinkercad.

This mod assumes you are using at least: 

-Nema 17 stepper motors for all axis and the extruder.

-12V 10AMP power supply.

-endstops for all axis.

-no autolevel.

-Heatbed (optional).

-Bowden titan extruder.

-MK8 hotend.

# Features included
    -MPC auto tune for the hoted, better than PID and more stable.
    -improved functionality of the 4 leveling buttons, home button, and feed/retract switch.
    -linear advance and input shaping are enabled by defaut.
    -Heatbed is enabled, set to zero on slicer if not installed.
    -Advanced pause and m600 command enabled for mid-print filament change.

#  Button behavior:

# PRINT Button

      Idle State:
         -Short Press: Prints the latest file on sd card
         -Long Press: Rises the printhead 2cm

      Active Printing:
         -Short Press: Pauses and moves the nozzle to a safe zone
         -Long Press: cancels current print job

      Paused / M600 Waiting:
         -Short Press: Resumes priniting

# FEED / RETRACT Buttons:

      Idle State:
     -preheat the nozzle to 220C and loads/unloads filament
 
      Active Printing:
     -disabled during printing

      Paused:
     -preheat the nozzle to 220C and loads/unloads filament, for manual filament changes
 
# Home button.

      Idle State:
      -Short Press: Home all axes (corner 1 for leveling)
      -Long Press: Performs hotend temperature autotune (M306)
  
      Active Printing: Cycles through printing speed 100%, 125%, 160%, 200%} using M220.

# Leveling buttons:
     
  # -Button1:
    -Idle: Moves printhead to safe zone
    -Printing: increases flow +5%
 #  -Button2:
    -Idle: Moves to corner 2 for leveling
    -Printing: decreases flow -5%
 # -Button3:
    -Idle: Moves to corner 3 for leveling
    -Printing: increases temp +5 degrees
#  -Button4:
    -Idle: Moves to corner 4 for leveling
    -Printing: decreases temp -5 degrees

Installation:
The board's bootloader is proprietary by MKS, which reads a binary firmware file mksLite.bin from the SD card on boot.

  Copy mksLite.bin to the SD card, and restart the printer
  After a short time (<30s) the firmware is written to the board, and mksLite.bin on the SD card is renamed to mksLite.CUR




