<br>
<br>

<div align="center">
    <img src="../../assets/images/chapter-5/capitulo-5.png" alt="Capitulo 5" />
</div>

<br>
<br>

# 5.2. Landing Page, Services & Applications Implementation.

## 5.2.3. Sprint 3

### 5.2.3.1. Sprint Planning 3

En esta seccion se especifica los aspectos principales del Sprint Planning Meeting correspondiente al Sprint 3. SafeStep inicia su tercer Sprint con el objetivo de implementar el backend real de la solucion, reemplazando progresivamente la dependencia de datos simulados utilizada en el Sprint 2 por un RESTful API desarrollado internamente con Spring Boot, Java, PostgreSQL y documentacion OpenAPI mediante Swagger.

El Sprint 3 representa una etapa clave para la madurez tecnica del producto, debido a que permite pasar de una aplicacion frontend basada en json-server a una arquitectura distribuida compuesta por Landing Page, Frontend Web Application y Web Services. Durante este Sprint, el equipo priorizo la implementacion de los bounded contexts principales del backend, manteniendo una estructura alineada con Domain-Driven Design, CQRS, capas de aplicacion, dominio, infraestructura e interfaces REST.

<table align="center" border="1" cellpadding="8" cellspacing="0" style="border-collapse: collapse; width: 100%; font-family: Arial, sans-serif;">
    <tbody>
        <tr>
            <td><b>Sprint #</b></td>
            <td>Sprint 3</td>
        </tr>
        <tr>
            <td colspan="2"><b>Sprint Planning Background</b></td>
        </tr>
        <tr>
            <td>Date</td>
            <td>2026-05-03</td>
        </tr>
        <tr>
            <td>Time</td>
            <td>10:00 AM</td>
        </tr>
        <tr>
            <td>Location</td>
            <td>Reunion virtual via Discord - Canal #sprint-planning</td>
        </tr>
        <tr>
            <td>Prepared by</td>
            <td>Melgarejo Quiroz, Josep Eliu</td>
        </tr>
        <tr>
            <td>Attendees (to planning meeting)</td>
            <td>Ayala Fernandez, Jorge Brayan / Sanchez Espinoza, Mathias Enrique / Melgarejo Quiroz, Josep Eliu / Flores Eusebio, Angel Thyago</td>
        </tr>
        <tr>
            <td>Sprint n - 1 Review Summary</td>
            <td>Sprint 2 completado exitosamente: aplicacion frontend Angular implementada con bounded contexts, arquitectura DDD, integracion con json-server y despliegue en Firebase Hosting. Se logro construir la experiencia principal del usuario con dashboard, simulaciones, gamificacion, estadisticas y tienda.</td>
        </tr>
        <tr>
            <td>Sprint n - 1 Retrospective Summary</td>
            <td>El equipo identifico que json-server permitio validar rapidamente los flujos del frontend, pero tambien se reconocio la necesidad de implementar un backend real para cumplir con la arquitectura distribuida solicitada por el curso. Se acordo priorizar estructura de capas, documentacion Swagger y endpoints estables.</td>
        </tr>
        <tr>
            <td colspan="2"><b>Sprint Goal / User Stories</b></td>
        </tr>
        <tr>
            <td>Sprint 3 Goal</td>
            <td>Implementar el RESTful API de SafeStep con Spring Boot, Java, PostgreSQL, JWT, bounded contexts y documentacion OpenAPI, permitiendo exponer endpoints reales para autenticacion, perfiles, comercio, simulaciones medicas, gamificacion y analitica.</td>
        </tr>
        <tr>
            <td>Sprint 3 Velocity</td>
            <td>El equipo estimo un velocity de 37 Story Points, considerando la complejidad de implementar el backend real, configurar persistencia con PostgreSQL, definir arquitectura DDD y documentar los endpoints mediante Swagger.</td>
        </tr>
        <tr>
            <td>Sum of Story Points</td>
            <td>Total: 37 SP - Distribuidos en technical stories de backend agregadas al EP09. El alcance combina configuracion Spring Boot, arquitectura por bounded contexts, seguridad JWT, persistencia PostgreSQL/JPA, endpoints REST, Swagger, seed data y validacion tecnica.</td>
        </tr>
    </tbody>
</table>

El Sprint Planning Meeting del 3 de mayo de 2026 duro aproximadamente 3 horas. Durante la reunion se reviso la arquitectura del backend de referencia del curso, se definieron los bounded contexts necesarios para SafeStep y se establecio que el backend debia seguir una estructura similar a la utilizada en Learning Center Platform, separando responsabilidades entre domain, application, infrastructure e interfaces.

Tambien se acordo que los endpoints del backend debian responder a las necesidades ya implementadas en el frontend del Sprint 2. Por ello, el equipo tomo como base los datos y flujos existentes en la aplicacion Angular, pero los traslado a un modelo persistente con PostgreSQL, entidades JPA y servicios de aplicacion.

**Technical Stories incluidos en el Sprint 3:**

Las historias seleccionadas para este Sprint corresponden a technical stories nuevas asociadas al backend y registradas dentro de EP09 - Soporte tecnico y arquitectura de la aplicacion. El equipo priorizo los elementos tecnicos necesarios para que las funcionalidades existentes de SafeStep puedan ser soportadas por Web Services reales.

