# Albion Tracker Mobile

Aplicación Flutter para consultar desde Android las estadísticas de Albion Online capturadas por SAT en un PC. Se conecta a [Albion Tracker Desktop](https://github.com/SebastianMejia1203/albion-tracker-desktop) mediante la red local y recibe datos con SignalR.

## Funcionalidades

- Dashboard de sesión con fama, plata y progresión.
- Medidor de daño y curación: DPS y HPS.
- Historial de mazmorras, intercambios y mapas.
- Estadísticas de recolección y datos de grupo local.
- Información de gremio y registros de actividad.
- Detección del servidor y configuración manual de conexión.
- Tema claro y oscuro e interfaz en español e inglés.

## Estado de las integraciones

La plataforma principal es Android. En esta versión las integraciones de Firebase y anuncios están deshabilitadas, y la función de grupo compartido en la nube no está disponible.

## Requisitos

- Flutter compatible con la restricción de Dart declarada en `pubspec.yaml`: `>=3.2.0 <4.0.0`.
- Toolchain de Android y dispositivo o emulador.
- PC con la adaptación de SAT que incluye el servidor móvil.
- Ambos dispositivos conectados a la misma red local.

## Inicio local

```bash
flutter pub get
flutter run
```

Para comprobar el código y generar un APK:

```bash
flutter analyze
flutter build apk --release
```

La generación de una versión de distribución requiere preparar la configuración de firma de Android.

## Conexión

1. Inicia SAT y su servidor móvil en el PC.
2. Abre la app y utiliza la detección automática o introduce IP y puerto.
3. Consulta las métricas en las pestañas de la aplicación.

Si no conecta, verifica IP, puerto, firewall y que SAT esté recibiendo eventos del juego. El servidor de escritorio usa `7777` por defecto.

## Estructura

| Ruta | Contenido |
| --- | --- |
| `lib/models/` | Modelos de datos |
| `lib/providers/` | Estado y lógica de presentación |
| `lib/screens/` | Pantallas |
| `lib/services/` | Conexión con SAT |
| `lib/theme/` y `lib/widgets/` | Tema y componentes |
| `android/` | Configuración de Android |

## Documentación y contribuciones

Consulta la [política de privacidad](privacy_policy.html). Antes de proponer cambios, ejecuta `flutter analyze` y describe cómo verificaste la conexión con SAT.
