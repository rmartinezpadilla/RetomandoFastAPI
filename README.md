# FastApi

### Estudio y práctica 

### Objetivos: 
    * Path Operations
    * Validaciones de datos
    * Documentación
    * Tipos de respuestas y códigos de estados
    * Middlewares
    * Dependencias
    * Modularización
    * Manejo de errores  

### Conocimientos previos: 
    * Python
    * Programación orientada a objetos
    * Creación de API Rest      

### ¿Que es fastApi?
FastAPI es un marco web moderno, rápido (de alto rendimiento) para crear API con Python basadas en sugerencias de tipos estándar de Python.

### Características
    * Rápido
    * Código rápido
    * Menos errores
    * Intuitivo
    * Fácil
    * En resumen: Minimiza la duplicación de código
    * Robusto
    * Basado en estándares

### Marcos utilizados por FastApi
    * Starlette
    * Pydantic
    * Uvicorn

### 1. Instalación
Primero necesitas tener Python instalado (idealmente Python 3.10+).
- Primero, instala FastApi:

    1. pip install fastapi[all]

"[all]" instala también uvicorn, que se usa como servidor de desarrollo.

### 2. Tu primera API

```
from fastapi import FastAPI

    app = FastAPI()

    @app.get("/")
    def read_root():
        return {"Hola": "FastAPI"}
```

#### 2.2. Ahora puedes ejecutar tus servicios con:
```
    uvicorn main:app --reload
```
### 3. Endpoints y métodos HTTP
FastAPI soporta:    

    * @app.get() → obtener datos

    * @app.post() → enviar datos

    * @app.put() → actualizar datos

    * @app.delete() → eliminar datos

## Ejemplo:
```
    @app.get("/items/{item_id}")
    def read_item(item_id: int, q: str = None):
        return {"item_id": item_id, "q": q}
```

### 4. Validaciones con Pydantic
Puedes usar modelos de datos con validación automática:
```
    from pydantic import BaseModel

    class Item(BaseModel):
        name: str
        price: float
        is_offer: bool = False

    @app.post("/items/")
    def create_item(item: Item):
        return item
```
### 5. Crear entorno virtual

python -m venv venv

    *   Activar entorno virtual
        - acceder la ruta/ven/scripts/activate
        - ./venv/Scripts/activate

    *   Prueba de instalacion de paquetes al entorno virtual
        - python.exe - pip install --upgrade pip

    *   Extraer requerimientos
        - pip freeze > requirements.txt

    *   Desactivar entorno virtua
        - desactivate (en consola)

    *   Instalar requirements.txt en otro entorno virtual
        - pip install -r (ruta de requirements.txt -> ejemplo ) .\requirements.txt

## Importante:
FastAPI genera automáticamente dos interfaces interactivas:
    
    *   http://localhost:8000/docs → Swagger UI

    *   http://localhost:8000/redoc → Redoc