| ID | Technical Story | Prioridad | Story Points |
| -- | ---------- | --------- | ------------ |
| TS13 | Como developer, quiero configurar el backend con Spring Boot, Maven, Java y perfiles de ambiente para contar con una base estable para los Web Services. | Must Have | 5 |
| TS14 | Como developer, quiero organizar el backend por bounded contexts y capas para mantener una estructura alineada con la arquitectura del curso. | Must Have | 5 |
| TS15 | Como developer, quiero implementar autenticacion con JWT y roles para proteger los endpoints que dependen de un usuario autenticado. | Must Have | 5 |
| TS16 | Como developer, quiero configurar persistencia con PostgreSQL y Spring Data JPA para almacenar datos reales de usuarios, simulaciones, compras y progreso. | Must Have | 5 |
| TS17 | Como developer, quiero exponer endpoints REST por bounded context para que el frontend pueda consumir datos reales de SafeStep. | Must Have | 8 |
| TS18 | Como developer, quiero documentar los endpoints con OpenAPI y Swagger UI para facilitar pruebas, revision e integracion del API. | Must Have | 3 |
| TS19 | Como developer, quiero cargar datos iniciales en el backend para probar flujos principales sin registrar toda la informacion manualmente. | Should Have | 3 |
| TS20 | Como developer, quiero ejecutar pruebas y validaciones con Maven para asegurar que el backend compile y funcione antes de integrarlo con el frontend. | Must Have | 3 |

La seleccion de estas technical stories responde a la necesidad de completar la capa de Web Services del producto SafeStep sin crear historias funcionales nuevas que no esten alineadas con el Product Backlog. A diferencia del Sprint 2, en el que se trabajo con datos simulados, este Sprint se enfoca en una API real con persistencia, seguridad y documentacion tecnica.

**User Stories funcionales soportadas por el backend:**

El backend implementado en este Sprint da soporte directo a historias funcionales ya existentes en el Capitulo 3, principalmente: US01, US02, US03, US10, US12, US14, US15, US18, US23, US26, US27, US29, US30, US36, US37, US38, US40, US41 y US42. Estas historias no se duplican ni se renombran; se consideran funcionalidades de usuario que ahora cuentan con soporte desde el RESTful API.

**Distribucion de Trabajo por Componente:**

- **Backend Setup & Architecture:** 10 Story Points enfocados en configuracion Spring Boot, Maven, perfiles de ambiente y organizacion por bounded contexts.
- **Security & Persistence:** 10 Story Points enfocados en autenticacion JWT, roles, PostgreSQL, JPA y acceso seguro a datos.
- **RESTful API Implementation:** 8 Story Points enfocados en endpoints para IAM, perfiles, comercio, simulaciones, gamificacion y analitica.
- **OpenAPI Documentation:** 3 Story Points enfocados en documentacion Swagger y revision de contratos REST.
- **Seed Data:** 3 Story Points enfocados en datos iniciales para simulaciones, comercio, gamificacion y analitica.
- **Build & Validation:** 3 Story Points enfocados en pruebas Maven, compilacion y validacion local de endpoints.

### 5.2.3.2. Aspect Leaders and Collaborators

En esta seccion el equipo elabora el artefacto Leadership-and-Collaboration Matrix (LACX) correspondiente al Sprint 3. Los aspectos del Sprint se enfocan en el desarrollo del backend de SafeStep, considerando los bounded contexts definidos para el API RESTful y las responsabilidades tecnicas asociadas a cada capa.

Para este Sprint, el equipo distribuyo el trabajo segun la complejidad de cada bounded context. Se busco que cada miembro activo lidere o colabore en un modulo especifico, manteniendo una vision compartida de arquitectura para evitar diferencias excesivas entre paquetes. La iteracion fue planificada con cuatro miembros activos del equipo.

**Aspectos del Sprint 3:**

1. **IAM & Profiles - Desarrollo:** Implementacion de autenticacion, autorizacion, usuarios, roles y perfiles.
2. **Commerce - Desarrollo:** Implementacion de catalogo, carrito, ordenes, direcciones, pagos y recomendaciones.
3. **Simulation - Desarrollo:** Implementacion de simulaciones medicas, pasos, opciones e intentos.
4. **Gamification - Desarrollo:** Implementacion de resumen, misiones, insignias, leaderboard y transacciones.
5. **Analytics - Desarrollo:** Implementacion de resumen de progreso, graficos y certificados.
6. **Shared Infrastructure - Desarrollo:** Configuracion de seguridad, errores, servicios comunes, OpenAPI y persistencia.
7. **Documentation & Validation:** Evidencias de Swagger, ejecucion local, pruebas y documentacion del Sprint.

<table align="center" border="1" cellpadding="8" cellspacing="0" style="border-collapse: collapse; width: 100%; font-family: Arial, sans-serif;">
    <tbody>
        <tr>
            <td><b>Team Member (Last Name, First Name)</b></td>
            <td><b>GitHub Username</b></td>
            <td><b>IAM & Profiles / L or C</b></td>
            <td><b>Commerce / L or C</b></td>
            <td><b>Simulation / L or C</b></td>
            <td><b>Gamification / L or C</b></td>
            <td><b>Analytics / L or C</b></td>
            <td><b>Shared Infrastructure / L or C</b></td>
            <td><b>Documentation / L or C</b></td>
        </tr>
        <tr>
            <td>Ayala Fernandez, Jorge Brayan</td>
            <td>jorgeayaladev</td>
            <td>C</td>
            <td>L</td>
            <td>C</td>
            <td>C</td>
            <td>C</td>
            <td>C</td>
            <td>C</td>
        </tr>
        <tr>
            <td>Sanchez Espinoza, Mathias Enrique</td>
            <td>Nounz27</td>
            <td>C</td>
            <td>C</td>
            <td>L</td>
            <td>C</td>
            <td>-</td>
            <td>C</td>
            <td>C</td>
        </tr>
        <tr>
            <td>Melgarejo Quiroz, Josep Eliu</td>
            <td>Melga1502</td>
            <td>C</td>
            <td>C</td>
            <td>C</td>
            <td>L</td>
            <td>L</td>
            <td>L</td>
            <td>C</td>
        </tr>
        <tr>
            <td>Flores Eusebio, Angel Thyago</td>
            <td>angelfdevs</td>
            <td>L</td>
            <td>C</td>
            <td>C</td>
            <td>C</td>
            <td>C</td>
            <td>C</td>
            <td>L</td>
        </tr>
    </tbody>
