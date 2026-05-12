<br>
<br>

<div align="center">
    <img src="../../assets/images/chapter-5/capitulo-5.png" alt="Capitulo 5" />
</div>

<br>
<br>

# 5.1. Software Configuration Management

## 5.1.1. Software Development Environment Configuration

### 5.1.1.1. Herramientas de Gestión de Proyectos y Requisitos

| Herramienta | Propósito |URL de Referencia | Tipo |
|-------------|-----------|------------------|------|
| Trello | Gestión del Product Backlog, Sprint Boards y seguimiento de tareas del proyecto | https://trello.com | SaaS |
| GitHub Projects | Gestión de Issues y seguimiento del progreso del desarrollo en sincronización con los repositorios | https://github.com/upc-1asi0729-2610-11990-chronos-team-3 | SaaS |
| Google Drive | Almacenamiento y colaboración documentos de análisis y requerimientos | https://drive.google.com | SaaS |
| Discord | Comunicación en tiempo real del equipo y reuniones virtuales | https://discord.com | SaaS |

### 5.1.1.2. Herramientas de Diseño UX/UI

| Herramienta | Propósito |URL de Referencia | Tipo |
|-------------|-----------|------------------|------|
| Figma | Diseño de interfaces, wireframes, mockups y prototipos interactivos | https://www.figma.com | SaaS |
| Canva | Creación de assets gráficos, presentaciones y materiales visuales | https://www.canva.com | SaaS |

### 5.1.1.3. Herramientas de Desarrollo Frontend

| Herramienta | Propósito |URL de Referencia | Tipo |
|-------------|-----------|------------------|------|
| Visual Studio Code | Editor de código principal para el desarrollo del frontend Angular | https://code.visualstudio.com | Descargable |
| Angular CLI | Interfaz de línea de comandos para crear, desarrollar y builds de proyectos Angular | https://angular.io/cli | Descargable (npm) |
| Node.js | Entorno de ejecución JavaScript del lado del servidor para servicios de desarrollo | https://nodejs.org | Descargable |
| npm | Gestor de paquetes para JavaScript, utilizado para instalar dependencias de Angular | https://www.npmjs.com | Descargable |
| TypeScript | Lenguaje de programación strongly-typed que compila a JavaScript | https://www.typescriptlang.org | Descargable (npm) |

### 5.1.1.4. Herramientas de Desarrollo Backend

| Herramienta | Propósito |URL de Referencia | Tipo |
|-------------|-----------|------------------|------|
| Spring Boot | Framework de desarrollo backend basado en Java | https://spring.io/projects/spring-boot | Descargable |
| Java Development Kit (JDK 17) | Kit de desarrollo de Java necesario para compilar y ejecutar aplicaciones Spring Boot | https://www.oracle.com/java/technologies/downloads/#java17 | Descargable |
| Apache Maven | Herramienta de gestión de proyectos y gestión de dependencias para Java | https://maven.apache.org | Descargable |
| IntelliJ IDEA | IDE recomendado para el desarrollo backend con Spring Boot | https://www.jetbrains.com/idea | Descargable |

### 5.1.1.5. Herramientas de Control de Versiones

| Herramienta | Propósito |URL de Referencia | Tipo |
|-------------|-----------|------------------|------|
| Git | Sistema de control de versiones distribuido | https://git-scm.com | Descargable |
| GitHub | Plataforma de alojamiento de repositorios Git y colaboración | https://github.com | SaaS |
| GitHub Desktop | Aplicación GUI para gestionar repositorios Git de forma visual | https://desktop.github.com | Descargable |

### 5.1.1.6. Herramientas de Documentación y Calidad de Código

| Herramienta | Propósito |URL de Referencia | Tipo |
|-------------|-----------|------------------|------|
| ESLint | Analizador de código estático para identificar patrones problemáticos en JavaScript/TypeScript | https://eslint.org | Descargable (npm) |
| Prettier | Formateador de código Opinionated para mantener consistencia en el código | https://prettier.io | Descargable (npm) |
| Markdown | Lenguaje de formato para documentación técnica | https://www.markdownguide.org | Referencia |
| OpenAPI (Swagger) | Especificación para documentar APIs REST | https://swagger.io/specification | Referencia |

