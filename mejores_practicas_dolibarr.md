
# Mejores Prácticas para el Desarrollo de Módulos en Dolibarr

Este documento recopila las mejores prácticas para desarrollar módulos en Dolibarr, asegurando que tu código sea mantenible, seguro y compatible con futuras versiones del ERP.

## 1. **Estructura del Módulo**

- **Nombre del Módulo**: Elige un nombre significativo y único para tu módulo. Utiliza prefijos o sufijos si es necesario para evitar conflictos con otros módulos.
- **Directorio del Módulo**: Coloca todos los archivos del módulo dentro de un directorio en `htdocs/custom/`. Usa un nombre de directorio que coincida con el nombre del módulo.

```bash
htdocs/custom/mi_modulo/
```

- **Subdirectorios**:
  - `core/`: Contiene las funciones y clases principales del módulo.
  - `class/`: Archivos de clases específicas.
  - `sql/`: Archivos SQL para la creación de tablas y datos iniciales.
  - `langs/`: Archivos de traducción.
  - `scripts/`: Scripts adicionales que tu módulo pueda necesitar.
  - `img/`: Imágenes y otros recursos estáticos.

## 2. **Uso de PSR (PHP Standards Recommendations)**

- **PSR-1 y PSR-2**:
  - Sigue las recomendaciones de codificación PSR-1 y PSR-2 para mantener la uniformidad del código.
  - Utiliza `PascalCase` para nombres de clases y `camelCase` para métodos y funciones.

```php
class MiModulo {
    public function ejecutarAccion() {
        // Código aquí
    }
}
```

- **PSR-4**:
  - Implementa PSR-4 para el autocargado de clases, asegurando que las clases se carguen automáticamente según su namespace y ubicación en el directorio.

## 3. **Estructura de la Base de Datos**

- **Prefijos de Tablas**: Usa el prefijo `llx_` para todas las tablas de tu módulo, asegurando consistencia y evitando conflictos con otras tablas.

```sql
CREATE TABLE llx_mi_modulo_tabla (
    rowid INTEGER PRIMARY KEY AUTOINCREMENT,
    ...
);
```

- **SQL de Creación**: Coloca los scripts SQL para la creación de tablas en el directorio `sql/` dentro de tu módulo.

## 4. **Uso de Hooks y Triggers**

- **Hooks**: Utiliza los hooks de Dolibarr para integrar tu módulo con el núcleo del ERP, en lugar de modificar directamente el código base.
- **Triggers**: Define triggers para ejecutar acciones automáticas cuando se realicen cambios en las tablas del módulo.

```php
function run_trigger($action, $object, $user, $langs, $conf) {
    // Código del trigger
}
```

## 5. **Manejo de Traducciones**

- **Archivos de Traducción**: Coloca los archivos de traducción en el directorio `langs/`. Usa nombres de archivo como `mi_modulo.lang` para asegurar que las traducciones se carguen correctamente.

```ini
[es_ES]
MiModuloTitulo=Mi Módulo
```

- **Función de Traducción**: Usa la función `langs->trans()` para cargar las cadenas de texto traducidas en tu módulo.

```php
echo $langs->trans("MiModuloTitulo");
```

## 6. **Seguridad**

- **Sanitización de Entradas**: Asegúrate de sanitizar y validar todas las entradas de usuario para evitar inyecciones SQL y XSS.
- **Control de Acceso**: Implementa controles de acceso basados en los permisos de usuario configurados en Dolibarr.

```php
if ($user->rights->mi_modulo->leer) {
    // Código accesible solo a usuarios con permiso
}
```

## 7. **Compatibilidad con Versiones**

- **Versiones de Dolibarr**: Asegúrate de que tu módulo sea compatible con múltiples versiones de Dolibarr. Usa la función `dol_version()` para verificar la versión actual y ajustar el comportamiento del módulo si es necesario.

```php
if (dol_version() >= "12.0.0") {
    // Código para versiones 12.0.0 y superiores
}
```

- **Deprecaciones**: Evita el uso de funciones o métodos que hayan sido deprecados en versiones recientes de Dolibarr.

## 8. **Documentación**

- **README.md**: Incluye un archivo `README.md` en la raíz de tu módulo con instrucciones claras sobre cómo instalar y configurar el módulo.
- **Comentarios en el Código**: Documenta tu código utilizando PHPDoc para mejorar la comprensión y mantenimiento.

```php
/**
 * Esta función realiza una acción específica.
 *
 * @param int $param1 El primer parámetro.
 * @return bool Verdadero en caso de éxito, falso en caso contrario.
 */
function miFuncion($param1) {
    // Código de la función
}
```

## 9. **Pruebas**

- **Pruebas Unitarias**: Implementa pruebas unitarias para las funciones y clases clave de tu módulo utilizando frameworks como PHPUnit.
- **Pruebas de Integración**: Realiza pruebas de integración para asegurarte de que tu módulo funcione correctamente con otros módulos y el núcleo de Dolibarr.

## 10. **Mantenimiento y Actualizaciones**

- **Changelog**: Mantén un archivo `CHANGELOG.md` con un historial de cambios y versiones del módulo.
- **Soporte Continuo**: Proporciona actualizaciones regulares para corregir errores y mejorar la funcionalidad.

```markdown
# Changelog

## [1.0.1] - 2024-08-27
### Fixed
- Solución a un problema de compatibilidad con Dolibarr 14.0.0.

## [1.0.0] - 2024-08-20
### Added
- Versión inicial del módulo.
```

## 11. **Mejora Continua**

- **Feedback**: Recoge feedback de los usuarios para mejorar tu módulo.
- **Refactorización**: Revisa y refactoriza el código periódicamente para mejorar la eficiencia y legibilidad.

---

Estas prácticas no solo mejorarán la calidad de tus módulos, sino que también asegurarán su compatibilidad y mantenibilidad en el entorno Dolibarr. Siguiéndolas, podrás desarrollar módulos robustos, seguros y fáciles de integrar.