</table>

**Distribucion detallada de responsabilidades:**

- **Flores Eusebio, Angel Thyago (Development Lead - IAM, Profiles & Documentation):** Responsable de apoyar la implementacion de autenticacion, usuarios, roles y perfiles, ademas de coordinar la documentacion de evidencias, pruebas manuales, revision de consistencia entre bounded contexts y validacion de endpoints desde Swagger.

- **Ayala Fernandez, Jorge Brayan (Development Lead - Commerce):** Responsable de implementar el bounded context de commerce, incluyendo catalogo de productos, categorias, kits de emergencia, cupones, recomendaciones, carrito de compras y ordenes.

- **Sanchez Espinoza, Mathias Enrique (Development Lead - Simulation):** Responsable de implementar el bounded context de simulation, incluyendo simulaciones medicas, pasos, opciones, sugerencias de productos e intentos registrados por usuario.

- **Melgarejo Quiroz, Josep Eliu (Development Lead - Gamification, Analytics & Shared Infrastructure):** Responsable de implementar gamificacion, analitica y componentes compartidos del backend. Coordina la estructura general del proyecto, configuracion de Swagger, seed data y convenciones de arquitectura.

### 5.2.3.3. Sprint Backlog 3

El Sprint Backlog 3 resume el objetivo principal del Sprint: implementar el backend RESTful API de SafeStep utilizando Spring Boot, PostgreSQL, JWT, OpenAPI y una arquitectura organizada por bounded contexts. Este Sprint Backlog representa el compromiso del equipo para completar los Web Services necesarios para soportar los flujos principales de la aplicacion.

El equipo organizo las tareas tomando como referencia las funcionalidades ya implementadas en el frontend durante el Sprint 2. De esta manera, cada endpoint del backend responde a una necesidad concreta de la Web Application, permitiendo que la futura integracion frontend-backend sea directa y mantenible.

**Trello Board:**
El equipo utiliza un Trello Board con las listas estandar de Scrum: "Sprint Goal", "To Do", "In Progress", "To Review" y "Done". Para este Sprint, las tarjetas se organizaron por bounded context y por endpoint, facilitando el seguimiento del avance de cada modulo.

**Referencia del Trello Board:** [Insertar URL del board de Sprint 3]

A continuacion, la tabla de control de estado para el Sprint 3:

<table align="center" border="1" cellpadding="8" cellspacing="0" style="border-collapse: collapse; width: 100%; font-family: Arial, sans-serif;">
    <tbody>
        <tr>
            <td><b>Sprint #</b></td>
            <td colspan="7">Sprint 3</td>
        </tr>
        <tr>
            <td colspan="2">User Story</td>
            <td colspan="6">Work-Item / Task</td>
        </tr>
        <tr>
            <td>Id</td>
            <td>Title</td>
            <td>Id</td>
            <td>Title</td>
            <td>Description</td>
            <td>Estimation (Hours)</td>
            <td>Assigned to</td>
            <td>Status (To-do / In-Process / To-Review / Done)</td>
        </tr>
        <tr>
            <td>TS13/TS14/TS16</td>
            <td>Configuracion backend</td>
            <td>T001</td>
            <td>Configurar proyecto Spring Boot</td>
            <td>Inicializar proyecto backend con Maven, Java, dependencias Spring Boot, estructura base y configuracion de perfiles.</td>
            <td>4</td>
            <td>Melgarejo Quiroz, Josep Eliu</td>
            <td>Done</td>
        </tr>
        <tr>
            <td>US01/US02/TS15</td>
            <td>Autenticacion segura</td>
            <td>T002</td>
            <td>Implementar IAM context</td>
            <td>Crear usuarios, roles, comandos, queries, servicios y endpoints de sign-in/sign-up.</td>
            <td>7</td>
            <td>Flores Eusebio, Angel Thyago</td>
            <td>Done</td>
        </tr>
        <tr>
            <td>US03</td>
            <td>Perfil de usuario</td>
            <td>T003</td>
            <td>Implementar Profiles context</td>
            <td>Crear agregado Profile, comandos, queries, repositorios, recursos REST y endpoints de consulta/actualizacion.</td>
            <td>5</td>
            <td>Flores Eusebio, Angel Thyago</td>
            <td>Done</td>
        </tr>
        <tr>
            <td>US30/US42</td>
            <td>Catalogo de comercio</td>
            <td>T004</td>
            <td>Implementar Commerce catalog</td>
            <td>Crear endpoints de productos, categorias, kits, cupones y recomendaciones personalizadas.</td>
            <td>8</td>
            <td>Ayala Fernandez, Jorge Brayan</td>
            <td>Done</td>
        </tr>
        <tr>
            <td>US36/US37/US38/US40/US41</td>
            <td>Carrito y ordenes</td>
            <td>T005</td>
            <td>Implementar Commerce operations</td>
            <td>Crear endpoints para carrito, agregar item, actualizar item, eliminar item, consultar ordenes y crear orden.</td>
            <td>8</td>
            <td>Ayala Fernandez, Jorge Brayan</td>
            <td>Done</td>
        </tr>
        <tr>
            <td>US10/US12</td>
            <td>Catalogo de simulaciones</td>
            <td>T006</td>
            <td>Implementar Simulation catalog</td>
            <td>Crear modelo de simulaciones medicas, pasos, opciones, sugerencias y endpoints de consulta.</td>
            <td>6</td>
            <td>Sanchez Espinoza, Mathias Enrique</td>
            <td>Done</td>
        </tr>
        <tr>
            <td>US14/US15</td>
            <td>Intentos de simulacion</td>
            <td>T007</td>
            <td>Implementar Simulation attempts</td>
            <td>Crear comando y endpoint para registrar intentos de simulacion y consultar intentos del usuario autenticado.</td>
            <td>5</td>
            <td>Sanchez Espinoza, Mathias Enrique</td>
            <td>Done</td>
        </tr>
        <tr>
            <td>US23/US26/US27/US29</td>
            <td>Gamificacion</td>
            <td>T008</td>
            <td>Implementar Gamification context</td>
            <td>Crear endpoints para resumen de gamificacion, misiones, insignias, leaderboard y transacciones de monedas.</td>
            <td>7</td>
            <td>Melgarejo Quiroz, Josep Eliu</td>
            <td>Done</td>
        </tr>
        <tr>
            <td>US18/TS17</td>
            <td>Analitica</td>
            <td>T009</td>
            <td>Implementar Analytics context</td>
            <td>Crear endpoints de summary, progress y certificates para presentar metricas del usuario.</td>
            <td>6</td>
            <td>Melgarejo Quiroz, Josep Eliu</td>
            <td>Done</td>
        </tr>
        <tr>
            <td>TS19</td>
            <td>Seed data</td>
            <td>T010</td>
            <td>Implementar seed inicial</td>
            <td>Crear archivo JSON de datos iniciales y handlers para cargar datos de simulaciones, comercio, gamificacion y analytics.</td>
            <td>5</td>
            <td>Flores Eusebio, Angel Thyago</td>
            <td>Done</td>
        </tr>
        <tr>
            <td>TS18</td>
            <td>Documentacion Swagger</td>
            <td>T011</td>
            <td>Configurar OpenAPI</td>
            <td>Configurar SpringDoc, documentar controllers y verificar visualizacion de endpoints en Swagger UI.</td>
            <td>4</td>
            <td>Melgarejo Quiroz, Josep Eliu</td>
            <td>Done</td>
        </tr>
        <tr>
            <td>TS20</td>
            <td>Validacion tecnica</td>
            <td>T012</td>
            <td>Ejecutar pruebas y build</td>
            <td>Ejecutar pruebas con Maven, validar compilacion, revisar Swagger y probar endpoints principales localmente.</td>
            <td>4</td>
            <td>Flores Eusebio, Angel Thyago</td>
            <td>Done</td>
        </tr>
    </tbody>
