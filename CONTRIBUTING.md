# 🤝 Contribuciones

Gracias por contribuir a este proyecto.

## Normativas Generales
- Todo el código se debe de escribir en **inglés**.
- Todas las funciones deben de tener una descripción de qué hace antes de su declaración. **En el Backend, se deben detallar especialmente los parámetros y la lógica de negocio.**
- Todos los archivos deben de tener una descripción del mismo en la parte superior, en el comentario debe estar la última fecha de edición y autores. **Si se realiza un fix, se debe especificar el autor de dicha corrección en el encabezado.**
- Los archivos no deben de ser más extensos que 1000 líneas, en caso de exceder, dividir. 
- Para las funciones dentro de los archivos se debe incluir argumentos de entrada, titulo y para que sirve. 
- Al inicio de cada archivo debe incluirse la fecha de modificación y que se encuentra dentro del archivo.

### Template para comentarios al inicio de cada archivo
```
/**
 * FileName
 * Description: ...
 * Authors: Original Moncarca team
 * Last Modification made:
 * 00/00/2026 [YourName] Added detailed comments and documentation for clarity and maintainability.
 */
```
### Template para comentarios de funciones
```
/**
 * FunctionName, purpose of the function...
 * Input: values on the input
 * Output: returned values
 */
```
---

## 👥 Segmentación del Equipo

Para optimizar el desarrollo entre los 10 integrantes, el equipo se divide en:

### Project Manager
**Responsabilidad:** Planificar el plan de trabajo, realizar seguimiento del avance y coordinar la comunicación en el equipo.
- `Sergio Xuan`

### Leader Architecture
**Responsabilidad:** Diseño técnico y decisiones de la arquitectura de todo el sistema.
- `Julio César Rodríguez`

### Equipo de Frontend
**Responsabilidad:** Interfaz y estado en React.
- `Rebeca Davila Araiza` Líder de equipo.
- `Nicolas Quintana`
- `Fausto Izquierdo`



### Equipo de Backend y Base de Datos
**Responsabilidad:** API, servicios y base de datos en NestJS.
- `Santiago Coronado` Líder de equipo.
- `Diego de la Vega`
- `Jin Sik Yoon`
- `Sebastian Borjas`
- `Juan Pablo Narchi`

### QA 
**Responsabilidad:** Son los encargados de verificar los Pull Request y la funcionalidad de lo que se esta implementando en el momento. Estos irán rotando con el tiempo para que todos podamos revisar la calidad del mismo.

### Testing 
**Responsabilidad** Todo el equipo realizará las pruebas que se encontrarán en el plan de pruebas. 

---

## Convención de nombres

### Para el código

- **camelCase**
    - Variables 
        ```
        myVar, i
        ```
    - Objeto/JSON
        ```
        myObject, myJSON, appService
        ```
    - Funciones, métodos
        ```
        myFunction(), getOne(), Class.methodOne()
        ```
- **PascalCase**
    - Clases
        ```
        MyClass, AppService
        ```
    - Tipos
        ```
        MyType, Point
        ```
    - Interfaces
        ```
        MyInterface, Person
        ```
    - Decoradores
        ```
        @Decorador(), @Get()
        ```
- **ALLCAPS**
    - Variables Constantes
        ```
        COLORS, WIDTH
        ```
    - Variables .env
        ```
        process.env.CONSTANT, process.env.POSTGRES_USER
        ```

### Para carpetas y archivos

Los nombres de archivos y carpetas deben transmitir claramente de qué trata el archivo siguiendo el siguiente formato:

#### Para nombres de carpetas empezando por minusculas:
```
Correcto:
components/
pages/
assets/
hooks/
utils/
config/
types/

Incorrecto:
Components/
Pages/
Assets/
Hooks/
```

#### Para nombres de archivos de componentes o páginas:
```
Correcto:
Login.tsx
Register.tsx
Dashboard.tsx
Bookings.tsx
CreateTravelRequest.tsx
EditTravelRequest.tsx
RequestInfo.tsx
Requests.tsx
Error.tsx

Incorrecto:
login.tsx
register.tsx
dashboard.tsx
create_travel_request.tsx
```

## Ejemplo de estructura de Archivos del Proyecto

