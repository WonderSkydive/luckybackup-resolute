# luckyBackup · Edición comunitaria

**Español** · [English](README-luckybackup-resolute-en.md)

Edición comunitaria de luckyBackup 0.5.0 que mejora la ayuda en español y explica cómo programar copias en Wayland. Los paquetes de esta publicación se preparan para **Kubuntu 26.04 LTS (Resolute), amd64**. La base de empaquetado es la versión 0.5.0-7build3 de Ubuntu.

## Programar copias en Wayland

En **Planificación**, añade o edita una tarea y marca **Modo consola (recomendado en Wayland)**. Guarda la tarea y aplica los cambios a cron desde luckyBackup.

El modo consola permite que cron ejecute la copia sin abrir una ventana ni depender de `DISPLAY=:0`. La salida queda en el registro de la tarea programada. En **Mostrar el crontab actual**, la entrada de esa tarea debe contener `luckybackup -c --no-questions`. Si has activado **Saltar críticos**, también aparecerá `--skip-critical`.

Al actualizar el paquete, la programación existente sigue con la configuración guardada. Activa el modo consola en cada tarea que quieras ejecutar de esa manera.

## Ayuda de las opciones de copia

En **Propiedades de la tarea → Opciones del comando → Plantillas**, pasa el puntero por los botones **?** o púlsalos para leer la ayuda. Debajo de **Borrar los archivos en el destino** aparece un aviso visible sobre las exclusiones y `--ignore-errors`. Si se añade esa opción, rsync puede seguir borrando archivos del destino tras errores de entrada o salida. [Manual de rsync](https://rsync.samba.org/ftp/rsync/rsync.1.html)

Esta versión conserva el motor de copia de luckyBackup. La selección gráfica de archivos y carpetas para una restauración parcial se abordará por separado.

## Instalar la versión de prueba

1. Descarga `luckybackup` y `luckybackup-data` de la misma versión desde los archivos de la publicación.
2. Guarda una copia de `~/.luckyBackup` y conserva los paquetes originales de Ubuntu si quieres tenerlos disponibles para volver atrás.
3. Cierra luckyBackup. En una terminal abierta en la carpeta que contiene únicamente los dos paquetes de prueba, ejecuta:

   ```bash
   sudo apt install ./luckybackup_*.deb ./luckybackup-data_*.deb
   ```

4. Abre luckyBackup y comprueba **Plantillas** y **Planificación**. Puedes revisar los textos sin ejecutar una copia ni aplicar cambios a cron.

## Volver a la versión de Ubuntu

Con luckyBackup cerrado, abre una terminal en la carpeta que contiene los dos paquetes originales 0.5.0-7build3 y ejecuta:

```bash
sudo apt install --allow-downgrades ./luckybackup_0.5.0-7build3_amd64.deb ./luckybackup-data_0.5.0-7build3_all.deb
```

## Código fuente y compilación

El repositorio contiene las modificaciones y el flujo de GitHub Actions para generar los dos paquetes. El flujo utiliza el código fuente y el empaquetado de la versión 0.5.0-7build3, aplica el parche y regenera el catálogo español de Qt. Antes de publicar los paquetes de prueba, comprueba que `luckybackup-data` contiene el catálogo que acaba de generar.

Si encuentras un problema, indica la versión de luckyBackup, tu distribución, si usas Wayland o X11 y los pasos para reproducirlo. Si compartes una captura o un registro, oculta las rutas y los datos personales.

## Autoría y licencia

luckyBackup es obra de **Loukas Avgeriou**. Copyright © 2008–2018 Loukas Avgeriou. Esta variante comunitaria usa el empaquetado de Ubuntu y conserva los avisos de autoría y la GNU General Public License, versión 3, del proyecto original. [Proyecto original en SourceForge](https://sourceforge.net/projects/luckybackup/) · [Licencia GPLv3](https://www.gnu.org/licenses/gpl-3.0.html)

Si te apetece apoyar el trabajo de WonderSkydive en esta edición comunitaria, puedes [hacer una aportación voluntaria por PayPal](https://www.paypal.com/ncp/payment/KWEHYT4HDTARE).