</table>

### 5.2.3.4. Development Evidence for Sprint Review

En esta seccion se explica y presenta los avances de implementacion realizados durante el Sprint 3 con relacion al producto Web Services de SafeStep. El equipo completo el desarrollo del backend RESTful API utilizando Spring Boot, Java, PostgreSQL, Maven y Swagger.

**Resumen de Avances Implementados:**

- **Configuracion base del backend:** Se creo el proyecto Spring Boot con Maven, Java, perfiles de configuracion, dependencias de seguridad, persistencia, validacion, JWT y documentacion OpenAPI.
- **Shared Infrastructure:** Se implementaron clases compartidas para resultados de aplicacion, errores, respuestas HTTP, configuracion de seguridad, OpenAPI, auditoria y servicios de usuario autenticado.
- **IAM bounded context:** Se implementaron usuarios, roles, autenticacion, registro, JWT y endpoints de consulta de usuarios y roles.
- **Profiles bounded context:** Se implemento la gestion de perfiles de usuario, incluyendo creacion, consulta, consulta por identificador y actualizacion del perfil actual.
- **Commerce bounded context:** Se implemento el catalogo de productos, categorias, kits, cupones y recomendaciones, ademas de operaciones de carrito y ordenes.
- **Simulation bounded context:** Se implemento el catalogo de simulaciones medicas, consulta por identificador, registro de intentos y consulta de intentos del usuario autenticado.
- **Gamification bounded context:** Se implemento resumen de gamificacion, misiones, insignias, ranking y transacciones de monedas.
- **Analytics bounded context:** Se implementaron endpoints de resumen, progreso visual y certificados del usuario.
- **Persistencia con PostgreSQL:** Se crearon entidades JPA, repositorios de persistencia y adaptadores para conectar el dominio con la base de datos.
- **Seed data:** Se agregaron datos iniciales para poder probar el backend sin carga manual de informacion.
- **Swagger:** Se expusieron los endpoints mediante Swagger UI para facilitar la validacion y documentacion del API.

**Commits Realizados:**

