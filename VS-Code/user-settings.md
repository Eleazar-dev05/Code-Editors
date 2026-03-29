# ⌨️ My Minimalist VS Code Setup
Esta es mi configuración personalizada de Visual Studio Code, enfocada en eliminar distracciones visuales y maximizar el área de escritura. Ideal para un flujo de trabajo "Zen" donde el código es el único protagonista.

## 🛠️ Los Ajustes (settings.json)
```json
{
    // --- Window & Theme ---
    "window.autoDetectColorScheme": true,          // Cambio automático entre tema claro/oscuro
    "workbench.statusBar.visible": false,          // Oculta la barra de estado inferior

    // --- Editor Layout (Zen Mode) ---
    "editor.minimap.enabled": false,               // Quita el minimapa a la derecha
    "editor.scrollbar.vertical": "hidden",         // Oculta la barra de desplazamiento
    "breadcrumbs.enabled": false,                  // Quita la ruta de carpetas superior
    "workbench.editor.showTabs": "none",           // Oculta las pestañas de archivos
    "workbench.activityBar.location": "hidden",    // Oculta la barra de iconos lateral
    "workbench.sideBar.location": "right",         // Mueve el explorador a la derecha (evita saltos de texto)

    // --- Cursor & Feedback ---
    "editor.cursorStyle": "block",                 // Cursor estilo terminal
    "editor.cursorBlinking": "expand",             // Animación de parpadeo elegante
    "editor.cursorSmoothCaretAnimation": "explicit", // Movimiento suave del cursor
    "editor.overviewRulerBorder": false,           // Limpia el borde de la regla derecha
    "editor.hideCursorInOverviewRuler": true,

    // --- Typo & Formatting ---
    "editor.fontSize": 13,
    "editor.lineHeight": 1.6,                      // Más aire entre líneas
    "editor.fontLigatures": true,                  // Soporte para ligaduras tipográficas
    "editor.formatOnSave": true,                   // Formateo automático al guardar
    "editor.linkedEditing": true,                  // Edición síncrona de etiquetas HTML/JSX

    // --- UX & Scrolling ---
    "editor.smoothScrolling": true,                // Desplazamiento fluido en el editor
    "workbench.list.smoothScrolling": true         // Desplazamiento fluido en listas y menús
}
```
## 💡 Cómo navegar sin UI
Al ocultar todos los elementos visuales, mi flujo de trabajo se basa en estos atajos:

`Ctrl + P:` Para cambiar entre archivos (ya que no hay pestañas).

`Ctrl + B:` Para mostrar/ocultar el explorador de archivos cuando sea necesario.

`Ctrl + Shift + P:` Para ejecutar cualquier comando.