### 5.1.1.7. Herramientas de Despliegue

| Herramienta | Propósito |URL de Referencia | Tipo |
|-------------|-----------|------------------|------|
| Render | Plataforma de despliegue en la nube para aplicaciones web y APIs | https://render.com | SaaS |
| Netlify | Plataforma de despliegue opcional para el frontend estático | https://www.netlify.com | SaaS |
| Vercel | Plataforma de despliegue opcional para aplicaciones frontend | https://vercel.com | SaaS |

### 5.1.1.8. Herramientas de Testing

| Herramienta | Propósito |URL de Referencia | Tipo |
|-------------|-----------|------------------|------|
| Jasmine | Framework de testing para aplicaciones Angular | https://jasmine.github.io | Descargable (npm) |
| Karma | Test runner para Angular que permite ejecutar pruebas en múltiples navegadores | https://karma-runner.github.io | Descargable (npm) |
| Jest | Framework de testing alternativo para aplicaciones JavaScript/TypeScript | https://jestjs.io | Descargable (npm) |
| JUnit | Framework de testing para aplicaciones Java/Spring Boot | https://junit.org/junit5 | Descargable |
| Postman | Herramienta para testing manual de endpoints API | https://www.postman.com | Descargable |

### 5.1.1.9. Requisitos del Sistema por Miembro del Equipo

Cada miembro del equipo debe contar con las siguientes especificaciones mínimas en su estación de trabajo para garantizar un desarrollo eficiente y sin problemas de compatibilidad:

**Requisitos Mínimos:**
- Sistema Operativo: Windows 10/11, macOS Ventura o superior, o Ubuntu 22.04 LTS
- Memoria RAM: Mínimo 8 GB (recomendado 16 GB para desarrollo fluido)
- Espacio en disco: Mínimo 20 GB libres para herramientas y proyectos
- Procesador: Intel Core i5 o equivalente AMD (recomendado i7 o Ryzen 7)
- Conexión a internet: Banda ancha mínima de 10 Mbps para trabajo colaborativo

**Software Requerido:**
- Git configurado con credenciales de GitHub
- Node.js LTS instalado (versión 20.x o superior)
- npm instalado (versión 10.x o superior)
- JDK 26 instalado y configurado en PATH
- Maven instalado (versión 3.9.x o superior)
- Visual Studio Code con extensiones recomendadas
- Acceso a cuenta GitHub organization upc-chronos-team-3

## 5.1.2. Source Code Management

En esta sección el equipo establece los medios y esquema de organización que aplicará para el seguimiento de modificaciones. Para ello utilizará GitHub como plataforma y sistema de control de versiones. Se incluye el URL del repositorio de GitHub para cada producto: Landing Page, Backend, Frontend Web Applications. En el caso del Backend, se incluye en el repositorio el proyecto y los archivos de pruebas, tanto unitarias como de integración/aceptación. En esta sección se explica de qué forma se implementará GitFlow como Workflow de control de versiones.

### 5.1.2.1. Repositorios de GitHub

El equipo Chronos utiliza la organización GitHub "upc-chronos-team-3" para gestionar los tres repositorios principales del proyecto, cada uno encargado de un componente específico de la solución:

| Repositorio | URL GitHub | Propósito |
|-------------|-----------|-----------|
| SafeStep Landing | https://github.com/upc-1asi0729-2610-11990-chronos-team-3/safestep-landing-page | Página landing pública de presentación del producto |
| SafeStep Backend | https://github.com/upc-1asi0729-2610-11990-chronos-team-3/safestep-backend | API RESTful desarrollada en Spring Boot |
| SafeStep Frontend | https://github.com/upc-1asi0729-2610-11990-chronos-team-3/safestep-frontend | Aplicación web interactiva desarrollada en Angular |

### 5.1.2.2. GitFlow Implementation

