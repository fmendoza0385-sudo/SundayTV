# Guía rápida: generar el APK de KoalaTV 1.1.0

## Método recomendado: GitHub Actions

1. En GitHub, crea un repositorio nuevo llamado `koalatv`.
2. Descomprime este ZIP.
3. Entra en la carpeta del proyecto y sube **todos sus archivos y carpetas** al repositorio. Asegúrate de incluir `.github/workflows/build.yml`.
4. Haz el commit a la rama `main`.
5. En GitHub abre la pestaña **Actions**.
6. Selecciona **Compilar KoalaTV (APK)** y pulsa **Run workflow** si el flujo no comenzó automáticamente.
7. Cuando termine correctamente, entra a la ejecución y baja el artefacto **KoalaTV-1.1.0-debug**.
8. Descomprime el artefacto. El archivo `app-debug.apk` es el instalador.

## Si la compilación falla

- Abre la ejecución fallida en **Actions**.
- Entra al paso rojo **Compilar APK debug**.
- Copia el primer error `FAILURE` o `e:` y compártelo para corregirlo.
- No cambies versiones de Gradle o Android Gradle Plugin al azar.

## Importante

- Este paquete contiene el **código fuente**; no contiene todavía un APK compilado.
- El APK debug sirve para pruebas e instalación manual. Para distribución pública se debe preparar una versión release firmada con una clave propia.
- El flujo de GitHub compila con Java 17, Gradle 8.7 y Android SDK 34.
- Esta versión conserva el reproductor Media3/ExoPlayer de KoalaTV y añade persistencia del último canal. No incorpora código fuente GPL de OwnTV; sus funciones se tomaron como referencia de diseño.