<table align="center" border="1" cellpadding="8" cellspacing="0" style="border-collapse: collapse; width: 100%; font-family: Arial, sans-serif;">
    <tbody>
        <tr>
            <td>Repository</td>
            <td>Branch</td>
            <td>Commit Id</td>
            <td>Commit message</td>
            <td>Commit body</td>
            <td>Commit on (Date)</td>
        </tr>
        <tr>
            <td>safestep-backend</td>
            <td>main</td>
            <td>[Insertar commit id]</td>
            <td>chore: initialize SafeStep backend project</td>
            <td>Initialize Spring Boot project with Maven, Java configuration and base resources.</td>
            <td>2026-05-03</td>
        </tr>
        <tr>
            <td>safestep-backend</td>
            <td>main</td>
            <td>[Insertar commit id]</td>
            <td>feat(shared): add common backend infrastructure</td>
            <td>Add shared result, error, response, security, OpenAPI and persistence support.</td>
            <td>2026-05-04</td>
        </tr>
        <tr>
            <td>safestep-backend</td>
            <td>main</td>
            <td>[Insertar commit id]</td>
            <td>feat(iam): add authentication and authorization context</td>
            <td>Implement sign-in, sign-up, roles, users and JWT support.</td>
            <td>2026-05-05</td>
        </tr>
        <tr>
            <td>safestep-backend</td>
            <td>main</td>
            <td>[Insertar commit id]</td>
            <td>feat(profiles): add user profiles context</td>
            <td>Implement profile aggregate, commands, queries, persistence and REST endpoints.</td>
            <td>2026-05-06</td>
        </tr>
        <tr>
            <td>safestep-backend</td>
            <td>main</td>
            <td>[Insertar commit id]</td>
            <td>feat(commerce): add commerce catalog endpoints</td>
            <td>Implement products, categories, emergency kits, coupons and recommendations endpoints.</td>
            <td>2026-05-07</td>
        </tr>
        <tr>
            <td>safestep-backend</td>
            <td>main</td>
            <td>[Insertar commit id]</td>
            <td>feat(commerce): add cart and order endpoints</td>
            <td>Implement cart item management, current user orders, shipping addresses and payment methods.</td>
            <td>2026-05-08</td>
        </tr>
        <tr>
            <td>safestep-backend</td>
            <td>main</td>
            <td>[Insertar commit id]</td>
            <td>feat(simulation): add medical simulation endpoints</td>
            <td>Implement simulation catalog, detail lookup, attempt creation and attempt history.</td>
            <td>2026-05-09</td>
        </tr>
        <tr>
            <td>safestep-backend</td>
            <td>main</td>
            <td>[Insertar commit id]</td>
            <td>feat(gamification): add gamification query endpoints</td>
            <td>Implement summary, missions, badges, leaderboard and coin transactions endpoints.</td>
            <td>2026-05-10</td>
        </tr>
        <tr>
            <td>safestep-backend</td>
            <td>main</td>
            <td>[Insertar commit id]</td>
            <td>feat(analytics): add analytics endpoints</td>
            <td>Implement summary, progress and certificates endpoints for current user.</td>
            <td>2026-05-11</td>
        </tr>
        <tr>
            <td>safestep-backend</td>
            <td>main</td>
            <td>[Insertar commit id]</td>
            <td>chore(seed): add SafeStep initial data</td>
            <td>Add seed JSON and event handlers for initial backend data.</td>
            <td>2026-05-12</td>
        </tr>
        <tr>
            <td>safestep-backend</td>
            <td>main</td>
            <td>[Insertar commit id]</td>
            <td>docs(api): add Swagger evidence and backend architecture notes</td>
            <td>Document OpenAPI endpoints, backend architecture and local execution requirements.</td>
            <td>2026-05-13</td>
        </tr>
    </tbody>
</table>

**Repositorio de Backend:**

[Insertar URL del repositorio de backend]

**Repositorio de Frontend relacionado:**

[Insertar URL del repositorio de frontend]

**Referencia de Swagger local o desplegado:**

[Insertar URL de Swagger UI]

### 5.2.3.5. Execution Evidence for Sprint Review

El Sprint 3 permitio construir el RESTful API real de SafeStep, habilitando la comunicacion entre la Web Application y una capa backend propia. Las evidencias de ejecucion demuestran que el equipo completo los endpoints principales, configuro persistencia con PostgreSQL y valido la documentacion con Swagger.

**Resumen de lo Alcanzado:**

- Backend Spring Boot funcional.
- API REST organizada por bounded contexts.
- Seguridad con JWT y endpoints de autenticacion.
- Persistencia en PostgreSQL mediante Spring Data JPA.
- Seed data inicial para pruebas.
- Swagger UI disponible para documentar y probar endpoints.
- Endpoints para IAM, Profiles, Commerce, Simulation, Gamification y Analytics.
- Pruebas ejecutadas con Maven.
- Configuracion de Docker y variables de entorno para ejecucion local.

**Capturas de Pantalla - Backend API:**

1. **Swagger UI:** Vista general de los controllers y endpoints documentados.

<div align="center">
  <p>
    <b>Grafico 1</b>: Swagger UI del backend SafeStep
  </p>
  <img src="../../assets/images/chapter-5/[insertar-imagen-swagger].png" alt="Swagger UI SafeStep" width="600" />
  <p>
    <i><b>Fuente</b>: Elaboracion propia.</i>
  </p>
</div>

2. **Authentication endpoint:** Evidencia de prueba de `POST /api/v1/authentication/sign-in`.

<div align="center">
  <p>
    <b>Grafico 2</b>: Ejecucion del endpoint de autenticacion
  </p>
  <img src="../../assets/images/chapter-5/[insertar-imagen-authentication].png" alt="Authentication endpoint" width="600" />
  <p>
    <i><b>Fuente</b>: Elaboracion propia.</i>
  </p>
</div>

3. **Commerce endpoints:** Evidencia de consulta de productos, kits o carrito.

<div align="center">
  <p>
    <b>Grafico 3</b>: Ejecucion de endpoints de commerce
  </p>
  <img src="../../assets/images/chapter-5/[insertar-imagen-commerce].png" alt="Commerce endpoint" width="600" />
  <p>
    <i><b>Fuente</b>: Elaboracion propia.</i>
  </p>
</div>

4. **Simulation endpoints:** Evidencia de consulta de simulaciones o registro de intento.

<div align="center">
  <p>
    <b>Grafico 4</b>: Ejecucion de endpoints de simulaciones
  </p>
  <img src="../../assets/images/chapter-5/[insertar-imagen-simulation].png" alt="Simulation endpoint" width="600" />
  <p>
    <i><b>Fuente</b>: Elaboracion propia.</i>
  </p>
</div>

5. **Maven test/build:** Evidencia de pruebas y compilacion exitosa.

