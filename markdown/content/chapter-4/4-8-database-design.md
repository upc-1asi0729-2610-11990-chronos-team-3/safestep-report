<br>
<br>

<div align="center">
    <img src="../../assets/images/chapter-4/capitulo-4.png" alt="Capitulo 4" />
</div>

<br>
<br>

# 4.8. Database Design

## 4.8.1. Database Diagrams

El siguiente Diagrama Entidad-Relación (ERD) representa la estructura de datos fundamental que soporta toda la lógica de la plataforma SafeStep. Este modelo relacional, compuesto por 33 entidades, ha sido diseñado aplicando las 3 fases de normalizacion. Para garantizar la escalabilidad, el mantenimiento y la separación de responsabilidades, la base de datos se ha estructurado en 5 paquetes o módulos lógicos:
### 1. Gestión de Usuarios y Seguridad: 
Controla la identidad, el Control de Acceso Basado en Roles (RBAC), el manejo de sesiones activas (para bloqueos de seguridad) y la libreta de direcciones de los usuarios.
### 2. Motor de Simulaciones:
Es el núcleo educativo. Gestiona los módulos de aprendizaje, el catálogo de escenarios interactivos (RCP, Sismos, etc.) y guarda un historial detallado de los intentos y errores específicos para generar recomendaciones personalizadas.
### 3. Motor de Gamificación:
Diseñado para maximizar la retención. Administra el progreso del usuario (Niveles y XP), misiones con caducidad de tiempo, insignias y el sistema de economía virtual (SafeCoins) para la adquisición de artículos cosméticos.
### 4. Marketplace y Logística:
Gestiona el catálogo de productos físicos (Kits de emergencia, torniquetes), permitiendo la creación de productos compuestos, el control de inventario y el sistema de reseñas y favoritos.
### 5. Ventas y Transacciones:
Maneja el flujo de conversión, desde el carrito de compras persistente, validación de cupones, hasta el registro de la orden final, la pasarela de pagos y el proceso de devoluciones con evidencia documentada.

<div align="center">
    <img src="../../assets/images/chapter-4/diagrama-basedatos-safestep.svg" alt="Diagrama de base de datos" />
    <br>
    <sub><small>link (vista del diagrama de base de datos en Miro): <a href="https://miro.com/app/live-embed/uXjVHWa4-Tg=/?focusWidget=3458764671099531415&embedMode=view_only_without_ui&embedId=945877900476">https://miro.com/app/live-embed/uXjVHWa4-Tg=/?focusWidget=3458764671099531415&embedMode=view_only_without_ui&embedId=945877900476</small></sub>
</div>

