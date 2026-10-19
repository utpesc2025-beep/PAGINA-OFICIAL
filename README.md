# Escuela Básica San Carlitos · Versión 2.0

## Publicación segura
1. Descomprime el ZIP. NO elimines el repositorio ni desconectes Netlify.
2. Crea una rama `redisenio-v2` en GitHub y sube **el contenido interior** de esta carpeta a la raíz de esa rama. No publiques directamente sobre `main` hasta revisar la vista previa de Netlify.
3. En Netlify, revisa Deploy previews de la rama o crea un sitio de prueba independiente. Confirma portada, noticias, documentos, fotos, formularios y `/admin/`.
4. Tras aprobar la vista previa, fusiona la rama a `main`. Netlify desplegará automáticamente si la conexión Git sigue activa.

## Administración
`/admin/` usa Sveltia CMS y el backend GitHub ya configurado para el repositorio existente. Los datos se guardan en `data/*.json`. Para noticias, talleres, actividades, álbumes y videos, marca Publicar. Los talleres y actividades pueden crearse sin límite desde sus listas. La portada muestra los seis primeros de cada categoría. Los álbumes permiten múltiples fotos. La portada, contacto, redes, misión, visión y aviso también son editables.

## Precauciones
- No subas tokens ni claves a GitHub.
- Comprueba autorizaciones para publicar fotos de estudiantes.
- Netlify Forms: realiza un envío de prueba y configura las notificaciones en Netlify; no des por funcional el correo hasta comprobar recepción.
- Calendario: pega una URL pública de inserción `https://calendar.google.com/calendar/embed?...` en el CMS; no pegues una URL privada.
- Las noticias antiguas de prueba sin valor institucional se excluyeron; se conserva la noticia de bienvenida.
- El dominio indicado `wwwescuelasancarlitos.com` no se configuró ni verificó. Revisa su propiedad y DNS antes de conectarlo.
- La vista previa de cambios sin publicar en el CMS depende del soporte de Sveltia para este tipo de colección; usa la vista previa de Netlify para verificar el sitio completo.
- Los documentos oficiales se incluyen sin modificar; verifica con Dirección su autorización y vigencia antes de hacer pública la nueva versión.

## Estructura
`index.html`, `noticias.html`, `galeria.html`, `documentos.html`, `admin/config.yml`, `data/*.json`, `assets/css/styles.css`, `assets/js/app.js`, `assets/img`, `assets/uploads`, `documentos/`. No hay duplicados de `config.yml` ni archivos JS de versiones antiguas en la raíz.

## Actualización fotográfica 21-09-2026
Se incorporaron 20 fotografías reales optimizadas en WebP. Portada: `frontis.jpeg`. Se crearon 4 álbumes editables y los 13 talleres informados para 2026, con campos editables de descripción, responsable, horario, cursos y fotografías. Los campos no proporcionados quedan vacíos o marcados pendientes; NO se atribuyen fotografías de infraestructura a actividades realizadas. Para cambiar fotos y textos usa `/admin/` > Talleres JEC / Álbumes fotográficos / Datos generales.

**Importante:** este ZIP es una nueva versión para subir a una rama de prueba de GitHub. No se ha modificado tu repositorio ni se ha publicado en Netlify. Revisa la vista previa y las autorizaciones de imágenes antes de fusionar a `main`.
