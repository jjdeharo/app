# Editor LaTeX para docentes

## Descripción del proyecto

Este conjunto de herramientas permite a los docentes crear y editar fórmulas matemáticas de manera visual, facilitando la creación de material educativo con notación matemática profesional.

## Componentes del sistema

### 1. Editor principal (index.html)
La aplicación principal que permite:
- Escribir código LaTeX directamente en un editor de texto.
- Ver la previsualización en tiempo real de las fórmulas.
- Acceder a un menú organizado por categorías con comandos LaTeX comunes.
- Copiar el código LaTeX generado.
- Visualizar y descargar las fórmulas como imágenes PNG.

**Uso típico:**
- Abrir el archivo index.html en cualquier navegador web.
- Seleccionar comandos del menú superior o escribir directamente en el editor.
- Copiar el código LaTeX para usar en otros documentos.
- Descargar imágenes de las fórmulas para presentaciones.

### 2. Editor de menús (editor_menu.html)
Herramienta de administración que permite editar el archivo `formulas.json`:
- Cargar y modificar el archivo de configuración JSON.
- Añadir, editar o eliminar categorías de comandos.
- Crear nuevos elementos LaTeX con vista previa.
- Reorganizar elementos mediante arrastrar y soltar.
- Exportar la configuración personalizada.
- **Pegar contenido generado por IA**: solicitar a una IA que genere categorías o elementos en formato JSON y pegarlos directamente.

**Características avanzadas:**
- Modo de pegado para importar elementos desde otras fuentes.
- Generador de matrices personalizadas.
- Sistema de plantillas para elementos complejos.
- **Integración con IA**: capacidad de pegar contenido JSON generado por asistentes de inteligencia artificial.

### 3. Archivo de configuración (formulas.json)
Base de datos en formato JSON que contiene:
- Organización de comandos LaTeX por categorías temáticas.
- Código LaTeX para insertar en el editor.
- Código LaTeX alternativo para visualización.
- Títulos descriptivos para cada comando.
- Configuración de diseño de cada categoría.

## Instalación y uso básico

### Requisitos
- Navegador web moderno (Chrome, Firefox, Safari, Edge).
- Conexión a internet (para cargar las librerías matemáticas).

### Pasos para usar
1. Descargar los tres archivos en una carpeta (`index.html`, `editor_menu.html` y `formulas.json`).
2. Abrir `index.html` en el navegador.
3. Comenzar a crear fórmulas usando el menú o escribiendo directamente.
4. Para personalizar el menú, usar `editor_menu.html` para modificar `formulas.json`.

## Personalización del menú

### ¿Por qué personalizar?
Cada docente puede necesitar comandos específicos según su materia:
- Física: vectores, derivadas, integrales.
- Química: fórmulas moleculares, reacciones.
- Estadística: distribuciones, probabilidades.
- Geometría: figuras, ángulos, medidas.

### Proceso de personalización

#### Opción 1: Usar inteligencia artificial (más rápido)
1. Abrir `editor_menu.html` en el navegador.
2. Solicitar a una IA (Claude, ChatGPT, etc.) que genere contenido específico:
   - **Para una categoría completa**: "Genera una categoría JSON para trigonometría con 10 comandos LaTeX básicos"
   - **Para elementos individuales**: "Crea 5 elementos JSON para comandos de estadística descriptiva"
3. Especificar el formato requerido mostrando un ejemplo del archivo `formulas.json`.
4. Copiar la respuesta de la IA.
5. Usar el botón "Pegar" en el editor y seleccionar una de las **tres opciones disponibles**:
   - **JSON Completo**: Para pegar una estructura completa con múltiples categorías
   - **Categoría**: Para pegar una categoría individual con sus elementos
   - **Elemento**: Para pegar un botón/comando individual en una categoría existente
6. Si eliges "Elemento", seleccionar la categoría de destino donde se añadirá.
7. Revisar y ajustar si es necesario.
8. Exportar el archivo JSON personalizado.

**Ejemplo de prompt para IA:**
```
Genera una categoría JSON para ecuaciones diferenciales con 8 comandos LaTeX.
Usa este formato:
{
  "nombre": "Ecuaciones diferenciales",
  "id": "ecuaciones-diferenciales", 
  "grid_template_columns": "repeat(auto-fit, minmax(120px, 1fr))",
  "elementos": [
    {
      "type": "button",
      "latex": "\\frac{dy}{dx}",
      "title": "Derivada primera"
    }
  ]
}
```

**Tipos de contenido que puede generar la IA:**

- **Para JSON completo**: "Crea un archivo completo con 5 categorías para física básica"
- **Para una categoría**: "Genera la categoría 'Trigonometría' con 12 funciones trigonométricas"
- **Para elementos individuales**: "Crea 3 comandos LaTeX para raíces (cuadrada, cúbica, n-ésima)"

#### Opción 2: Usar el editor visual
1. Abrir `editor_menu.html` en el navegador.
2. Cargar el archivo `formulas.json` usando el botón "Cargar JSON".
3. Añadir o modificar categorías y elementos según necesidades.
4. Exportar el archivo `formulas.json` modificado usando "Exportar JSON".

