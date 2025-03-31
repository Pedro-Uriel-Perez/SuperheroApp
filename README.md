# SuperheroApp - Aplicación Multiplataforma con Kotlin y Jetpack Compose

## Descripción
SuperheroApp es una aplicación multiplataforma desarrollada con Kotlin Multiplatform Mobile (KMM) y Jetpack Compose que consume la API de Superhéroes para mostrar información detallada sobre personajes de cómics.

## API Utilizada
Para este proyecto, utilize la **SuperheroAPI** (https://superheroapi.com/):

### Características de la API:
- API gratuita que proporciona información detallada sobre superhéroes de cómics
- Endpoints sencillos que facilitan su consumo
- Datos variados como nombres, biografías, estadísticas de poder e imágenes
- Permite búsqueda por nombre de superhéroe

### Endpoints utilizados:
- **Búsqueda**: `https://superheroapi.com/api/{access-token}/search/{name}`
  - Devuelve una lista de superhéroes que coincidan con el nombre buscado
- **Detalle**: `https://superheroapi.com/api/{access-token}/{hero-id}`
  - Devuelve información detallada de un superhéroe específico

### Estructura de datos:
La API devuelve datos en formato JSON con la siguiente estructura principal:
```json
{
  "response": "success",
  "results-for": "batman",
  "results": [
    {
      "id": "69",
      "name": "Batman",
      "powerstats": {
        "intelligence": "81",
        "strength": "40",
        "speed": "29",
        "durability": "55",
        "power": "63",
        "combat": "90"
      },
      "biography": {
        "full-name": "Bruce Wayne",
        "publisher": "DC Comics"
      },
      "image": {
        "url": "https://www.superherodb.com/pictures2/portraits/10/100/639.jpg"
      }
    }
  ]
}
```

## Estructura del Proyecto KMM
El proyecto está organizado en los siguientes módulos:

- **shared**: Código común compartido entre plataformas
  - Modelos de datos
  - Comunicación con la API
  - ViewModels

- **androidApp**: Implementación específica para Android
  - UI con Jetpack Compose
  - Navegación entre pantallas

- **iosApp**: Implementación específica para iOS (estructura base)

## Funcionalidades
- Búsqueda de superhéroes por nombre
- Visualización de lista de resultados (vista maestro)
- Visualización de detalles de un superhéroe específico (vista detalle)
- Visualización de estadísticas de poder mediante barras de progreso
- Carga de imágenes de superhéroes


## Capturas de Pantalla
![Pantalla de Búsqueda](![image](https://github.com/user-attachments/assets/66eb4636-ea6d-4095-93d3-d1488bceb072)
![Lista de Superhéroes](screenshots/heroes_list.png)
![Detalle de Superhéroe](screenshots/hero_detail.png)

## Herramientas y Tecnologías
- **Kotlin Multiplatform Mobile**: Para compartir código entre plataformas
- **Jetpack Compose**: Para la interfaz de usuario en Android
- **Ktor**: Para la comunicación con la API
- **Kotlinx Serialization**: Para procesar JSON
- **Kotlinx Coroutines**: Para programación asíncrona
- **Coil**: Para cargar imágenes

## Ejecución del Proyecto
1. Clona el repositorio
2. Abre el proyecto en Android Studio (Arctic Fox o superior)
3. Sincroniza el proyecto con Gradle
4. Ejecuta la aplicación en un emulador o dispositivo Android

## Mejoras Futuras
- Implementación completa de la interfaz de usuario para iOS
- Añadir filtros por categorías (editores, alineación, etc.)
- Implementar favoritos usando almacenamiento local
- Mejorar el diseño visual con animaciones y transiciones
