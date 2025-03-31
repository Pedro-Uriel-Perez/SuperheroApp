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

# Evidencias de Funcionamiento

## Búsqueda de Superman

<table>
  <tr>
    <td width="33%">
      <img src="https://github.com/user-attachments/assets/66eb4636-ea6d-4095-93d3-d1488bceb072" alt="Pantalla de Búsqueda" width="200"/>
      <p align="center">Pantalla de Búsqueda</p>
    </td>
    <td width="33%">
      <img src="https://github.com/user-attachments/assets/fc49e49d-1519-4f98-836f-f780eac91b79" alt="Lista de Superhéroes" width="200"/>
      <p align="center">Lista de Resultados</p>
    </td>
    <td width="33%">
      <img src="https://github.com/user-attachments/assets/a49e5603-3df5-483e-83ef-c7416c5a470f" alt="Detalle de Superhéroe" width="200"/>
      <p align="center">Detalle del Superhéroe</p>
    </td>
  </tr>
</table>

## Búsqueda de Kick-Ass

<table>
  <tr>
    <td width="50%">
      <img src="https://github.com/user-attachments/assets/2a459001-623c-4719-9130-dc27b666d21a" alt="Lista de Superhéroes" width="200"/>
      <p align="center">Lista de Resultados</p>
    </td>
    <td width="50%">
      <img src="https://github.com/user-attachments/assets/ae801f14-7570-47e1-9378-9783a7d65716" alt="Detalle de Superhéroe" width="200"/>
      <p align="center">Detalle del Superhéroe</p>
    </td>
  </tr>
</table>

## Demostración de Funcionalidades

En las capturas de pantalla podemos observar las principales funcionalidades de la aplicación:

1. **Búsqueda de superhéroes**: La aplicación permite buscar superhéroes por su nombre.

2. **Vista maestro (lista de resultados)**: Muestra los resultados con imagen, nombre y detalles básicos.

3. **Vista detalle**: Al seleccionar un superhéroe, se muestran:
   - Imagen a mayor tamaño
   - Nombre del superhéroe
   - Nombre real
   - Editorial
   - Estadísticas de poder con barras de progreso

4. **Consumo de API**: Se evidencia el correcto consumo de la API de superhéroes al mostrar datos reales.

5. **Interfaz responsive**: La interfaz se adapta correctamente al contenido mostrado.