```
frontend/
├── src/
│   ├── components/ # Componentes reutilizables
│   ├── pages/ # Vistas/páginas principales (Login.tsx, Dashboard.tsx, etc.)
│   ├── hooks/ # Custom hooks (useAuth, etc.)
│   ├── utils/ # Funciones auxiliares
│   ├── assets/ # Imágenes, iconos, fonts
│   ├── config/ # Archivos de configuración
│   └── types/ # Definiciones de tipos TypeScript
└── public/
```

### Para base de datos

Nombres de tablas de bases de datos en plural, columnas en singular.
- **snake_case**
    - Columnas
        ```
        id, name, email,
        ```
    - Tablas
        ```
        approved_trips, user_roles, assistants, preferences
        ```
    - Databases
        ```
        users, trips, db
        ```
    - Schemas
        ```
        public
        ```
---

## 🧠 GitFlow

Seguimos el modelo [GitFlow](https://nvie.com/posts/a-successful-git-branching-model/):

| Rama          | Propósito                           |
|---------------|-------------------------------------|
| `main`        | Código listo para producción (entregables finales). |
| `develop`     | Última versión estable en desarrollo. |
| `feature/*`   | Nuevas funcionalidades.              |
| `bugfix/*`    | Corrección de errores.               |
| `release/*`   | Preparación para una nueva versión (Semana 3 y 5). |

### Nota sobre el flujo de estabilidad (Ramas Release)

El paso de código de la rama `develop` a `main` no es directo. Será necesario el uso de ramas `release/*`:

1.  **Aislamiento para el Entregable:** Al llegar a un hito, se crea la rama `release/nombre o area/vX.Y.Z`. Esto genera un "congelamiento de código" (code freeze) en tal versión, permitiendo que el equipo de desarrollo continúe trabajando en nuevas funciones en `develop` sin afectar la estabilidad de lo que se va a entregar.

2.  **Validación Rigurosa:** Esta rama es el escenario exclusivo para ejecutar el plan de pruebas. Aquí se validan tanto los requerimientos funcionales (flujos del Mapa Global de Operaciones) como los no funcionales (seguridad, carga y portabilidad). Solo si el sistema supera estas validaciones sin errores críticos, se considera estable.

3.  **Garantía de Calidad en `main`:** La rama `main` representa exclusivamente versiones terminadas, probadas y aprobadas por el equipo de Backend, Frontend y QA. Al usar una rama `release/*` como filtro, aseguramos evitar errores accidental de integración.

4.  **Cierre del Ciclo:** Una vez realizada la entrega, la rama `release/*` se fusiona con `main` (etiquetándola con su versión correspondiente) y también se reintegra a `develop` para asegurar que cualquier corrección de último minuto se mantenga en el flujo de desarrollo futuro.

---

## 💬 Convención de commits

Usamos [Conventional Commits](https://www.conventionalcommits.org/):

**tipo**(área): mensaje

| Tipo      | ¿Para qué se usa?                                         |
| --------- | --------------------------------------------------------- |
| `feat`    |  Nuevas funcionalidades                                   |
| `fix`     |  Corrección de bugs                                       |
| `docs`    |  Cambios en documentación                                 |
| `style`   |  Cambios de formato (espacios, comas)                     |
| `refactor`|  Reestructuración de código sin cambiar funcionalidad     |
| `test`    |  Agregar o modificar pruebas                              |
| `chore`   |  Tareas de mantenimiento (builds, dependencias)           |

### 💡 Ejemplos:
- `feat(frontend): agregar pantalla de login`
- `fix(auth): corregir bug de token`


---

## ✅ Proceso de Pull Requests 

Para integrar código a `develop`, se debe cumplir este checklist:
- [ ] La rama parte desde `develop`
- [ ] La funcionalidad está probada y funciona
- [ ] El código sigue los estándares de formato y estilo
- [ ] El commit sigue la convención (`feat:`, `fix:`, etc.)
- [ ] **Aprobación:** Se requiere la revisión y aprobación de al menos un integrante de cada equipo (Front, Back, y QA).
- [ ] Se ha actualizado la documentación (si aplica)

Una vez se complete este proceso, se podrá subir a la rama de main por alguno de los Líderes de los respectivos equipos que aprueben el pull request en `develop`.

