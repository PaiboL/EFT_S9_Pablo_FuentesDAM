# SeñalSegura · Evaluación Final Transversal S9

**Entrega:** domingo 11 de octubre de 2026 a las 23:59, hora de Chile. Adjuntar este ZIP y el enlace del video individual de Kaltura en la misma entrega del AVA.

Aplicación Android en Kotlin, Jetpack Compose y Material 3 orientada a la comunicación accesible para personas con discapacidad auditiva. Paquete `cl.duoc.senalsegura`, versión `1.1.0` (`versionCode` 9), Android API 24 o superior.

## Recorrido principal

1. Registro, inicio de sesión y recuperación mediante Firebase Authentication.
2. Saludo, escritura de un mensaje o selección de una frase rápida.
3. Presentación visual, solicitud de voz sintetizada o alerta visual con vibración.
4. Registro de la interacción como alerta de categoría `Comunicación` en `alerts/{uid}/{id}`.
5. Consulta de historial, perfil y CRUD de alertas desde **Historial y datos guardados**.
6. Ayuda de cinco pasos desde **Cómo usar la aplicación** en Inicio.

`FirebaseBackendRepository` organiza las operaciones por UID. Las reglas de `firebase.database.rules.json` limitan el acceso a la cuenta autenticada. La configuración de cliente `app/google-services.json` está incluida para el proyecto Firebase usado en la asignatura. Su presencia no demuestra que los servicios o reglas estén activos al momento de la evaluación: compruébalos en el dispositivo y en Firebase Console.

Si Firebase no está configurado, la aplicación ofrece un respaldo local de demostración. Los registros de ese respaldo duran solo mientras la aplicación permanece en memoria; la persistencia entre sesiones requiere Firebase.

## Contenido de la entrega

- `app/src/main/`: código y recursos de la aplicación.
- `app/src/test/`: pruebas JUnit.
- `presentacion/EFT_S9_Pablo_Fuentes.pptx`: material gráfico basado en la plantilla oficial (12 diapositivas).
- `presentacion/GUIA_GRABACION_EFT_S9.md`: pauta de exposición y demostración de 10 a 15 minutos.
- `distribucion/SenalSegura-1.1.0-EFT-S9.apk`: APK release firmado.
- `distribucion/evidencia_firma/`: salida de verificación de la firma, huella del APK y descripción de la evidencia.
- `documentacion/resultados_pruebas_S9/`: reporte HTML y XML.
- `documentacion/VERIFICACION_EFT_S9.txt`: versión, firma, alineación, huella y pruebas.
- `.git/`: historial del proyecto; las modificaciones S8/S9 se incluyen en el árbol de trabajo local.

## Compilar y probar

Abre esta carpeta en Android Studio con JDK 21, Android SDK 36 y Build Tools 36.1.0. El proyecto usa Gradle 9.5.0 y Android Gradle Plugin 9.3.1.

```bash
./gradlew testDebugUnitTest
./gradlew assembleRelease
```

La ejecución de esta entrega verificó 43 pruebas JUnit aprobadas, cero fallos/errores/omisiones, y una compilación release satisfactoria. No se ejecutaron pruebas instrumentadas ni una instalación en un dispositivo físico en este entorno. Antes de grabar, verifica el flujo completo en tu equipo Android y el acceso efectivo a Firebase.

## Distribución y video

El APK de esta entrega fue firmado con una nueva clave temporal resguardada fuera del ZIP. Como la clave privada de la versión S8 no se entregó, Android no aceptará instalar la versión S9 como actualización sobre ese APK anterior: desinstala la versión S8 antes de instalar S9 y considera que se borrarán sus datos locales. Conserva una clave de carga permanente para cualquier publicación futura.

La aclaración docente sobre no comprar una cuenta de Google Play permite explicar ese proceso en la presentación. La pauta escrita conserva un criterio de disponibilidad en una plataforma descargable; si deseas acreditarlo, puedes usar una plataforma gratuita y verificar su enlace. `presentacion/GUIA_GRABACION_EFT_S9.md` detalla el recorrido y el enlace de Kaltura que se debe adjuntar en AVA. Este ZIP no acredita una carga externa ni una grabación ya realizada.

Repositorio remoto previo: https://github.com/PaiboL/Exp2_S5_Pablo_FuentesDAM. Las modificaciones S8/S9 incluidas aquí no se subieron automáticamente a ese remoto.