El equipo implementa el modelo de ramificaciones GitFlow basado en el artículo "A successful Git branching model" de Vincent Driessen. Este modelo establece una estructura clara y organizada para el desarrollo colaborativo, permitiendo múltiples líneas de trabajo paralelas sin afectar la estabilidad del código en producción. A continuación se detallan las ramas principales y su propósito dentro del flujo de trabajo adoptado.

#### 5.1.2.2.1. Rama Principal (main)

La rama "main" representa la rama principal del repositorio y contiene exclusivamente el código que ha sido validado completamente y está listo para ejecución en producción. Esta rama está protegida contra pushes directos, lo que significa que ningún miembro del equipo puede realizar commits directamente a esta rama. Cualquier cambio que llegue a "main" debe pasar por el proceso completo de revisión y pruebas en ramas de característica o corrección. El código en esta rama refleja los releases finalizados y desplegados. Cada merge a main genera automáticamente una etiqueta (tag) de versión usando semantic versioning. La rama main es la fuente de verdad para despliegues automáticos a producción.

#### 5.1.2.2.2. Rama de Desarrollo (develop)

La rama "develop" sirve como rama de integración para características completadas. Es la rama base para crear nuevas ramas de características (feature branches) y constituye el centro de integración del desarrollo diario. El código en esta rama representa el estado más reciente del desarrollo con las características acumuladas del Sprint actual. Antes de cada release, se crea una rama de publicación (release branch) desde "develop". Esta rama también está protegida contra pushes directos, forzando que todos los cambios pasen por revisión. Es la rama que se despliega automáticamente al entorno de staging/pre-producción para testing de integración.

#### 5.1.2.2.3. Ramas de Características (feature/*)

Las ramas de características (feature branches) se crean desde la rama "develop" y se utilizan para desarrollar nuevas funcionalidades de manera aislada. Cada característica tiene su propia rama, lo que permite trabajar en múltiples funcionalidades simultáneamente sin interferir con el trabajo de otros miembros del equipo. Estas ramas siguen una convención de nomenclatura específica que incluye el tipo de trabajo y una descripción breve de la característica.

**Convención de nomenclatura:** `feature/<id-ticket>-<descripcion-corta>` o alternativamente `feature/<descripcion-corta>` cuando no se cuente con un ticket asociado. Por ejemplo: `feature/US001-user-registration` para implementar el registro de usuarios, `feature/API001-modules-endpoint` para crear el endpoint de módulos, o `feature/UI002-landing-hero` para diseñar la sección hero de la landing page. Esta convención permite identificar rápidamente el propósito de cada rama y su relación con el backlog del producto.

Una vez que la característica está completa y las pruebas pasan exitosamente, la rama de característica se fusiona (merge) de vuelta a "develop" mediante un Pull Request que requiere revisión de al menos un otro miembro del equipo. Después del merge, la rama de característica se elimina para mantener limpio el repositorio.

#### 5.1.2.2.4. Ramas de Publicación (release/*)

Las ramas de publicación (release branches) se crean desde "develop" cuando el equipo está listo para publicar una nueva versión. Estas ramas permiten realizar ajustes finales, correctivos y preparar los artefactos de despliegue sin afectar el desarrollo continuo. El nombre de estas ramas sigue el formato: `release/v<major>.<minor>.<patch>` siguiendo semantic versioning.

Durante la fase de publicación, solo se permiten cambios relacionados con la configuración de despliegue, documentación de release, y corrección de errores críticos. No se añaden nuevas funcionalidades en esta rama. Una vez completados los preparativos, la rama de release se fusiona tanto a "main" como a "develop", y se genera la etiqueta de versión correspondiente. Después de la publicación exitosa, la rama de release se elimina.

#### 5.1.2.2.5. Ramas de Corrección Urgente (hotfix/*)

Las ramas de corrección urgente (hotfix branches) se crean desde "main" para abordar errores críticos que requieren solución inmediata en producción. Estas ramas siguen la convención de nomenclatura: `hotfix/<id-ticket>-<descripcion-corta>` o simplemente `hotfix/<descripcion-corta>`. Permiten resolver problemas críticos sin afectar el desarrollo en curso en "develop".