#### Opción 3: Editar manualmente el JSON
```json
{
  "categorias": [
    {
      "nombre": "Mi categoría",
      "id": "mi-categoria",
      "grid_template_columns": "repeat(auto-fit, minmax(80px, 1fr))",
      "elementos": [
        {
          "type": "button",
          "latex": "\\mi_comando{}",
          "display": "\\mi_comando{x}",
          "title": "Descripción del comando"
        }
      ]
    }
  ]
}
```

**Explicación de campos clave:**
- `grid_template_columns`: Controla cómo se organizan los botones en filas y columnas
  - `repeat(auto-fit, minmax(80px, 1fr))`: Crea columnas automáticamente según el espacio disponible
  - `80px`: Ancho mínimo de cada botón
  - `1fr`: Los botones se expanden para llenar el espacio restante
  - **Ejemplos prácticos:**
    - `"repeat(auto-fit, minmax(60px, 1fr))"`: Botones más pequeños (símbolos simples)
    - `"repeat(auto-fit, minmax(120px, 1fr))"`: Botones más anchos (fórmulas complejas)
    - `"repeat(3, 1fr)"`: Siempre 3 columnas de igual ancho

### Publicación de menús personalizados

#### GitHub (recomendado)
1. Crear una cuenta gratuita en [GitHub](https://github.com).
2. Crear un nuevo repositorio público.
3. Subir el archivo `formulas.json` personalizado.
4. Obtener la URL del archivo raw.
5. Modificar en `index.html` la línea:
```javascript
const url = 'https://raw.githubusercontent.com/jjdeharo/app/refs/heads/main/mat/editor_latex/formulas.json';
```
Y cambiar esa dirección por la del usuario.

#### Otras opciones
- **Google Drive**: compartir el archivo JSON con acceso público.
- **Dropbox**: usar enlaces públicos para el archivo.
- **Servidor web propio**: subir el archivo a un servidor personal.

## Casos de uso educativo

### Para docentes de matemáticas
- Crear exámenes con fórmulas complejas.
- Generar material de apoyo visual.
- Preparar presentaciones con notación matemática.

### Para docentes de física
- Documentar ecuaciones y leyes físicas.
- Crear problemas con notación vectorial.
- Desarrollar apuntes con fórmulas específicas.

### Para docentes de química
- Escribir ecuaciones químicas balanceadas.
- Documentar fórmulas moleculares.
- Crear ejercicios de estequiometría.

## Consejos prácticos

### Uso de inteligencia artificial
- **Prompt específico**: describir claramente qué comandos necesitas ("comandos de cálculo diferencial", "fórmulas de geometría plana").
- **Mostrar formato**: incluir un ejemplo del JSON actual para que la IA mantenga la estructura correcta.
- **Revisar siempre**: verificar que los comandos LaTeX generados sean válidos antes de usarlos.
- **Iterar**: pedir ajustes o correcciones si el resultado no es el esperado.

### Organización del menú
- Agrupar comandos por tema o frecuencia de uso.
- Usar nombres descriptivos para las categorías.
- Incluir tooltips explicativos en cada botón.

### Creación de comandos
- Probar cada comando antes de guardarlo.
- Usar códigos de visualización alternativos cuando sea necesario.
- Incluir ejemplos representativos en las previsualizaciones.

### Mantenimiento
- Hacer copias de seguridad del archivo JSON personalizado.
- Documentar los cambios realizados.
- Probar regularmente que los enlaces externos funcionen.

## Solución de problemas comunes

### El menú no carga
- Verificar la conexión a internet.
- Comprobar que la URL del JSON sea correcta y accesible.
- Revisar la sintaxis del archivo JSON.

### Las fórmulas no se muestran
- Asegurar que el código LaTeX sea válido.
- Verificar que MathJax se haya cargado correctamente.
- Comprobar la consola del navegador para errores.

### El editor de menús no funciona
- Verificar que el archivo JSON tenga el formato correcto.
- Comprobar que todos los campos obligatorios estén presentes.
- Reiniciar el navegador si es necesario.

## Recursos adicionales

### Documentación LaTeX
- [Guía de comandos LaTeX básicos](https://es.wikibooks.org/wiki/Manual_de_LaTeX)
- [Símbolos matemáticos en LaTeX](https://oeis.org/wiki/List_of_LaTeX_mathematical_symbols)

### Herramientas complementarias
- **Detexify**: identificar símbolos LaTeX dibujándolos.
- **Mathpix**: convertir imágenes de fórmulas a LaTeX.
- **Overleaf**: editor LaTeX online completo.

## Licencia y distribución

Este proyecto está disponible bajo licencia Creative Commons BY-SA, lo que permite:
- Usar libremente para fines educativos.
- Modificar y adaptar según necesidades.
- Distribuir las modificaciones bajo la misma licencia.
- Dar crédito al autor original.

---

**Contacto**: Para dudas o sugerencias sobre estas herramientas, consultar la documentación original o contactar con el desarrollador a través de los enlaces incluidos en la aplicación.
