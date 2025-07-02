# Planificador de Rutas con OpenStreetMap

Una aplicación web sencilla y potente para planificar rutas con múltiples paradas utilizando OpenStreetMap. Permite añadir, editar y reordenar lugares para visualizar el recorrido en un mapa interactivo.

## Características

- **Mapa interactivo integrado**: Visualiza tu ruta directamente en la página sin necesidad de abrir nuevas pestañas, gracias a Leaflet.js.
- **Gestión de paradas**: Añade, edita, elimina y reordena las paradas de tu ruta fácilmente.
- **Reordenación intuitiva**: Cambia el orden de las paradas simplemente arrastrándolas y soltándolas.
- **Selección de transporte**: Calcula la ruta para coche, bicicleta o a pie, y verás cómo el recorrido y el tiempo estimado se actualizan al instante.
- **Información de la ruta**: Obtén una estimación de la distancia total y el tiempo del viaje.
- **Temas claro y oscuro**: Incluye un modo oscuro que se activa manual o automáticamente según la configuración de tu sistema.
- **Multilingüe**: Interfaz disponible en catalán y español, con detección automática del idioma del navegador.
- **Configuración persistente**: La aplicación recuerda el último idioma y tema que has seleccionado.
- **Diseño adaptable**: La interfaz se ajusta correctamente a dispositivos de escritorio, tabletas y móviles.

## Tecnologías utilizadas

Este proyecto está construido exclusivamente con tecnologías web estándar, sin depender de ningún *framework* complejo.

- **HTML5**
- **CSS3** con **Tailwind CSS** para un diseño rápido y adaptable.
- **JavaScript (Vanilla)** para toda la lógica de la aplicación.
- **Leaflet.js**: Para la creación del mapa interactivo.
- **Leaflet Routing Machine**: Para dibujar las rutas sobre el mapa.
- **API de Nominatim**: Para la geocodificación (convertir nombres de lugares en coordenadas).
- **API de OSRM (Open Source Routing Machine)**: Para el cálculo de las rutas.
- **SortableJS**: Para la funcionalidad de arrastrar y soltar en la lista de paradas.

## Cómo utilizarlo localmente

No necesitas ninguna herramienta de compilación ni servidor complejo. Solo tienes que seguir estos pasos:

1.  Clona o descarga este repositorio en tu ordenador.
2.  Abre el archivo `index.html` directamente en tu navegador web preferido.

## Créditos y licencia

Este proyecto es una adaptación y mejora de la idea original de **Raül Torres**.

- **Desarrollo y adaptación**: Juan José de Haro ([bilateria.org](https://bilateria.org)).
- **Idea original**: Raül Torres ([Proyecto original](https://raultorres-ia.github.io/apps/rutes/rutes.html)).

Esta obra está bajo una [Licencia Creative Commons Atribución-CompartirIgual 4.0 Internacional](https://creativecommons.org/licenses/by-sa/4.0/deed.es).