<div align="center">
  <p>
    <b>Grafico 5</b>: Ejecucion de pruebas Maven
  </p>
  <img src="../../assets/images/chapter-5/[insertar-imagen-maven-test].png" alt="Maven test" width="600" />
  <p>
    <i><b>Fuente</b>: Elaboracion propia.</i>
  </p>
</div>

**Comandos utilizados para ejecucion local:**

```bash
mvn clean test
```

```bash
mvn spring-boot:run
```

**URL local de Swagger:**

```text
http://localhost:8092/swagger-ui/index.html
```

**URL local de OpenAPI JSON:**

```text
http://localhost:8092/v3/api-docs
```

### 5.2.3.6. Services Documentation Evidence for Sprint Review

En esta seccion se incluye la relacion de endpoints documentados con OpenAPI, relacionados con el alcance del Sprint 3. Durante este Sprint, el equipo implemento el RESTful API interno de SafeStep y expuso la documentacion mediante Swagger UI.

La documentacion de servicios permite que los integrantes del equipo frontend y backend comprendan la sintaxis de cada llamada, los metodos HTTP disponibles, los parametros requeridos y el tipo de respuesta esperada. La URL de Swagger utilizada durante el Sprint fue:

**Swagger UI:** [Insertar URL de Swagger UI local o desplegado]

**OpenAPI JSON:** [Insertar URL de OpenAPI JSON local o desplegado]

| Bounded Context | Endpoint | Metodo | Descripcion | Parametros | Ejemplo Response |
|-----------------|----------|--------|-------------|------------|------------------|
| Authentication | `/api/v1/authentication/sign-in` | POST | Autentica usuario y devuelve JWT | Body: username, password | `{ "id": 1, "username": "ana.torres", "token": "..." }` |
| Authentication | `/api/v1/authentication/sign-up` | POST | Registra un nuevo usuario | Body: username, password, roles | `{ "id": 2, "username": "new.user", "roles": [...] }` |
| IAM | `/api/v1/roles` | GET | Obtiene roles disponibles | Bearer token | `[ { "id": 1, "name": "ROLE_USER" } ]` |
| IAM | `/api/v1/users` | GET | Obtiene usuarios registrados | Bearer token | `[ { "id": 1, "username": "ana.torres" } ]` |
| IAM | `/api/v1/users/{userId}` | GET | Obtiene usuario por identificador | Path: userId | `{ "id": 1, "username": "ana.torres" }` |
| Profiles | `/api/v1/profiles` | GET | Obtiene todos los perfiles | Bearer token | `[ { "id": 1, "firstName": "Ana" } ]` |
| Profiles | `/api/v1/profiles` | POST | Crea un perfil | Body: datos de perfil | `{ "id": 1, "firstName": "Ana" }` |
| Profiles | `/api/v1/profiles/me` | GET | Obtiene perfil actual | Bearer token | `{ "id": 1, "firstName": "Ana" }` |
| Profiles | `/api/v1/profiles/me` | PUT | Actualiza perfil actual | Body: datos actualizados | `{ "id": 1, "firstName": "Ana" }` |
| Profiles | `/api/v1/profiles/{profileId}` | GET | Obtiene perfil por identificador | Path: profileId | `{ "id": 1, "firstName": "Ana" }` |
| Commerce | `/api/v1/commerce/products` | GET | Obtiene productos del catalogo | Ninguno | `[ { "id": "kit-basic", "name": "Basic Kit" } ]` |
| Commerce | `/api/v1/commerce/products/{productId}` | GET | Obtiene producto por identificador | Path: productId | `{ "id": "kit-basic", "name": "Basic Kit" }` |
| Commerce | `/api/v1/commerce/categories` | GET | Obtiene categorias de productos | Ninguno | `[ { "id": "bandages", "name": "Bandages" } ]` |
| Commerce | `/api/v1/commerce/kits` | GET | Obtiene kits de emergencia | Ninguno | `[ { "id": "home-kit", "name": "Home Kit" } ]` |
| Commerce | `/api/v1/commerce/coupons` | GET | Obtiene cupones disponibles | Ninguno | `[ { "id": "SAFE10", "discount": 10 } ]` |
| Commerce | `/api/v1/commerce/recommendations/me` | GET | Obtiene recomendaciones del usuario actual | Bearer token | `[ { "productId": "kit-basic", "reason": "Recommended" } ]` |
| Commerce | `/api/v1/commerce/cart/me` | GET | Obtiene carrito del usuario actual | Bearer token | `[ { "id": "cart-001", "quantity": 2 } ]` |
| Commerce | `/api/v1/commerce/cart/items` | POST | Agrega producto al carrito | Body: productId, quantity | `{ "id": "cart-001", "quantity": 1 }` |
| Commerce | `/api/v1/commerce/cart/items/{itemId}` | PUT | Actualiza item del carrito | Path: itemId, Body: quantity | `{ "id": "cart-001", "quantity": 3 }` |
| Commerce | `/api/v1/commerce/cart/items/{itemId}` | DELETE | Elimina item del carrito | Path: itemId | `204 No Content` |
| Commerce | `/api/v1/commerce/orders/me` | GET | Obtiene ordenes del usuario actual | Bearer token | `[ { "id": "order-001", "status": "PAID" } ]` |
| Commerce | `/api/v1/commerce/orders` | POST | Crea una orden | Body: status | `{ "id": "order-001", "status": "CREATED" }` |
| Commerce | `/api/v1/commerce/shipping-addresses/me` | GET | Obtiene direcciones del usuario actual | Bearer token | `[ { "city": "Lima", "country": "Peru" } ]` |
| Commerce | `/api/v1/commerce/payment-methods` | GET | Obtiene metodos de pago disponibles | Ninguno | `[ { "id": "card", "label": "Credit Card" } ]` |
| Simulation | `/api/v1/simulations` | GET | Obtiene simulaciones medicas | Ninguno | `[ { "id": "cpr-basic", "title": "CPR Basic" } ]` |
| Simulation | `/api/v1/simulations/{simulationId}` | GET | Obtiene simulacion por identificador | Path: simulationId | `{ "id": "cpr-basic", "steps": [...] }` |
| Simulation | `/api/v1/simulations/{simulationId}/attempts` | POST | Registra intento de simulacion | Path: simulationId, Body: answers | `{ "id": "attempt-001", "score": 90 }` |
| Simulation | `/api/v1/simulations/attempts/me` | GET | Obtiene intentos del usuario actual | Bearer token | `[ { "simulationId": "cpr-basic", "score": 90 } ]` |
| Gamification | `/api/v1/gamification/summary/me` | GET | Obtiene resumen de gamificacion | Bearer token | `{ "level": 4, "coins": 120 }` |
| Gamification | `/api/v1/gamification/missions` | GET | Obtiene misiones disponibles | Bearer token | `[ { "id": "mission-001", "title": "Complete simulation" } ]` |
| Gamification | `/api/v1/gamification/badges/me` | GET | Obtiene insignias del usuario actual | Bearer token | `[ { "id": "badge-001", "unlocked": true } ]` |
| Gamification | `/api/v1/gamification/leaderboard` | GET | Obtiene leaderboard | Bearer token | `[ { "rank": 1, "username": "ana.torres" } ]` |
| Gamification | `/api/v1/gamification/coin-transactions/me` | GET | Obtiene transacciones de monedas | Bearer token | `[ { "amount": 20, "reason": "Simulation completed" } ]` |
| Analytics | `/api/v1/analytics/summary/me` | GET | Obtiene resumen analitico del usuario | Bearer token | `{ "completedSimulations": 8, "accuracy": 85 }` |
| Analytics | `/api/v1/analytics/progress/me` | GET | Obtiene progreso visual del usuario | Bearer token | `{ "weeklyProgress": [...] }` |
| Analytics | `/api/v1/analytics/certificates/me` | GET | Obtiene certificados del usuario | Bearer token | `[ { "id": "cert-001", "title": "First Aid Basics" } ]` |

