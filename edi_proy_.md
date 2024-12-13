
# Documentación General de la API

## Tabla de Contenidos
1. [Introducción](#introducción)
2. [Requisitos Previos](#requisitos-previos)
3. [Instalación](#instalación)
   - [Clonación del Repositorio](#clonación-del-repositorio)
   - [Configuración del Entorno](#configuración-del-entorno)
4. [Uso de Docker](#uso-de-docker)
   - [Construcción de la Imagen](#construcción-de-la-imagen)
   - [Ejecución del Contenedor](#ejecución-del-contenedor)
   - [Detener y Eliminar Contenedores](#detener-y-eliminar-contenedores)
5. [Endpoints de la API](#endpoints-de-la-api)
   - [POST /clasification_image](#post-clasification_image)
6. [Manejo de Errores](#manejo-de-errores)

---

## Introducción
Esta API permite clasificar imágenes de caras en 7 categorias de emociones dadas. 
La aplicacion se puede usar en publicidad como en otros usos.

### Fecha de Actualización
Última actualización: 25-11-2024

---

## Requisitos Previos
- Docker y Docker Compose instalados.
- Git instalado.
- Python 3.10 o superior (para desarrollo).
- Configuración básica del sistema operativo.

## Instalación

### Clonación del Repositorio
Clona el repositorio del proyecto:
```bash

```
## Carga del modelo

El archivo de modelo necesario para ejecutar la API se puedes descargarlo desde el siguiente enlace:
 
[Descargar modelo Clasificador_emociones.h5]()

Por favor, guarda el archivo en la ubicación indicada en la configuración del modelo (/app/Clasificador_emociones.h5 si usas Docker).
 
## Uso de Docker

### Construcción de la Imagen
Construye la imagen de Docker:
```bash
docker build -t nombre-api .
```

### Ejecución del Contenedor
Inicia el contenedor con Docker:
```bash
docker run -d -p 80:80 nombre-api
```
Accede a la API en `http:` para la documentación interactiva.

### Detener y Eliminar Contenedores
Para detener un contenedor:
```bash
docker stop id_contenedor
```
Para eliminarlo:
```bash
docker rm id_contenedor
```

---

## Endpoints de la API

### POST /clasification_image
**Descripción:** Clasifica una imagen para detectar las emociones.

**Request Body:**
- `img_base64` (string): Imagen codificada en Base64.

**Ejemplo:**
```bash
curl -X POST -H "Content-Type: application/json" -d '{"img_base64": "base64_string"}' http://localhost:80/clasification_image
```

**Response:**
```json
{
  "confidence": 0.98,
  "predicted_class": "angry" "neutral" "disgust" "fear" "happy" "sad" "surprise", 
}
```

---

## Manejo de Errores
La API devuelve respuestas HTTP con códigos de error estándar:
- **400**: Error en la solicitud (p. ej., imagen inválida o no soportada).
- **404**: Endpoint no encontrado.
- **500**: Error interno del servidor.

## Observaciones

- Los modelos deben estar entrenados y disponibles en el directorio `/app`.
