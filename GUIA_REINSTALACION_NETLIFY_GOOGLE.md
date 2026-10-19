# Guía de actualización y publicación segura

## Diagnóstico del ZIP original
- `index.html` mostraba el CMS de administración en lugar de la portada. La portada real estaba en `index (2).html`. Se corrigió.
- El formulario de contacto ya tenía marcado Netlify Forms, pero recibir mensajes en un correo requiere configurar notificaciones en Netlify.
- Existían copias de archivos de datos y configuración en la raíz que podían provocar errores de mantenimiento. Se retiraron las copias obvias, conservando `data/` y `admin/`.

## Publicación recomendada (sin borrar el sitio en producción)
1. Haz copia de seguridad de tu repositorio y exporta los envíos de formularios del sitio actual.
2. Crea una rama nueva en GitHub y sube el contenido de este ZIP a la raíz de la rama, no el ZIP ni una carpeta contenedora.
3. En Netlify, crea un sitio de prueba con el repositorio y la rama; build command vacío, publish directory `.`.
4. Prueba `index.html`, `/admin/`, `/participacion.html`, enlaces, fotos y envíos de los tres formularios.
5. En Netlify > Forms, verifica que aparezcan `contacto`, `encuesta-comunicacion` y `recepcion-archivos` después del despliegue. Activa detección de formularios si tu configuración lo requiere y vuelve a desplegar.
6. En Forms > notificaciones, agrega una notificación de correo a `utp.esc2025@gmail.com` para nuevos envíos. Envía un mensaje real y comprueba bandeja, spam y Netlify Forms. Las notificaciones no se activan por editar HTML.
7. Revisa los límites de formularios y carga de archivos de tu plan Netlify.
8. Solo tras validar, fusiona la rama a `main` y conecta el dominio personalizado al sitio definitivo.

## Edición desde el panel
- Abre `/admin/`; el CMS usa GitHub como backend y requiere autorizar una cuenta con permisos de escritura sobre el repositorio.
- Configuración del repositorio en `admin/config.yml`: `utpesc2025-beep/escuelasancarlitos`. Cámbiala si creas un repositorio nuevo.
- Los contenidos están en `data/*.json`; las imágenes subidas por CMS en `assets/uploads/`.
- Las encuestas adicionales se administran desde `Encuestas externas` y apuntan a Google Forms.
- Si el acceso con GitHub falla, revisa el método de autenticación de Sveltia CMS, los permisos y la configuración OAuth admitida por la versión vigente. Nunca publiques un token de GitHub.

## Google Drive y servicios Google
1. Inicia sesión en Google con `utp.esc2025@gmail.com`.
2. Crea una carpeta de Drive para documentos públicos de la escuela; comparte solo archivos aprobados, nunca carpetas con datos personales de estudiantes.
3. Para encuestas personalizables, crea un Google Form y enlázalo desde `/admin/` > Encuestas externas. Respuestas se gestionan en Forms o en una hoja de Google Sheets vinculada.
4. Para integrar automáticamente cargas de Netlify con Drive necesitas una función backend autenticada, OAuth 2.0 o una cuenta de servicio autorizada, y almacenamiento seguro de secretos. **Esta automatización NO está configurada en esta entrega**.
5. Google Calendar puede mostrarse con una URL pública de inserción desde la configuración general del CMS.
6. La cuenta Google no queda vinculada por escribir su dirección en el sitio. Autoriza las integraciones solo desde los flujos oficiales de Google.

## Cómo retirar lo anterior y volver a vincular Netlify
1. Antes de borrar, respalda repositorio, dominio/DNS, variables de entorno, registros de formularios y medios.
2. Si quieres reemplazar código, NO necesitas borrar GitHub ni Netlify: actualiza `main` y ejecuta `Trigger deploy` en Netlify. Es la opción más segura.
3. Si necesitas un sitio nuevo, en Netlify agrega un nuevo proyecto importando el repositorio GitHub, selecciona `main`, deja build command vacío y publish directory `.`.
4. Verifica primero el subdominio temporal `*.netlify.app`.
5. En la configuración del dominio del sitio antiguo, desconecta el dominio personalizado y conéctalo al sitio nuevo; ajusta DNS solo si Netlify lo solicita. Espera la emisión del certificado HTTPS.
6. Tras verificar el nuevo sitio, elimina el sitio antiguo desde la configuración de Netlify (zona de peligro / Delete site). Esta operación puede eliminar formularios y despliegues antiguos.
7. Si deseas borrar el repositorio antiguo, hazlo solo después de comprobar que Netlify está vinculado al nuevo repositorio y que el CMS apunta a ese repositorio. En GitHub: Settings > General > Danger Zone > Delete this repository. Es irreversible sin respaldo.

## Pruebas imprescindibles
- Enviar contacto y verificar en Netlify y en el correo destinatario.
- Enviar encuesta y confirmar registro.
- Subir un PDF pequeño de prueba y comprobar que Netlify guarda el archivo.
- Iniciar sesión en `/admin/`, cambiar texto y verificar commit y publicación.
- Abrir desde móvil y escritorio; revisar links y documentos.

## Privacidad y protección
- No solicitar RUT, diagnósticos, certificados médicos ni otros datos sensibles en formularios públicos.
- Para cargas con información personal o escolar reservada, usar una solución autenticada y autorizada institucionalmente.
- Definir aviso de privacidad, consentimiento cuando corresponda y políticas de acceso y retención antes de producción.