Una vez que la corrección está completa y validada, se fusiona tanto a "main" como a "develop" para asegurar que la corrección esté disponible en futuras publicaciones. Al igual que otras ramas temporales, las ramas hotfix se eliminan después del merge. Este tipo de rama es esencial para mantener la calidad del servicio en producción y responder rápidamente a incidentes.

### 5.1.2.3. Semantic Versioning

El equipo aplica Semantic Versioning (SemVer) como sistema de versionado según la especificación "Semantic Versioning 2.0.0". El formato de versión sigue el patrón: `MAJOR.MINOR.PATCH`, donde cada componente tiene un significado específico que comunica el tipo de cambios realizados en cada release.

**MAJOR (X.0.0):** Se incrementa cuando se realizan cambios incompatibles en la API. Esto incluye cambios que rompen la compatibilidad hacia atrás en la API pública, como la eliminación de endpoints, cambios en el formato de request/response que no son retrocompatibles, o restructuración significativa del código que afecta a integraciones existentes. Cuando se incrementa la versión mayor, las versiones menores y de parche se reinician a cero.

**MINOR (x.Y.0):** Se incrementa cuando se añaden nuevas funcionalidades compatibles hacia atrás. Añadir nuevos endpoints, nuevos campos en respuestas (sin afectar los existentes), o nueva funcionalidad que no rompe la compatibilidad con consumidores existentes de la API. Cuando se incrementa la versión menor, la versión de parche se reinicia a cero.

**PATCH (x.x.Z):** Se incrementa cuando se realizan correcciones de errores compatibles hacia atrás. Correcciones de bugs que no cambian la API pública, mejoras de rendimiento que no alteran el comportamiento externo, o documentación actualizada que no afecta al código.

Ejemplos de versionado: `v1.0.0` (versión inicial), `v1.1.0` (nueva funcionalidad añadida como módulos de curso), `v1.1.1` (corrección de bug en autenticación), `v2.0.0` (cambio breaking en estructura de API).

### 5.1.2.4. Conventional Commits

El equipo adopta Conventional Commits para estructurar los mensajes de commit de manera clara y consistente. Esta convención permite generar automáticamente registros de cambios (changelogs), identificar tipos de cambios, y facilitar la comunicación en el equipo. El formato del mensaje de commit sigue la estructura: `<tipo>[alcance opcional]: <descripción>`.

**Tipos de commits aceptados:**

| Tipo | Descripción |
|------|------------|
| feat | Nueva funcionalidad añadida al proyecto |
| fix | Corrección de un bug |
| docs | Cambios únicamente en documentación |
| style | Cambios de formato que no afectan la lógica del código |
| refactor | Reestructuración del código que no añade ni elimina características |
| perf | Cambios que mejoran el rendimiento |
| test | Añadir o corregir pruebas |
| chore | Tareas de mantenimiento que no afectan al código de producción |
| build | Cambios en el sistema de build o dependencias |
| ci | Cambios en archivos de configuración de CI/CD |

**Ejemplos de mensajes de commit:**

- `feat(auth): add JWT token refresh endpoint` - Añade endpoint para refresh de tokens JWT
- `fix(modules): resolve null pointer in module retrieval` - Corrige error de puntero nulo al obtener módulos
- `docs(api): update endpoint documentation for user registration` - Actualiza documentación del endpoint de registro
- `style(ui): apply consistent spacing in landing page components` - Aplica espaciado consistente en componentes
- `refactor(db): optimize database queries for lesson fetch` - Optimiza consultas de base de datos para lecciones
- `perf(api): add caching layer for module content` - Añade capa de caché para contenido de módulos
- `test(auth): add unit tests for login service` - Añade pruebas unitarias para servicio de login
- `build(deps): update Angular to version 17` - Actualiza Angular a versión 17

Para commits que incluyen más detalle, se puede añadir un cuerpo descriptivo después de la línea en blanco, separado por un footer para información adicional como números de ticket:

```
feat(api): add pagination support to lessons endpoint

Add limit and offset parameters to GET /api/lessons endpoint to support
paginated responses for better performance with large datasets.

Closes #45
```

### 5.1.2.5. Pull Request Guidelines

