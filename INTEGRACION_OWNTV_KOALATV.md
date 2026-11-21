# KoalaTV — integración funcional inspirada en OwnTV

## Alcance de esta entrega

Esta versión conserva la aplicación KoalaTV existente y añade persistencia del último canal visto.

### Cambio implementado
- Al sintonizar un canal, KoalaTV guarda su URL, nombre y número en `SharedPreferences`.
- Al abrir la aplicación, busca primero la URL guardada dentro del catálogo de canales actual.
- Si el canal ya no existe en las listas cargadas, utiliza el canal predeterminado de `ChannelStore`.
- La reproducción sigue iniciándose desde el flujo actual de `SplashActivity` → `MainActivity`.

### Funciones preexistentes conservadas
- Media3 / ExoPlayer.
- Lectura de listas M3U y M3U8.
- Numeración de canales desde 100.
- OSD y reloj.
- Lista lateral de canales.
- CH+/CH−, navegación con D-pad y selección numérica.
- Importación y administración de listas adicionales.
- Reintentos de reproducción cuando ocurre un error.

## Relación con OwnTV

Se revisó el archivo fuente OwnTV entregado por el usuario. OwnTV está bajo GPL-3.0 y su ZIP de aplicación declara dependencias externas de OwnTV Core y del motor libmpv. El ZIP recibido no contiene el código fuente completo de esos componentes.

Para mantener la posibilidad de distribuir KoalaTV como producto propietario, esta integración NO copia ni enlaza código de OwnTV ni su OwnTV Core. Se implementa de forma independiente una mejora funcional equivalente (recordar el último canal), tomando OwnTV únicamente como referencia de producto.

Si en el futuro se decide incorporar código GPL-3.0 de OwnTV o de OwnTV Core, habrá que revisar y aceptar las obligaciones de GPL-3.0 para el conjunto derivado antes de distribuirlo.

## Pendiente para una siguiente fase
1. EPG XMLTV y asociación de `tvg-id`.
2. Mejoras del OSD: programa actual/siguiente y datos técnicos.
3. Evaluar un segundo motor multimedia independiente y compatible con la estrategia de licencia.
4. Ajustes de inicio automático y recuperación al despertar, con pruebas en TV Box reales.
5. Pruebas de compilación e instalación en Android TV y teléfono Android.

## Limitación de validación
Esta entrega contiene el código fuente modificado. No se declara compilación APK exitosa: en el entorno de edición no estaba disponible Gradle/Android SDK para ejecutar el build. La compilación está prevista mediante el workflow de GitHub incluido en el proyecto.