**Captura de documentacion Swagger:**

<div align="center">
  <p>
    <b>Grafico 1</b>: Documentacion OpenAPI del backend SafeStep
  </p>
  <img src="../../assets/images/chapter-5/[insertar-imagen-openapi-documentation].png" alt="OpenAPI documentation" width="600" />
  <p>
    <i><b>Fuente</b>: Elaboracion propia.</i>
  </p>
</div>

### 5.2.3.7. Software Deployment Evidence for Sprint Review

En esta seccion se resumen los procesos realizados en relacion con Deployment durante el Sprint 3. Para este Sprint, el equipo se enfoco en configurar la ejecucion local del backend Spring Boot, preparar el proyecto para despliegue mediante Docker y documentar las variables de entorno necesarias para conectar el API con PostgreSQL.

Aunque la validacion principal se realizo en entorno local, el backend fue preparado para poder desplegarse posteriormente en una plataforma cloud compatible con aplicaciones Java y contenedores Docker. Esta decision permite avanzar primero en estabilidad funcional y luego completar el despliegue productivo en un sprint posterior.

**Paso 1: Configuracion del entorno local**

Se instalo y configuro Java Development Kit, Apache Maven y PostgreSQL. El equipo creo la base de datos `safestep` y definio las credenciales locales necesarias para conectar la aplicacion con el motor de base de datos.

```text
Database name: safestep
Database user: postgres
Database password: [Insertar password usado por el equipo]
Backend port: 8092
```

**Paso 2: Configuracion de application properties**

El backend utiliza archivos de configuracion por ambiente para definir la conexion a base de datos, el puerto de ejecucion y las variables necesarias para JWT. La configuracion de desarrollo permite levantar el API localmente sin modificar codigo fuente.

**Referencia de archivo de configuracion:** `src/main/resources/application-dev.properties`

**Paso 3: Configuracion de Docker**

Se agrego un `Dockerfile` para construir la imagen del backend y un `docker-compose.yml` para levantar PostgreSQL junto con las variables requeridas por la aplicacion. Esta configuracion permite que otro integrante del equipo pueda ejecutar el proyecto con menor friccion.

**Referencia de Dockerfile:** [Insertar captura o enlace al archivo Dockerfile]

**Referencia de docker-compose:** [Insertar captura o enlace al archivo docker-compose.yml]

**Paso 4: Ejecucion local del backend**

Para levantar el backend en ambiente local, se ejecuta el siguiente comando desde la raiz del proyecto:

```bash
mvn spring-boot:run
```

Luego se verifica la disponibilidad de Swagger UI:

```text
http://localhost:8092/swagger-ui/index.html
```

**Paso 5: Verificacion de endpoints**

El equipo verifico los endpoints principales utilizando Swagger UI y peticiones HTTP manuales. Se comprobaron endpoints de autenticacion, perfiles, comercio, simulaciones, gamificacion y analitica.

<div align="center">
  <p>
    <b>Grafico 1</b>: Backend ejecutandose localmente
  </p>
  <img src="../../assets/images/chapter-5/[insertar-imagen-backend-running].png" alt="Backend running" width="600" />
  <p>
    <i><b>Fuente</b>: Elaboracion propia.</i>
  </p>
</div>

**Resultado del despliegue o ejecucion:**

| Producto | Plataforma | URL |
|----------|-----------|-----|
| Backend Spring Boot | Local environment | http://localhost:8092 |
| Swagger UI | Local environment | http://localhost:8092/swagger-ui/index.html |
| OpenAPI JSON | Local environment | http://localhost:8092/v3/api-docs |
| Backend desplegado | [Insertar plataforma] | [Insertar URL del backend desplegado] |