Todos los miembros del equipo deben seguir estas pautas al crear y revisar Pull Requests. Antes de crear un PR, el branch debe estar al día con develop y pasar todas las pruebas locales. El título del PR debe seguir el formato Conventional Commits. El cuerpo del PR debe incluir descripción clara del cambio, screenshots para cambios visuales, y referencias a tickets relacionados. Los PRs requieren al menos una aprobación de otro miembro del equipo antes de poder hacer merge. El reviewer debe verificar que el código sigue las convenciones del proyecto, las pruebas pasan, y no introduce regresiones.

## 5.1.3. Source Code Style Guide & Conventions

Aquí el equipo explica e indica las referencias que adoptará para nombrar elementos y programar en los lenguajes que se utilizan en la solución (en este caso HTML, CSS, JavaScript, TypeScript, Java). Para todos los lenguajes debe aplicar la nomenclatura en inglés. Adicionalmente, se adoptan convenciones estándares para coding basadas en las guías de referencia de la industria tecnológica.

### 5.1.3.1. Convenciones Generales

El equipo SafeStep establece las siguientes convenciones generales que aplican a todos los lenguajes de programación utilizados en el proyecto, con el objetivo de mantener consistencia, legibilidad y mantenibilidad en todo el código fuente producido por el equipo de desarrollo.

**Nomenclatura en Inglés:** Todos los nombres de variables, funciones, clases, métodos, constantes, interfaces, y cualquier otro elemento de código debe ser nombrar en inglés. Esto incluye nombres de archivos, directorios, comentarios, y documentación. La razón principal es que el código será revisado y eventualmente mantenido por desarrolladores de diferentes nacionalidades, y el inglés es el idioma universal de la programación. Además, todas las palabras clave de los lenguajes de programación están en inglés, lo que hace que el código sea más coherente cuando se mezclan elementos propios con los del lenguaje.

**Sistema de Archivos:** La estructura de directorios debe seguir una organización lógica y coherente. Los nombres de archivos deben ser descriptivos y seguir una convención consistente. Los directorios deben usar nombres en minúsculas con guiones (-) como separadores cuando sea necesario. Por ejemplo: `src/app/components/user-profile`, `src/app/services/auth.service.ts`, `src/app/models/user.model.ts`.

### 5.1.3.2. Convenciones para HTML

El equipo sigue las "HTML Style Guide and Coding Conventions" ampliamente aceptadas en la industria, adaptadas a las necesidades específicas del proyecto SafeStep. HTML se utiliza principalmente para la construcción de la Landing Page y las plantillas de componentes Angular.

**Estructura del Documento:** Todo documento HTML debe incluir la declaración DOCTYPE, el elemento html con el atributo lang correspondiente, y los metadatos esenciales en la sección head. El código debe sangría (indent) correctamente utilizando 4 espacios para mantener legibilidad. Los atributos deben estar en orden alfabético dentro de cada etiqueta para facilitar la búsqueda visual. Los valores de atributos deben estar siempre entre comillas dobles.

**Convenciones de Nomenclatura:** Los IDs y clases deben seguir el patrón kebab-case, siendo descriptivos y coherentes con la función del elemento. Por ejemplo: `main-navigation`, `hero-section`, `cta-button`. Los atributos data- deben seguir un patrón similar: `data-module-id`, `data-lesson-progress`.

**Comentarios:** Los comentarios en HTML deben ser significativos y explicar el propósito de secciones complejas o componentes no obvios. Se utiliza el formato estándar `<!-- comentario -->` para comentarios de una línea y múltiples líneas cuando sea necesario.

### 5.1.3.3. Convenciones para CSS

El equipo adopta las directrices del "Google HTML/CSS Style Guide" como base para las convenciones de CSS, complementadas con prácticas específicas del ecosistema Angular.

**Organización del Código CSS:** El código CSS se organiza siguiendo metodologías modernas como BEM (Block Element Modifier) para la nomenclatura de clases, lo que facilita el mantenimiento y la escalabilidad de los estilos. Cada componente en Angular debe tener su propio archivo de estilos encapsulado, utilizando preferentemente SCSS para aprovechar características como variables y mixins.

