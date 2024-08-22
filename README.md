# Dolibarr CMS Module

## Descripción
Este proyecto es un módulo CMS para Dolibarr, inspirado en WordPress y WinterCMS, diseñado para ser simple en su primera versión, pero con la capacidad de escalar y permitir la adición de nuevas características en el futuro. El objetivo es ofrecer un sistema de gestión de contenido dentro de Dolibarr que permita la creación de páginas estáticas, entradas dinámicas, menús, y más, con un enfoque en la facilidad de uso y la extensibilidad.

## Hoja de Ruta - Versión 1.0

### Fase 1: Estructura y Fundamentos
- **Configuración del Módulo:**
  - Crear la estructura básica del módulo en Dolibarr.
  - Definir las tablas de base de datos necesarias (`pages`, `posts`, `categories`, `tags`, `menus`, `comments`, `meta_tags`).
  - Implementar un sistema de permisos para gestionar el acceso al contenido.

### Fase 2: Funcionalidades Esenciales
- **Páginas Estáticas:**
  - Desarrollar la funcionalidad para crear y gestionar páginas estáticas.
  - Implementar un editor WYSIWYG básico para la creación de contenido.
  
- **Entradas Dinámicas:**
  - Permitir la creación de entradas con soporte para etiquetas y categorías.
  - Desarrollar una interfaz para gestionar categorías y etiquetas.

- **Menús Dinámicos:**
  - Crear una interfaz para gestionar menús de navegación dinámicos.
  - Permitir la integración de páginas, enlaces personalizados, y categorías en los menús.

### Fase 3: Interactividad y SEO
- **Comentarios:**
  - Desarrollar un sistema de comentarios para las entradas.
  - Incluir opciones de moderación de comentarios.

- **Enlaces Amigables y SEO:**
  - Implementar enlaces amigables para mejorar el SEO.
  - Permitir la personalización de meta tags para páginas y entradas.

### Fase 4: Extensibilidad y Personalización (Futuro)
- **Widgets y Plugins:**
  - Definir una arquitectura para la extensión del CMS mediante widgets y plugins en versiones futuras.
  - Crear una API básica para la integración de funcionalidades adicionales.

- **Meta Tags Personalizados:**
  - Permitir la configuración de meta tags personalizados desde el backend.

## Consideraciones de Desarrollo
- **Flexibilidad y Escalabilidad:** Arquitectura modular para futuras expansiones.
- **Interfaz de Usuario:** Diseño limpio y moderno, usando Smarty y Bulma.
- **Seguridad:** Implementar buenas prácticas de seguridad desde el principio.

## Próximos Pasos
- Crear un prototipo básico de la estructura del módulo.
- Desarrollar funcionalidades de páginas estáticas y entradas.
- Establecer un sistema de gestión de menús dinámicos.
- Planificar la implementación de SEO y comentarios.

## Contribuciones
Las contribuciones son bienvenidas. Si tienes ideas, sugerencias, o encuentras un problema, por favor, abre un issue o envía un pull request.

## Licencia
Este proyecto está licenciado bajo la [GNU General Public License v3.0](https://www.gnu.org/licenses/gpl-3.0.html), en coherencia con la licencia de Dolibarr.
