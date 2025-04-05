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

#### 2.2. Ejecutar:
```
    uvicorn main:app --reload
```

#### 2.4. Define los steps en JavaScript
Crea steps/loginSteps.js:

    const { Given, When, Then, Before, After } = require('@cucumber/cucumber');

    Before(async function () {
        await this.launchBrowser();
    });
    
    After(async function () {
        await this.closeBrowser();
    });
    
    Given('el usuario abre la página de login', async function () {
        await this.page.goto('https://example.com/login');
    });

    When('el usuario ingresa {string} y {string}', async function (usuario, contraseña) {
        await this.page.fill('input[name="username"]', usuario);
        await this.page.fill('input[name="password"]', contraseña);
        await this.page.click('button[type="submit"]');
    });
    
    Then('el usuario debería ver la página de inicio', async function () {
        await this.page.waitForSelector('#dashboard');
    });

### 3. Configurar el package.json para ejecutar las pruebas
En package.json, agrega el siguiente script para ejecutar las pruebas:

    "scripts": {
      "test": "cucumber-js"
    }

## Ahora puedes ejecutar tus pruebas con:
    npm test

## Importante:
Para ejecutar solo un archivo .feature específico con Cucumber, usa el siguiente comando:
    
    sh
    npx cucumber-js features/login.feature

Si tus archivos .feature están en una subcarpeta, asegúrate de proporcionar la ruta correcta, por ejemplo:

    sh
    npx cucumber-js features/autenticacion/login.feature
También puedes filtrar escenarios usando tags. Por ejemplo, si en tu .feature tienes:

gherkin
@regresion
Scenario: Usuario inicia sesión correctamente
Puedes ejecutar solo los escenarios con ese tag:
sh
npx cucumber-js --tags @regresion