**Convenciones de Nomenclatura:** Las clases CSS siguen el patrón BEM: `bloque__elemento--modificador`. Por ejemplo: `button--primary`, `card__title--highlighted`. Los nombres deben ser descriptivos y en inglés. Se evita el uso de IDs para estilos, prefiriendo clases para permitir la reutilización.

**Propiedades Ordenadas:** Las propiedades CSS dentro de un bloque deben estar ordenadas lógicamente, agrupando propiedades relacionadas juntas. Una estructura recomendada es: posicionamiento, modelo de caja, tipografía, fondo, bordes, efectos visuales, otros.

**Valores y Unidades:** Los valores numéricos deben incluir la unidad excepto cuando el valor sea cero. Los colores deben usarse en formato hexadecimal o rgb() para consistencia. Se utilizan variables CSS para valores repetidos para facilitar cambios globales.

### 5.1.3.4. Convenciones para JavaScript y TypeScript

El equipo sigue las "Google TypeScript Style Guide" y las mejores prácticas del ecosistema Angular para el desarrollo en JavaScript y TypeScript. Estas convenciones aseguran que el código sea type-safe, legible y mantenible.

**Declaración de Variables:** Se utiliza `const` por defecto para variables que no serán reasignadas. Solo se usa `let` cuando es necesario permitir reasignación. Se evita el uso de `var` completamente. Los nombres de variables utilizan camelCase y deben ser descriptivos, evitando abreviaturas que dificulten la lectura.

**Funciones:** Las funciones utilizan arrow functions (funciones flecha) cuando no se necesita el objeto `this`. Se prefiere funciones declarativas sobre funciones anónimas cuando sea posible. Los parámetros opcionales deben tener un valor default. La documentación de funciones mediante JSDoc o TypeDoc es obligatoria para funciones exportadas.

**Tipos y TypeScript:** Todos los parámetros de funciones deben tener tipos definidos. Se utilizan interfaces para definir la forma de objetos que se utilizan repetidamente. Los tipos primitivos se escriben en minúsculas: `string`, `number`, `boolean`. Los arrays se tipan usando la notación `Type[]` o `Array<Type>`. Se evita el uso de `any` a menos que sea absolutamente necesario.

**Clases y Orientación a Objetos:** Las clases siguen PascalCase. Los miembros privados utilizan el prefijo underscore (`_`) o el modificador `private` de TypeScript. Los getters y setters se utilizan para acceder a miembros privados cuando hay lógica asociada. Las interfaces se nomin con el prefijo `I` o como sustantivos descriptivos.

**Módulos y Imports:** Los imports se organizan en grupos: módulos externos, módulos internos del proyecto, módulos relativos. Dentro de cada grupo, se ordenan alfabéticamente. Se utilizan imports con nombres claros para facilitar el debugging.

### 5.1.3.5. Convenciones para Java y Spring Boot

El equipo adopta el "Google Java Style Guide" como referencia principal para el desarrollo backend con Java y Spring Boot, complementado con las convenciones específicas del framework.

**Organización del Código:** El código Java sigue una estructura de paquetes (packages) lógica y jerárquica. Los nombres de paquetes siguen el patrón inverso de dominio: `com.safestep.api`, `com.safestep.model`, `com.safestep.service`. Esta estructura facilita la identificación del propósito de cada clase.

**Convenciones de Nomenclatura:** Las clases utilizan PascalCase y son sustantivos descriptivos. Los métodos utilizan verbos o frases verbales en camelCase. Las constantes utilizan UPPER_SNAKE_CASE. Los tipos genéricos utilizan letras mayúsculas simples (E, T, K, V).

**Spring Boot Specific:** Las clases anotadas con `@Controller` o `@RestController` son responsables únicamente de manejar requests HTTP. La lógica de negocio reside en clases anotadas con `@Service`. El acceso a datos se realiza a través de clases anotadas con `@Repository`. Las entidades JPA siguen el patrón de nomenclatura de la base de datos.

**Anotaciones:** Las anotaciones se colocan en la línea anterior al elemento que anotan. Se evita la anotación redundante. Las anotaciones de Spring se ordenan primero, seguidas de anotaciones personalizadas.