### 5.2.3.8. Team Collaboration Insights during Sprint

En esta seccion el equipo explica como se desarrollaron las actividades de implementacion del Sprint 3 y presenta las evidencias de colaboracion relacionadas con el backend. El trabajo se distribuyo por bounded context, manteniendo coordinacion constante para que la estructura del codigo sea consistente y alineada con la arquitectura de referencia del curso.

**Distribucion de Trabajo:**

Los cuatro miembros activos del equipo participaron en el desarrollo del backend. La distribucion se baso en los aspectos definidos en la matriz LACX, asignando lideres por bounded context y colaboradores para revision, validacion y documentacion.

Durante este Sprint, el equipo realizo revisiones internas de estructura para asegurar que los paquetes de cada bounded context mantuvieran una organizacion similar: domain, application, infrastructure e interfaces. Tambien se reviso que los comandos, queries y resources estuvieran separados en archivos individuales, permitiendo que el codigo sea mas facil de explicar durante la sustentacion.

**Metricas de Colaboracion:**

<table align="center" border="1" cellpadding="8" cellspacing="0" style="border-collapse: collapse; width: 100%; font-family: Arial, sans-serif;">
    <tbody>
        <tr>
            <td><b>Miembro</b></td>
            <td><b>Repositorio</b></td>
            <td><b>Commits</b></td>
            <td><b>Lineas additions</b></td>
            <td><b>Lineas eliminadas</b></td>
            <td><b>PRs merged</b></td>
        </tr>
        <tr>
            <td>Ayala Fernandez, Jorge Brayan</td>
            <td>safestep-backend</td>
            <td>[Insertar cantidad]</td>
            <td>[Insertar cantidad]</td>
            <td>[Insertar cantidad]</td>
            <td>[Insertar cantidad]</td>
        </tr>
        <tr>
            <td>Sanchez Espinoza, Mathias Enrique</td>
            <td>safestep-backend</td>
            <td>[Insertar cantidad]</td>
            <td>[Insertar cantidad]</td>
            <td>[Insertar cantidad]</td>
            <td>[Insertar cantidad]</td>
        </tr>
        <tr>
            <td>Melgarejo Quiroz, Josep Eliu</td>
            <td>safestep-backend</td>
            <td>[Insertar cantidad]</td>
            <td>[Insertar cantidad]</td>
            <td>[Insertar cantidad]</td>
            <td>[Insertar cantidad]</td>
        </tr>
        <tr>
            <td>Flores Eusebio, Angel Thyago</td>
            <td>safestep-backend</td>
            <td>[Insertar cantidad]</td>
            <td>[Insertar cantidad]</td>
            <td>[Insertar cantidad]</td>
            <td>[Insertar cantidad]</td>
        </tr>
    </tbody>
</table>

**Analiticos de GitHub:**

<div align="center">
  <p>
    <b>Grafico 1</b>: Analytics Sprint 3 Backend
  </p>
  <img src="../../assets/images/chapter-5/[insertar-imagen-github-analytics-sprint-3].png" alt="Analytics Sprint 3" width="500" />
  <p>
    <i><b>Fuente</b>: Elaboracion propia.</i>
  </p>
</div>

**Distribucion de trabajo por tipo de tarea:**

- Configuracion del proyecto Spring Boot y dependencias: 10% del tiempo total.
- Implementacion de bounded contexts: 55% del tiempo total.
- Persistencia JPA y PostgreSQL: 15% del tiempo total.
- Seguridad JWT y configuracion compartida: 8% del tiempo total.
- Documentacion Swagger y pruebas manuales: 7% del tiempo total.
- Documentacion del Sprint y evidencias: 5% del tiempo total.

**Reflexiones del Equipo:**

- Ayala Fernandez, Jorge Brayan: "Implementar el bounded context de commerce nos permitio trasladar la tienda del frontend a una API real. El mayor reto fue mantener la relacion entre productos, carrito, ordenes y recomendaciones sin perder claridad en la estructura del codigo."

- Sanchez Espinoza, Mathias Enrique: "El modulo de simulaciones fue importante porque conecta directamente con el valor principal de SafeStep. Separar simulaciones, pasos, opciones e intentos ayudo a que el backend sea mas ordenado y facil de probar desde Swagger."

- Melgarejo Quiroz, Josep Eliu: "Trabajar en gamification, analytics y shared infrastructure permitio dar soporte transversal al backend. La configuracion de Swagger, seed data y servicios compartidos fue clave para que los demas bounded contexts funcionen de forma consistente."

- Flores Eusebio, Angel Thyago: "Durante este Sprint apoye en IAM, Profiles, validacion de endpoints, seed data y documentacion. Probar el backend desde Swagger ayudo a identificar rapidamente problemas de rutas, respuestas y datos iniciales."

**Lecciones Aprendidas:**

1. **El backend requiere una estructura mas estricta que el frontend con datos simulados:** Al trabajar con base de datos, seguridad y persistencia, fue necesario definir responsabilidades claras entre capas.

2. **Swagger facilita la comunicacion entre frontend y backend:** Tener endpoints visibles y probables desde una interfaz comun redujo dudas sobre rutas, parametros y respuestas.

3. **La separacion por bounded contexts mejora la explicacion del proyecto:** Organizar el backend en iam, profiles, commerce, simulation, gamification y analytics permite sustentar mejor la arquitectura durante la exposicion.

4. **El seed data acelera las pruebas iniciales:** Contar con datos precargados permitio validar endpoints sin depender de carga manual desde base de datos.

5. **La consistencia de nombres ayuda a evitar errores:** Mantener convenciones similares en commands, queries, resources, controllers y services hizo que el equipo pudiera moverse entre bounded contexts con menor dificultad.
