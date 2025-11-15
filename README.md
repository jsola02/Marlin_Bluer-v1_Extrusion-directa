<p align="center"><img src="buildroot/share/pixmaps/logo/marlin-outrun-nf-500.png" height="250" alt="MarlinFirmware's logo" /></p>

<h1 align="center">Marlin 3D Printer Firmware</h1>

## Versión personalizada Two Trees Bluer v1 / Mks Robin Nano v.20

Este repositorio es una **rama personalizada de Marlin 2.1.2.5** pensada para compartir con la comunidad de impresión 3D de **Two Trees** y la comunidad de makers de impresión 3D.  
Está configurada específicamente para una Two Trees Bluer muy modificada:

- Placa base: **MKS Robin Nano V2.0**, 32 bits (`BOARD_MKS_ROBIN_NANO_V2`).
- Firmware: **Marlin 2.1.2.5**, compilación `02010205`, entorno PlatformIO `mks_robin_nano_v1v2`.
- Pantalla: **MKS TS35 v2.0** (compatible TFT35) con `TFT_COLOR_UI` y calibración táctil (`TOUCH_SCREEN`).
- Drivers: **MKS TMC2209 V2** para X, Y, Z y E0 (modo standalone).
- Extrusión: **Creality Sprite Extruder Pro Kit**, filamento de 1.75 mm.
- Eje Z: **doble eje Z** con motores independientes.
- Finales de carrera: X, Y, Z con nuevo cableado independiente y posicionamiento modificado.
- Cama: **flexible / vidrio**.
- Ruedas: **V-SLOT en V, Trianglelab**.
- Barra de luz LED: **Ender 3 V3** instalada en el marco.
- Sensor de filamento: detección de corte de filamento activa (`FILAMENT_RUNOUT_SENSOR` + `M600` / `ADVANCED_PAUSE_FEATURE`).

### Características principales de esta configuración

- Volumen de impresión: **230 x 230 x 260 mm**.
- 1 extrusor, filamento **1.75 mm**.
- Nivelación: **MESH_BED_LEVELING** con sondeo manual y `Z_SAFE_HOMING` en el centro de la cama.
- Sensor de fin de filamento activado con script de cambio `M600`.
- **POWER_LOSS_RECOVERY** para recuperación tras cortes de energía.
- **EEPROM** activada para guardar ajustes (M500/M501/M502).
- Control de temperatura por **PID** en hotend y cama (`TEMP_SENSOR_0 1`, `TEMP_SENSOR_BED 1`).
- Asistente de tramming desde LCD (`LCD_BED_TRAMMING`).

### Cómo compilar esta versión

1. Instala **Visual Studio Code** y la extensión **PlatformIO IDE** (o Auto Build Marlin).
2. Abre esta carpeta de proyecto en VS Code.
3. Asegúrate de que en `platformio.ini` el entorno por defecto es:
   - `default_envs = mks_robin_nano_v1v2`
4. Compila el proyecto desde PlatformIO / Auto Build Marlin.
5. El binario generado habitual es:
   - `.pio/build/mks_robin_nano_v1v2/Robin_nano35.bin`

### Cómo instalar el firmware en la MKS Robin Nano v2.0

1. Formatea una tarjeta **microSD** (FAT32, tamaño pequeño recomendado).
2. Copia el archivo `Robin_nano35.bin` a la raíz de la tarjeta.
3. Con la impresora apagada, inserta la tarjeta microSD en la placa.
4. Enciende la impresora y espera a que termine el proceso de actualización.
5. Tras actualizar, comprueba en la pantalla que el nombre de la máquina y versión corresponden a esta compilación.

> **Aviso:** Esta configuración está adaptada a una impresora concreta muy modificada. Si tu máquina difiere (mecánica, sensores, drivers, doble Z, etc.), revisa y ajusta `Configuration.h` y `Configuration_adv.h` antes de compilar.

## Marlin 2.1

Marlin 2.1 continues to support both 32-bit ARM and 8-bit AVR boards while adding support for up to 9 coordinated axes and to up to 8 extruders.

Download earlier versions of Marlin on the [Releases page](//github.com/MarlinFirmware/Marlin/releases).

## Example Configurations

Before you can build Marlin for your machine you'll need a configuration for your specific hardware. Upon request, your vendor will be happy to provide you with the complete source code and configurations for your machine, but you'll need to get updated configuration files if you want to install a newer version of Marlin. Fortunately, Marlin users have contributed dozens of tested configurations to get you started. Visit the [MarlinFirmware/Configurations](//github.com/MarlinFirmware/Configurations) repository to find the right configuration for your hardware.

## Building Marlin 2.1

To build and upload Marlin you will use one of these tools:

- The free [Visual Studio Code](//code.visualstudio.com/download) using the [Auto Build Marlin](//marlinfw.org/docs/basics/auto_build_marlin.html) extension.
- The free [Arduino IDE](//www.arduino.cc/en/main/software) : See [Building Marlin with Arduino](//marlinfw.org/docs/basics/install_arduino.html)
- You can also use VSCode with devcontainer : See [Installing Marlin (VSCode devcontainer)](http://marlinfw.org/docs/basics/install_devcontainer_vscode.html).

Marlin is optimized to build with the **PlatformIO IDE** extension for **Visual Studio Code**. You can still build Marlin with **Arduino IDE**, and we hope to improve the Arduino build experience, but at this time PlatformIO is the better choice.

## Marlin Support

The Issue Queue is reserved for Bug Reports and Feature Requests. Please use the following resources for help with configuration and troubleshooting:

- [Marlin Documentation](//marlinfw.org) - Official Marlin documentation
- [Marlin Discord](//discord.com/servers/marlin-firmware-461605380783472640) - Discuss issues with Marlin users and developers
- Facebook Group ["Marlin Firmware"](//www.facebook.com/groups/1049718498464482/)
- RepRap.org [Marlin Forum](//forums.reprap.org/list.php?415)
- Facebook Group ["Marlin Firmware for 3D Printers"](//www.facebook.com/groups/3Dtechtalk/)
- [Marlin Configuration](//www.youtube.com/results?search_query=marlin+configuration) on YouTube

## Contributors

Marlin is constantly improving thanks to a huge number of contributors from all over the world bringing their specialties and talents. Huge thanks are due to [all the contributors](//github.com/MarlinFirmware/Marlin/graphs/contributors) who regularly patch up bugs, help direct traffic, and basically keep Marlin from falling apart. Marlin's continued existence would not be possible without them.

Marlin Firmware original logo design by Ahmet Cem TURAN [@ahmetcemturan](//github.com/ahmetcemturan).

## Star History

<a id="starchart" href="https://star-history.com/#MarlinFirmware/Marlin&Date">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=MarlinFirmware/Marlin&type=Date&theme=dark" />
    <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=MarlinFirmware/Marlin&type=Date" />
    <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=MarlinFirmware/Marlin&type=Date" />
  </picture>
</a>

## License

Marlin is published under the [GPL license](/LICENSE) because we believe in open development. The GPL comes with both rights and obligations. Whether you use Marlin firmware as the driver for your open or closed-source product, you must keep Marlin open, and you must provide your compatible Marlin source code to end users upon request. The most straightforward way to comply with the Marlin license is to make a fork of Marlin on Github, perform your modifications, and direct users to your modified fork.