### 5.1.3.6. Convenciones para Gherkin (Specifications)

El equipo utiliza las "Gherkin Conventions for Readable Specifications" para escribir user stories en formato Given-When-Then y para crear pruebas de aceptación automatizadas.

**Estructura de Feature Files:** Cada archivo Gherkin representa una característica específica del sistema. La primera línea contiene la palabra clave Feature seguida de un nombre y descripción opcionales. Los archivos se nomin descriptivamente en inglés.

**Escritura de Escenarios:** Los escenarios siguen la estructura Given-When-Then. Given establece el contexto inicial, When describe la acción a realizar, Then verifica el resultado esperado. Se evita escribir pasos demasiado largos o complejos.

**Step Definitions:** Los step definitions en el código deben ser reutilizables. Se parametrizan los valores que cambian entre escenarios. Se agrupan los steps relacionados en archivos lógicos.

## 5.1.4. Software Deployment Configuration

En esta sección el equipo especifica la configuración del despliegue de la solución, incluyendo los pasos necesarios para que, a partir de los repositorios de código fuente, se pueda lograr el despliegue o publicación satisfactorio de cada uno de los productos digitales en la solución (Landing Page, Web Services, Frontend Web Applications).

### 5.1.4.1. Estrategia de Despliegue

El equipo SafeStep adopta una estrategia de despliegue progresivo y automatizado que permite entregar valor de manera continua mientras se mantiene la estabilidad y calidad del sistema. Esta estrategia contempla múltiples entornos de despliegue, cada uno con un propósito específico en el ciclo de desarrollo y release.

#### 5.1.4.1.1. Entornos de Despliegue

El proyecto cuenta con tres entornos de despliegue claramente diferenciados, cada uno cumpliendo un rol específico en el ciclo de vida del software. El primer entorno es el entorno de desarrollo local, donde cada miembro del equipo puede trabajar de manera independiente en su máquina local, utilizando contenedores Docker para mantener consistencia con el entorno de producción. Este entorno permite una búsqueda rápida y pruebas sin afectar a otros miembros del equipo.

El segundo entorno es el entorno de staging/pre-producción, que es una réplica exacta del entorno de producción en términos de configuración, base de datos y servicios. Este entorno se utiliza para pruebas de integración completas, pruebas de aceptación por el usuario, y validación de releases antes del despliegue a producción. Cualquier cambio en la rama develop se despliega automáticamente a este entorno.

El tercer entorno es el de producción, donde los usuarios finales acceden a la aplicación. Los despliegues a producción se realizan únicamente desde ramas release, después de pasar todas las validaciones en staging. Este entorno cuenta con configuración optimizada para rendimiento y alta disponibilidad.

#### 5.1.4.1.2. Pipeline de CI/CD

El equipo implementa pipelines de Integración Continua y Entrega Continua (CI/CD) utilizando las herramientas disponibles en GitHub Actions. Cada repositorio cuenta con su propio pipeline de CI/CD adaptado a sus características específicas.

Para el repositorio de Frontend (Angular), el pipeline de CI/CD incluye las siguientes etapas: instalación de dependencias con npm install, verificación de código con ESLint y análisis estático, ejecución de pruebas unitarias con Karma o Jest, construcción de la aplicación para producción, y finalmente despliegue automático a Render si las pruebas pasan exitosamente.

Para el repositorio de Web Services (Spring Boot), el pipeline incluye: verificación de código con herramientas de análisis estático, compilación del proyecto con Maven, ejecución de pruebas unitarias y de integración, construcción del artefacto JAR/WAR, y despliegue automático a Render.

Para el repositorio de Landing Page, se implementa un pipeline simplified que incluye build estático y despliegue a Render o Netlify.

### 5.1.4.2. Configuración de Render

Render es la plataforma de despliegue principal seleccionada para el proyecto SafeStep. A continuación se detallan los pasos de configuración para cada componente de la solución en la plataforma Render.

#### 5.1.4.2.1. Configuración de Web Services en Render

