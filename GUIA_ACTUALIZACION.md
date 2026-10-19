# Escuela San Carlitos — revisión integral v2

## Cambios implementados
- Equipo directivo ahora se dibuja desde `data/team.json` en portada.
- Se corrigió ID duplicado de videos.
- Se muestran todas las secciones editables de `data/pages.json` con su imagen y texto completo.
- Talleres y actividades tienen páginas de listado propias y fichas de detalle, incluidas fotos, video, responsable, cursos y horarios cuando se completen en CMS.
- Se amplió el menú, se añadieron controles de contraste y tamaño de letra.
- Los datos se siguen leyendo desde los diez JSON que edita Sveltia CMS.

## Publicación segura
1. NO elimines el sitio Netlify ni el dominio. Descomprime este ZIP.
2. En el repositorio correcto `utpesc2025-beep/escuelasancarlitos`, sube el CONTENIDO de la carpeta del proyecto a la rama `main`, manteniendo la estructura de carpetas. Preferiblemente usa Git local para reemplazar archivos con un commit y push.
3. En Netlify, revisa que el repositorio conectado sea exactamente el mismo y que el directorio de publicación sea `.`. Si figura `Auto Publishing Locked`, desbloquéalo desde Deploys antes de esperar publicaciones automáticas.
4. Comprueba el commit publicado y abre la web en una ventana privada. Comprueba también `/admin/`.
5. Para usar Sveltia, la cuenta GitHub o token debe tener acceso de escritura al repositorio; la configuración indica `backend: github`, repositorio y rama. Nunca compartas el token en el chat ni lo subas al repositorio.

## Datos pendientes (no inventados)
`data/activities.json`, `data/events.json` y `data/videos.json` están vacíos. `data/general.json` no tiene URL de calendario. Las fotografías del equipo directivo y muchos talleres no están cargadas. La publicación de contenidos desde CMS requiere acceso GitHub funcional. Verifica Netlify Forms enviando una prueba y consultando Forms en Netlify; no se ha probado en producción.

## Cómo editar
En `/admin/`, abre la colección correspondiente, cambia el texto o sube imágenes y guarda/publica. Los cambios deben generar un commit en GitHub; Netlify debe publicar ese commit. Los archivos JSON nunca se editan a mano si el CMS ya funciona. Para noticias, talleres y álbumes, los campos de fotos están configurados en `admin/config.yml`.

## Privacidad
Antes de publicar fotos de estudiantes, comprueba autorizaciones de uso de imagen y evita divulgar información personal de menores.
