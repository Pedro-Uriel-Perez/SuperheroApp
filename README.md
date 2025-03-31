# SuperheroApp
Aplicación multiplataforma Kotlin que consume la API de Superhéroes usando Jetpack Compose



# SuperheroApp - Aplicación Multiplataforma con Kotlin y Jetpack Compose

## Descripción
SuperheroApp es una aplicación multiplataforma (Android e iOS) desarrollada con Kotlin Multiplatform Mobile (KMM) y Jetpack Compose que consume la API de Superhéroes para mostrar información detallada sobre personajes de cómics.

## Objetivos del Proyecto
- Desarrollar una aplicación multiplataforma utilizando KMM
- Implementar una interfaz de usuario con Jetpack Compose
- Consumir una API pública sin autenticación compleja
- Procesar datos JSON y mostrarlos en un formato maestro-detalle
- No utilizar base de datos local para almacenar la información

## API Utilizada
Para este proyecto, se utilizó la **SuperheroAPI** (https://superheroapi.com/):

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

## Arquitectura del Proyecto
El proyecto utiliza una arquitectura limpia (Clean Architecture) con las siguientes capas:

### 1. Capa de Datos (Data Layer)
- **API**: Interfaces y clases para comunicarse con la API de superhéroes
- **Modelo**: Clases de datos que representan la información de los superhéroes

### 2. Capa de Dominio (Domain Layer)
- **Repositorio**: Interfaz y clase que coordina la obtención de datos de la API

### 3. Capa de Presentación (UI Layer)
- **ViewModel**: Gestiona el estado de la UI y la lógica de negocio
- **UI**: Pantallas y componentes implementados con Jetpack Compose

## Estructura del Proyecto KMM
El proyecto está organizado en los siguientes módulos:

- **shared**: Código común compartido entre plataformas
  - Implementación de la lógica de negocio
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

## Desafíos y Soluciones
Durante el desarrollo del proyecto enfrenté varios desafíos:

1. **Configuración de Kotlin Multiplatform**: 
   - Problema: Configuración inicial de la estructura del proyecto KMM.
   - Solución: Investigación de la documentación oficial y uso de plantillas predefinidas.

2. **Integración de Ktor para comunicación con API**:
   - Problema: Configuración de cliente HTTP para realizar peticiones a la API.
   - Solución: Implementación de serializadores y manejo de errores HTTP.

3. **Manejo de estados en Compose**:
   - Problema: Gestión de estados de carga, éxito y error.
   - Solución: Uso de StateFlow y sealed classes para representar los diferentes estados.

4. **Optimización de la búsqueda**:
   - Problema: La aplicación se bloqueaba al realizar múltiples búsquedas.
   - Solución: Cancelación de jobs previos al iniciar una nueva búsqueda.

## Capturas de Pantalla
![Pantalla de Búsqueda](screenshots/search_screen.png)
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