El despliegue de los Web Services en Render requiere una serie de pasos de configuración que aseguran el correcto funcionamiento de la API en producción. El primer paso consiste en crear una cuenta en Render y vincula con el repositorio de GitHub. Se recomienda utilizar el plan gratuito para desarrollo, con opción de upgrade a planes de pago según las necesidades de producción.

Una vez vinculada la cuenta, el equipo debe crear un nuevo Web Service para el repositorio de safestep-web-services. Durante la configuración, se selecciona la rama que déclencheur el despliegue (típicamente main o una rama específica de producción). Render detectará automáticamente que es una aplicación Spring Boot correctamente en el build command y run command.

Los parámetros de configuración críticos incluyen: la variable de entorno `PORT` que Render asigna dinámicamente, la configuración de base de datos si se utiliza una base de datos gestionada por Render, y las variables de entorno para credentials de la aplicación. Es importante asegurar que todas las variables sensibles se configuren como secrets en Render y nunca se expongan en el código fuente.

La URL del servicio desplegado se utilizará como base URL para las llamadas API desde el Frontend. Por ejemplo, si el servicio se despliega en `https://safestep-api.onrender.com`, las llamadas API se realizarán a endpoints como `https://safestep-api.onrender.com/api/modules`.

#### 5.1.4.2.2. Configuración de Frontend en Render

El Frontend de Angular también se despliega en Render como un Web Service estático o como una aplicación Node.js si se requiere Server-Side Rendering (SSR). La configuración incluye especificar el directorio de salida (típicamente `dist/safestep-frontend`) y el comando de build: `npm install && npm run build`.

Es importante configurar las variables de entorno en Render para especificar la URL base del API. Esto permite cambiar la URL del backend sin necesidad de recompilar la aplicación. Por ejemplo: `API_BASE_URL=https://safestep-api.onrender.com`.

Para el Frontend, también se puede considerar el uso de servicios como Netlify o Vercel, que ofrecen características específicas para aplicaciones estáticas y de frontend, incluyendo CDN global para mejor rendimiento.

#### 5.1.4.2.3. Configuración de Landing Page en Render o Netlify

La Landing Page, al ser un sitio estático, puede desplegarse en Render como Web Service estático o en Netlify. Netlify ofrece características específicas para sitios estáticos, incluyendo forms integrados, funciones serverless, y despliegues automáticos desde Git.

La configuración en Netlify requiere crear un archivo `netlify.toml` en la raíz del repositorio que especifique el comando de build y el directorio de publish. Por ejemplo: `[build] publish = "dist" command = "npm run build"`. El despliegue se déclencheur automáticamente cada vez que se hace push a la rama principal.

### 5.1.4.3. Procedimientos de Despliegue

El equipo establece procedimientos detallados para ejecutar despliegues, asegurando consistencia y minimizando errores en el proceso de publicación del software.

#### 5.1.4.3.1. Despliegue a Staging

El despliegue a staging ocurre automáticamente cuando se hace push a la rama develop. Este proceso no requiere intervención manual y serve como validación automática de que el código integrado funciona correctamente. El equipo debe verificar en staging antes de promover cualquier cambio a producción.

#### 5.1.4.3.2. Despliegue a Producción

El despliegue a producción requiere un proceso más formal. Primero, se debe crear una rama release desde develop. Luego, se ejecutan las pruebas finales en staging. Una vez validadas, se hace merge de la rama release a main, lo que déclencheur el despliegue automático a producción. Se debe verificar el funcionamiento correcto después del despliegue. Finalmente, se hace merge de main a develop para mantener la sincronización.

#### 5.1.4.3.3. Rollback

En caso de problemas en producción, el equipo puede realizar un rollback a la versión anterior. Render permite desplegar versiones anteriores directamente desde el dashboard. También se puede utilizar git para reverti el cambio y vuelto a desplegar.

### 5.1.4.4. Monitoreo y Logging

El equipo implementa capacidades de monitoreo y logging para mantener visibilidad sobre el estado de la aplicación en producción. Los logs de aplicación se almacenan en Render dashboard para revisión manual. Para métricas, se puede integrar servicios gratuitos como Sentry para tracking de errores. Estos herramientas permiten identificar y resolver problemas rápidamente.