# Editor LaTeX online

## ¿Qué es esto?

Este proyecto es una herramienta gratuita pensada para que docentes puedan crear y editar fórmulas matemáticas fácilmente, sin necesidad de conocer a fondo el lenguaje LaTeX. Permite generar materiales educativos con notación matemática clara, profesional y bien presentada.

## ¿Qué incluye?

### 1. index.html → El editor de fórmulas

* Escribes el código LaTeX o eliges fórmulas del menú.
* Ves la previsualización en tiempo real.
* Puedes copiar el código para usarlo en otras plataformas.
* También puedes descargar la fórmula como imagen PNG para presentaciones o documentos.

### 2. editor\_menu.html → El editor del menú de botones

* Permite modificar el menú que aparece en el editor.
* Puedes añadir, cambiar o quitar categorías y botones.
* Admite copiar y pegar contenido generado por una IA, como ChatGPT.
* Vista previa instantánea de cada cambio.
* Todo se guarda en el archivo `formulas.json`.

### 3. formulas.json → El archivo de configuración

* Contiene todas las categorías y botones del menú.
* Cada botón tiene un título, un código LaTeX para insertar y otro para mostrar (opcional).
* Se puede editar visualmente desde `editor_menu.html`.

## ¿Cómo empiezo?

Para poder personalizar el menú del editor online y adaptarlo a tus necesidades como docente, sigue estos pasos:

1. Descarga los tres archivos: `index.html`, `editor_menu.html` y `formulas.json`.
2. Ábrelos desde tu ordenador o súbelos a un servidor web (por ejemplo, GitHub Pages).
3. Abre `index.html` para escribir fórmulas.
4. Si quieres modificar el menú de botones, abre `editor_menu.html`.

## ¿Puedo personalizarlo?

Sí, puedes hacerlo de dos maneras:

### Opción 1: Con ayuda de una IA (como ChatGPT)

Puedes pedirle a una IA que genere comandos o categorías en formato JSON. Por ejemplo:

```json
{
  "nombre": "Trigonometría",
  "id": "trigonometria",
  "grid_template_columns": "repeat(auto-fit, minmax(120px, 1fr))",
  "elementos": [
    {
      "type": "button",
      "latex": "\\sin",
      "title": "Seno"
    }
  ]
}
```

Después, lo pegas en `editor_menu.html` con el botón "Pegar" y seleccionas si es una categoría o un elemento. A partir de ahí, puedes ajustarlo visualmente igual que en la opción 2.

### Opción 2: Usar el editor visual

1. Abre `editor_menu.html`.
2. Carga o pega el archivo `formulas.json`.
3. Añade, edita o borra lo que necesites.
4. Exporta o copia el resultado final.

## ¿Dónde puedo alojar mis archivos?

### Recomendado: GitHub Pages

1. Crea una cuenta en [GitHub](https://github.com).
2. Sube los archivos a un repositorio público.
3. Copia el enlace "raw" de tu `formulas.json`.
4. Sustituye la línea correspondiente en `index.html`:

```js
const url = 'https://raw.githubusercontent.com/usuario/repositorio/ruta/formulas.json';
```

## Licencia

Este proyecto tiene licencia Creative Commons BY-SA. Puedes usarlo, modificarlo y compartirlo libremente, siempre que cites al autor y mantengas la misma licencia en tus versiones.

---

**Autor**: Juan José de Haro
[https://bilateria.org](https://bilateria.org)
