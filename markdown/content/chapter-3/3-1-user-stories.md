<br>
<br>

<div align="center">
    <img src="../../assets/images/chapter-3/capitulo-3.png" alt="Capitulo 3" />
</div>

<br>
<br>

# 3.1. User Stories

## Epics

<table align="center">
    <tr>
        <td align="center">
        <b>Epic ID</b>
        </td>
        <td align="center">
        <b>Descripción de la épica</b>
        </td>
    </tr>
    <tr>
        <td align="center"><b>EP01</b></td>
        <td align="center">Onboarding y Accesibilidad</td>
    </tr>
    <tr>
        <td align="center"><b>EP02</b></td>
        <td align="center">Simulaciones de Emergencias</td>
    </tr>
    <tr>
        <td align="center"><b>EP03</b></td>
        <td align="center">Retroalimentación y Aprendizaje Progresivo</td>
    </tr>
    <tr>
        <td align="center"><b>EP04</b></td>
        <td align="center">Comercio electrónico</td>
    </tr>
    <tr>
        <td align="center"><b>EP05</b></td>
        <td align="center">Gamificación y recompensas</td>
    </tr>
    <tr>
        <td align="center"><b>EP06</b></td>
        <td align="center">Captación y conversión de usuarios nuevos</td>
    </tr>
    <tr>
        <td align="center"><b>EP07</b></td>
        <td align="center">Seguridad, Estabilidad y Rendimiento de la Plataforma</td>
    </tr>
</table>

## User Stories

<table align="center">
    <tr>
        <td><b>User Story ID</b></td>
        <td>US01</b></td>
        <td><b>Epic ID</b></td>
        <td>EP01</b></td>
    </tr>
    <tr>
        <td><b>Título</b></td>
        <td colspan="3">Registro de nuevo usuario</b></td>
    </tr>
    <tr>
        <td><b>Descripción</b></td>
        <td colspan="3">Como nuevo usuario, quiero registrarme en SafeStep de forma rápida y segura utilizando mi correo electrónico, número de teléfono o cuentas de redes sociales (Google, Facebook, Apple), para crear mi perfil personalizado, acceder a todas las funcionalidades de la plataforma y comenzar mi aprendizaje en primeros auxilios sin demoras innecesarias.</b></td>
    </tr>
    <tr>
        <td colspan="4">
            <b>Criterios de aceptación:</b> <br/>
            <ol>
                <li>El sistema debe ofrecer múltiples opciones de registro: correo electrónico + contraseña, número de teléfono + SMS, o autenticación mediante OAuth (Google, Facebook, Apple).</li>
                <li>Para registro con correo, debe validar que el correo no esté previamente registrado y que la contraseña cumpla requisitos mínimos (mínimo 8 caracteres, al menos una letra mayúscula, un número y un carácter especial).</li>
                <li>Para registro con teléfono, debe enviar un código de verificación SMS de 6 dígitos con vigencia de 5 minutos, y solicitar al usuario que lo ingrese para activar la cuenta.</li>
                <li>Para registro con OAuth, debe completarse en menos de 10 segundos, solicitando solo los permisos mínimos necesarios (nombre, correo electrónico, foto de perfil).</li>
                <li>Durante el registro, el sistema debe solicitar información básica del perfil: nombre completo (obligatorio), fecha de nacimiento (opcional, para personalizar contenido por edad), país y ciudad (opcional, para recomendar eventos locales).</li>
                <li>El usuario debe aceptar los términos y condiciones y la política de privacidad antes de completar el registro, con enlaces visibles y legibles.</li>
                <li>En caso de error (correo duplicado, teléfono ya registrado, contraseña débil), la aplicación debe mostrar mensajes claros y específicos, indicando cómo corregir el problema.</li>
                <li>Después del registro exitoso, el sistema debe enviar un correo electrónico de bienvenida con un enlace de verificación (opcional, para confirmar la dirección) y mostrar un tour guiado opcional del dashboard.</li>
                <li>Los datos del usuario deben almacenarse cumpliendo con los lineamientos de protección de datos personales (GDPR, CCPA o equivalentes locales), con opción de solicitar la eliminación de la cuenta en cualquier momento.</li>
                <li>El sistema debe implementar mecanismos anti-bots (reCAPTCHA o similar) en el formulario de registro para prevenir registros automatizados.</li>
            </ol>
            <b>Escenario 1 (Registro exitoso con correo electrónico):</b> <br/>
            <ul>
                <li><b>Given</b> que una persona abre la aplicación SafeStep por primera vez en su dispositivo,</li>
                <li><b>And</b> selecciona la opción "Registrarse" en la pantalla de bienvenida,</li>
                <li><b>When</b> completa el formulario con nombre completo "Juan Pérez", correo "juan@example.com", teléfono opcional y contraseña segura "Juan2024*",</li>
                <li><b>And</b> acepta los términos y condiciones,</li>
                <li><b>Then</b> el sistema valida que el correo no existe previamente,</li>
                <li><b>And</b> crea la cuenta exitosamente,</li>
                <li><b>And</b> redirige al usuario al dashboard principal ya autenticado,</li>
                <li><b>And</b> envía un correo de bienvenida a juan@example.com con un enlace de verificación.</li>
            </ul>
            <b>Escenario 2 (Registro con Google OAuth):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario está en la pantalla de registro,</li>
                <li><b>When</b> selecciona la opción "Continuar con Google",</li>
                <li><b>Then</b> el sistema abre la ventana emergente de autenticación de Google,</li>
                <li><b>When</b> el usuario selecciona su cuenta y autoriza el acceso,</li>
                <li><b>Then</b> el sistema recibe los datos básicos (nombre, correo, foto de perfil),</li>
                <li><b>And</b> crea automáticamente la cuenta asociada a ese correo,</li>
                <li><b>And</b> redirige al usuario al dashboard principal ya autenticado,</li>
                <li><b>And</b> el proceso completo dura menos de 10 segundos.</li>
            </ul>
            <b>Escenario 3 (Registro con número de teléfono y SMS):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario selecciona la opción "Registrarse con teléfono",</li>
                <li><b>When</b> ingresa su número "+51 987654321" y presiona "Enviar código",</li>
                <li><b>Then</b> el sistema envía un código SMS de 6 dígitos al número proporcionado,</li>
                <li><b>When</b> el usuario ingresa el código correctamente dentro de los 5 minutos,</li>
                <li><b>Then</b> el sistema completa el registro, solicita el nombre completo del usuario,</li>
                <li><b>And</b> crea la cuenta exitosamente,</li>
                <li><b>And</b> redirige al dashboard principal ya autenticado.</li>
            </ul>
            <b>Escenario 4 (Error - correo ya registrado):</b> <br/>
            <ul>
                <li><b>Given</b> que un usuario intenta registrarse con un correo que ya existe en la base de datos,</li>
                <li><b>When</b> completa el formulario y presiona "Registrarse",</li>
                <li><b>Then</b> el sistema detecta el correo duplicado,</li>
                <li><b>And</b> muestra un mensaje claro: "Este correo electrónico ya está registrado. ¿Deseas iniciar sesión o recuperar tu contraseña?",</li>
                <li><b>And</b> ofrece enlaces directos a "Iniciar sesión" y "¿Olvidaste tu contraseña?" para ayudar al usuario a recuperar el acceso.</li>
            </ul>
            <b>Escenario 5 (Error - contraseña débil):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario intenta registrarse con una contraseña débil,</li>
                <li><b>When</b> ingresa "12345" en el campo de contraseña,</li>
                <li><b>Then</b> el sistema muestra un mensaje de error en tiempo real: "La contraseña debe tener al menos 8 caracteres, una mayúscula, un número y un carácter especial",</li>
                <li><b>And</b> el botón "Registrarse" permanece deshabilitado hasta que la contraseña cumpla los requisitos.</li>
            </ul>
        </b></td>
    </tr>
</table>

<table align="center">
    <tr>
        <td><b>User Story ID</b></td>
        <td>US02</b></td>
        <td><b>Epic ID</b></td>
        <td>EP01</b></td>
    </tr>
    <tr>
        <td><b>Título</b></td>
        <td colspan="3">Inicio de sesión</b></td>
    </tr>
    <tr>
        <td><b>Descripción</b></td>
        <td colspan="3">Como usuario registrado, quiero iniciar sesión en SafeStep de forma rápida, segura y sin fricciones, utilizando mis credenciales (correo/contraseña, teléfono/SMS o redes sociales), para acceder a mi dashboard personalizado, retomar mis simulaciones donde las dejé y continuar mi progreso de aprendizaje sin interrupciones.</b></td>
    </tr>
    <tr>
        <td colspan="4">
            <b>Criterios de aceptación:</b> <br/>
            <ol>
                <li>El sistema debe ofrecer múltiples métodos de inicio de sesión: correo electrónico + contraseña, número de teléfono + código SMS, o autenticación mediante OAuth (Google, Facebook, Apple).</li>
                <li>El proceso de inicio de sesión no debe exceder los 5 segundos en condiciones normales de red.</li>
                <li>El sistema debe incluir una opción "Recordarme" que mantenga la sesión activa durante 30 días (o el tiempo configurado por el administrador).</li>
                <li>Después de 3 intentos fallidos consecutivos de inicio de sesión, el sistema debe mostrar un captcha (reCAPTCHA o similar) para verificar que no es un bot.</li>
                <li>Después de 5 intentos fallidos consecutivos, el sistema debe bloquear temporalmente la cuenta durante 15 minutos y notificar al usuario por correo electrónico o SMS sobre el intento de acceso sospechoso.</li>
                <li>Los mensajes de error de inicio de sesión deben ser genéricos para proteger la privacidad: "Correo electrónico o contraseña incorrectos" (sin revelar si el correo existe o no).</li>
                <li>El sistema debe ofrecer la opción "¿Olvidaste tu contraseña?" visible desde la pantalla de inicio de sesión, que inicie el flujo de recuperación (US03).</li>
                <li>Una vez autenticado, el sistema debe mostrar el nombre y avatar del usuario en la barra de navegación del dashboard.</li>
                <li>El sistema debe implementar autenticación de dos factores (2FA) opcional para usuarios que deseen mayor seguridad, utilizando una app autenticadora (Google Authenticator, Authy) o SMS.</li>
                <li>El sistema debe registrar la dirección IP, el dispositivo y la fecha/hora de cada inicio de sesión, permitiendo al usuario ver esta información en la sección "Seguridad" de su perfil.</li>
            </ol>
            <b>Escenario 1 (Inicio de sesión exitoso con correo y contraseña):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario ya tiene una cuenta creada en SafeStep,</li>
                <li><b>When</b> ingresa su correo "juan@example.com" y su contraseña válida,</li>
                <li><b>And</b> pulsa el botón "Iniciar sesión",</li>
                <li><b>Then</b> el sistema valida las credenciales en menos de 3 segundos,</li>
                <li><b>And</b> crea un token de sesión activo,</li>
                <li><b>And</b> redirige al usuario a su dashboard personalizado,</li>
                <li><b>And</b> muestra en la barra superior "Hola, Juan" junto con su foto de perfil.</li>
            </ul>
            <b>Escenario 2 (Inicio de sesión con "Recordarme"):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario marca la opción "Recordarme" antes de iniciar sesión,</li>
                <li><b>When</b> ingresa sus credenciales correctamente y presiona "Iniciar sesión",</li>
                <li><b>Then</b> el sistema crea una sesión persistente,</li>
                <li><b>And</b> cuando el usuario cierra el navegador o la aplicación y vuelve a abrirla dentro de los próximos 30 días,</li>
                <li><b>Then</b> el sistema lo mantiene autenticado sin solicitar nuevamente sus credenciales,</li>
                <li><b>And</b> muestra un mensaje: "Sesión reanudada. ¿No eres tú? Cierra sesión aquí".</li>
            </ul>
            <b>Escenario 3 (Inicio de sesión fallido - bloqueo temporal):</b> <br/>
            <ul>
                <li><b>Given</b> que un usuario intenta iniciar sesión con credenciales incorrectas,</li>
                <li><b>When</b> realiza 3 intentos fallidos,</li>
                <li><b>Then</b> en el cuarto intento, el sistema muestra un captcha para verificar que no es un bot,</li>
                <li><b>When</b> el usuario continúa fallando hasta 5 intentos,</li>
                <li><b>Then</b> el sistema bloquea temporalmente la cuenta durante 15 minutos,</li>
                <li><b>And</b> envía un correo de alerta a la dirección registrada: "Se detectaron múltiples intentos fallidos de inicio de sesión en tu cuenta. Si no fuiste tú, contacta a soporte",</li>
                <li><b>And</b> después de 15 minutos, la cuenta se desbloquea automáticamente.</li>
            </ul>
            <b>Escenario 4 (Inicio de sesión con autenticación de dos factores - 2FA):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario tiene habilitada la autenticación de dos factores en su perfil,</li>
                <li><b>When</b> ingresa su correo y contraseña correctamente,</li>
                <li><b>Then</b> el sistema solicita un código de verificación de 6 dígitos,</li>
                <li><b>When</b> el usuario ingresa el código generado por su app autenticadora (Google Authenticator),</li>
                <li><b>Then</b> el sistema completa la autenticación y redirige al dashboard,</li>
                <li><b>And</b> registra el dispositivo como "confiable" si el usuario lo autoriza, evitando solicitar 2FA en ese dispositivo durante 30 días.</li>
            </ul>
            <b>Escenario 5 (Inicio de sesión con teléfono y SMS):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario tiene registrado su número de teléfono en SafeStep,</li>
                <li><b>When</b> selecciona la opción "Iniciar sesión con teléfono", ingresa su número "+51 987654321" y presiona "Enviar código",</li>
                <li><b>Then</b> el sistema envía un código SMS de 6 dígitos con vigencia de 5 minutos,</li>
                <li><b>When</b> el usuario ingresa el código correctamente,</li>
                <li><b>Then</b> el sistema autentica al usuario y redirige al dashboard,</li>
                <li><b>And</b> este método de inicio de sesión es útil para usuarios que olvidaron su contraseña o prefieren no usar correo.</li>
            </ul>
        </b></td>
    </tr>
</table>

<table align="center">
    <tr>
        <td><b>User Story ID</b></td>
        <td>US03</b></td>
        <td><b>Epic ID</b></td>
        <td>EP01</b></td>
    </tr>
    <tr>
        <td><b>Título</b></td>
        <td colspan="3">Recuperación de contraseña</b></td>
    </tr>
    <tr>
        <td><b>Descripción</b></td>
        <td colspan="3">Como usuario registrado, quiero poder recuperar mi contraseña olvidada de forma rápida, segura y sin complicaciones, utilizando mi correo electrónico o número de teléfono registrado, para restablecer el acceso a mi cuenta sin necesidad de crear un nuevo perfil ni perder mi progreso de aprendizaje.</b></td>
    </tr>
    <tr>
        <td colspan="4">
            <b>Criterios de aceptación:</b> <br/>
            <ol>
                <li>El sistema debe ofrecer la opción "¿Olvidaste tu contraseña?" desde la pantalla de inicio de sesión, visible y accesible.</li>
                <li>La recuperación debe poder realizarse mediante correo electrónico (envío de enlace único) o número de celular registrado previamente (envío de código SMS).</li>
                <li>El enlace de restablecimiento (correo) o código SMS debe tener una vigencia máxima de 15 minutos y ser de un solo uso.</li>
                <li>El sistema debe validar que el correo o número ingresado estén asociados a una cuenta activa antes de enviar el enlace o código, pero sin revelar si la cuenta existe (para evitar enumeración de usuarios).</li>
                <li>La nueva contraseña debe cumplir con los requisitos de seguridad establecidos (mínimo 8 caracteres, al menos una mayúscula, un número y un carácter especial).</li>
                <li>Una vez restablecida la contraseña, el sistema debe invalidar automáticamente cualquier enlace o código de restablecimiento anterior no utilizado.</li>
                <li>El sistema debe notificar al usuario por correo electrónico y/o SMS que su contraseña ha sido cambiada, incluyendo la fecha, hora y dispositivo desde el que se realizó el cambio (con advertencia de contactar a soporte si no fue el usuario).</li>
                <li>Después de 3 solicitudes de restablecimiento en menos de 1 hora para la misma cuenta, el sistema debe bloquear temporalmente nuevos intentos durante 30 minutos (para prevenir ataques de spam).</li>
                <li>El sistema debe permitir al usuario cancelar una solicitud de restablecimiento pendiente desde el correo o SMS recibido.</li>
                <li>Si el usuario restablece su contraseña, debe cerrar sesión en todos los dispositivos activos (excepto el actual) por seguridad.</li>
            </ol>
            <b>Escenario 1 (Recuperación exitosa por correo electrónico):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario se encuentra en la pantalla de inicio de sesión,</li>
                <li><b>When</b> pulsa la opción "¿Olvidaste tu contraseña?" e ingresa su correo electrónico "juan@example.com",</li>
                <li><b>Then</b> el sistema valida que el correo existe en la base de datos (sin revelarlo al usuario),</li>
                <li><b>And</b> envía un correo electrónico con un enlace único de restablecimiento (ejemplo: https://safestep.com/reset?token=abc123),</li>
                <li><b>When</b> el usuario hace clic en el enlace dentro de los 15 minutos,</li>
                <li><b>Then</b> se abre una página segura donde puede ingresar su nueva contraseña (con validación de requisitos de seguridad),</li>
                <li><b>When</b> confirma la nueva contraseña,</li>
                <li><b>Then</b> el sistema actualiza la contraseña, invalida el token, y redirige al usuario a la pantalla de inicio de sesión con un mensaje: "Contraseña restablecida exitosamente. Inicia sesión con tu nueva contraseña".</li>
            </ul>
            <b>Escenario 2 (Recuperación por SMS - código de verificación):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario selecciona la opción "Recuperar por SMS" en la pantalla de recuperación,</li>
                <li><b>When</b> ingresa su número de teléfono registrado "+51 987654321",</li>
                <li><b>Then</b> el sistema envía un código SMS de 6 dígitos con vigencia de 15 minutos,</li>
                <li><b>When</b> el usuario ingresa el código correctamente en la aplicación,</li>
                <li><b>Then</b> se habilita el formulario para ingresar una nueva contraseña,</li>
                <li><b>When</b> el usuario establece y confirma la nueva contraseña válida,</li>
                <li><b>Then</b> el sistema actualiza la contraseña y redirige al inicio de sesión con un mensaje de éxito.</li>
            </ul>
            <b>Escenario 3 (Enlace expirado - solicitar nuevo):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario solicitó un restablecimiento de contraseña por correo,</li>
                <li><b>When</b> hace clic en el enlace después de 20 minutos (excediendo la vigencia de 15 minutos),</li>
                <li><b>Then</b> el sistema muestra un mensaje: "El enlace de restablecimiento ha expirado por seguridad. Por favor, solicita un nuevo enlace",</li>
                <li><b>And</b> ofrece un botón "Enviar nuevo enlace" que reenvía el correo con un token fresco,</li>
                <li><b>When</b> el usuario solicita un nuevo enlace,</li>
                <li><b>Then</b> el sistema invalida el token anterior y envía uno nuevo.</li>
            </ul>
            <b>Escenario 4 (Notificación de cambio de contraseña - seguridad):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario ha restablecido su contraseña exitosamente,</li>
                <li><b>Then</b> el sistema envía un correo electrónico de notificación a la dirección registrada (y SMS opcional),</li>
                <li><b>And</b> el mensaje incluye: "Tu contraseña fue cambiada el [fecha] a las [hora] desde la IP [xxx.xxx.xxx.xxx]. Si no realizaste este cambio, contacta inmediatamente a soporte@SafeStep.com",</li>
                <li><b>And</b> el sistema cierra todas las sesiones activas del usuario en otros dispositivos, solicitando iniciar sesión nuevamente con la nueva contraseña.</li>
            </ul>
            <b>Escenario 5 (Límite de solicitudes - prevención de spam):</b> <br/>
            <ul>
                <li><b>Given</b> que un usuario solicita restablecimiento de contraseña 3 veces en menos de 1 hora para la misma cuenta,</li>
                <li><b>When</b> intenta una cuarta solicitud,</li>
                <li><b>Then</b> el sistema muestra un mensaje: "Has excedido el número de solicitudes de restablecimiento. Por favor, espera 30 minutos antes de intentar nuevamente",</li>
                <li><b>And</b> el contador se reinicia después del tiempo de espera.</li>
            </ul>
        </b></td>
    </tr>
</table>

<table align="center">
    <tr>
        <td><b>User Story ID</b></td>
        <td>US04</b></td>
        <td><b>Epic ID</b></td>
        <td>EP01</b></td>
    </tr>
    <tr>
        <td><b>Título</b></td>
        <td colspan="3">Dashboard principal y personalización</b></td>
    </tr>
    <tr>
        <td><b>Descripción</b></td>
        <td colspan="3">Como usuario autenticado, quiero acceder a un dashboard principal personalizado que muestre mi progreso de aprendizaje, simulaciones recomendadas, estadísticas clave y accesos rápidos a las funcionalidades más importantes, para tener una visión clara de mi estado actual y poder navegar eficientemente por la plataforma.</b></td>
    </tr>
    <tr>
        <td colspan="4">
            <b>Criterios de aceptación:</b> <br/>
            <ol>
                <li>El dashboard debe ser la pantalla principal después del inicio de sesión, con una estructura clara y responsiva (adaptable a móvil, tablet y escritorio).</li>
                <li>Debe mostrar un saludo personalizado con el nombre del usuario y, opcionalmente, una frase motivacional diaria (ejemplo: "¡Hola, Juan! Sigue así, llevas 5 días de racha").</li>
                <li>El dashboard debe incluir un resumen visual del progreso general: porcentaje de avance en el plan de aprendizaje, número de simulaciones completadas, certificaciones obtenidas y racha actual de práctica.</li>
                <li>Debe mostrar las simulaciones recomendadas (basadas en US12 - Recomendaciones personalizadas) con acceso directo a cada una.</li>
                <li>Debe incluir una sección "Continuar donde lo dejaste" que muestre la última simulación o lección no completada, permitiendo reanudarla con un solo clic.</li>
                <li>El dashboard debe mostrar notificaciones recientes (actividad de la comunidad, logros desbloqueados, nuevos contenidos) en una sección colapsable o feed.</li>
                <li>Debe incluir accesos rápidos a las secciones principales: "Simulaciones", "Mi Progreso", "Certificaciones", "Tienda" (EP04), "Comunidad" (EP05), y "Configuración".</li>
                <li>El usuario debe poder personalizar el dashboard: elegir qué widgets mostrar (progreso, recomendaciones, actividad reciente, insignias), reordenarlos mediante arrastrar y soltar, y ocultar los que no le interesen.</li>
                <li>El dashboard debe mostrar insignias o logros recientemente desbloqueados con animación de celebración.</li>
                <li>Debe incluir un banner rotativo con noticias o promociones relevantes (nuevos módulos, ofertas en la tienda, eventos comunitarios) que el usuario pueda cerrar si no le interesan.</li>
                <li>El tiempo de carga del dashboard no debe exceder los 2 segundos en condiciones normales de red.</li>
            </ol>
            <b>Escenario 1 (Vista general del dashboard al iniciar sesión):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario "Juan Pérez" ha iniciado sesión correctamente,</li>
                <li><b>When</b> es redirigido a su dashboard principal,</li>
                <li><b>Then</b> ve un saludo personalizado: "¡Hola, Juan! ¡Buenos días! Tu racha actual es de 7 días",</li>
                <li><b>And</b> un widget de progreso muestra un gráfico circular con "Avance general: 65%",</li>
                <li><b>And</b> una sección "Continuar donde lo dejaste" muestra la simulación "Control de hemorragias - Paso 3/5" con un botón "Reanudar",</li>
                <li><b>And</b> una sección "Recomendado para ti" muestra dos tarjetas: "Refuerza RCP" y "Práctica de torniquete",</li>
                <li><b>And</b> en la parte inferior, las insignias desbloqueadas: "Primera simulación", "Racha de 7 días", "Maestro de RCP".</li>
            </ul>
            <b>Escenario 2 (Personalización del dashboard - ocultar/mostrar widgets):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario accede a su dashboard y no le interesa ver la sección "Actividad de la comunidad",</li>
                <li><b>When</b> hace clic en el ícono de configuración del widget (tres puntos) y selecciona "Ocultar esta sección",</li>
                <li><b>Then</b> el widget desaparece del dashboard,</li>
                <li><b>And</b> la preferencia se guarda en el perfil del usuario,</li>
                <li><b>When</b> el usuario vuelve a iniciar sesión en otro dispositivo,</li>
                <li><b>Then</b> el dashboard mantiene la misma configuración de widgets (sincronizada en la nube).</li>
            </ul>
            <b>Escenario 3 (Reordenamiento de widgets mediante arrastrar y soltar):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario está en su dashboard y desea que el widget "Mi progreso" aparezca antes que "Recomendaciones",</li>
                <li><b>When</b> mantiene presionado el widget "Mi progreso" (en móvil) o hace clic y arrastra (en web) hacia la posición superior,</li>
                <li><b>Then</b> el sistema permite reordenar los widgets visualmente,</li>
                <li><b>And</b> al soltar, la nueva posición se guarda automáticamente,</li>
                <li><b>And</b> el orden se mantiene en futuras sesiones.</li>
            </ul>
            <b>Escenario 4 (Acceso rápido a secciones principales):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario está en el dashboard,</li>
                <li><b>When</b> toca o hace clic en el acceso rápido "Simulaciones",</li>
                <li><b>Then</b> el sistema navega al catálogo de simulaciones (EP02),</li>
                <li><b>And</b> cuando regresa al dashboard usando el botón "Atrás" o el menú principal, el dashboard se muestra exactamente como estaba antes de navegar.</li>
            </ul>
            <b>Escenario 5 (Banner de promociones - cierre temporal):</b> <br/>
            <ul>
                <li><b>Given</b> que el sistema muestra un banner promocional: "¡Nuevo módulo de RCP avanzado disponible!",</li>
                <li><b>When</b> el usuario hace clic en el ícono "X" para cerrar el banner,</li>
                <li><b>Then</b> el banner desaparece del dashboard,</li>
                <li><b>And</b> no se muestra nuevamente durante 7 días (a menos que el administrador marque la promoción como "urgente"),</li>
                <li><b>And</b> el usuario puede volver a ver el banner desde la sección "Notificaciones" si lo desea.</li>
            </ul>
        </b></td>
    </tr>
</table>

<table align="center">
    <tr>
        <td><b>User Story ID</b></td>
        <td>US05</b></td>
        <td><b>Epic ID</b></td>
        <td>EP01</b></td>
    </tr>
    <tr>
        <td><b>Título</b></td>
        <td colspan="3">Gestión de perfil y preferencias</b></td>
    </tr>
    <tr>
        <td><b>Descripción</b></td>
        <td colspan="3">Como usuario registrado, quiero poder gestionar mi perfil (datos personales, foto, preferencias de aprendizaje, notificaciones y seguridad) desde una sección centralizada, para mantener mi información actualizada, controlar mi privacidad y personalizar mi experiencia en SafeStep según mis necesidades.</b></td>
    </tr>
    <tr>
        <td colspan="4">
            <b>Criterios de aceptación:</b> <br/>
            <ol>
                <li>El sistema debe incluir una sección "Mi Perfil" accesible desde el dashboard (clic en avatar o menú lateral).</li>
                <li>El usuario debe poder editar su información personal: nombre completo, fecha de nacimiento, país, ciudad, idioma preferido (español, inglés, portugués, etc.).</li>
                <li>El usuario debe poder cambiar su foto de perfil (subir imagen o usar avatar generado por iniciales), con opción de recortar y ajustar la imagen antes de guardar.</li>
                <li>El usuario debe poder cambiar su contraseña (ingresando la actual y luego la nueva, con validación de requisitos de seguridad).</li>
                <li>El usuario debe poder gestionar métodos de autenticación adicionales: vincular/desvincular cuentas de Google/Facebook/Apple, habilitar/deshabilitar 2FA (autenticación de dos factores).</li>
                <li>El usuario debe poder configurar preferencias de notificaciones: push (móvil), correo electrónico, o ambas, con opciones específicas para: nuevas simulaciones, eventos comunitarios, ofertas de tienda, recordatorios de práctica, logros desbloqueados.</li>
                <li>El usuario debe poder gestionar su privacidad: permitir o no que su progreso sea visible para la comunidad, permitir o no recibir correos promocionales, solicitar exportación de sus datos (GDPR) o eliminar su cuenta permanentemente.</li>
                <li>El sistema debe mostrar una sección "Dispositivos conectados" con lista de sesiones activas (dispositivo, ubicación aproximada, fecha/hora), permitiendo al usuario cerrar sesión remotamente en cualquier dispositivo.</li>
                <li>El sistema debe mostrar estadísticas de actividad: fecha de registro, última conexión, total de horas de aprendizaje, simulaciones completadas.</li>
                <li>Todos los cambios en el perfil deben requerir confirmación de contraseña para acciones sensibles (cambio de correo, eliminación de cuenta, desvinculación de método de autenticación).</li>
                <li>Los datos deben actualizarse en tiempo real y reflejarse en todas las sesiones activas del usuario.</li>
            </ol>
            <b>Escenario 1 (Edición de perfil - cambio de foto y nombre):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario accede a la sección "Mi Perfil" desde el dashboard,</li>
                <li><b>When</b> edita su nombre de "Juan Pérez" a "Juan Carlos Pérez",</li>
                <li><b>And</b> sube una nueva foto de perfil desde su dispositivo (recortándola a un cuadrado),</li>
                <li><b>Then</b> el sistema guarda los cambios,</li>
                <li><b>And</b> el nombre actualizado y la nueva foto se reflejan inmediatamente en el dashboard y en todas las secciones de la aplicación,</li>
                <li><b>And</b> se muestra un mensaje: "Perfil actualizado exitosamente".</li>
            </ul>
            <b>Escenario 2 (Cambio de contraseña - con verificación):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario accede a la pestaña "Seguridad" dentro de Mi Perfil,</li>
                <li><b>When</b> ingresa su contraseña actual, luego una nueva contraseña válida "NuevaClave2024*", y la confirma,</li>
                <li><b>Then</b> el sistema valida la contraseña actual, verifica que la nueva cumpla requisitos, y actualiza la contraseña,</li>
                <li><b>And</b> envía un correo de notificación de cambio de contraseña,</li>
                <li><b>And</b> cierra sesión en todos los demás dispositivos, manteniendo solo la sesión actual.</li>
            </ul>
            <b>Escenario 3 (Configuración de notificaciones - preferencias detalladas):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario accede a la pestaña "Preferencias / Notificaciones",</li>
                <li><b>When</b> activa "Notificaciones push" y desactiva "Correos promocionales",</li>
                <li><b>And</b> dentro de "Recordatorios de práctica", selecciona "Diario a las 9:00 AM",</li>
                <li><b>Then</b> el sistema guarda las preferencias,</li>
                <li><b>And</b> al día siguiente a las 9:00 AM, el usuario recibe una notificación push: "¡Es hora de tu práctica diaria! Completa una micro-lección hoy".</li>
            </ul>
            <b>Escenario 4 (Gestión de dispositivos conectados - cierre remoto):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario olvidó cerrar sesión en un dispositivo público (biblioteca),</li>
                <li><b>When</b> accede a "Mi Perfil / Seguridad / Dispositivos conectados",</li>
                <li><b>Then</b> ve una lista: "Dispositivo actual: Mi iPhone - Lima, Perú", "Otro dispositivo: Chrome en Biblioteca Pública - IP 190.xxx.xxx.xxx - última actividad hace 2 horas",</li>
                <li><b>When</b> selecciona "Cerrar sesión" junto al dispositivo de la biblioteca,</li>
                <li><b>Then</b> el sistema invalida la sesión remota inmediatamente,</li>
                <li><b>And</b> muestra un mensaje: "Sesión cerrada exitosamente en el dispositivo remoto".</li>
            </ul>
            <b>Escenario 5 (Eliminación de cuenta - proceso con confirmación):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario desea eliminar su cuenta de SafeStep permanentemente,</li>
                <li><b>When</b> accede a "Mi Perfil / Privacidad / Eliminar cuenta",</li>
                <li><b>Then</b> el sistema muestra una advertencia: "Esta acción es irreversible. Se eliminarán todos tus datos: progreso, certificaciones, historial de compras (excepto facturas por requisitos legales). ¿Continuar?",</li>
                <li><b>When</b> el usuario confirma e ingresa su contraseña nuevamente,</li>
                <li><b>Then</b> el sistema programa la eliminación de la cuenta después de un período de gracia de 7 días (durante el cual el usuario puede cancelar la solicitud),</li>
                <li><b>And</b> envía un correo de confirmación con un enlace para cancelar la eliminación,</li>
                <li><b>And</b> después de 7 días sin cancelación, la cuenta y todos los datos asociados se eliminan permanentemente.</li>
            </ul>
        </b></td>
    </tr>
</table>

<table align="center">
    <tr>
        <td><b>User Story ID</b></td>
        <td>US06</b></td>
        <td><b>Epic ID</b></td>
        <td>EP02</b></td>
    </tr>
    <tr>
        <td><b>Título</b></td>
        <td colspan="3">Escenario de RCP básico</b></td>
    </tr>
    <tr>
        <td><b>Descripción</b></td>
        <td colspan="3">Como estudiante, quiero practicar un escenario de RCP (Reanimación cardio pulmonar) básico para aprender a reaccionar correctamente ante un paro cardio respiratorio, siguiendo los pasos recomendados por guías internacionales, recibiendo retroalimentación en tiempo real y obteniendo una puntuación que refleje mi nivel de desempeño y áreas de mejora.</b></td>
    </tr>
    <tr>
        <td colspan="4">
            <b>Criterios de aceptación:</b> <br/>
            <ol>
                <li>La simulación debe presentar un escenario realista de paro cardio respiratorio (víctima inconsciente, sin respiración o con respiración agónica).</li>
                <li>El sistema debe guiar al usuario paso a paso: verificar escena segura, evaluar conciencia, pedir ayuda, verificar respiración y pulso, iniciar compresiones torácicas y ventilaciones de rescate.</li>
                <li>La app debe permitir al usuario realizar las compresiones mediante interacción táctil (clic, teclas o sensores de dispositivo móvil) indicando profundidad, frecuencia (100-120 compresiones por minuto) y posición correcta.</li>
                <li>El sistema debe evaluar cada acción en tiempo real, indicando si es correcta o incorrecta, y mostrando retroalimentación inmediata con mensajes claros y explicativos.</li>
                <li>La simulación debe incluir ciclos de 30 compresiones por 2 ventilaciones, repitiendo hasta que la víctima muestre signos de vida o llegue ayuda profesional.</li>
                <li>Al finalizar, la aplicación debe mostrar una puntuación total basada en: tiempo de respuesta, efectividad de compresiones (ritmo y profundidad), ventilaciones correctas y secuencia de pasos.</li>
                <li>El sistema debe generar recomendaciones personalizadas de mejora, señalando los errores cometidos y ofreciendo micro-lecciones o videos de refuerzo.</li>
                <li>Debe existir una modalidad práctica (con sugerencias visuales y auditivas) y una modalidad evaluativa (sin ayudas, registrando puntaje).</li>
                <li>Los resultados (puntuación, errores y tiempo) deben almacenarse en el historial del usuario y permitir reintentos para mejorar la calificación.</li>
                <li>La simulación debe incluir señales multimodales (audio, visual y texto) para accesibilidad, con opción de activar un metrónomo audible para guiar el ritmo de compresiones.</li>
                <li>La experiencia debe ser responsiva para web y móvil, con tiempos de respuesta menores a 0.5 segundos al registrar cada acción.</li>
            </ol>
            <b>Escenario 1 (Ciclo completo exitoso):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario ha iniciado sesión y selecciona el escenario "RCP básico" en el catálogo de simulaciones,</li>
                <li><b>And</b> el sistema presenta una víctima inconsciente en el suelo,</li>
                <li><b>When</b> el usuario sigue correctamente los pasos: verifica la escena, llama al 911 (o servicio de emergencia simulado), inicia compresiones torácicas a un ritmo de 110 por minuto con profundidad adecuada, realiza 2 ventilaciones de rescate, y completa 5 ciclos de 30:2,</li>
                <li><b>Then</b> la aplicación evalúa cada paso como correcto,</li>
                <li><b>And</b> muestra feedback positivo ("¡Excelente ritmo de compresiones!", "Ventilación correcta"),</li>
                <li><b>And</b> al finalizar, entrega una puntuación del 95% y recomienda seguir practicando para mejorar la técnica de apertura de vía aérea.</li>
            </ul>
            <b>Escenario 2 (Error en compresiones):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario está realizando la simulación de RCP básico,</li>
                <li><b>When</b> realiza las compresiones demasiado lentas (menos de 90 por minuto) o demasiado superficiales,</li>
                <li><b>Then</b> la aplicación detecta el error y muestra un mensaje de alerta: "Las compresiones son demasiado lentas. Aumenta la frecuencia a 100-120 por minuto",</li>
                <li><b>And</b> activa un metrónomo audible opcional para ayudar al usuario a mantener el ritmo correcto,</li>
                <li><b>And</b> solo permite avanzar al siguiente ciclo cuando el usuario corrige la frecuencia.</li>
            </ul>
            <b>Escenario 3 (Secuencia incorrecta de pasos):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario inicia la simulación de RCP,</li>
                <li><b>When</b> intenta comenzar las compresiones sin verificar la escena ni la conciencia de la víctima,</li>
                <li><b>Then</b> la aplicación pausa la simulación y muestra un mensaje explicativo: "Antes de iniciar RCP, debes asegurarte de que la escena sea segura y verificar si la víctima responde",</li>
                <li><b>And</b> ofrece una guía visual paso a paso con la secuencia correcta (seguridad, evaluación, pedir ayuda, compresiones, ventilaciones),</li>
                <li><b>And</b> permite al usuario reiniciar el escenario o continuar desde el paso omitido después de revisar la guía.</li>
            </ul>
            <b>Escenario 4 (Modalidad evaluativa):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario selecciona la modalidad "Evaluación" en lugar de "Práctica",</li>
                <li><b>When</b> realiza la simulación completa sin sugerencias visuales ni auditivas,</li>
                <li><b>Then</b> el sistema registra cada acción sin intervenir,</li>
                <li><b>And</b> al finalizar, muestra la puntuación obtenida (ejemplo: 82%), desglosando aciertos y errores,</li>
                <li><b>And</b> almacena el resultado en el historial del usuario para seguimiento de progreso.</li>
            </ul>
            <b>Escenario 5 (Reintento y mejora):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario completó la simulación con una puntuación baja (ejemplo: 45%),</li>
                <li><b>When</b> accede a la sección "Mis resultados" y selecciona "Reintentar simulación",</li>
                <li><b>Then</b> el sistema reinicia el escenario,</li>
                <li><b>And</b> muestra un resumen rápido de los errores anteriores antes de comenzar,</li>
                <li><b>And</b> al finalizar el segundo intento, compara ambas puntuaciones y muestra un mensaje motivacional si hubo mejora ("¡Has mejorado tu puntuación en un 20%! Sigue así").</li>
            </ul>
        </td>
    </tr>
</table>

<table align="center">
    <tr>
        <td><b>User Story ID</b></td>
        <td>US07</b></td>
        <td><b>Epic ID</b></td>
        <td>EP02</b></td>
    </tr>
    <tr>
        <td><b>Título</b></td>
        <td colspan="3">Escenario de atragantamiento</b></td>
    </tr>
    <tr>
        <td><b>Descripción</b></td>
        <td colspan="3">Como usuario, quiero practicar cómo reaccionar ante un caso de atragantamiento mediante una simulación interactiva, para aprender a seleccionar y ejecutar las maniobras correctas (por ejemplo, Heimlich o golpes en la espalda), ganar confianza y saber cómo actuar en una emergencia real.</b></td>
    </tr>
    <tr>
        <td colspan="4">
            <b>Criterios de aceptación:</b> <br/>
            <ol>
                <li>La simulación debe presentar un escenario realista con síntomas claros de atragantamiento (tosiendo poco, incapacidad para respirar, pérdida de conciencia, cianosis).</li>
                <li>El sistema debe permitir seleccionar distintas maniobras según la víctima: golpes en la espalda (5 golpes), compresiones abdominales (maniobra de Heimlich), o protocolos específicos para bebés (menores de 1 año: golpes en la espalda y compresiones torácicas).</li>
                <li>El sistema debe adaptar el escenario según el tipo de víctima: adulto, niño (1-8 años) o bebé (menor de 1 año), mostrando las maniobras apropiadas para cada caso.</li>
                <li>Al ejecutar una maniobra, la app debe simular el resultado (éxito/parcial/fracaso) en tiempo real y ofrecer retroalimentación inmediata explicando por qué la acción fue correcta o incorrecta.</li>
                <li>Si la maniobra es incorrecta o no resuelve la obstrucción, la app debe pausar la simulación y mostrar la secuencia correcta paso a paso antes de permitir continuar.</li>
                <li>El sistema debe verificar que el usuario aplique la fuerza y posición correcta (simulada mediante controles táctiles o selección de opciones) para cada maniobra.</li>
                <li>Debe existir una modalidad práctica (con sugerencias visuales y auditivas, ejemplos animados) y una modalidad evaluativa (sin ayudas, registrando puntuación y tiempo de respuesta).</li>
                <li>Los resultados (puntuación, errores, tiempo de respuesta, maniobras aplicadas) deben almacenarse en el historial del usuario y permitir reintentos para mejorar la puntuación.</li>
                <li>La simulación debe incluir señales multimodales (audio, visual y texto) para accesibilidad y claridad, incluyendo animaciones que muestren la posición correcta de las manos.</li>
                <li>La experiencia debe ser responsiva para web y móvil y mantener tiempos de respuesta adecuados (sin latencia perceptible al ejecutar acciones).</li>
                <li>El sistema debe incluir un caso especial para cuando la víctima está embarazada o con obesidad (compresiones torácicas en lugar de abdominales).</li>
                <li>Si la víctima pierde el conocimiento, el sistema debe guiar al usuario para realizar RCP y activar emergencias.</li>
            </ol>
            <b>Escenario 1 (Maniobra de Heimlich exitosa en adulto):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario ha iniciado sesión y selecciona el escenario "Atragantamiento" desde el menú de simulaciones,</li>
                <li><b>And</b> el sistema presenta una víctima adulta consciente que no puede hablar ni toser, con las manos en el cuello (signo universal de atragantamiento),</li>
                <li><b>When</b> el usuario selecciona la maniobra de Heimlich, se coloca detrás de la víctima, posiciona correctamente los puños y aplica 5 compresiones abdominales rápidas hacia adentro y arriba,</li>
                <li><b>Then</b> la aplicación simula que el objeto obstruyente es expulsado,</li>
                <li><b>And</b> muestra retroalimentación positiva: "¡Excelente! Has realizado correctamente la maniobra de Heimlich. La víctima ahora puede respirar",</li>
                <li><b>And</b> otorga una puntuación del 100% en ese paso y permite continuar o finalizar la simulación.</li>
            </ul>
            <b>Escenario 2 (Error crítico - posición incorrecta de manos):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario está realizando la simulación de atragantamiento en un adulto,</li>
                <li><b>When</b> intenta aplicar la maniobra de Heimlich pero coloca sus manos demasiado arriba (sobre el esternón) o demasiado abajo (sobre la pelvis),</li>
                <li><b>Then</b> la app detecta el error y pausa la simulación,</li>
                <li><b>And</b> muestra un mensaje explicativo: "Posición incorrecta de manos. Colocar el puño en la línea media, justo encima del ombligo y debajo del esternón para evitar dañar órganos internos",</li>
                <li><b>And</b> despliega una animación o diagrama mostrando la posición correcta,</li>
                <li><b>And</b> permite al usuario reintentar la maniobra antes de continuar.</li>
            </ul>
            <b>Escenario 3 (Atragantamiento en bebé - golpes en la espalda):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario selecciona el escenario "Atragantamiento" y el sistema presenta un caso con un bebé menor de 1 año que no llora ni respira,</li>
                <li><b>When</b> el usuario posiciona al bebé boca abajo sobre su antebrazo, sosteniendo la cabeza, y aplica 5 golpes firmes en la espalda entre los omóplatos,</li>
                <li><b>Then</b> la aplicación simula que el objeto es expulsado,</li>
                <li><b>And</b> muestra retroalimentación: "¡Correcto! Los golpes en la espalda son la primera línea de acción para bebés atragantados",</li>
                <li><b>And</b> explica que si no funciona, se deben alternar con 5 compresiones torácicas (dos dedos en el centro del pecho).</li>
            </ul>
            <b>Escenario 4 (Secuencia completa fallida - pérdida de conciencia):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario ha intentado la maniobra de Heimlich dos veces sin éxito,</li>
                <li><b>When</b> el sistema detecta que la víctima ha perdido el conocimiento y deja de responder,</li>
                <li><b>Then</b> la simulación cambia automáticamente al protocolo de víctima inconsciente,</li>
                <li><b>And</b> guía al usuario para: acostar a la víctima boca arriba, llamar a emergencias, iniciar RCP con compresiones torácicas y revisar la boca en busca del objeto obstruyente,</li>
                <li><b>And</b> evalúa cada paso y muestra feedback específico,</li>
                <li><b>And</b> al finalizar, muestra un resumen de la secuencia completa y recomienda practicar también el protocolo de RCP.</li>
            </ul>
            <b>Escenario 5 (Modalidad evaluativa - tiempo de respuesta):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario selecciona la modalidad "Evaluación" en el escenario de atragantamiento,</li>
                <li><b>When</b> el sistema presenta el caso y comienza a medir el tiempo de respuesta desde que se muestran los síntomas,</li>
                <li><b>Then</b> el usuario debe aplicar la maniobra correcta sin ayudas visuales ni sugerencias,</li>
                <li><b>And</b> el sistema registra el tiempo transcurrido hasta la primera acción (reacción inicial),</li>
                <li><b>And</b> al finalizar, muestra una puntuación compuesta por: tiempo de reacción (30%), efectividad de maniobras (50%) y secuencia de pasos (20%),</li>
                <li><b>And</b> almacena el resultado en el historial y permite comparar con intentos anteriores.</li>
            </ul>
            <b>Escenario 6 (Caso especial - víctima embarazada):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario selecciona el escenario de atragantamiento y el sistema indica que la víctima está embarazada (tercer trimestre) o tiene obesidad,</li>
                <li><b>When</b> el usuario intenta aplicar la maniobra de Heimlich estándar,</li>
                <li><b>Then</b> la app muestra una alerta: "En víctimas embarazadas, NO se deben realizar compresiones abdominales. Utiliza compresiones torácicas en su lugar",</li>
                <li><b>And</b> guía al usuario para posicionar las manos en el centro del esternón (como en RCP) y aplicar compresiones hacia adentro,</li>
                <li><b>And</b> evalúa si el usuario aplica la técnica correcta para este caso especial.</li>
            </ul>
        </td>
    </tr>
</table>

<table align="center">
    <tr>
        <td><b>User Story ID</b></td>
        <td>US08</b></td>
        <td><b>Epic ID</b></td>
        <td>EP02</b></td>
    </tr>
    <tr>
        <td><b>Título</b></td>
        <td colspan="3">Escenario de quemaduras</b></td>
    </tr>
    <tr>
        <td><b>Descripción</b></td>
        <td colspan="3">Como usuario, quiero aprender cómo atender una quemadura a través de una simulación interactiva, para comprender los pasos adecuados de primeros auxilios, evitar errores comunes y actuar correctamente ante diferentes grados de lesión.</b></td>
    </tr>
    <tr>
        <td colspan="4">
            <b>Criterios de aceptación:</b> <br/>
            <ol>
                <li>La simulación debe presentar distintos tipos y grados de quemaduras (primer grado o superficial, segundo grado o parcial, tercer grado o profunda) con sus respectivas características visuales y síntomas (enrojecimiento, ampollas, piel carbonizada, etc.).</li>
                <li>El sistema debe guiar al usuario en la toma de decisiones sobre cómo actuar según el grado de quemadura: enfriar con agua corriente (no helada), cubrir la zona con gasa estéril o apósito, evitar remedios inadecuados (hielo, cremas caseras, algodón) y buscar ayuda profesional según la gravedad.</li>
                <li>La aplicación debe evaluar las acciones del usuario en tiempo real, indicando si son correctas o incorrectas, y explicar los motivos con lenguaje claro y educativo.</li>
                <li>El sistema debe diferenciar entre quemaduras por calor (térmicas), químicas, eléctricas y por radiación solar, adaptando el protocolo de primeros auxilios según el tipo.</li>
                <li>Para quemaduras químicas, la app debe instruir sobre el lavado prolongado con abundante agua (al menos 20 minutos) y la identificación del agente causante.</li>
                <li>Para quemaduras eléctricas, debe advertir sobre el peligro de la corriente y la necesidad de desconectar la fuente antes de tocar a la víctima.</li>
                <li>La simulación debe enseñar al usuario a reconocer cuándo una quemadura requiere atención médica inmediata (tercer grado, quemaduras en cara, manos, pies, genitales, articulaciones o quemaduras grandes).</li>
                <li>Al finalizar la simulación, la app debe ofrecer material complementario (videos, infografías o artículos) sobre el tratamiento y prevención de quemaduras, incluyendo cuidados posteriores.</li>
                <li>Los resultados (aciertos, errores, nivel de desempeño y tipo de quemadura practicado) deben almacenarse en el historial del usuario.</li>
                <li>El diseño debe priorizar la accesibilidad visual, la claridad de los textos y la navegación intuitiva en dispositivos móviles y web.</li>
                <li>La simulación debe incluir retroalimentación audiovisual para mejorar la comprensión (indicadores visuales, sonidos de alerta y mensajes explicativos).</li>
                <li>Debe existir una modalidad práctica (con sugerencias paso a paso) y una modalidad evaluativa (sin ayudas, registrando puntuación y tiempo de respuesta).</li>
                <li>El usuario debe poder seleccionar entre diferentes casos de quemadura al iniciar la simulación: "quemadura en la cocina", "quemadura solar", "quemadura química en el trabajo", "quemadura eléctrica doméstica".</li>
            </ol>
            <b>Escenario 1 (Quemadura térmica de segundo grado - tratamiento correcto):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario ha accedido al escenario "Quemaduras" y selecciona el caso "Quemadura en la cocina",</li>
                <li><b>And</b> el sistema presenta una víctima con una quemadura en el antebrazo que muestra ampollas y enrojecimiento intenso (segundo grado),</li>
                <li><b>When</b> el usuario sigue correctamente los pasos sugeridos por la app: retira la fuente de calor, enfría la zona con agua corriente (no helada) durante 10-15 minutos, cubre con una gasa estéril sin romper las ampollas, y recomienda consultar a un médico,</li>
                <li><b>Then</b> la aplicación confirma que las acciones fueron adecuadas,</li>
                <li><b>And</b> muestra una explicación educativa: "Enfriar la quemadura con agua corriente detiene el daño térmico y reduce el dolor. Cubrir con gasa estéril previene infecciones. No romper las ampollas porque actúan como barrera natural",</li>
                <li><b>And</b> otorga una puntuación del 100% en ese caso.</li>
            </ul>
            <b>Escenario 2 (Error común - aplicar hielo directamente):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario ha accedido al escenario "Quemaduras" y se enfrenta a una quemadura de primer grado (enrojecimiento, piel caliente),</li>
                <li><b>When</b> decide aplicar hielo directamente sobre la lesión pensando que aliviará el dolor,</li>
                <li><b>Then</b> la aplicación muestra una alerta inmediata: "¡Acción incorrecta! El hielo directo puede causar daño adicional por congelación y empeorar la lesión",</li>
                <li><b>And</b> despliega una guía visual paso a paso explicando que se debe usar agua corriente fría (no helada) durante 10-15 minutos,</li>
                <li><b>And</b> ofrece material adicional sobre por qué el hielo está contraindicado en quemaduras,</li>
                <li><b>And</b> permite al usuario corregir la acción y continuar.</li>
            </ul>
            <b>Escenario 3 (Quemadura química - lavado prolongado):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario selecciona el caso "Quemadura química en el trabajo",</li>
                <li><b>And</b> el sistema presenta una víctima con una quemadura en la mano causada por un producto químico corrosivo,</li>
                <li><b>When</b> el usuario debe decidir cómo actuar,</li>
                <li><b>Then</b> la app evalúa si el usuario recuerda retirar la ropa contaminada, lavar con abundante agua corriente durante al menos 20 minutos, y buscar atención médica urgente,</li>
                <li><b>And</b> si el usuario intenta neutralizar el químico con otra sustancia, muestra una alerta: "¡Nunca neutralices un químico sin conocimiento específico! Esto puede generar reacciones exotérmicas. Lava con abundante agua",</li>
                <li><b>And</b> al completar correctamente, explica la importancia del lavado prolongado para diluir y eliminar el agente químico.</li>
            </ul>
            <b>Escenario 4 (Quemadura eléctrica - seguridad primero):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario selecciona el caso "Quemadura eléctrica doméstica",</li>
                <li><b>And</b> el sistema presenta a una víctima que ha tocado un cable expuesto y permanece en contacto con la fuente eléctrica,</li>
                <li><b>When</b> el usuario debe priorizar las acciones,</li>
                <li><b>Then</b> la app verifica que el usuario primero corte la corriente eléctrica (desconectar interruptor o usar un objeto no conductor) antes de tocar a la víctima,</li>
                <li><b>And</b> si el usuario intenta tocar a la víctima sin desconectar la corriente, muestra una alerta crítica: "¡Peligro! No toques a la víctima sin desconectar la fuente eléctrica. Podrías electrocutarte también",</li>
                <li><b>And</b> después de la acción correcta, guía sobre cómo atender las quemaduras de entrada y salida y la necesidad de evaluación médica urgente por posibles daños internos.</li>
            </ul>
            <b>Escenario 5 (Reconocimiento de gravedad - quemadura facial):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario accede a un caso donde la víctima tiene una quemadura en el rostro y las vías respiratorias podrían estar afectadas,</li>
                <li><b>When</b> el usuario evalúa la situación y debe decidir si es una emergencia que requiere atención médica inmediata,</li>
                <li><b>Then</b> el sistema evalúa si el usuario identifica correctamente los signos de alarma: dificultad para respirar, tos con esputo carbonáceo, vello nasal chamuscado,</li>
                <li><b>And</b> si el usuario recomienda llamar a emergencias (911 o número local) de inmediato, la app confirma: "Correcto. Las quemaduras faciales pueden comprometer las vías respiratorias. Siempre requieren evaluación médica urgente",</li>
                <li><b>And</b> si el usuario subestima la gravedad, la app muestra una advertencia y explica por qué este tipo de quemadura es crítico.</li>
            </ul>
            <b>Escenario 6 (Remedios caseros inadecuados - cremas, pasta dental, huevo):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario está atendiendo una quemadura de primer grado,</li>
                <li><b>When</b> el usuario selecciona aplicar pasta dental, crema de mantequilla, clara de huevo o algún remedio casero popular,</li>
                <li><b>Then</b> la aplicación muestra una alerta educativa: "¡Acción incorrecta! Los remedios caseros como pasta dental, mantequilla o huevo pueden atrapar el calor, empeorar la lesión y aumentar el riesgo de infección",</li>
                <li><b>And</b> explica que solo se deben usar apósitos estériles específicos para quemaduras o gasa, y que el enfriamiento con agua es el primer paso,</li>
                <li><b>And</b> despliega una infografía con los productos seguros y los prohibidos para tratar quemaduras.</li>
            </ul>
            <b>Escenario 7 (Modalidad evaluativa - múltiples casos):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario selecciona la modalidad "Evaluación" en el escenario de quemaduras,</li>
                <li><b>When</b> el sistema presenta 3 casos diferentes de quemadura (térmica leve, química, eléctrica) en secuencia,</li>
                <li><b>Then</b> el usuario debe responder cada caso sin ayudas ni sugerencias,</li>
                <li><b>And</b> el sistema registra las decisiones, el orden de acciones y el tiempo de respuesta para cada caso,</li>
                <li><b>And</b> al finalizar, muestra una puntuación global y un desglose por tipo de quemadura, identificando fortalezas y áreas de mejora,</li>
                <li><b>And</b> ofrece acceso directo a material de refuerzo para los tipos de quemadura donde el usuario tuvo errores.</li>
            </ul>
            <b>Escenario 8 (Prevención de quemaduras):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario ha completado exitosamente la simulación de quemaduras,</li>
                <li><b>When</b> accede a la sección "Material complementario",</li>
                <li><b>Then</b> el sistema muestra contenido sobre prevención de quemaduras: consejos para cocinar, manejo seguro de químicos, protección solar, instalación eléctrica segura y prevención de quemaduras en niños,</li>
                <li><b>And</b> ofrece un checklist descargable de seguridad para el hogar,</li>
                <li><b>And</b> registra que el usuario ha completado el módulo de prevención.</li>
            </ul>
        </td>
    </tr>
</table>

<table align="center">
    <tr>
        <td><b>User Story ID</b></td>
        <td>US09</b></td>
        <td><b>Epic ID</b></td>
        <td>EP02</b></td>
    </tr>
    <tr>
        <td><b>Título</b></td>
        <td colspan="3">Escenario de sismos</b></td>
    </tr>
    <tr>
        <td><b>Descripción</b></td>
        <td colspan="3">Como miembro de la comunidad, quiero practicar qué hacer durante y después de un sismo para reaccionar con seguridad, proteger mi integridad y la de los demás, y aplicar medidas de primeros auxilios si es necesario, fortaleciendo mi preparación ante emergencias sísmicas.</b></td>
    </tr>
    <tr>
        <td colspan="4">
            <b>Criterios de aceptación:</b> <br/>
            <ol>
                <li>La simulación debe presentar un escenario realista de sismo con efectos audiovisuales (vibración de pantalla, sonido de alerta sísmica, objetos que caen, luces que parpadean) para crear inmersión.</li>
                <li>El sistema debe permitir al usuario seleccionar su ubicación al inicio de la simulación (casa, oficina, escuela, vía pública, vehículo, playa) para adaptar las acciones de protección según el entorno.</li>
                <li>Durante la fase de "sismo", el usuario debe elegir entre múltiples opciones de acción (ejemplo: cubrirse bajo una mesa, alejarse de ventanas, correr hacia la salida, etc.) y el sistema evalúa la seguridad de cada decisión en tiempo real.</li>
                <li>La aplicación debe enseñar el protocolo internacional de protección sísmica "PAS" (Proteger, Agacharse, Sujetarse) como primera línea de acción.</li>
                <li>El sistema debe penalizar acciones peligrosas como correr hacia ascensores, pararse bajo marcos de puertas (mito desmentido), o salir corriendo durante el movimiento.</li>
                <li>Después del sismo, la simulación debe incluir una fase de "evaluación del entorno" donde el usuario debe identificar peligros secundarios (fugas de gas, incendios, estructuras inestables, objetos caídos).</li>
                <li>El sistema debe guiar al usuario en la verificación de lesiones propias y de terceros, aplicando conocimientos básicos de primeros auxilios (cortes, fracturas, contusiones).</li>
                <li>La simulación debe incluir la activación de números de emergencia y la evacuación segura hacia puntos de reunión designados.</li>
                <li>El sistema debe evaluar si el usuario recuerda cortar el suministro de gas y electricidad después del sismo (si es seguro hacerlo).</li>
                <li>Al finalizar, la aplicación debe generar una puntuación de seguridad basada en: acciones durante el sismo (50%), decisiones post-sismo (30%) y primeros auxilios aplicados (20%).</li>
                <li>La simulación debe ofrecer una modalidad "Entrenamiento" (con sugerencias visuales) y una modalidad "Evaluación" (sin ayudas, cronometrada).</li>
                <li>Los resultados deben almacenarse en el historial del usuario, permitiendo reintentos y mostrando progreso en preparación sísmica.</li>
                <li>La simulación debe incluir señales multimodales (audio, visual y texto) para accesibilidad, con opción de activar alertas hápticas en dispositivos móviles.</li>
            </ol>
            <b>Escenario 1 (Sismo en casa - acciones correctas durante el movimiento):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario inicia la simulación "Sismo" y selecciona la ubicación "Casa",</li>
                <li><b>When</b> el sistema activa la alerta sísmica con vibración de pantalla y sonido de alarma, simulando el inicio del movimiento,</li>
                <li><b>And</b> el usuario debe elegir rápidamente entre las opciones disponibles,</li>
                <li><b>When</b> selecciona las acciones correctas: agacharse debajo de una mesa resistente, cubrirse la cabeza y el cuello con los brazos, y sujetarse a la pata de la mesa hasta que pase el movimiento,</li>
                <li><b>Then</b> la aplicación evalúa cada decisión como segura,</li>
                <li><b>And</b> muestra mensajes de refuerzo positivo: "¡Excelente! Agacharte y cubrirte bajo una mesa resistente es una de las acciones más seguras durante un sismo",</li>
                <li><b>And</b> continúa la simulación hasta que cesa la vibración.</li>
            </ul>
            <b>Escenario 2 (Acciones peligrosas durante el sismo - penalización):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario está en la fase activa del sismo simulado,</li>
                <li><b>When</b> el usuario selecciona una acción peligrosa como: correr hacia la salida, pararse bajo un marco de puerta, usar el ascensor, o pararse cerca de ventanas o estanterías,</li>
                <li><b>Then</b> la aplicación muestra una alerta inmediata: "¡Acción peligrosa! Correr durante el sismo aumenta el riesgo de caídas y lesiones. Lo más seguro es agacharte, cubrirte y sujetarte donde estás",</li>
                <li><b>And</b> explica por qué esa acción específica es riesgosa (ejemplo: "Los marcos de puertas ya no se consideran seguros en construcciones modernas; pueden colapsar o no proteger de objetos que caen"),</li>
                <li><b>And</b> penaliza la decisión en la puntuación final, pero permite al usuario corregir la acción en el siguiente paso.</li>
            </ul>
            <b>Escenario 3 (Sismo en vía pública - diferentes reglas):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario selecciona la ubicación "Vía pública" al iniciar la simulación,</li>
                <li><b>When</b> ocurre el sismo simulado,</li>
                <li><b>Then</b> el sistema debe evaluar si el usuario se aleja de edificios, postes eléctricos, árboles y carteles publicitarios,</li>
                <li><b>And</b> si el usuario selecciona "cubrirse la cabeza y agacharse en un área abierta", la app confirma: "Correcto. En la calle, aléjate de estructuras que puedan colapsar y busca un área abierta",</li>
                <li><b>And</b> si el usuario selecciona "refugiarse bajo un puente o marquesina", la app advierte: "Las estructuras elevadas pueden colapsar durante el sismo. Busca un lugar alejado de edificios y objetos que puedan caer".</li>
            </ul>
            <b>Escenario 4 (Sismo en vehículo):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario selecciona la ubicación "Vehículo",</li>
                <li><b>When</b> comienza la simulación del sismo,</li>
                <li><b>Then</b> la app debe guiar al usuario a: reducir la velocidad, estacionar en un lugar seguro (alejado de puentes, postes y edificios), permanecer dentro del vehículo con el cinturón puesto hasta que cese el movimiento,</li>
                <li><b>And</b> evalúa si el usuario evita detenerse debajo de puentes o pasos elevados,</li>
                <li><b>And</b> muestra feedback: "Bien. Dentro del vehículo estás protegido de objetos que caen. Espera a que pase el sismo antes de continuar".</li>
            </ul>
            <b>Escenario 5 (Post-sismo - evaluación de peligros y primeros auxilios):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario ha completado la fase del sismo,</li>
                <li><b>When</b> el sistema presenta una escena post-sismo con daños visibles (objetos caídos, una persona con una herida en el brazo, olor a gas),</li>
                <li><b>Then</b> el usuario debe tomar decisiones sobre: evacuar o no, verificar lesiones, cortar suministros, llamar a emergencias,</li>
                <li><b>And</b> la aplicación evalúa si el usuario: revisa si hay fugas de gas antes de usar interruptores eléctricos, atiende a la persona herida (aplica presión sobre la herida, inmoviliza si hay fractura), y dirige la evacuación hacia un punto de reunión seguro,</li>
                <li><b>And</b> si el usuario olvida cortar el gas o intenta encender una cerilla, la app muestra una alerta crítica: "¡Peligro de explosión! Si hay fuga de gas, no enciendas ninguna llama ni uses interruptores eléctricos. Abre ventanas y evacúa".</li>
            </ul>
            <b>Escenario 6 (Réplicas - mantenerse alerta):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario está en la fase post-sismo evaluando el entorno,</li>
                <li><b>When</b> el sistema simula una réplica (segundo sismo de menor intensidad),</li>
                <li><b>Then</b> la aplicación evalúa si el usuario vuelve a aplicar el protocolo "agacharse, cubrirse, sujetarse" inmediatamente,</li>
                <li><b>And</b> muestra feedback: "¡Correcto! Las réplicas son comunes después de un sismo mayor. Siempre debes volver a protegerte durante cada movimiento",</li>
                <li><b>And</b> si el usuario ignora la réplica y continúa evacuando, la app advierte: "No ignores las réplicas. Vuelve a agacharte y cúbrete hasta que cese el movimiento".</li>
            </ul>
            <b>Escenario 7 (Modalidad evaluativa - simulación completa):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario selecciona la modalidad "Evaluación" en el escenario de sismos,</li>
                <li><b>When</b> el sistema ejecuta una simulación completa que incluye: sismo inicial, fase de protección, réplica, evaluación post-sismo, primeros auxilios y evacuación,</li>
                <li><b>Then</b> el usuario debe tomar todas las decisiones sin ayudas visuales ni sugerencias,</li>
                <li><b>And</b> el sistema cronometra el tiempo de reacción inicial (desde la alerta hasta la primera acción de protección),</li>
                <li><b>And</b> al finalizar, muestra una puntuación global (0-100) con desglose por fase,</li>
                <li><b>And</b> genera un certificado digital de "Preparación Sísmica Básica" si la puntuación supera el 80%.</li>
            </ul>
            <b>Escenario 8 (Mochila de emergencia y plan familiar):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario completa la simulación de sismo con un puntaje alto,</li>
                <li><b>When</b> accede a la sección "Material complementario",</li>
                <li><b>Then</b> el sistema muestra contenido educativo sobre: cómo preparar una mochila de emergencia (agua, alimentos no perecibles, botiquín, linterna, radio, silbato, copias de documentos),</li>
                <li><b>And</b> cómo crear un plan familiar de emergencia (puntos de reunión, contactos de emergencia, simulacros regulares),</li>
                <li><b>And</b> ofrece una lista de verificación descargable en PDF,</li>
                <li><b>And</b> permite al usuario marcar elementos como "Ya preparados" para hacer seguimiento a su preparación real.</li>
            </ul>
            <b>Escenario 9 (Primeros auxilios específicos post-sismo):</b> <br/>
            <ul>
                <li><b>Given</b> que en la fase post-simo el sistema presenta múltiples víctimas con diferentes lesiones (una persona con una fractura expuesta, otra con una herida leve, otra inconsciente),</li>
                <li><b>When</b> el usuario debe priorizar la atención,</li>
                <li><b>Then</b> la aplicación evalúa si el usuario aplica el principio de triage: atender primero a la víctima inconsciente (vía aérea, respiración), luego la fractura expuesta (inmovilizar, no reubicar el hueso), finalmente la herida leve,</li>
                <li><b>And</b> si el usuario intenta mover a un lesionado grave sin inmovilización, muestra una advertencia: "No muevas a una víctima con posible fractura de columna a menos que esté en peligro inmediato. Inmoviliza y espera ayuda profesional".</li>
            </ul>
            <b>Escenario 10 (Sismo en escuela - protección de menores):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario selecciona la ubicación "Escuela" y el rol de "docente",</li>
                <li><b>When</b> ocurre el sismo simulado,</li>
                <li><b>Then</b> la aplicación evalúa si el usuario ordena a los estudiantes agacharse bajo sus pupitres, cubrirse la cabeza y alejarse de ventanas,</li>
                <li><b>And</b> verifica que el usuario no abandone el aula antes que los estudiantes,</li>
                <li><b>And</b> después del sismo, evalúa si el usuario dirige una evacuación ordenada hacia el punto de reunión, evitando estampidas,</li>
                <li><b>And</b> muestra feedback: "Excelente liderazgo. La calma y el orden salvan vidas durante una evacuación escolar".</li>
            </ul>
        </td>
    </tr>
</table>

<table align="center">
    <tr>
        <td><b>User Story ID</b></td>
        <td>US10</b></td>
        <td><b>Epic ID</b></td>
        <td>EP02</b></td>
    </tr>
    <tr>
        <td><b>Título</b></td>
        <td colspan="3">Escenario de cortes y hemorragias</b></td>
    </tr>
    <tr>
        <td><b>Descripción</b></td>
        <td colspan="3">Como usuario, quiero aprender a detener una hemorragia para actuar de forma correcta en emergencias con cortes, aplicando técnicas como presión directa, elevación del miembro afectado y uso de torniquete en casos graves, para salvar vidas mientras llega ayuda profesional.</b></td>
    </tr>
    <tr>
        <td colspan="4">
            <b>Criterios de aceptación:</b> <br/>
            <ol>
                <li>La simulación debe presentar diferentes tipos de hemorragias: capilar (leve), venosa (sangre oscura, flujo continuo) y arterial (sangre roja brillante, flujo pulsátil o en chorro), adaptando el protocolo de atención a cada caso.</li>
                <li>El sistema debe guiar al usuario en el uso correcto de equipo de protección personal (guantes de látex o nitrilo) antes de atender la herida, para prevenir infecciones y contagios.</li>
                <li>La aplicación debe enseñar el protocolo estándar para hemorragias: aplicar presión directa con gasa estéril o tela limpia, mantener presión por al menos 5-10 minutos sin levantar para verificar, y elevar la extremidad por encima del corazón si no hay fractura.</li>
                <li>El sistema debe incluir un módulo específico sobre uso de torniquete (tourniquet) para hemorragias arteriales graves que no ceden con presión directa, enseñando la colocación correcta (5-7 cm por encima de la herida, nunca sobre articulaciones, registrar la hora de aplicación).</li>
                <li>La simulación debe advertir sobre errores comunes: retirar gasas empapadas para colocar nuevas (se debe añadir más gasa encima), aplicar torniquete demasiado flojo o demasiado apretado, olvidar registrar la hora, o no buscar atención médica para heridas profundas.</li>
                <li>El sistema debe diferenciar entre heridas con o sin objetos incrustados (cuchillo, vidrio, metal), enseñando a no retirar el objeto y a colocar apósitos alrededor para inmovilizarlo.</li>
                <li>La aplicación debe evaluar si el usuario recuerda activar el sistema de emergencias (llamar al 911 o número local) antes o después de iniciar los primeros auxilios según la gravedad.</li>
                <li>Debe existir una modalidad práctica (con sugerencias paso a paso) y una modalidad evaluativa (sin ayudas, cronometrada).</li>
                <li>Los resultados (puntuación, errores, tiempo de respuesta, tipo de hemorragia practicado) deben almacenarse en el historial del usuario.</li>
                <li>La simulación debe incluir señales multimodales (audio, visual y texto) para accesibilidad, con animaciones que muestren la posición correcta de las manos al aplicar presión.</li>
                <li>El sistema debe presentar casos específicos: hemorragia nasal (epistaxis), hemorragia en embarazadas (precaución con elevación de miembros), hemorragia en zonas de difícil acceso (cuello, ingle, axila).</li>
                <li>Al finalizar, la app debe ofrecer material complementario (videos, infografías) sobre técnicas avanzadas de control de hemorragias y contenido de botiquines.</li>
            </ol>
            <b>Escenario 1 (Hemorragia venosa moderada - presión directa correcta):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario selecciona el escenario "Cortes y hemorragias" en el menú de simulaciones,</li>
                <li><b>And</b> el sistema presenta una víctima con un corte profundo en el antebrazo que sangra con flujo continuo de sangre oscura (hemorragia venosa),</li>
                <li><b>When</b> el usuario sigue las instrucciones: se coloca guantes, aplica presión directa con una gasa estéril sobre la herida sin retirarla, mantiene presión constante durante 5 minutos, y eleva el brazo por encima del corazón,</li>
                <li><b>Then</b> la aplicación evalúa cada acción en tiempo real como correcta,</li>
                <li><b>And</b> muestra retroalimentación positiva: "¡Excelente! Aplicaste presión directa correctamente. No retirar la gasa empapada y añadir más encima si es necesario es la técnica adecuada",</li>
                <li><b>And</b> la hemorragia se detiene en la simulación, y el usuario pasa a la fase de vendaje y búsqueda de atención médica.</li>
            </ul>
            <b>Escenario 2 (Error crítico - retirar gasa empapada):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario se encuentra realizando la simulación de "Cortes y hemorragias",</li>
                <li><b>When</b> aplica presión inicial pero luego retira la gasa empapada para verificar si la hemorragia cesó,</li>
                <li><b>Then</b> la aplicación pausa la simulación inmediatamente,</li>
                <li><b>And</b> muestra una guía rápida de primeros auxilios: "¡Error! Retirar la gasa empapada interrumpe el proceso de coagulación y puede reiniciar la hemorragia. En lugar de retirarla, añade más gasa o tela limpia encima y continúa presionando",</li>
                <li><b>And</b> permite al usuario corregir la acción añadiendo una segunda gasa sin retirar la primera,</li>
                <li><b>And</b> al hacerlo correctamente, la simulación continúa y se registra el error para la puntuación final.</li>
            </ul>
            <b>Escenario 3 (Hemorragia arterial grave - uso de torniquete):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario selecciona un caso avanzado de hemorragia arterial en el muslo (sangre roja brillante que sale en chorro),</li>
                <li><b>And</b> la presión directa no ha detenido el sangrado después de 2 minutos (simulado),</li>
                <li><b>When</b> el usuario debe decidir aplicar un torniquete,</li>
                <li><b>Then</b> la aplicación evalúa si el usuario: coloca el torniquete 5-7 cm por encima de la herida (no sobre la rodilla), lo aprieta hasta detener el sangrado, y registra la hora de aplicación visiblemente,</li>
                <li><b>And</b> si el usuario olvida registrar la hora, la app muestra una alerta: "Es crítico anotar la hora de aplicación del torniquete para informar al personal médico. El torniquete no debe permanecer más de 2 horas",</li>
                <li><b>And</b> si la hemorragia se detiene, la app confirma: "Correcto. El torniquete está bien aplicado. No lo aflojes ni retires; espera ayuda profesional",</li>
                <li><b>And</b> registra la acción en el historial como "Técnica avanzada de control de hemorragias".</li>
            </ul>
            <b>Escenario 4 (Objeto incrustado - NO retirar):</b> <br/>
            <ul>
                <li><b>Given</b> que el sistema presenta una víctima con un cuchillo o vidrio incrustado en el muslo, con sangrado alrededor,</li>
                <li><b>When</b> el usuario intenta retirar el objeto para aplicar presión directa,</li>
                <li><b>Then</b> la aplicación pausa la simulación y muestra una alerta crítica: "¡PELIGRO! Nunca retires un objeto incrustado. Esto puede causar una hemorragia masiva incontrolable y dañar estructuras internas",</li>
                <li><b>And</b> muestra la guía correcta: colocar apósitos alrededor del objeto para inmovilizarlo, aplicar presión en los bordes de la herida (no sobre el objeto), y transportar a la víctima urgentemente,</li>
                <li><b>And</b> permite al usuario practicar la técnica correcta antes de continuar.</li>
            </ul>
            <b>Escenario 5 (Hemorragia nasal - epistaxis):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario selecciona el caso específico "Hemorragia nasal",</li>
                <li><b>When</b> la simulación presenta a una persona con sangrado activo por la nariz,</li>
                <li><b>Then</b> la aplicación evalúa si el usuario: inclina la cabeza ligeramente hacia adelante (no hacia atrás), pellizca las fosas nasales suavemente durante 10 minutos, aplica frío en el puente nasal, y evita introducir gasas profundamente,</li>
                <li><b>And</b> si el usuario inclina la cabeza hacia atrás, muestra una alerta: "Inclinar la cabeza hacia atrás puede causar que la sangre fluya hacia la garganta, provocando náuseas o asfixia. Inclina la cabeza hacia adelante",</li>
                <li><b>And</b> al completar correctamente, explica cuándo buscar ayuda médica (sangrado que no cede después de 20 minutos, antecedentes de presión alta, etc.).</li>
            </ul>
            <b>Escenario 6 (Hemorragia en zona de difícil acceso - ingle):</b> <br/>
            <ul>
                <li><b>Given</b> que el sistema presenta una víctima con una herida en la ingle que sangra profusamente,</li>
                <li><b>When</b> el usuario debe aplicar presión directa en una zona anatómicamente compleja,</li>
                <li><b>Then</b> la aplicación evalúa si el usuario utiliza técnica de "presión con empaquetamiento" (packing) con gasa hemostática o tela limpia, aplicando presión firme hacia el hueso,</li>
                <li><b>And</b> muestra animaciones específicas para esta zona, advirtiendo sobre los vasos femorales,</li>
                <li><b>And</b> si el usuario aplica presión inadecuada, la app ofrece una guía paso a paso con imágenes anatómicas.</li>
            </ul>
            <b>Escenario 7 (Evaluación completa - resumen y puntuación):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario completó todos los pasos de la simulación (protección personal, presión directa, elevación, torniquete si aplicó, llamado a emergencias),</li>
                <li><b>When</b> el sistema evalúa el desempeño total,</li>
                <li><b>Then</b> muestra un resumen de resultados con: puntuación total (0-100), desglose por fase (preparación 10%, presión directa 40%, torniquete 30%, llamado a emergencias 10%, cuidados post-hemorragia 10%), lista de errores cometidos con explicaciones educativas,</li>
                <li><b>And</b> ofrece la opción de "Reintentar simulación" (para mejorar puntuación) o "Pasar al siguiente nivel" (hemorragias múltiples o trauma complejo),</li>
                <li><b>And</b> si la puntuación supera el 85%, genera un certificado digital de "Control Básico de Hemorragias".</li>
            </ul>
            <b>Escenario 8 (Modalidad evaluativa - tiempo y precisión):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario selecciona la modalidad "Evaluación" en el escenario de cortes y hemorragias,</li>
                <li><b>When</b> el sistema presenta una hemorragia arterial grave con cronómetro activo,</li>
                <li><b>Then</b> el usuario debe aplicar el protocolo completo sin ayudas visuales ni sugerencias,</li>
                <li><b>And</b> el sistema mide el tiempo desde la presentación del caso hasta la aplicación efectiva del torniquete (tiempo crítico real: menos de 60 segundos ideal),</li>
                <li><b>And</b> al finalizar, muestra la puntuación y compara el tiempo del usuario con los estándares de referencia,</li>
                <li><b>And</b> ofrece retroalimentación específica sobre velocidad de respuesta y precisión técnica.</li>
            </ul>
            <b>Escenario 9 (Material complementario - botiquín y contenidos):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario ha completado exitosamente la simulación,</li>
                <li><b>When</b> accede a la sección "Material complementario",</li>
                <li><b>Then</b> el sistema muestra: lista de elementos esenciales para un botiquín de primeros auxilios (gasas estériles, vendas, guantes, torniquete, tijeras, solución salina, etc.), videos tutoriales sobre técnicas de vendaje compresivo, infografía descargable de "Pasos para controlar una hemorragia", y enlace a la tienda SafeStep (EP04) para adquirir kits de emergencia,</li>
                <li><b>And</b> permite al usuario marcar qué elementos de botiquín ya posee en su hogar.</li>
            </ul>
            <b>Escenario 10 (Hemorragia en paciente anticoagulado):</b> <br/>
            <ul>
                <li><b>Given</b> que el sistema presenta una víctima que menciona estar tomando anticoagulantes (warfarina, aspirina, etc.),</li>
                <li><b>When</b> el usuario atiende una herida que sangra abundantemente a pesar de la presión directa,</li>
                <li><b>Then</b> la aplicación evalúa si el usuario reconoce la importancia de informar al personal médico sobre la medicación, y si aplica presión por más tiempo (10-15 minutos mínimo),</li>
                <li><b>And</b> muestra información educativa: "Los anticoagulantes dificultan la coagulación. Debes mantener la presión por más tiempo y buscar atención médica urgente",</li>
                <li><b>And</b> si el usuario no ajusta su técnica, la app advierte y ofrece la opción de revisar un módulo específico sobre "Atención a pacientes con trastornos de coagulación".</li>
            </ul>
        </b></td>
    </tr>
</table>

<table align="center">
    <tr>
        <td><b>User Story ID</b></td>
        <td>US11</b></td>
        <td><b>Epic ID</b></td>
        <td>EP03</b></td>
    </tr>
    <tr>
        <td><b>Título</b></td>
        <td colspan="3">Feedback inmediato</b></td>
    </tr>
    <tr>
        <td><b>Descripción</b></td>
        <td colspan="3">Como usuario, quiero recibir retroalimentación inmediata después de cada acción que realizo durante las simulaciones, para comprender rápidamente mis errores, reforzar mis aciertos y mejorar mi desempeño en tiempo real, sin tener que esperar hasta el final de la simulación.</b></td>
    </tr>
    <tr>
        <td colspan="4">
            <b>Criterios de aceptación:</b> <br/>
            <ol>
                <li>El sistema debe evaluar cada acción del usuario en tiempo real, con un tiempo de respuesta menor a 0.5 segundos después de cada interacción.</li>
                <li>Para acciones correctas, debe mostrar un mensaje de confirmación positivo con icono verde (check o pulgar arriba), texto motivador y breve explicación de por qué la acción fue adecuada.</li>
                <li>Para acciones incorrectas, debe mostrar un mensaje de error con icono rojo (alerta o pulgar abajo), texto explicativo indicando por qué la acción fue incorrecta o peligrosa, y una sugerencia para corregirla.</li>
                <li>Los mensajes de feedback deben ser claros, concisos y educativos, adaptados al nivel de conocimiento del usuario (principiante o avanzado).</li>
                <li>El sistema debe permitir al usuario configurar la intensidad del feedback: "Detallado" (explicaciones largas y ejemplos) o "Resumido" (mensajes cortos y directos).</li>
                <li>El feedback debe incluir elementos multimodales: visual (texto y color), auditivo (sonido de éxito para acciones correctas, sonido de alerta para errores), y háptico (vibración en dispositivos móviles para errores críticos).</li>
                <li>Después de un error, el sistema debe permitir al usuario reintentar la misma acción antes de continuar (sin penalización adicional en la puntuación por el reintento).</li>
                <li>El sistema debe acumular estadísticas de errores comunes del usuario para generar recomendaciones personalizadas al final de la simulación.</li>
                <li>El feedback no debe interrumpir completamente el flujo de la simulación a menos que el error sea crítico para la seguridad de la víctima simulada.</li>
                <li>El usuario debe poder desactivar temporalmente el feedback auditivo o háptico desde el menú de configuración, manteniendo el visual.</li>
                <li>El sistema debe registrar cada feedback mostrado para análisis posterior y mejora continua de la experiencia educativa.</li>
                <li>Para acciones parcialmente correctas (ejemplo: técnica adecuada pero mala posición), el sistema debe mostrar feedback de advertencia amarilla, indicando qué parte estuvo bien y qué necesita mejora.</li>
            </ol>
            <b>Escenario 1 (Acción correcta - feedback positivo inmediato):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario está realizando una simulación de control de hemorragias,</li>
                <li><b>When</b> aplica presión directa sobre la herida con una gasa estéril durante el tiempo adecuado,</li>
                <li><b>Then</b> la aplicación evalúa la acción como correcta en menos de 0.5 segundos,</li>
                <li><b>And</b> muestra un mensaje positivo con fondo verde: "¡Excelente! Aplicaste presión directa correctamente. Mantener la presión constante es clave para detener la hemorragia",</li>
                <li><b>And</b> reproduce un sonido corto de éxito (ejemplo: "ding"),</li>
                <li><b>And</b> permite continuar con el siguiente paso sin interrupciones.</li>
            </ul>
            <b>Escenario 2 (Acción incorrecta - feedback negativo con sugerencia):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario está realizando una simulación de atención a una víctima de accidente,</li>
                <li><b>When</b> intenta mover a la víctima sin evaluar si tiene posibles fracturas o lesiones en la columna,</li>
                <li><b>Then</b> la aplicación detecta el error inmediatamente,</li>
                <li><b>And</b> muestra un mensaje con fondo rojo: "¡Cuidado! No debes mover a una víctima sin evaluar posibles fracturas o lesiones de columna. Esto podría empeorar las lesiones o causar parálisis",</li>
                <li><b>And</b> ofrece una sugerencia: "En su lugar, estabiliza la cabeza y el cuello con tus manos y espera a que llegue ayuda profesional. Solo mueve a la víctima si está en peligro inminente (incendio, derrumbe, etc.)",</li>
                <li><b>And</b> reproduce un sonido de alerta,</li>
                <li><b>And</b> pausa la simulación brevemente para que el usuario lea y comprenda el error,</li>
                <li><b>And</b> permite al usuario corregir la acción o continuar con el siguiente paso.</li>
            </ul>
            <b>Escenario 3 (Acción parcialmente correcta - feedback de advertencia amarilla):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario está realizando compresiones torácicas en una simulación de RCP,</li>
                <li><b>When</b> aplica la profundidad correcta (5-6 cm) pero la frecuencia es demasiado baja (80 compresiones por minuto en lugar de 100-120),</li>
                <li><b>Then</b> la aplicación muestra un feedback de advertencia con fondo amarillo: "¡Bien en profundidad! Pero la frecuencia es baja. Debes realizar entre 100 y 120 compresiones por minuto. ¡Aumenta el ritmo!",</li>
                <li><b>And</b> muestra un metrónomo visual o audible para guiar al usuario al ritmo correcto,</li>
                <li><b>And</b> permite continuar pero registra el error parcial para la puntuación final.</li>
            </ul>
            <b>Escenario 4 (Error crítico - feedback con bloqueo y guía obligatoria):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario está atendiendo una simulación de atragantamiento en un bebé,</li>
                <li><b>When</b> intenta aplicar la maniobra de Heimlich (compresiones abdominales) en lugar de golpes en la espalda,</li>
                <li><b>Then</b> la aplicación detecta un error crítico que podría causar daño grave en un caso real,</li>
                <li><b>And</b> muestra un mensaje con fondo rojo intenso y borde parpadeante: "¡ERROR GRAVE! En bebés menores de 1 año NO se debe aplicar la maniobra de Heimlich porque puede dañar órganos internos. La técnica correcta es: 5 golpes en la espalda seguidos de 5 compresiones torácicas",</li>
                <li><b>And</b> bloquea la simulación hasta que el usuario visualice una guía paso a paso obligatoria (video o animación de 30 segundos),</li>
                <li><b>And</b> después de ver la guía, permite al usuario reintentar la acción correctamente,</li>
                <li><b>And</b> registra el error crítico en el historial para reforzamiento posterior.</li>
            </ul>
            <b>Escenario 5 (Feedback con opción de más información - modo aprendizaje):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario tiene activado el modo "Aprendizaje detallado" en la configuración,</li>
                <li><b>When</b> comete un error, por ejemplo, aplicar hielo directamente sobre una quemadura,</li>
                <li><b>Then</b> además del mensaje de error estándar, aparece un botón adicional "¿Por qué está mal?",</li>
                <li><b>When</b> el usuario hace clic en ese botón,</li>
                <li><b>Then</b> se despliega un panel con información ampliada: "El hielo directo puede causar vasoconstricción extrema, reduciendo el flujo sanguíneo y empeorando el daño tisular. Además, puede provocar congelación en la zona quemada. Siempre usa agua corriente fría (no helada) durante 10-15 minutos",</li>
                <li><b>And</b> se incluye un enlace a un artículo o video relacionado para profundizar.</li>
            </ul>
            <b>Escenario 6 (Feedback acumulado al final de la simulación):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario ha completado una simulación completa con múltiples acciones, algunas correctas y otras incorrectas,</li>
                <li><b>When</b> finaliza la simulación,</li>
                <li><b>Then</b> el sistema muestra un resumen con: número total de aciertos, número total de errores, lista de los 3 errores más frecuentes o críticos, y recomendaciones personalizadas de micro-lecciones o simulaciones específicas para reforzar esos temas,</li>
                <li><b>And</b> ofrece la opción de "Revisar mis errores" que permite al usuario volver a cada momento de error con el feedback correspondiente,</li>
                <li><b>And</b> muestra un mensaje motivacional basado en el desempeño: "¡Mejoraste un 15% respecto a tu intento anterior!" o "¡Sigue practicando para dominar este tema!".</li>
            </ul>
            <b>Escenario 7 (Feedback configurable - modo silencioso):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario accede al menú de configuración de la aplicación,</li>
                <li><b>When</b> desactiva la opción "Feedback auditivo" y "Feedback háptico", manteniendo solo "Feedback visual",</li>
                <li><b>Then</b> durante las simulaciones posteriores, las acciones correctas solo mostrarán mensajes visuales sin sonidos ni vibración,</li>
                <li><b>And</b> las acciones incorrectas mostrarán mensajes visuales con alerta visual (color rojo) pero sin sonidos ni vibración,</li>
                <li><b>And</b> la configuración se guarda para futuras sesiones.</li>
            </ul>
            <b>Escenario 8 (Feedback positivo reforzador - racha de aciertos):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario ha realizado 5 acciones correctas consecutivas en una misma simulación,</li>
                <li><b>When</b> realiza una sexta acción correcta,</li>
                <li><b>Then</b> además del feedback positivo estándar, se muestra un mensaje especial: "¡Impresionante! Llevas 6 aciertos consecutivos. ¡Sigue así!",</li>
                <li><b>And</b> se reproduce un sonido especial de logro (ejemplo: fanfarria corta),</li>
                <li><b>And</b> se suma un bonus pequeño a la puntuación final (ejemplo: +2 puntos por racha).</li>
            </ul>
            <b>Escenario 9 (Feedback predictivo - prevención de errores comunes):</b> <br/>
            <ul>
                <li><b>Given</b> que el sistema detecta que el usuario está a punto de cometer un error común basado en su patrón de comportamiento previo,</li>
                <li><b>When</b> el usuario mueve el cursor o el dedo hacia una opción peligrosa (ejemplo: "retirar gasa empapada" en una hemorragia),</li>
                <li><b>Then</b> el sistema muestra un feedback preventivo antes de que el usuario confirme la acción: "¿Estás seguro? Retirar la gasa empapada puede reiniciar la hemorragia. Es mejor añadir más gasa encima",</li>
                <li><b>And</b> permite al usuario reconsiderar su decisión sin penalización,</li>
                <li><b>And</b> si el usuario ignora la advertencia y comete el error, se registra como error estándar.</li>
            </ul>
            <b>Escenario 10 (Feedback en tiempo real para acciones físicas - RCP):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario está practicando compresiones torácicas en una simulación de RCP que utiliza el micrófono o acelerómetro del dispositivo para medir ritmo y profundidad,</li>
                <li><b>When</b> realiza una compresión demasiado superficial (menos de 5 cm),</li>
                <li><b>Then</b> la aplicación muestra feedback inmediato durante la compresión: "Más profundidad. Las compresiones deben ser de al menos 5 cm",</li>
                <li><b>And</b> si la frecuencia es incorrecta, muestra un indicador visual en tiempo real: "Ritmo actual: 85/min → Acelera hacia 100-120/min",</li>
                <li><b>And</b> al completar el ciclo de compresiones, muestra un resumen del desempeño: "85% de compresiones con profundidad adecuada, 70% con ritmo correcto".</li>
            </ul>
        </b></td>
    </table>
</tr>

<table align="center">
    <tr>
        <td><b>User Story ID</b></td>
        <td>US12</b></td>
        <td><b>Epic ID</b></td>
        <td>EP03</b></td>
    </tr>
    <tr>
        <td><b>Título</b></td>
        <td colspan="3">Recomendaciones personalizadas</b></td>
    </tr>
    <tr>
        <td><b>Descripción</b></td>
        <td colspan="3">Como usuario, quiero recibir sugerencias de temas en los que fallé durante las simulaciones, para reforzar mi aprendizaje y mejorar mis conocimientos en primeros auxilios de manera progresiva y personalizada, enfocándome en mis áreas débiles sin perder tiempo en contenido que ya domino.</b></td>
    </tr>
    <tr>
        <td colspan="4">
            <b>Criterios de aceptación:</b> <br/>
            <ol>
                <li>El sistema debe analizar automáticamente los resultados de cada simulación realizada por el usuario, identificando errores específicos o áreas de bajo desempeño (puntuación inferior al 70% en un tema determinado).</li>
                <li>A partir del análisis, la aplicación debe generar recomendaciones personalizadas de módulos, micro-lecciones, videos o simulaciones relacionadas con los temas en los que el usuario cometió errores.</li>
                <li>Las recomendaciones deben mostrarse de manera clara al finalizar cada simulación (pantalla de resultados) y también dentro de una sección dedicada llamada "Mis Recomendaciones" accesible desde el menú principal.</li>
                <li>El usuario debe poder acceder directamente desde cada recomendación al contenido sugerido con un solo clic o toque.</li>
                <li>El sistema debe registrar el historial de refuerzos completados (qué recomendaciones aceptó y completó) para medir la mejora del desempeño en evaluaciones posteriores.</li>
                <li>Las sugerencias deben actualizarse dinámicamente conforme el usuario repite simulaciones y mejora sus resultados, eliminando temas ya dominados y añadiendo nuevos basados en errores recientes.</li>
                <li>El algoritmo de recomendación debe priorizar la relevancia (errores más críticos o frecuentes primero) y la variedad de temas, evitando repeticiones innecesarias del mismo contenido.</li>
                <li>El sistema debe permitir al usuario descartar una recomendación si no le interesa, y aprender de esa acción para futuras sugerencias.</li>
                <li>Las recomendaciones deben incluir un nivel de prioridad (Alta, Media, Baja) basado en la criticidad del tema para la seguridad en emergencias reales.</li>
                <li>El sistema debe enviar notificaciones opcionales (push o correo) cuando se generen nuevas recomendaciones importantes basadas en errores recientes.</li>
                <li>El algoritmo debe considerar el tiempo desde el último refuerzo del tema (recomendar repaso periódico aunque el usuario haya aprobado, para evitar el olvido).</li>
                <li>Las recomendaciones pueden incluir también contenido complementario (infografías, artículos, videos) no solo simulaciones, etiquetado por tipo de recurso.</li>
            </ol>
            <b>Escenario 1 (Recomendaciones post-simulación con bajo desempeño):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario completa una simulación de "Hemorragias" y obtiene una puntuación del 45%,</li>
                <li><b>When</b> el sistema analiza su desempeño y detecta debilidades específicas: "No aplicó presión el tiempo suficiente", "No elevó la extremidad", "No usó torniquete correctamente",</li>
                <li><b>Then</b> la aplicación genera una lista de módulos o simulaciones de refuerzo relacionadas,</li>
                <li><b>And</b> los presenta en la pantalla de resultados con niveles de prioridad: "Alta prioridad: Técnica de presión directa", "Alta prioridad: Uso correcto del torniquete", "Media prioridad: Elevación de extremidades",</li>
                <li><b>And</b> cada recomendación incluye un botón "Practicar ahora" que redirige directamente a la simulación o micro-lección específica,</li>
                <li><b>And</b> muestra un mensaje: "Para mejorar tu puntuación, te recomendamos reforzar estos 3 temas antes de reintentar la simulación".</li>
            </ul>
            <b>Escenario 2 (Sección "Mis Recomendaciones" - vista centralizada):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario ha realizado múltiples simulaciones durante la semana en diferentes temas (RCP, quemaduras, atragantamiento),</li>
                <li><b>When</b> accede a la sección "Mis Recomendaciones" desde el menú principal,</li>
                <li><b>Then</b> el sistema muestra un tablero personalizado con todas las recomendaciones activas, organizadas por categorías: "Pendientes de reforzar", "En progreso", "Completadas",</li>
                <li><b>And</b> cada tarjeta de recomendación muestra: tema, prioridad (color rojo/naranja/verde), fecha de generación, tiempo estimado de práctica (ejemplo: "5 min"), y un botón "Comenzar",</li>
                <li><b>And</b> se muestra un indicador de progreso general: "Has completado 4 de 7 recomendaciones esta semana".</li>
            </ul>
            <b>Escenario 3 (Actualización dinámica - mejora y reemplazo de temas):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario tenía una recomendación activa de "Maniobra de Heimlich en adultos" por haber fallado en ese tema,</li>
                <li><b>When</b> el usuario completa la micro-lección de refuerzo y luego realiza nuevamente la simulación de atragantamiento, obteniendo una puntuación del 90% en ese tema específico,</li>
                <li><b>Then</b> el sistema detecta la mejora significativa,</li>
                <li><b>And</b> actualiza la sección "Mis Recomendaciones" eliminando la recomendación de "Heimlich en adultos",</li>
                <li><b>And</b> si el usuario aún tiene debilidades en otros temas (ejemplo: "Heimlich en bebés"), mantiene esas recomendaciones o añade nuevas basadas en errores recientes,</li>
                <li><b>And</b> muestra un mensaje de logro: "¡Has dominado la maniobra de Heimlich en adultos! Pasas a la siguiente área de mejora".</li>
            </ul>
            <b>Escenario 4 (Recomendaciones basadas en errores críticos de seguridad):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario comete un error crítico durante una simulación de RCP, como no verificar la escena antes de actuar,</li>
                <li><b>When</b> el sistema analiza el error y lo clasifica como "Crítico - Seguridad del rescatista",</li>
                <li><b>Then</b> la recomendación generada tiene prioridad "Máxima" y aparece destacada en la parte superior de la lista,</li>
                <li><b>And</b> el sistema envía una notificación push opcional: "Error crítico detectado. Te recomendamos revisar el módulo 'Seguridad en la escena' antes de continuar",</li>
                <li><b>And</b> si el usuario ignora la recomendación y vuelve a cometer el mismo error crítico, el sistema puede sugerir un modo "Entrenamiento obligatorio" para ese tema específico.</li>
            </ul>
            <b>Escenario 5 (Recomendaciones variadas - no solo simulaciones):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario tiene dificultades para recordar los pasos de la maniobra de Heimlich,</li>
                <li><b>When</b> el sistema genera recomendaciones personalizadas,</li>
                <li><b>Then</b> ofrece una variedad de recursos educativos, no solo simulaciones: "Video tutorial: Maniobra de Heimlich paso a paso (3 min)", "Infografía descargable: Resumen de atragantamiento", "Micro-lección interactiva: 5 preguntas para practicar", "Simulación corta: Atragantamiento en adulto (5 min)",</li>
                <li><b>And</b> el usuario puede elegir el formato que prefiera según su estilo de aprendizaje,</li>
                <li><b>And</b> el sistema registra qué tipo de recurso completó el usuario para futuras recomendaciones similares.</li>
            </ul>
            <b>Escenario 6 (Recomendaciones periódicas por repaso - evitar olvido):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario aprobó la simulación de "Quemaduras" con un 85% hace 3 meses, pero no ha vuelto a practicar ese tema desde entonces,</li>
                <li><b>When</b> el algoritmo de recomendación detecta el tiempo transcurrido sin práctica en un tema importante,</li>
                <li><b>Then</b> el sistema genera una recomendación de "Repaso periódico": "Ha pasado tiempo desde tu última práctica en Quemaduras. ¿Recuerdas los pasos? Te sugerimos un repaso rápido de 3 minutos",</li>
                <li><b>And</b> el usuario puede completar una micro-lección de repaso o una simulación corta para mantener sus conocimientos actualizados,</li>
                <li><b>And</b> el sistema reinicia el contador de "última práctica" para ese tema.</li>
            </ul>
            <b>Escenario 7 (Usuario descarta recomendación - aprendizaje del algoritmo):</b> <br/>
            <ul>
                <li><b>Given</b> que el sistema recomienda al usuario el módulo "RCP en bebés" porque tuvo errores en ese tema,</li>
                <li><b>When</b> el usuario hace clic en "Descartar" o "No me interesa ahora",</li>
                <li><b>Then</b> la recomendación desaparece de la lista principal pero se mueve a una sección "Descartadas",</li>
                <li><b>And</b> el algoritmo registra el descarte y no recomendará el mismo tema específico durante al menos 7 días, a menos que el usuario vuelva a fallar en él,</li>
                <li><b>And</b> prioriza otras recomendaciones basadas en otros errores o áreas de mejora.</li>
            </ul>
            <b>Escenario 8 (Recomendaciones basadas en comparativa con otros usuarios):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario ha completado varias simulaciones con puntuaciones promedio del 65%,</li>
                <li><b>When</b> el sistema compara su desempeño con usuarios de perfil similar (mismo nivel, misma ubicación geográfica, etc.),</li>
                <li><b>Then</b> puede generar recomendaciones basadas en "brechas de conocimiento comunitario": "Muchos usuarios en tu comunidad han mejorado su preparación para sismos. Tú tienes un 60% en ese tema. ¿Quieres practicar 'Sismos' para estar al día?",</li>
                <li><b>And</b> muestra un gráfico comparativo anónimo: "Tu puntuación: 60% | Promedio de tu comunidad: 78%",</li>
                <li><b>And</b> ofrece un enlace directo al escenario de sismos.</li>
            </ul>
            <b>Escenario 9 (Recomendaciones para certificación - preparación de examen):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario ha activado el objetivo "Obtener certificación básica en primeros auxilios",</li>
                <li><b>When</b> el sistema analiza su progreso general y detecta que tiene cubierto el 70% de los temas necesarios para la certificación,</li>
                <li><b>Then</b> genera una lista priorizada de temas pendientes: "Para obtener tu certificación, solo te faltan estos 3 temas: Hemorragias (45%), RCP (60%), Quemaduras (75%)",</li>
                <li><b>And</b> muestra un plan de estudio personalizado con fechas sugeridas: "Semana 1: Practica Hemorragias. Semana 2: Refuerza RCP. Semana 3: Repaso general y examen final",</li>
                <li><b>And</b> ofrece la opción de añadir recordatorios al calendario del usuario.</li>
            </ul>
            <b>Escenario 10 (Recomendaciones gamificadas - retos semanales):</b> <br/>
            <ul>
                <li><b>Given</b> que el sistema detecta que el usuario tiene debilidad en tres temas específicos (torniquete, RCP, atragantamiento),</li>
                <li><b>When</b> el usuario accede a la sección "Recomendaciones" al inicio de la semana,</li>
                <li><b>Then</b> el sistema presenta un "Reto semanal personalizado": "Completa estas 3 recomendaciones antes del domingo y gana 100 puntos extra + una insignia 'Refuerzo Estrella'",</li>
                <li><b>And</b> muestra una barra de progreso del reto que se actualiza cada vez que el usuario completa una recomendación,</li>
                <li><b>And</b> al completar el reto, el sistema felicita al usuario y actualiza su perfil con la insignia y los puntos ganados.</li>
            </ul>
        </b></td>
    </tr>
</table>

<table align="center">
    <tr>
        <td><b>User Story ID</b></td>
        <td>US13</b></td>
        <td><b>Epic ID</b></td>
        <td>EP03</b></td>
    </tr>
    <tr>
        <td><b>Título</b></td>
        <td colspan="3">Progreso visual</b></td>
    </tr>
    <tr>
        <td><b>Descripción</b></td>
        <td colspan="3">Como usuario, quiero visualizar mi progreso mediante gráficos e indicadores visuales claros y atractivos, para conocer mi avance en los distintos módulos de primeros auxilios, identificar rápidamente mis fortalezas y debilidades, y mantenerme motivado para seguir aprendiendo y mejorando.</b></td>
    </tr>
    <tr>
        <td colspan="4">
            <b>Criterios de aceptación:</b> <br/>
            <ol>
                <li>El sistema debe registrar automáticamente el desempeño del usuario en cada simulación (puntaje, tiempo, aciertos y errores por tema específico).</li>
                <li>En la sección "Perfil" o "Mi progreso", deben mostrarse gráficos dinámicos (barras, anillos, líneas o radar) que representen el avance general y por módulo (RCP, hemorragias, quemaduras, atragantamiento, sismos).</li>
                <li>Los porcentajes deben calcularse según la cantidad de simulaciones completadas, puntajes promedio obtenidos, módulos aprobados (puntuación ≥ 70%) y tiempo de respuesta.</li>
                <li>El usuario debe poder filtrar la información por periodo (semanal, mensual, trimestral, anual, total) y por tipo de escenario (todos o específico).</li>
                <li>El diseño de los gráficos debe ser responsivo, accesible (con opciones de alto contraste y etiquetas claras) y fácil de interpretar tanto en web como en dispositivos móviles.</li>
                <li>Al interactuar con los gráficos (hover, clic o toque), el usuario debe poder ver información detallada como: "75% de avance en quemaduras", "2 errores en maniobra Heimlich", "Mejor tiempo: 45 segundos".</li>
                <li>Los datos deben actualizarse en tiempo real tras finalizar cada simulación o módulo, sin necesidad de recargar la página.</li>
                <li>El sistema debe mostrar una puntuación general compuesta (ejemplo: "Nivel de preparación: 68%") basada en el promedio ponderado de todos los módulos.</li>
                <li>Debe incluir un indicador visual de "rachas" (consecutive days of practice) para motivar la práctica diaria.</li>
                <li>El usuario debe poder exportar su progreso en formato PDF o CSV para compartirlo con instructores o instituciones.</li>
                <li>El sistema debe mostrar comparativas anónimas con el promedio de la comunidad (si el usuario lo permite) para contextualizar su progreso.</li>
                <li>Los gráficos deben incluir códigos de color intuitivos: verde (dominado, ≥80%), amarillo (en progreso, 50-79%), rojo (necesita mejora, &lt;50%).</li>
            </ol>
            <b>Escenario 1 (Vista general del progreso - panel principal):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario ha completado varias simulaciones en distintos módulos (RCP, hemorragias, quemaduras, atragantamiento, sismos),</li>
                <li><b>When</b> accede a la sección "Perfil / Mi progreso" desde el menú principal,</li>
                <li><b>Then</b> la aplicación muestra un panel visual con los siguientes elementos:</li>
                <li><b>And</b> un gráfico de anillo circular mostrando el nivel de preparación general (ejemplo: 68% con un arco verde-amarillo-rojo),</li>
                <li><b>And</b> un gráfico de barras horizontales con el porcentaje de avance por cada módulo (RCP: 85%, Hemorragias: 45%, Quemaduras: 70%, Atragantamiento: 60%, Sismos: 90%),</li>
                <li><b>And</b> los módulos con puntaje menor al 50% (Hemorragias: 45%) se resaltan en rojo con un mensaje: "Área crítica - Te recomendamos reforzar",</li>
                <li><b>And</b> un indicador de racha actual: "Llevas 7 días consecutivos practicando. ¡Sigue así!".</li>
            </ul>
            <b>Escenario 2 (Interacción con gráficos - vista detallada por módulo):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario se encuentra en la sección de progreso visualizando el gráfico de barras por módulo,</li>
                <li><b>When</b> hace clic o toca la barra del módulo "Atragantamiento",</li>
                <li><b>Then</b> el sistema despliega un panel lateral o modal con información detallada sobre su desempeño en ese módulo:</li>
                <li><b>And</b> "Número de simulaciones realizadas: 4",</li>
                <li><b>And</b> "Mejor puntuación: 85%", "Peor puntuación: 45%", "Promedio: 68%",</li>
                <li><b>And</b> "Errores comunes: Posición incorrecta de manos en Heimlich (2 veces), No verificar respuesta de la víctima (1 vez)",</li>
                <li><b>And</b> "Tiempo promedio de respuesta: 12 segundos",</li>
                <li><b>And</b> un botón "Reforzar este módulo" que redirige a las recomendaciones personalizadas para atragantamiento.</li>
            </ul>
            <b>Escenario 3 (Filtro por periodo - evolución temporal):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario ha estado usando la aplicación durante 3 meses y quiere ver su evolución,</li>
                <li><b>When</b> accede a la sección de progreso y selecciona el filtro "Evolución mensual" y el módulo "RCP",</li>
                <li><b>Then</b> el sistema muestra un gráfico de líneas con los puntajes obtenidos mes a mes:</li>
                <li><b>And</b> "Enero: 55%", "Febrero: 70%", "Marzo: 85%",</li>
                <li><b>And</b> una línea de tendencia que indica mejora progresiva,</li>
                <li><b>And</b> un mensaje motivacional: "¡Has mejorado un 30% en RCP en los últimos 3 meses! Excelente progreso",</li>
                <li><b>And</b> permite cambiar el filtro a "semanal" para ver detalles más finos de las últimas semanas.</li>
            </ul>
            <b>Escenario 4 (Gráfico de radar - competencias multidimensionales):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario quiere una visión holística de sus competencias en primeros auxilios,</li>
                <li><b>When</b> selecciona la vista "Gráfico de radar" en la sección de progreso,</li>
                <li><b>Then</b> el sistema muestra un gráfico radial con 5 ejes (RCP, Hemorragias, Quemaduras, Atragantamiento, Sismos),</li>
                <li><b>And</b> cada eje tiene una marca del porcentaje alcanzado (ejemplo: RCP 85%, Hemorragias 45%, etc.), formando un polígono irregular,</li>
                <li><b>And</b> se superpone un polígono de referencia "Promedio de la comunidad" (si el usuario aceptó compartir datos),</li>
                <li><b>And</b> se resalta visualmente que "Hemorragias" es el área más alejada del promedio, sugiriendo prioridad de mejora.</li>
            </ul>
            <b>Escenario 5 (Actualización en tiempo real - post-simulación):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario acaba de completar una simulación de "Hemorragias" obteniendo un puntaje del 75% (mejorando su promedio anterior del 45%),</li>
                <li><b>When</b> el sistema muestra la pantalla de resultados con el puntaje obtenido,</li>
                <li><b>Then</b> si el usuario navega inmediatamente a la sección "Mi progreso",</li>
                <li><b>And</b> el gráfico de barras del módulo "Hemorragias" se actualiza automáticamente del 45% al 58% (nuevo promedio),</li>
                <li><b>And</b> el color de la barra cambia de rojo a amarillo (de "necesita mejora" a "en progreso"),</li>
                <li><b>And</b> se muestra una notificación de logro: "¡Has mejorado tu puntuación en Hemorragias! Sigue así para alcanzar el nivel dominado (≥80%)".</li>
            </ul>
            <b>Escenario 6 (Exportación de progreso - PDF y CSV):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario necesita presentar su progreso en primeros auxilios a su empleador o institución educativa,</li>
                <li><b>When</b> accede a la sección "Mi progreso" y presiona el botón "Exportar",</li>
                <li><b>Then</b> el sistema muestra opciones de formato: "Exportar como PDF" (informe visual con gráficos) o "Exportar como CSV" (datos brutos para análisis),</li>
                <li><b>And</b> al seleccionar PDF, se genera un documento con: nombre del usuario, fecha de exportación, gráficos de progreso general y por módulo, tabla de puntuaciones históricas, resumen de certificaciones obtenidas,</li>
                <li><b>And</b> permite descargar el archivo o enviarlo por correo electrónico,</li>
                <li><b>And</b> se registra la exportación en el historial de actividad del usuario.</li>
            </ul>
            <b>Escenario 7 (Comparativa con la comunidad - opcional):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario ha habilitado en su configuración la opción "Comparar mi progreso con la comunidad",</li>
                <li><b>When</b> accede a la sección "Mi progreso" y activa el toggle "Ver comparativa comunitaria",</li>
                <li><b>Then</b> el sistema muestra, junto a sus gráficos personales, una línea o barra adicional que representa el promedio anónimo de usuarios con perfil similar (mismo país, mismo rango de edad, mismo nivel de experiencia),</li>
                <li><b>And</b> se muestran mensajes como: "Estás por encima del promedio en RCP (+12%), pero por debajo en Hemorragias (-15%)",</li>
                <li><b>And</b> se ofrece la opción de "Ver ranking comunitario" para motivar la superación.</li>
            </ul>
            <b>Escenario 8 (Indicadores de logros e insignias):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario ha alcanzado ciertos hitos en su progreso (ejemplo: completar 10 simulaciones, obtener 90% en un módulo, racha de 30 días),</li>
                <li><b>When</b> accede a la sección "Mi progreso",</li>
                <li><b>Then</b> el sistema muestra una galería de insignias desbloqueadas en la parte superior,</li>
                <li><b>And</b> cada insignia tiene un tooltip con la descripción del logro y la fecha de obtención,</li>
                <li><b>And</b> las insignias pendientes se muestran en gris con el requisito para desbloquearlas (ejemplo: "Completa el módulo de Hemorragias con ≥80%"),</li>
                <li><b>And</b> el usuario puede compartir sus insignias en redes sociales directamente desde esta sección.</li>
            </ul>
            <b>Escenario 9 (Accesibilidad - modo de alto contraste y lectores de pantalla):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario tiene activado el modo de alto contraste en la configuración de accesibilidad,</li>
                <li><b>When</b> accede a la sección "Mi progreso",</li>
                <li><b>Then</b> los gráficos se adaptan automáticamente para mantener un contraste mínimo de 4.5:1,</li>
                <li><b>And</b> las etiquetas de datos y leyendas son legibles con colores alternativos,</li>
                <li><b>And</b> los lectores de pantalla pueden interpretar los gráficos mediante texto alternativo descriptivo (ejemplo: "Gráfico de barras: RCP 85%, Hemorragias 45%..."),</li>
                <li><b>And</b> se ofrece una vista alternativa en tabla para usuarios que prefieren datos textuales.</li>
            </ul>
            <b>Escenario 10 (Recomendaciones integradas en el progreso):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario visualiza su progreso y detecta que el módulo "Hemorragias" está en rojo (45%),</li>
                <li><b>When</b> el sistema detecta esta debilidad,</li>
                <li><b>Then</b> automáticamente muestra debajo del gráfico una tarjeta de recomendación: "Basado en tu progreso, te sugerimos reforzar el módulo de Hemorragias. ¡Mejorarás tu puntuación general en un 15%!",</li>
                <li><b>And</b> incluye un botón "Ir a recomendaciones" que redirige a US12 (Recomendaciones personalizadas),</li>
                <li><b>And</b> si el usuario ya ha completado algunas recomendaciones, muestra un mensaje: "Completaste 2 de 3 recomendaciones para Hemorragias. ¡Una más y dominarás el tema!".</li>
            </ul>
        </b></td>
    </tr>
</table>

<table align="center">
    <tr>
        <td><b>User Story ID</b></td>
        <td>US14</b></td>
        <td><b>Epic ID</b></td>
        <td>EP03</b></td>
    </tr>
    <tr>
        <td><b>Título</b></td>
        <td colspan="3">Micro-lecciones de refuerzo</b></td>
    </tr>
    <tr>
        <td><b>Descripción</b></td>
        <td colspan="3">Como usuario, quiero recibir pequeñas lecciones diarias de primeros auxilios para mantener mis conocimientos actualizados, reforzar lo aprendido y conservar una rutina constante de práctica incluso cuando no realizo simulaciones completas, de manera rápida y sin necesidad de invertir mucho tiempo.</b></td>
    </tr>
    <tr>
        <td colspan="4">
            <b>Criterios de aceptación:</b> <br/>
            <ol>
                <li>El sistema debe detectar periodos de inactividad (por ejemplo, más de 3 días sin práctica de simulaciones completas) y activar automáticamente el envío o la visualización de una micro-lección al abrir la aplicación.</li>
                <li>Las micro-lecciones deben ser breves (1–3 minutos de duración estimada), centradas en un solo concepto o procedimiento específico, e incluir ejemplos visuales, animaciones simples o ilustraciones.</li>
                <li>El contenido debe actualizarse diariamente y adaptarse al historial del usuario (priorizando temas donde haya tenido errores en simulaciones anteriores o donde tenga poca práctica registrada).</li>
                <li>Las micro-lecciones deben mostrarse al abrir la aplicación, en formato de tarjeta destacada o pop-up no intrusivo, con opciones claras de "Comenzar ahora", "Ver más tarde" (posponer) o "No mostrar esta lección".</li>
                <li>Al finalizar una micro-lección, el sistema debe registrar la fecha, el tema y el tiempo invertido, y actualizar la racha (contador de días consecutivos de práctica) del usuario.</li>
                <li>El diseño debe ser accesible, claro y responsivo tanto en versión web como en dispositivos móviles, con tipografía legible y botones fáciles de tocar.</li>
                <li>La app debe ofrecer la posibilidad de acceder a un historial completo de micro-lecciones vistas, con fecha, tema y nivel de retención (opcional: mini quiz de verificación).</li>
                <li>El sistema debe permitir al usuario configurar la frecuencia de las micro-lecciones (diaria, cada 2 días, solo cuando hay inactividad, o desactivarlas).</li>
                <li>Las micro-lecciones deben incluir al final una pregunta rápida de opción múltiple (1-2 preguntas) para verificar la comprensión del concepto, con feedback inmediato.</li>
                <li>El sistema debe acumular puntos o experiencia por cada micro-lección completada, contribuyendo al nivel general del usuario y desbloqueo de insignias (ejemplo: "Racha de 7 días", "Maestro de micro-lecciones").</li>
                <li>Las micro-lecciones deben estar disponibles en modo offline si el usuario las descargó previamente (sincronización al volver a conectarse).</li>
                <li>El contenido de las micro-lecciones debe ser revisado y actualizado periódicamente por expertos en primeros auxilios para garantizar precisión médica.</li>
            </ol>
            <b>Escenario 1 (Inactividad prolongada - activación automática):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario no ha abierto la aplicación ni ha practicado ninguna simulación durante los últimos 5 días,</li>
                <li><b>When</b> finalmente abre la aplicación,</li>
                <li><b>Then</b> el sistema muestra una tarjeta destacada en la pantalla de inicio: "¡Te hemos extrañado! Aquí tienes una micro-lección de 2 minutos para retomar tu práctica",</li>
                <li><b>And</b> la micro-lección está relacionada con un tema que el usuario había dejado pendiente (ejemplo: "Repaso rápido: Pasos para controlar una hemorragia"),</li>
                <li><b>And</b> el usuario tiene las opciones: "Comenzar ahora", "Ver más tarde" (posponer 4 horas) o "No mostrar esta lección".</li>
            </ul>
            <b>Escenario 2 (Completar micro-lección - registro y actualización de racha):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario ha visualizado y completado una micro-lección diaria sobre "Maniobra de Heimlich en adultos", incluyendo la pregunta de verificación al final,</li>
                <li><b>When</b> marca la actividad como finalizada o responde correctamente la pregunta,</li>
                <li><b>Then</b> el sistema registra la fecha y tema de la micro-lección en su historial personal,</li>
                <li><b>And</b> actualiza el contador de racha (días consecutivos de práctica), mostrando un mensaje motivacional: "¡Excelente! Llevas 5 días seguidos reforzando tus conocimientos. ¡Sigue así!",</li>
                <li><b>And</b> otorga 10 puntos de experiencia al usuario, acercándolo a la siguiente insignia,</li>
                <li><b>And</b> si el usuario responde incorrectamente la pregunta de verificación, se muestra la respuesta correcta con una breve explicación y se ofrece otra pregunta similar más adelante.</li>
            </ul>
            <b>Escenario 3 (Micro-lección adaptada al historial de errores):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario ha cometido errores específicos en simulaciones anteriores, como "No verificar la escena antes de ayudar en un accidente",</li>
                <li><b>When</b> el sistema selecciona la micro-lección del día para este usuario,</li>
                <li><b>Then</b> el contenido se adapta a sus áreas débiles: "Seguridad en la escena: Antes de ayudar, verifica que no haya peligros (fuego, tráfico, cables eléctricos)",</li>
                <li><b>And</b> incluye una animación corta que muestra un ejemplo de una escena insegura vs. segura,</li>
                <li><b>And</b> al final, pregunta: "¿Qué debes hacer primero al llegar a un accidente de tránsito?" con opciones que refuerzan el concepto.</li>
            </ul>
            <b>Escenario 4 (Configuración de frecuencia - preferencias del usuario):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario accede a la sección "Configuración / Preferencias de aprendizaje",</li>
                <li><b>When</b> selecciona la opción "Micro-lecciones diarias" y elige "Recibir una micro-lección cada día (aunque haya practicado)",</li>
                <li><b>Then</b> el sistema guarda su preferencia y, a partir del día siguiente, mostrará una micro-lección diaria independientemente de su actividad de simulación,</li>
                <li><b>And</b> el usuario puede cambiar en cualquier momento a "Solo cuando esté inactivo por más de 3 días" o "Desactivar micro-lecciones",</li>
                <li><b>And</b> si elige desactivarlas, el sistema deja de mostrar las tarjetas pero mantiene el historial de lecciones previas accesible.</li>
            </ul>
            <b>Escenario 5 (Historial de micro-lecciones vistas):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario ha completado varias micro-lecciones durante las últimas semanas (ejemplo: "RCP en adultos", "Quemaduras de primer grado", "Maniobra de Heimlich", "Control de hemorragias"),</li>
                <li><b>When</b> accede a la sección "Mi progreso / Micro-lecciones",</li>
                <li><b>Then</b> el sistema muestra un historial cronológico con: fecha de visualización, título del tema, duración estimada, resultado de la pregunta de verificación (correcto/incorrecto), y un botón "Repetir lección",</li>
                <li><b>And</b> permite filtrar el historial por tema, por mes o por resultado,</li>
                <li><b>And</b> muestra estadísticas: "Has completado 12 micro-lecciones en total. Tu promedio de aciertos es del 85%".</li>
            </ul>
            <b>Escenario 6 (Modo offline - micro-lecciones descargadas):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario ha descargado previamente un paquete de micro-lecciones cuando tenía conexión a internet,</li>
                <li><b>When</b> se encuentra sin conexión (por ejemplo, en un viaje o zona sin cobertura) y abre la aplicación,</li>
                <li><b>Then</b> el sistema detecta el modo offline y muestra una micro-lección disponible localmente,</li>
                <li><b>And</b> el usuario puede completarla normalmente,</li>
                <li><b>And</b> el progreso se almacena localmente y se sincroniza automáticamente cuando el dispositivo recupera la conexión,</li>
                <li><b>And</b> se muestra un indicador: "Modo offline - Tu progreso se sincronizará al volver a conectarte".</li>
            </ul>
            <b>Escenario 7 (Gamificación - puntos e insignias por micro-lecciones):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario completa una micro-lección diaria durante 7 días consecutivos,</li>
                <li><b>When</b> alcanza el séptimo día,</li>
                <li><b>Then</b> el sistema muestra una animación de logro: "¡Insignia desbloqueada! 'Racha de una semana' - Has completado micro-lecciones durante 7 días seguidos",</li>
                <li><b>And</b> otorga 50 puntos de experiencia adicionales como bonificación por la racha,</li>
                <li><b>And</b> si el usuario continúa hasta 30 días, desbloquea la insignia "Maestro de la constancia" con 200 puntos de bonificación,</li>
                <li><b>And</b> las insignias se muestran en el perfil público del usuario (opcional).</li>
            </ul>
            <b>Escenario 8 (Contenido variado - formatos multimedia):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario recibe una micro-lección diferente cada día,</li>
                <li><b>When</b> el sistema selecciona el formato de la lección,</li>
                <li><b>Then</b> alterna entre diferentes tipos de contenido para mantener el interés: "Tarjeta didáctica" (texto + imagen), "Mini video" (15-30 segundos), "Animación interactiva" (clic para revelar pasos), "Infografía animada", o "Quiz rápido" de 3 preguntas,</li>
                <li><b>And</b> el usuario puede indicar su preferencia por un formato específico en la configuración,</li>
                <li><b>And</b> el sistema prioriza ese formato cuando sea posible.</li>
            </ul>
            <b>Escenario 9 (Micro-lecciones temáticas por temporada o campaña):</b> <br/>
            <ul>
                <li><b>Given</b> que estamos en una temporada específica (ejemplo: verano, temporada de lluvias, campaña de prevención),</li>
                <li><b>When</b> el sistema selecciona la micro-lección del día para todos los usuarios,</li>
                <li><b>Then</b> puede priorizar temas relevantes para la temporada: "Protección solar y golpe de calor" en verano, "Prevención de ahogamientos" en vacaciones, "Manejo de inundaciones" en temporada de lluvias, o "RCP" durante la campaña del mes del corazón,</li>
                <li><b>And</b> muestra un ícono temático junto a la lección,</li>
                <li><b>And</b> al finalizar, ofrece recursos adicionales relacionados con la campaña (enlaces a simulaciones, artículos, etc.).</li>
            </ul>
            <b>Escenario 10 (Notificaciones recordatorio de micro-lección):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario tiene activadas las notificaciones push en la aplicación,</li>
                <li><b>When</b> el sistema tiene una nueva micro-lección disponible para el día (por inactividad o por configuración diaria),</li>
                <li><b>Then</b> envía una notificación push al dispositivo del usuario en un horario configurable (ejemplo: 9:00 AM),</li>
                <li><b>And</b> el mensaje de la notificación es atractivo y breve: "🧠 ¡Tu micro-lección diaria te espera! Aprende algo nuevo en 2 minutos",</li>
                <li><b>And</b> al hacer clic en la notificación, la aplicación se abre directamente en la tarjeta de la micro-lección,</li>
                <li><b>And</b> si el usuario no abre la notificación, se envía un segundo recordatorio opcional 6 horas después (configurable).</li>
            </ul>
        </b></td>
    </tr>
</tr>

<table align="center">
    <tr>
        <td><b>User Story ID</b></td>
        <td>US15</b></td>
        <td><b>Epic ID</b></td>
        <td>EP03</b></td>
    </tr>
    <tr>
        <td><b>Título</b></td>
        <td colspan="3">Evaluación final por módulo</b></td>
    </tr>
    <tr>
        <td><b>Descripción</b></td>
        <td colspan="3">Como estudiante, quiero rendir una evaluación final por módulo que integre todos los temas aprendidos, para validar mi aprendizaje de manera integral, obtener una certificación que acredite mis conocimientos y recibir retroalimentación detallada sobre mi desempeño antes de avanzar al siguiente nivel.</b></td>
    </tr>
    <tr>
        <td colspan="4">
            <b>Criterios de aceptación:</b> <br/>
            <ol>
                <li>El sistema debe requerir que el usuario haya completado al menos el 80% de las simulaciones del módulo (o todas las obligatorias) antes de desbloquear la "Evaluación final".</li>
                <li>La evaluación debe incluir una combinación de formatos: preguntas de opción múltiple (teoría), escenarios interactivos ramificados (aplicación práctica) y preguntas de ordenamiento de pasos (procedimientos).</li>
                <li>El número de preguntas por evaluación debe ser proporcional a la complejidad del módulo (mínimo 10 preguntas para módulos básicos, hasta 20-25 para módulos avanzados).</li>
                <li>El sistema debe establecer un tiempo límite para la evaluación (ejemplo: 60 segundos por pregunta) y mostrar un temporizador visible.</li>
                <li>La calificación mínima aprobatoria debe ser configurable por módulo (recomendado: 70% para módulos básicos, 80% para avanzados).</li>
                <li>Al finalizar, el sistema debe mostrar la calificación obtenida (porcentaje y nota), desglose por área temática, lista de respuestas correctas e incorrectas con explicaciones educativas, y tiempo total empleado.</li>
                <li>El sistema debe ofrecer sugerencias personalizadas de refuerzo (micro-lecciones o simulaciones específicas) basadas en las áreas de menor desempeño en la evaluación.</li>
                <li>Si el usuario no aprueba, debe poder reintentar la evaluación hasta 3 veces, con un tiempo de espera de 24 horas entre intentos (para fomentar el estudio).</li>
                <li>Si el usuario aprueba, el sistema debe generar automáticamente un certificado digital con: nombre completo del usuario, nombre del módulo, fecha de aprobación, calificación obtenida, nivel de logro (Básico, Intermedio, Avanzado), y código QR de verificación.</li>
                <li>El certificado debe poder descargarse en formato PDF, compartirse en redes sociales o enviarse por correo electrónico, y almacenarse en la sección "Mis certificaciones" del perfil.</li>
                <li>El sistema debe registrar todas las evaluaciones completadas en el historial del usuario, incluyendo intentos fallidos y exitosos, para seguimiento de progreso.</li>
                <li>La evaluación debe contar con un sistema anti-trampas: prohibición de copiar/pegar, aleatorización del orden de preguntas y respuestas, y detección de cambios de pestaña (en web).</li>
                <li>El usuario debe poder pausar la evaluación una sola vez por intento (por un máximo de 10 minutos) en caso de interrupción justificada.</li>
            </ol>
            <b>Escenario 1 (Desbloqueo y inicio de evaluación - requisitos cumplidos):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario ha completado todas las simulaciones obligatorias del módulo "Primeros Auxilios Básicos" (RCP, hemorragias, atragantamiento, quemaduras), obteniendo al menos el 60% en cada una,</li>
                <li><b>When</b> accede a la sección del módulo y selecciona la opción "Evaluación final",</li>
                <li><b>Then</b> la aplicación muestra una pantalla de confirmación con: "Esta evaluación consta de 15 preguntas. Tiempo estimado: 15 minutos. Calificación mínima aprobatoria: 70%. ¿Estás listo para comenzar?",</li>
                <li><b>And</b> al confirmar, inicia la evaluación con un temporizador visible en la parte superior,</li>
                <li><b>And</b> la primera pregunta aparece con formato de opción múltiple sobre RCP.</li>
            </ul>
            <b>Escenario 2 (Evaluación completada exitosamente - resultados y certificado):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario finalizó la evaluación respondiendo 12 de 15 preguntas correctamente (80% de aciertos),</li>
                <li><b>When</b> el sistema procesa los resultados y verifica que supera el 70% mínimo,</li>
                <li><b>Then</b> muestra una pantalla de felicitaciones con: "¡Felicidades! Has aprobado el módulo 'Primeros Auxilios Básicos' con una calificación del 80%",</li>
                <li><b>And</b> muestra un desglose detallado: "RCP: 3/3 correctas", "Hemorragias: 2/4 correctas (área de mejora)", "Atragantamiento: 4/4 correctas", "Quemaduras: 3/4 correctas",</li>
                <li><b>And</b> ofrece sugerencias personalizadas: "Te recomendamos reforzar el tema de Hemorragias con la micro-lección 'Control de hemorragias: técnicas avanzadas'",</li>
                <li><b>And</b> muestra un botón "Ver certificado" y otro "Descargar certificado en PDF".</li>
            </ul>
            <b>Escenario 3 (Generación y compartición de certificado digital):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario aprobó la evaluación final del módulo y está en la pantalla de resultados,</li>
                <li><b>When</b> selecciona la opción "Ver certificado",</li>
                <li><b>Then</b> la aplicación genera un certificado digital con: nombre completo del usuario, nombre del módulo ("Primeros Auxilios Básicos"), fecha de emisión, calificación (80%), nivel de logro ("Intermedio"), código QR único de verificación, y firma digital del director de SafeStep,</li>
                <li><b>And</b> permite al usuario descargarlo como PDF, compartirlo en LinkedIn, Facebook o WhatsApp, o enviarlo por correo electrónico,</li>
                <li><b>And</b> el certificado se guarda automáticamente en la sección "Mis certificaciones" del perfil, accesible en cualquier momento,</li>
                <li><b>And</b> cualquier persona con el código QR puede verificar la autenticidad del certificado en el sitio web de SafeStep.</li>
            </ul>
            <b>Escenario 4 (Evaluación no aprobada - reintento con recomendaciones):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario finalizó la evaluación obteniendo 9 de 15 respuestas correctas (60%, por debajo del 70% mínimo),</li>
                <li><b>When</b> el sistema procesa los resultados,</li>
                <li><b>Then</b> muestra una pantalla de retroalimentación constructiva: "No alcanzaste la calificación mínima (60% vs 70% requerido). No te desanimes, ¡puedes intentarlo de nuevo!",</li>
                <li><b>And</b> detalla las áreas con errores: "RCP: 2/3 correctas (fallaste en frecuencia de compresiones)", "Hemorragias: 1/4 correctas (necesitas reforzar)", "Atragantamiento: 3/4 correctas", "Quemaduras: 3/4 correctas",</li>
                <li><b>And</b> ofrece un plan de estudio personalizado: "Te sugerimos practicar estas 2 simulaciones: 'Control de hemorragias' y 'RCP - ritmo y profundidad', y luego reintentar la evaluación",</li>
                <li><b>And</b> informa que puede reintentar en 24 horas, mostrando un contador regresivo,</li>
                <li><b>And</b> después del segundo intento fallido, sugiere contactar a un tutor o revisar el material completo del módulo antes de un tercer intento.</li>
            </ul>
            <b>Escenario 5 (Evaluación con escenarios interactivos ramificados):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario está rindiendo la evaluación final del módulo "Emergencias Complejas",</li>
                <li><b>When</b> llega a una pregunta de tipo "escenario interactivo",</li>
                <li><b>Then</b> el sistema presenta una situación realista (ejemplo: "Encuentras a una persona inconsciente en la calle. ¿Cuál es tu primera acción?"),</li>
                <li><b>And</b> el usuario debe seleccionar una opción, y dependiendo de su respuesta, el escenario se ramifica (ejemplo: si elige "verificar la escena" → sigue a "verificar respiración"; si elige "comenzar RCP inmediatamente" → se le penaliza por omitir la verificación de seguridad),</li>
                <li><b>And</b> el sistema evalúa no solo la respuesta final sino también la secuencia de decisiones,</li>
                <li><b>And</b> al finalizar el escenario, se muestra un resumen de las decisiones y su corrección.</li>
            </ul>
            <b>Escenario 6 (Anti-trampas - detección de cambio de pestaña):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario está rindiendo la evaluación en la versión web,</li>
                <li><b>When</b> intenta cambiar de pestaña o abrir una nueva ventana del navegador para buscar respuestas,</li>
                <li><b>Then</b> el sistema detecta la pérdida de foco de la ventana de la evaluación,</li>
                <li><b>And</b> muestra una advertencia: "Se ha detectado un cambio de pestaña. Esto puede afectar tu calificación. Por favor, mantén la evaluación en primer plano",</li>
                <li><b>And</b> registra el incidente, y si ocurre más de 2 veces, la evaluación se cancela automáticamente y se marca como "Intento inválido",</li>
                <li><b>And</b> el usuario debe esperar 24 horas para un nuevo intento.</li>
            </ul>
            <b>Escenario 7 (Pausa justificada - reanudación de evaluación):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario está a la mitad de la evaluación y recibe una llamada urgente,</li>
                <li><b>When</b> selecciona la opción "Pausar evaluación" (disponible solo una vez por intento),</li>
                <li><b>Then</b> el sistema guarda automáticamente el progreso (preguntas respondidas y tiempo restante),</li>
                <li><b>And</b> muestra un mensaje: "Evaluación pausada. Tienes 10 minutos para reanudar. Pasado ese tiempo, se contará como intento fallido",</li>
                <li><b>And</b> al regresar dentro del tiempo límite, la evaluación se reanuda exactamente donde se quedó, con el temporizador ajustado al tiempo restante,</li>
                <li><b>And</b> si el usuario excede los 10 minutos, la evaluación se cierra y cuenta como intento fallido.</li>
            </ul>
            <b>Escenario 8 (Historial de evaluaciones - seguimiento de intentos):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario ha realizado 3 intentos de evaluación para el módulo "RCP Avanzado" (2 fallidos, 1 exitoso),</li>
                <li><b>When</b> accede a la sección "Mi progreso / Evaluaciones",</li>
                <li><b>Then</b> el sistema muestra un historial detallado de cada intento: fecha, calificación obtenida, tiempo empleado, estado (aprobado/reprobado), y un botón "Ver detalles" que muestra las respuestas y retroalimentación de ese intento,</li>
                <li><b>And</b> muestra una gráfica de mejora: "Primer intento: 55% → Segundo intento: 68% → Tercer intento: 82% (aprobado)",</li>
                <li><b>And</b> ofrece la opción de "Repetir evaluación" solo si el usuario desea mejorar su calificación (máximo 3 intentos adicionales por módulo).</li>
            </ul>
            <b>Escenario 9 (Evaluación adaptativa - dificultad según desempeño previo):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario ha demostrado un alto desempeño en simulaciones previas del módulo (promedio >85%),</li>
                <li><b>When</b> inicia la evaluación final,</li>
                <li><b>Then</b> el sistema puede presentar una versión de la evaluación con preguntas de mayor complejidad (casos más desafiantes, escenarios con múltiples variables),</li>
                <li><b>And</b> si el usuario responde correctamente las primeras preguntas, el nivel de dificultad aumenta progresivamente,</li>
                <li><b>And</b> al finalizar, la calificación se pondera considerando la dificultad de las preguntas respondidas,</li>
                <li><b>And</b> si el usuario tiene bajo desempeño previo, la evaluación mantiene un nivel básico para no desmotivar.</li>
            </ul>
            <b>Escenario 10 (Certificado con código QR verificable):</b> <br/>
            <ul>
                <li><b>Given</b> que un empleador recibe el certificado PDF de un candidato que aprobó el módulo "Primeros Auxilios Laborales",</li>
                <li><b>When</b> escanea el código QR incluido en el certificado con su teléfono,</li>
                <li><b>Then</b> se abre una página oficial de SafeStep que muestra: nombre del certificado, nombre del usuario, fecha de emisión, calificación, y un sello de verificación "Certificado auténtico",</li>
                <li><b>And</b> si el certificado es falso o el código no existe, la página muestra "Certificado no válido",</li>
                <li><b>And</b> el empleador puede descargar una copia de verificación desde esa página.</li>
            </ul>
        </b></td>
    </tr>
</tr>

<table align="center">
    <tr>
        <td><b>User Story ID</b></td>
        <td>US16</td>
        <td><b>Epic ID</b></td>
        <td>EP04</td>
    </tr>
    <tr>
        <td><b>Título</b></td>
        <td colspan="3">Catálogo de productos</td>
    </tr>
    <tr>
        <td><b>Descripción</b></td>
        <td colspan="3">Como usuario registrado, quiero visualizar un catálogo completo de productos de primeros auxilios (torniquetes, botiquines, mochilas de emergencia, etc.) organizado por categorías, para explorar fácilmente los materiales disponibles y decidir qué comprar según mis necesidades de preparación ante emergencias.</td>
    </tr>
    <tr>
        <td colspan="4">
            <b>Criterios de aceptación:</b> <br/>
            <ol>
                <li>El sistema debe mostrar los productos en formato de cuadrícula (grid) o lista, con imagen, nombre, precio y puntuación promedio.</li>
                <li>Los productos deben estar organizados por categorías predefinidas (ejemplo: "Torniquetes", "Botiquines", "Mochilas de emergencia", "Material de curación", "Protección personal").</li>
                <li>Cada página del catálogo debe mostrar un mínimo de 12 productos, con paginación o desplazamiento infinito (lazy loading).</li>
                <li>El catálogo debe ser responsivo, adaptándose correctamente a dispositivos móviles, tablets y escritorio.</li>
                <li>Debe mostrar un indicador visual cuando un producto está agotado ("Sin stock") o en oferta ("Oferta").</li>
                <li>El tiempo de carga del catálogo no debe superar los 3 segundos en condiciones normales de red.</li>
                <li>Si no hay productos disponibles en una categoría, debe mostrarse un mensaje amigable ("No hay productos disponibles en esta categoría por el momento").</li>
            </ol>
            <b>Escenario 1:</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario ha iniciado sesión en SafeStep,</li>
                <li><b>And</b> accede a la sección "Tienda" o "Comercio" desde el menú principal,</li>
                <li><b>When</b> el sistema carga la pantalla de catálogo,</li>
                <li><b>Then</b> se muestran los productos disponibles organizados por defecto en orden de popularidad o fecha de lanzamiento,</li>
                <li><b>And</b> cada tarjeta de producto incluye imagen, nombre, precio y un botón "Ver detalles".</li>
            </ul>
            <b>Escenario 2:</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario navega por el catálogo,</li>
                <li><b>When</b> selecciona una categoría específica (ejemplo: "Mochilas de emergencia"),</li>
                <li><b>Then</b> el sistema filtra los productos y muestra solo aquellos pertenecientes a esa categoría,</li>
                <li><b>And</b> actualiza el título de la página para indicar la categoría seleccionada.</li>
            </ul>
        </td>
    </tr>
</table>

<table align="center">
    <tr>
        <td><b>User Story ID</b></td>
        <td>US17</td>
        <td><b>Epic ID</b></td>
        <td>EP04</td>
    </tr>
    <tr>
        <td><b>Título</b></td>
        <td colspan="3">Filtros y búsqueda de productos</td>
    </tr>
    <tr>
        <td><b>Descripción</b></td>
        <td colspan="3">Como usuario, quiero filtrar y buscar productos específicos dentro del catálogo utilizando criterios como categoría, rango de precio, calificación y disponibilidad, para encontrar rápidamente el material de primeros auxilios que necesito sin tener que revisar manualmente todos los artículos.</td>
    </tr>
    <tr>
        <td colspan="4">
            <b>Criterios de aceptación:</b> <br/>
            <ol>
                <li>El sistema debe incluir una barra de búsqueda por texto (nombre del producto o palabra clave).</li>
                <li>Debe ofrecer filtros combinables: categoría, precio mínimo y máximo, calificación (1-5 estrellas), disponibilidad (en stock / agotado).</li>
                <li>Los filtros deben aplicarse en tiempo real sin necesidad de recargar la página completa (usando AJAX o similar).</li>
                <li>El sistema debe mostrar cuántos resultados coinciden con los filtros aplicados.</li>
                <li>Debe existir un botón para "Limpiar filtros" que restablezca la vista del catálogo completo.</li>
                <li>Si la búsqueda o filtros no arrojan resultados, debe mostrarse un mensaje claro ("No se encontraron productos con esos criterios. Prueba con otros filtros").</li>
                <li>Los filtros deben ser accesibles desde dispositivos móviles (por ejemplo, mediante un botón desplegable "Filtrar").</li>
                <li>La respuesta del sistema al aplicar filtros no debe exceder los 2 segundos.</li>
            </ol>
            <b>Escenario 1:</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario se encuentra en el catálogo de productos,</li>
                <li><b>When</b> escribe "torniquete" en la barra de búsqueda y presiona "Buscar",</li>
                <li><b>Then</b> el sistema muestra solo los productos cuyo nombre o descripción contengan la palabra "torniquete",</li>
                <li><b>And</b> actualiza el contador de resultados encontrados.</li>
            </ul>
            <b>Escenario 2:</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario está en el catálogo,</li>
                <li><b>When</b> selecciona el filtro de precio "S/20 - S/50" y la categoría "Botiquines",</li>
                <li><b>Then</b> el sistema actualiza automáticamente la lista mostrando solo botiquines cuyo precio esté entre S/20 y S/50,</li>
                <li><b>And</b> mantiene visibles los demás filtros para que el usuario pueda seguir refinando la búsqueda.</li>
            </ul>
            <b>Escenario 3:</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario aplicó varios filtros y obtuvo cero resultados,</li>
                <li><b>When</b> presiona el botón "Limpiar filtros",</li>
                <li><b>Then</b> el sistema restablece todos los filtros a su estado por defecto,</li>
                <li><b>And</b> vuelve a mostrar el catálogo completo de productos.</li>
            </ul>
        </td>
    </tr>
</table>

<table align="center">
    <tr>
        <td><b>User Story ID</b></td>
        <td>US18</td>
        <td><b>Epic ID</b></td>
        <td>EP04</td>
    </tr>
    <tr>
        <td><b>Título</b></td>
        <td colspan="3">Vista detallada del producto</td>
    </tr>
    <tr>
        <td><b>Descripción</b></td>
        <td colspan="3">Como usuario, quiero acceder a una página de detalle de cada producto que incluya información completa (descripción ampliada, especificaciones técnicas, imágenes adicionales, opiniones de otros compradores y disponibilidad de stock), para tomar una decisión informada antes de agregar el artículo a mi carrito de compras.</td>
    </tr>
    <tr>
        <td colspan="4">
            <b>Criterios de aceptación:</b> <br/>
            <ol>
                <li>Cada producto debe tener una página de detalle accesible desde el catálogo o resultados de búsqueda.</li>
                <li>La vista debe incluir: nombre del producto, precio, calificación promedio (con número de reseñas), descripción detallada, especificaciones (material, dimensiones, peso, incluidos), stock disponible ("Quedan X unidades" o "En stock").</li>
                <li>Debe mostrarse un carrusel o galería con al menos 3 imágenes del producto.</li>
                <li>El usuario debe poder seleccionar cantidad (con un selector numérico, mínimo 1, máximo hasta stock disponible).</li>
                <li>Debe incluir botones claros: "Agregar al carrito" y "Comprar ahora".</li>
                <li>Si el producto está agotado, el botón "Agregar al carrito" debe deshabilitarse y mostrar un mensaje "Sin stock" o "Notificarme cuando esté disponible".</li>
                <li>Debe mostrarse una sección de reseñas y valoraciones de otros usuarios (con opción de ordenar por más reciente o más útil).</li>
                <li>El sistema debe sugerir productos relacionados o complementarios (ejemplo: "Quienes compraron este producto también adquirieron..." o "Complementos ideales").</li>
                <li>La carga de la página de detalle no debe exceder los 2 segundos.</li>
            </ol>
            <b>Escenario 1:</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario navega por el catálogo,</li>
                <li><b>When</b> hace clic en la tarjeta de un producto (por ejemplo, "Mochila de emergencia 72h") o en el botón "Ver detalles",</li>
                <li><b>Then</b> el sistema navega a la página de detalle de ese producto,</li>
                <li><b>And</b> muestra toda la información completa: imágenes, precio, descripción, especificaciones, stock y reseñas.</li>
            </ul>
            <b>Escenario 2:</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario está en la página de detalle de un producto con stock disponible,</li>
                <li><b>When</b> selecciona la cantidad "2" (sin superar el stock) y presiona "Agregar al carrito",</li>
                <li><b>Then</b> el sistema agrega el producto con la cantidad seleccionada al carrito de compras,</li>
                <li><b>And</b> muestra una notificación de confirmación ("Producto agregado al carrito") con un enlace para ir al carrito o seguir comprando.</li>
            </ul>
            <b>Escenario 3:</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario está en la página de detalle de un producto agotado,</li>
                <li><b>When</b> intenta agregarlo al carrito,</li>
                <li><b>Then</b> el botón "Agregar al carrito" aparece deshabilitado,</li>
                <li><b>And</b> se muestra un mensaje: "Producto agotado. Activa la notificación para recibir un aviso cuando vuelva a estar disponible",</li>
                <li><b>And</b> aparece un botón opcional "Notificarme" que registra el interés del usuario.</li>
            </ul>
        </td>
    </tr>
</table>

<table align="center">
    <tr>
        <td><b>User Story ID</b></td>
        <td>US19</b></td>
        <td><b>Epic ID</td>
        <td>EP04</b></td>
    </tr>
    <tr>
        <td><b>Título</b></td>
        <td colspan="3">Agregar productos al carrito de compras</b></td>
    </tr>
    <tr>
        <td><b>Descripción</td>
        <td colspan="3">Como usuario, quiero agregar productos al carrito de compras desde el catálogo o desde la vista detallada, seleccionando la cantidad deseada, para acumular los artículos que deseo adquirir antes de proceder al pago, de manera rápida y sin perder mi sesión de navegación.</b></td>
    </tr>
    <tr>
        <td colspan="4">
            <b>Criterios de aceptación:</b> <br/>
            <ol>
                <li>El sistema debe permitir agregar productos al carrito tanto desde la tarjeta del catálogo (con un botón rápido) como desde la página de detalle.</li>
                <li>Al agregar un producto desde el catálogo, debe usar la cantidad predeterminada de 1 unidad.</li>
                <li>Desde la vista detallada, el usuario debe poder seleccionar una cantidad específica (mínimo 1, máximo el stock disponible).</li>
                <li>El sistema debe validar que la cantidad solicitada no supere el stock disponible antes de agregar al carrito.</li>
                <li>Al agregar un producto, debe mostrarse una notificación visual clara (ejemplo: "Producto agregado al carrito") con un enlace directo al carrito y otro para "Seguir comprando".</li>
                <li>Si el usuario agrega un producto que ya existe en el carrito, el sistema debe actualizar la cantidad sumando la nueva selección (sin duplicar el ítem).</li>
                <li>El ícono del carrito en la barra de navegación debe actualizarse dinámicamente mostrando el número total de artículos agregados.</li>
                <li>El proceso de agregar al carrito no debe recargar la página completa (debe ser mediante AJAX o similar).</li>
                <li>El tiempo de respuesta al agregar un producto no debe exceder 1 segundo.</li>
            </ol>
            <b>Escenario 1:</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario está navegando por el catálogo de productos,</li>
                <li><b>And</b> el producto "Torniquete táctico" tiene stock disponible,</li>
                <li><b>When</b> presiona el botón "Agregar al carrito" en la tarjeta del producto,</li>
                <li><b>Then</b> el sistema agrega 1 unidad del producto al carrito,</li>
                <li><b>And</b> muestra una notificación emergente con el mensaje "Torniquete táctico agregado al carrito",</li>
                <li><b>And</b> actualiza el contador del ícono del carrito.</li>
            </ul>
            <b>Escenario 2:</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario está en la página de detalle del producto "Botiquín básico",</li>
                <li><b>And</b> el stock disponible es de 10 unidades,</li>
                <li><b>When</b> selecciona la cantidad "3" usando el selector numérico y presiona "Agregar al carrito",</li>
                <li><b>Then</b> el sistema agrega 3 unidades del botiquín al carrito,</li>
                <li><b>And</b> muestra un mensaje de confirmación con las opciones "Ver carrito" y "Seguir comprando".</li>
            </ul>
            <b>Escenario 3:</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario intenta agregar un producto que ya está en el carrito,</li>
                <li><b>When</b> agrega 2 unidades adicionales del mismo producto,</li>
                <li><b>Then</b> el sistema no duplica el ítem,</li>
                <li><b>And</b> actualiza la cantidad existente sumando las 2 nuevas unidades,</li>
                <li><b>And</b> muestra una notificación indicando "Cantidad actualizada en el carrito".</li>
            </ul>
        </td>
    </tr>
</table>

<table align="center">
    <tr>
        <td><b>User Story ID</td>
        <td>US20</td>
        <td><b>Epic ID</td>
        <td>EP04</td>
    </tr>
    <tr>
        <td><b>Título</td>
        <td colspan="3">Modificar cantidades y eliminar productos del carrito</td>
    </tr>
    <tr>
        <td><b>Descripción</td>
        <td colspan="3">Como usuario, quiero poder modificar las cantidades de los productos agregados al carrito o eliminar aquellos que ya no deseo comprar, para tener control total sobre mi selección de compra antes de proceder al pago, de forma intuitiva y con actualización automática de precios.</td>
    </tr>
    <tr>
        <td colspan="4">
            <b>Criterios de aceptación:</b> <br/>
            <ol>
                <li>El carrito de compras debe mostrar una lista clara de todos los productos agregados, con imagen, nombre, precio unitario, cantidad seleccionada y subtotal por producto.</li>
                <li>Cada producto debe tener controles para aumentar/disminuir la cantidad (botones "+" y "-") y un campo numérico editable manualmente.</li>
                <li>El sistema debe validar que la cantidad no sea menor a 1 ni mayor al stock disponible.</li>
                <li>Al modificar la cantidad de un producto, el subtotal de ese producto y el total general del carrito deben actualizarse automáticamente sin recargar la página.</li>
                <li>Cada producto debe incluir un botón "Eliminar" o ícono de papelera para removerlo completamente del carrito.</li>
                <li>Al eliminar un producto, debe mostrarse un mensaje de confirmación opcional ("¿Eliminar este producto del carrito?") y actualizarse el carrito inmediatamente.</li>
                <li>Si el carrito queda vacío, debe mostrarse un mensaje amigable ("Tu carrito está vacío. ¡Explora nuestro catálogo!") con un enlace para seguir comprando.</li>
                <li>El sistema debe mostrar el subtotal, costos de envío (si aplica) y el total final actualizados en tiempo real.</li>
                <li>Todas las modificaciones deben persistir aunque el usuario cierre la sesión o el navegador (usando almacenamiento local o base de datos).</li>
            </ol>
            <b>Escenario 1:</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario tiene en su carrito 2 unidades de "Mochila de emergencia" a S/120 cada una,</li>
                <li><b>When</b> presiona el botón "+" para aumentar la cantidad a 3 unidades,</li>
                <li><b>Then</b> el sistema actualiza la cantidad a 3,</li>
                <li><b>And</b> el subtotal del producto cambia de S/240 a S/360,</li>
                <li><b>And</b> el total general del carrito se actualiza automáticamente.</li>
            </ul>
            <b>Escenario 2:</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario tiene un producto en su carrito,</li>
                <li><b>When</b> presiona el botón "Eliminar" o ícono de papelera junto al producto,</li>
                <li><b>Then</b> el sistema muestra un cuadro de diálogo de confirmación ("¿Eliminar este producto?"),</li>
                <li><b>And</b> al confirmar, remueve el producto del carrito,</li>
                <li><b>And</b> actualiza el total general y el contador del carrito.</li>
            </ul>
            <b>Escenario 3:</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario edita manualmente el campo de cantidad de un producto,</li>
                <li><b>When</b> ingresa un número válido (ejemplo: 5) y presiona "Enter" o sale del campo,</li>
                <li><b>Then</b> el sistema valida que 5 no supere el stock disponible,</li>
                <li><b>And</b> actualiza la cantidad, el subtotal y el total general.</li>
            </ul>
        </td>
    </tr>
</table>

<table align="center">
    <tr>
        <td><b>User Story ID</b></td>
        <td>US21</b></td>
        <td><b>Epic ID</b></td>
        <td>EP04</b></td>
    </tr>
    <tr>
        <td><b>Título</b></td>
        <td colspan="3">Resumen de compra y cálculo de envío</b></td>
    </tr>
    <tr>
        <td><b>Descripción</b></td>
        <td colspan="3">Como usuario, quiero visualizar un resumen claro de mi compra (productos, cantidades, subtotal, envío e impuestos) antes de proceder al pago, y poder calcular el costo de envío según mi ubicación, para conocer el monto total a pagar y decidir si continúo con la transacción o realizo ajustes.</b></td>
    </tr>
    <tr>
        <td colspan="4">
            <b>Criterios de aceptación:</b> <br/>
            <ol>
                <li>El carrito debe incluir una sección de "Resumen de compra" con los siguientes campos: subtotal (suma de productos), costo de envío, impuestos (si aplica) y total final.</li>
                <li>El sistema debe permitir al usuario ingresar su código postal o seleccionar su ubicación (ciudad/distrito) para calcular el costo de envío en tiempo real.</li>
                <li>Deben mostrarse diferentes opciones de envío si están disponibles (estándar, express, recogida en tienda) con sus respectivos costos y tiempos estimados.</li>
                <li>El usuario debe poder aplicar un cupón de descuento (campo de texto y botón "Aplicar") con validación inmediata.</li>
                <li>El resumen debe actualizarse automáticamente al modificar cantidades, eliminar productos, cambiar ubicación o aplicar descuentos.</li>
                <li>Debe mostrarse un desglose claro de cada producto (nombre, cantidad, precio unitario y subtotal).</li>
                <li>El sistema debe indicar si se alcanza el monto mínimo para envío gratis (ejemplo: "¡Agrega S/30 más para obtener envío gratis!").</li>
                <li>Debe incluir un botón prominente "Proceder al pago" que solo se active si el carrito no está vacío y la dirección de envío es válida.</li>
                <li>El resumen debe ser visible tanto en versión escritorio (columna lateral) como en móvil (acordeón o parte inferior).</li>
            </ol>
            <b>Escenario 1:</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario tiene productos en su carrito por un subtotal de S/150,</li>
                <li><b>When</b> ingresa su código postal "LIMA01" y selecciona la opción "Envío estándar (S/15, 3-5 días)",</li>
                <li><b>Then</b> el sistema calcula el costo de envío de S/15,</li>
                <li><b>And</b> muestra el total final como S/165 (más impuestos si aplica),</li>
                <li><b>And</b> actualiza el resumen automáticamente.</li>
            </ul>
            <b>Escenario 2:</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario tiene un subtotal de S/200 en el carrito,</li>
                <li><b>When</b> ingresa un cupón válido "BIENVENIDO10" que otorga 10% de descuento,</li>
                <li><b>Then</b> el sistema aplica el descuento de S/20,</li>
                <li><b>And</b> actualiza el resumen mostrando "Descuento: -S/20",</li>
                <li><b>And</b> recalcula el total final.</li>
            </ul>
            <b>Escenario 3:</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario no ha ingresado una ubicación válida para envío,</li>
                <li><b>When</b> intenta proceder al pago,</li>
                <li><b>Then</b> el botón "Proceder al pago" debe estar deshabilitado o mostrar un mensaje de advertencia,</li>
                <li><b>And</b> el sistema solicita al usuario que ingrese su código postal o dirección de envío antes de continuar.</li>
            </ul>
        </td>
    </tr>
</tr>

<table align="center">
    <tr>
        <td><b>User Story ID</b></td>
        <td>US22</b></td>
        <td><b>Epic ID</td>
        <td>EP04</b></td>
    </tr>
    <tr>
        <td><b>Título</td>
        <td colspan="3">Proceso de pago seguro (tarjeta, transferencia, billetera digital)</b></td>
    </tr>
    <tr>
        <td><b>Descripción</td>
        <td colspan="3">Como usuario, quiero realizar el pago de mi compra de forma segura utilizando múltiples métodos de pago (tarjeta de crédito/débito, transferencia bancaria o billetera digital), para completar mi transacción con confianza, protegendo mis datos financieros y recibiendo una confirmación inmediata.</b></td>
    </tr>
    <tr>
        <td colspan="4">
            <b>Criterios de aceptación:</b> <br/>
            <ol>
                <li>El sistema debe ofrecer al menos tres métodos de pago: tarjeta de crédito/débito, transferencia bancaria y billetera digital (ejemplo: Yape, Plin, PayPal según la región).</li>
                <li>Todo el proceso de pago debe realizarse bajo conexión cifrada (HTTPS) y cumplir con estándares PCI DSS para datos de tarjetas.</li>
                <li>Para pagos con tarjeta, el sistema debe solicitar: número de tarjeta, fecha de vencimiento, CVV y nombre del titular.</li>
                <li>Para transferencia bancaria, debe mostrar los datos de la cuenta (banco, número de cuenta, titular, RUC) y un comprobante de pago a enviar.</li>
                <li>Para billetera digital, debe redirigir al usuario a la pasarela de pago correspondiente o generar un código QR.</li>
                <li>El sistema debe validar en tiempo real los datos de la tarjeta (formato, fecha no vencida, CVV de 3 o 4 dígitos).</li>
                <li>Después de un pago exitoso, el sistema debe mostrar una pantalla de confirmación con el número de pedido y un resumen de la compra.</li>
                <li>Debe enviar un correo electrónico de confirmación con los detalles del pedido y el comprobante de pago.</li>
                <li>En caso de error en el pago, el sistema debe mostrar un mensaje claro ("Fondos insuficientes", "Tarjeta rechazada", etc.) sin revelar información sensible.</li>
                <li>El usuario debe poder reintentar el pago hasta 3 veces antes de ser redirigido a modificar su método de pago.</li>
                <li>El tiempo total del proceso de pago no debe exceder los 30 segundos en condiciones normales.</li>
            </ol>
            <b>Escenario 1:</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario ha revisado el resumen de compra y está listo para pagar,</li>
                <li><b>When</b> selecciona la opción "Pagar con tarjeta", ingresa los datos de su tarjeta válida y presiona "Confirmar pago",</li>
                <li><b>Then</b> el sistema procesa el pago a través de la pasarela de pagos,</li>
                <li><b>And</b> muestra una pantalla de éxito con el número de pedido #SAF-12345,</li>
                <li><b>And</b> envía un correo de confirmación al usuario.</li>
            </ul>
            <b>Escenario 2:</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario selecciona "Transferencia bancaria" como método de pago,</li>
                <li><b>When</b> el sistema muestra los datos bancarios de SafeStep y solicita subir el comprobante de transferencia,</li>
                <li><b>Then</b> el usuario puede subir una imagen o PDF del comprobante,</li>
                <li><b>And</b> el sistema registra el pedido como "Pendiente de verificación",</li>
                <li><b>And</b> notifica al usuario que recibirá una confirmación en un plazo máximo de 24 horas hábiles.</li>
            </ul>
            <b>Escenario 3:</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario ingresa datos de tarjeta inválidos (ejemplo: CVV incorrecto),</li>
                <li><b>When</b> presiona "Confirmar pago",</li>
                <li><b>Then</b> el sistema rechaza la transacción,</li>
                <li><b>And</b> muestra un mensaje de error específico pero genérico ("Error en los datos de la tarjeta. Verifica e intenta nuevamente"),</li>
                <li><b>And</b> permite al usuario corregir los datos sin perder el progreso.</li>
            </ul>
        </b></td>
    </tr>
</table>

<table align="center">
    <tr>
        <td><b>User Story ID</td>
        <td>US23</td>
        <td><b>Epic ID</td>
        <td>EP04</td>
    </tr>
    <tr>
        <td><b>Título</td>
        <td colspan="3">Guardar múltiples direcciones de envío</td>
    </tr>
    <tr>
        <td><b>Descripción</td>
        <td colspan="3">Como usuario frecuente, quiero guardar múltiples direcciones de envío (casa, trabajo, domicilio de un familiar) en mi perfil, para agilizar el proceso de compra y seleccionar rápidamente la dirección deseada sin tener que escribir los datos cada vez que realizo un pedido.</td>
    </tr>
    <tr>
        <td colspan="4">
            <b>Criterios de aceptación:</b> <br/>
            <ol>
                <li>El sistema debe permitir a los usuarios registrados agregar, editar y eliminar direcciones de envío desde la sección "Mis direcciones" en su perfil.</li>
                <li>Cada dirección debe incluir: nombre de la dirección (ejemplo: "Casa", "Oficina"), destinatario, teléfono de contacto, país, región/estado, ciudad, distrito, código postal, calle y número, referencia adicional (opcional).</li>
                <li>El usuario debe poder marcar una dirección como "Predeterminada" para que aparezca automáticamente en el checkout.</li>
                <li>El sistema debe permitir guardar hasta 10 direcciones por usuario.</li>
                <li>Durante el proceso de pago, el usuario debe poder seleccionar cualquiera de sus direcciones guardadas desde un menú desplegable.</li>
                <li>También debe permitir agregar una dirección nueva y temporal sin guardarla en el perfil (opción "Usar otra dirección").</li>
                <li>El sistema debe validar que los campos obligatorios (destinatario, teléfono, ciudad, dirección) estén completos antes de guardar.</li>
                <li>Las direcciones deben almacenarse de forma segura y sincronizarse entre dispositivos (web y móvil).</li>
                <li>Al eliminar una dirección, el sistema debe mostrar una confirmación ("¿Eliminar esta dirección?") y verificar que no sea la única dirección asociada al usuario (si lo es, debe advertir que debe agregar otra antes de eliminar).</li>
            </ol>
            <b>Escenario 1:</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario accede a la sección "Mis direcciones" en su perfil,</li>
                <li><b>When</b> completa el formulario con los datos de su domicilio (nombre "Casa", destinatario "Juan Pérez", dirección "Av. Siempre Viva 123", ciudad "Lima", código postal "15001") y presiona "Guardar dirección",</li>
                <li><b>Then</b> el sistema valida los campos, guarda la dirección en su lista,</li>
                <li><b>And</b> muestra la nueva dirección junto con las existentes,</li>
                <li><b>And</b> permite marcarla como predeterminada si lo desea.</li>
            </ul>
            <b>Escenario 2:</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario está en el proceso de pago y ya tiene direcciones guardadas,</li>
                <li><b>When</b> selecciona la dirección "Oficina" desde el menú desplegable de direcciones,</li>
                <li><b>Then</b> el sistema autocompleta automáticamente todos los campos de envío con los datos de esa dirección,</li>
                <li><b>And</b> recalcula el costo de envío según la ubicación seleccionada,</li>
                <li><b>And</b> permite al usuario continuar con el pago sin necesidad de escribir nuevamente los datos.</li>
            </ul>
            <b>Escenario 3:</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario tiene al menos una dirección guardada,</li>
                <li><b>When</b> accede a la opción "Eliminar" junto a una dirección que no es la predeterminada,</li>
                <li><b>Then</b> el sistema muestra un mensaje de confirmación,</li>
                <li><b>And</b> al confirmar, elimina la dirección de la lista,</li>
                <li><b>And</b> actualiza la vista sin afectar las demás direcciones.</li>
            </ul>
        </td>
    </tr>
</tr>

<table align="center">
    <tr>
        <td><b>User Story ID</b></td>
        <td>US24</b></td>
        <td><b>Epic ID</b></td>
        <td>EP04</b></td>
    </tr>
    <tr>
        <td><b>Título</b></td>
        <td colspan="3">Historial de pedidos y estado de envío</b></td>
    </tr>
    <tr>
        <td><b>Descripción</b></td>
        <td colspan="3">Como usuario, quiero consultar el historial completo de mis pedidos realizados en SafeStep y ver el estado actual de cada uno (confirmado, en preparación, enviado, entregado), para hacer seguimiento a mis compras y tener un registro de mis transacciones anteriores en caso de necesitar facturación o soporte.</b></td>
    </tr>
    <tr>
        <td colspan="4">
            <b>Criterios de aceptación:</b> <br/>
            <ol>
                <li>El sistema debe incluir una sección "Mis pedidos" accesible desde el perfil del usuario.</li>
                <li>Debe mostrar una lista de todos los pedidos realizados, ordenados del más reciente al más antiguo.</li>
                <li>Cada pedido en la lista debe mostrar: número de pedido, fecha de compra, total pagado, estado actual y un resumen de productos (cantidad y nombre).</li>
                <li>Los estados de pedido deben ser al menos: "Confirmado", "En preparación", "Enviado", "Entregado", "Cancelado".</li>
                <li>El usuario debe poder hacer clic en cualquier pedido para ver los detalles completos: lista de productos con precios, dirección de envío, método de pago, costo de envío, impuestos, y cualquier cupón aplicado.</li>
                <li>Para pedidos en estado "Enviado", el sistema debe mostrar un número de guía de rastreo (tracking) con un enlace a la página del transportista o un mapa de seguimiento.</li>
                <li>El usuario debe poder filtrar pedidos por estado (ejemplo: "Mostrar solo pedidos entregados") y por rango de fechas.</li>
                <li>El sistema debe permitir descargar la factura o comprobante de pago en formato PDF desde los detalles del pedido.</li>
                <li>Si un pedido está en estado "Cancelado" (por decisión del usuario o del sistema), debe mostrarse el motivo y si aplica reembolso.</li>
                <li>El historial debe cargarse de forma paginada (10 pedidos por página) y el tiempo de carga no debe superar los 2 segundos.</li>
            </ol>
            <b>Escenario 1:</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario ha realizado al menos una compra anterior en SafeStep,</li>
                <li><b>When</b> accede a la sección "Mis pedidos" desde su perfil,</li>
                <li><b>Then</b> el sistema muestra una lista con todos sus pedidos ordenados cronológicamente,</li>
                <li><b>And</b> cada pedido muestra su estado actual (ejemplo: "Entregado" o "En camino"),</li>
                <li><b>And</b> el usuario puede hacer clic en "Ver detalles" para ampliar la información.</li>
            </ul>
            <b>Escenario 2:</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario tiene un pedido en estado "Enviado",</li>
                <li><b>When</b> accede a los detalles de ese pedido,</li>
                <li><b>Then</b> el sistema muestra el número de guía y un enlace a la página de rastreo del transportista,</li>
                <li><b>And</b> muestra la última ubicación conocida o el estado actualizado del envío,</li>
                <li><b>And</b> permite al usuario copiar el número de guía con un botón.</li>
            </ul>
            <b>Escenario 3:</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario necesita un comprobante de un pedido anterior,</li>
                <li><b>When</b> accede a los detalles del pedido y presiona "Descargar factura",</li>
                <li><b>Then</b> el sistema genera un archivo PDF con todos los detalles de la compra (productos, precios, impuestos, dirección de envío, método de pago),</li>
                <li><b>And</b> inicia la descarga automática del archivo,</li>
                <li><b>And</b> muestra una confirmación al usuario ("Factura descargada correctamente").</li>
            </ul>
        </td>
    </tr>
</table>

<table align="center">
    <tr>
        <td><b>User Story ID</b></td>
        <td>US25</b></td>
        <td><b>Epic ID</td>
        <td>EP04</b></td>
    </tr>
    <tr>
        <td><b>Título</td>
        <td colspan="3">Cancelar o devolver un pedido</b></td>
    </tr>
    <tr>
        <td><b>Descripción</td>
        <td colspan="3">Como usuario, quiero poder cancelar un pedido antes de que sea enviado o solicitar la devolución de un producto después de recibirlo, para tener flexibilidad en mis compras y garantizar mi satisfacción en caso de arrepentimiento, producto defectuoso o error en el pedido.</b></td>
    </tr>
    <tr>
        <td colspan="4">
            <b>Criterios de aceptación:</b> <br/>
            <ol>
                <li>El sistema debe permitir cancelar un pedido automáticamente si el usuario lo solicita mientras el estado es "Confirmado" o "En preparación" (antes de ser enviado).</li>
                <li>Una vez que el pedido está en estado "Enviado", el usuario no puede cancelarlo automáticamente, pero debe poder solicitar una devolución.</li>
                <li>Para solicitar una devolución, el usuario debe acceder a los detalles del pedido y seleccionar "Solicitar devolución", indicando el motivo (producto defectuoso, producto incorrecto, arrepentimiento, etc.).</li>
                <li>El sistema debe permitir seleccionar uno o varios productos del pedido para la devolución.</li>
                <li>El usuario debe poder adjuntar hasta 3 fotos o videos como evidencia (en caso de productos defectuosos o incorrectos).</li>
                <li>El sistema debe generar un número de solicitud de devolución y notificar al equipo de soporte para su revisión.</li>
                <li>El usuario debe recibir una notificación por correo y dentro de la app sobre el estado de su solicitud (aprobada, rechazada, en revisión).</li>
                <li>Si la devolución es aprobada, el sistema debe generar una guía de devolución (etiqueta de envío) y enviarla al usuario por correo.</li>
                <li>El reembolso debe procesarse según el método de pago original en un plazo máximo de 14 días hábiles después de recibir el producto devuelto.</li>
                <li>El sistema debe mostrar el historial de cancelaciones y devoluciones del usuario en la sección "Mis pedidos".</li>
                <li>El usuario no puede cancelar o devolver productos que tengan más de 30 días desde la fecha de entrega (excepto por garantía especial).</li>
            </ol>
            <b>Escenario 1:</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario tiene un pedido en estado "Confirmado",</li>
                <li><b>When</b> accede a los detalles del pedido y presiona el botón "Cancelar pedido",</li>
                <li><b>Then</b> el sistema muestra un mensaje de confirmación ("¿Estás seguro de que deseas cancelar este pedido?"),</li>
                <li><b>And</b> al confirmar, el sistema cancela el pedido inmediatamente,</li>
                <li><b>And</b> envía un correo de confirmación de cancelación,</li>
                <li><b>And</b> actualiza el estado del pedido a "Cancelado" en el historial.</li>
            </ul>
            <b>Escenario 2:</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario ha recibido un producto defectuoso y el pedido está en estado "Entregado",</li>
                <li><b>When</b> accede a los detalles del pedido, selecciona "Solicitar devolución", elige el producto defectuoso, indica el motivo "Producto defectuoso" y adjunta 2 fotos como evidencia,</li>
                <li><b>Then</b> el sistema genera una solicitud de devolución con número #DEV-12345,</li>
                <li><b>And</b> notifica al equipo de soporte para revisión,</li>
                <li><b>And</b> envía un correo al usuario indicando que su solicitud está siendo procesada.</li>
            </ul>
            <b>Escenario 3:</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario intenta cancelar un pedido que ya está en estado "Enviado",</li>
                <li><b>When</b> accede a los detalles del pedido,</li>
                <li><b>Then</b> el botón "Cancelar pedido" no está disponible o aparece deshabilitado,</li>
                <li><b>And</b> se muestra un mensaje informativo: "Este pedido ya fue enviado. Si deseas devolverlo, utiliza la opción 'Solicitar devolución' una vez lo recibas".</li>
            </ul>
        </b></td>
    </tr>
</tr>

<table align="center">
    <tr>
        <td><b>User Story ID</td>
        <td>US26</td>
        <td><b>Epic ID</td>
        <td>EP04</td>
    </tr>
    <tr>
        <td><b>Título</td>
        <td colspan="3">Cupones de descuento y promociones</td>
    </tr>
    <tr>
        <td><b>Descripción</td>
        <td colspan="3">Como usuario, quiero aplicar cupones de descuento y aprovechar promociones especiales durante el proceso de compra, para obtener beneficios económicos en mis pedidos y sentirme incentivado a seguir comprando en SafeStep.</td>
    </tr>
    <tr>
        <td colspan="4">
            <b>Criterios de aceptación:</b> <br/>
            <ol>
                <li>El sistema debe incluir un campo para ingresar código de cupón en el carrito de compras y en la página de pago.</li>
                <li>Al ingresar un código válido y presionar "Aplicar", el sistema debe calcular el descuento y actualizar el total final inmediatamente.</li>
                <li>Los cupones pueden ser de diferentes tipos: porcentaje de descuento (ejemplo: 10% off), monto fijo (ejemplo: S/20 de descuento), envío gratis, o descuento en productos específicos.</li>
                <li>El sistema debe validar que el cupón esté vigente (fecha de inicio y fin), que no haya excedido su uso máximo, y que aplique al carrito actual (monto mínimo de compra, productos elegibles, etc.).</li>
                <li>Si el cupón no es válido, el sistema debe mostrar un mensaje claro: "Cupón inválido", "Cupón expirado", "No alcanza el monto mínimo", etc.</li>
                <li>El usuario debe poder eliminar un cupón aplicado (con un botón "Quitar" o "Eliminar") y el total debe revertirse al valor original.</li>
                <li>El sistema debe mostrar un resumen de los descuentos aplicados en el carrito (ejemplo: "Descuento por cupón: -S/15").</li>
                <li>Los administradores deben poder crear, editar y deshabilitar cupones desde un panel de gestión.</li>
                <li>Cada cupón debe tener parámetros configurables: código único o genérico, tipo de descuento, valor, fecha de inicio y fin, límite de usos totales, límite por usuario, monto mínimo de compra, productos aplicables (todos o específicos), y usuarios aplicables (todos o segmentos).</li>
                <li>El sistema debe permitir promociones automáticas como "Lleva 2 y paga 1" o "Compra arriba de S/200 y obtén envío gratis" sin necesidad de código.</li>
                <li>El usuario debe poder ver una lista de cupones disponibles en su perfil (por ejemplo, "Cupón de bienvenida", "Cupón por cumpleaños", etc.).</li>
            </ol>
            <b>Escenario 1:</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario tiene un carrito con un subtotal de S/150,</li>
                <li><b>And</b> dispone de un cupón válido "BIENVENIDO10" que otorga 10% de descuento sin monto mínimo,</li>
                <li><b>When</b> ingresa el código "BIENVENIDO10" en el campo de cupón y presiona "Aplicar",</li>
                <li><b>Then</b> el sistema valida el cupón y aplica un descuento de S/15,</li>
                <li><b>And</b> actualiza el total final a S/135,</li>
                <li><b>And</b> muestra el descuento en el resumen ("Descuento: -S/15").</li>
            </ul>
            <b>Escenario 2:</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario ingresa un cupón "ENVIOGRATIS" que solo aplica para compras mayores a S/100,</li>
                <li><b>When</b> su carrito tiene un subtotal de S/80 e intenta aplicar el cupón,</li>
                <li><b>Then</b> el sistema rechaza el cupón,</li>
                <li><b>And</b> muestra un mensaje: "El cupón ENVIOGRATIS requiere una compra mínima de S/100. Agrega S/20 más para obtener envío gratis".</li>
            </ul>
            <b>Escenario 3:</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario ya aplicó un cupón y desea eliminarlo,</li>
                <li><b>When</b> presiona el botón "Quitar cupón" junto al descuento aplicado,</li>
                <li><b>Then</b> el sistema elimina el descuento,</li>
                <li><b>And</b> el total final vuelve al valor original sin cupón,</li>
                <li><b>And</b> el campo de cupón queda vacío y listo para ingresar otro código.</li>
            </ul>
        </td>
    </tr>
</table>

<table align="center">
    <tr>
        <td><b>User Story ID</b></td>
        <td>US27</b></td>
        <td><b>Epic ID</b></td>
        <td>EP04</b></td>
    </tr>
    <tr>
        <td><b>Título</b></td>
        <td colspan="3">Valoraciones y reseñas de productos comprados</b></td>
    </tr>
    <tr>
        <td><b>Descripción</b></td>
        <td colspan="3">Como usuario, quiero calificar y escribir reseñas sobre los productos que he comprado, para compartir mi experiencia con otros miembros de la comunidad SafeStep y ayudarles a tomar mejores decisiones de compra, además de recibir retroalimentación sobre mi propia elección.</b></td>
    </tr>
    <tr>
        <td colspan="4">
            <b>Criterios de aceptación:</b> <br/>
            <ol>
                <li>Solo los usuarios que hayan comprado un producto (pedido en estado "Entregado") pueden calificarlo y escribir una reseña.</li>
                <li>El sistema debe permitir calificar con un sistema de 1 a 5 estrellas (siendo 5 la mejor puntuación).</li>
                <li>La reseña debe incluir: título opcional, texto de comentario (mínimo 10 caracteres, máximo 500), y opción de adjuntar hasta 3 imágenes del producto recibido.</li>
                <li>El usuario puede editar o eliminar su propia reseña dentro de los primeros 30 días después de publicarla.</li>
                <li>Todas las reseñas deben ser moderadas antes de ser publicadas visiblemente (para evitar spam o lenguaje inapropiado), excepto la calificación de estrellas que puede mostrarse de inmediato.</li>
                <li>El sistema debe mostrar el promedio de calificación (promedio de estrellas) y el número total de reseñas en la página de detalle del producto.</li>
                <li>Las reseñas publicadas deben mostrarse ordenadas por "Más recientes" o "Más útiles" (con opción de filtro para el usuario).</li>
                <li>Los usuarios pueden marcar una reseña como "Útil" o "No útil" para ayudar a la comunidad.</li>
                <li>El sistema debe notificar al usuario cuando su reseña haya sido publicada o rechazada (con motivo del rechazo).</li>
                <li>El usuario debe poder ver un historial de todas sus reseñas en su perfil, con acceso directo al producto reseñado.</li>
                <li>Los administradores deben poder eliminar reseñas inapropiadas o falsas.</li>
                <li>Si un producto tiene menos de 3 reseñas, el sistema debe mostrar un mensaje motivador: "Sé el primero en calificar este producto".</li>
            </ol>
            <b>Escenario 1:</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario ha recibido un pedido con el producto "Mochila de emergencia 72h",</li>
                <li><b>When</b> accede a "Mis pedidos", selecciona el pedido entregado y presiona "Calificar producto" junto a la mochila,</li>
                <li><b>Then</b> el sistema muestra un formulario con opción de calificar de 1 a 5 estrellas, un campo para comentario y para subir fotos,</li>
                <li><b>And</b> al enviar, la reseña queda pendiente de moderación,</li>
                <li><b>And</b> la calificación de estrellas se suma inmediatamente al promedio del producto.</li>
            </ul>
            <b>Escenario 2:</b> <br/>
            <ul>
                <li><b>Given</b> que un usuario visita la página de detalle del producto "Botiquín básico",</li>
                <li><b>When</b> desplaza hacia la sección de reseñas,</li>
                <li><b>Then</b> el sistema muestra el promedio de calificación (ejemplo: 4.5 estrellas basado en 23 reseñas),</li>
                <li><b>And</b> lista las reseñas publicadas ordenadas por defecto de más reciente a más antigua,</li>
                <li><b>And</b> cada reseña muestra el nombre del usuario (o seudónimo), la calificación, el comentario y las fotos adjuntas.</li>
            </ul>
            <b>Escenario 3:</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario publicó una reseña que fue rechazada por contener lenguaje inapropiado,</li>
                <li><b>When</b> el administrador revisa y rechaza la reseña,</li>
                <li><b>Then</b> el sistema envía una notificación al usuario por correo y dentro de la app,</li>
                <li><b>And</b> el mensaje indica: "Tu reseña fue rechazada porque contiene lenguaje inapropiado. Por favor, edítala y vuelve a enviarla".</li>
                <li><b>And</b> el usuario puede editar su reseña original y reenviarla para moderación.</li>
            </ul>
        </td>
    </tr>
</table>

<table align="center">
    <tr>
        <td><b>User Story ID</b></td>
        <td>US28</b></td>
        <td><b>Epic ID</td>
        <td>EP04</b></td>
    </tr>
    <tr>
        <td><b>Título</td>
        <td colspan="3">Recomendaciones personalizadas según historial de simulaciones</b></td>
    </tr>
    <tr>
        <td><b>Descripción</td>
        <td colspan="3">Como usuario, quiero recibir recomendaciones de productos basadas en mi historial de simulaciones y áreas de mejora, para adquirir materiales que complementen mi aprendizaje práctico y me ayuden a estar mejor preparado ante emergencias reales según los escenarios que he practicado.</b></td>
    </tr>
    <tr>
        <td colspan="4">
            <b>Criterios de aceptación:</b> <br/>
            <ol>
                <li>El sistema debe analizar automáticamente el historial de simulaciones completadas por el usuario, identificando los tipos de emergencias practicadas (RCP, atragantamiento, quemaduras, hemorragias, sismos, etc.).</li>
                <li>Basado en ese análisis, debe generar una lista de productos recomendados que sean útiles para esas emergencias específicas (ejemplo: si practicó RCP, recomendar un maniquí de práctica o un DEA; si practicó hemorragias, recomendar torniquetes y gasas hemostáticas).</li>
                <li>Las recomendaciones deben mostrarse en una sección llamada "Para ti" o "Basado en tu práctica" dentro de la tienda y también en el dashboard principal del usuario.</li>
                <li>Si el usuario tuvo bajo desempeño en un escenario específico (ejemplo: errores en maniobra de Heimlich), el sistema debe recomendar productos relacionados con ese tema (ejemplo: cartel instructivo de primeros auxilios para atragantamiento o un maniquí de práctica).</li>
                <li>Las recomendaciones deben actualizarse dinámicamente cada vez que el usuario complete una nueva simulación o mejore su puntuación.</li>
                <li>El sistema debe mostrar un máximo de 6 productos recomendados por categoría, con opción de "Ver más".</li>
                <li>Cada recomendación debe incluir un breve mensaje explicativo (ejemplo: "Practicaste RCP - Te recomendamos este kit de entrenamiento").</li>
                <li>El usuario debe poder descartar una recomendación si no le interesa, y el sistema debe aprender de esa acción para futuras sugerencias.</li>
                <li>La sección de recomendaciones debe cargarse en menos de 2 segundos y ser responsiva para móvil y escritorio.</li>
                <li>Si el usuario no tiene suficiente historial de simulaciones, el sistema debe mostrar recomendaciones genéricas basadas en popularidad o temporada.</li>
            </ol>
            <b>Escenario 1:</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario ha completado 3 simulaciones de "Hemorragias" y 2 de "RCP básico",</li>
                <li><b>When</b> accede a la sección "Tienda" o al dashboard principal,</li>
                <li><b>Then</b> el sistema muestra una sección "Basado en tu práctica" con productos recomendados,</li>
                <li><b>And</b> entre ellos aparecen: "Torniquete táctico", "Gasa hemostática" y "Maniquí de RCP portátil",</li>
                <li><b>And</b> cada producto incluye un mensaje como "Por tus prácticas en hemorragias" o "Para reforzar tu entrenamiento en RCP".</li>
            </ul>
            <b>Escenario 2:</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario obtuvo una puntuación baja en la simulación de "Atragantamiento en bebés",</li>
                <li><b>When</b> el sistema analiza su desempeño y detecta errores específicos,</li>
                <li><b>Then</b> genera una recomendación personalizada como "Maniquí infantil para práctica de Heimlich" o "Guía visual de primeros auxilios para bebés",</li>
                <li><b>And</b> muestra un mensaje: "Mejora tu técnica en atragantamiento infantil con este material de práctica".</li>
            </ul>
            <b>Escenario 3:</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario ha descartado una recomendación de producto en dos ocasiones,</li>
                <li><b>When</b> el sistema genera nuevas recomendaciones,</li>
                <li><b>Then</b> no debe volver a sugerir ese mismo producto a menos que el usuario cambie su comportamiento o el producto sea parte de una promoción especial,</li>
                <li><b>And</b> debe priorizar otros productos relacionados con el mismo tema o temas diferentes.</li>
            </ul>
        </b></td>
    </tr>
</table>

<table align="center">
    <tr>
        <td><b>User Story ID</td>
        <td>US29</td>
        <td><b>Epic ID</td>
        <td>EP04</td>
    </tr>
    <tr>
        <td><b>Título</td>
        <td colspan="3">Kits de emergencia pre-armados (por tipo de riesgo: sismo, incendio, RCP)</td>
    </tr>
    <tr>
        <td><b>Descripción</td>
        <td colspan="3">Como usuario, quiero comprar kits de emergencia pre-armados según el tipo de riesgo (sismo, incendio, RCP, accidentes domésticos, etc.), para adquirir de forma rápida y sencilla todos los materiales necesarios para una preparación completa sin tener que seleccionar producto por producto.</td>
    </tr>
    <tr>
        <td colspan="4">
            <b>Criterios de aceptación:</b> <br/>
            <ol>
                <li>El sistema debe ofrecer al menos 4 tipos de kits pre-armados: "Kit para sismos", "Kit para incendios", "Kit para RCP y paros cardíacos", "Kit básico de primeros auxilios para hogar".</li>
                <li>Cada kit debe mostrar una lista detallada de los productos incluidos, con imágenes, cantidades y especificaciones.</li>
                <li>El precio del kit debe ser menor a la suma de los productos individuales (descuento por paquete del 10% al 20%).</li>
                <li>El usuario debe poder ver el ahorro total al comprar el kit en lugar de los productos por separado.</li>
                <li>Cada kit debe tener una descripción clara de para qué tipo de emergencia está diseñado y qué nivel de preparación ofrece (básico, intermedio, avanzado).</li>
                <li>El sistema debe permitir al usuario personalizar el kit: agregar o quitar productos de la lista base, manteniendo el descuento proporcional.</li>
                <li>Los kits deben tener un stock independiente o calcularse según el stock de los productos individuales (si un producto está agotado, el kit muestra "Disponibilidad limitada" o se actualiza automáticamente).</li>
                <li>En la página de detalle del kit, el sistema debe mostrar productos relacionados o complementarios (ejemplo: "Agrega una linterna recargable a tu kit de sismo").</li>
                <li>El usuario debe poder guardar kits como favoritos para comprarlos después.</li>
                <li>Los kits deben tener imágenes atractivas que muestren todos los productos juntos (foto grupal) y un video explicativo opcional del contenido.</li>
                <li>El sistema debe recomendar kits según la ubicación geográfica del usuario (ejemplo: zonas sísmicas → kit para sismos, zonas con riesgo de incendios forestales → kit para incendios).</li>
                <li>El usuario debe poder comparar hasta 3 kits lado a lado (tabla comparativa de contenidos y precios).</li>
            </ol>
            <b>Escenario 1:</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario vive en una zona de alta actividad sísmica,</li>
                <li><b>When</b> accede a la sección "Kits de emergencia" en la tienda,</li>
                <li><b>Then</b> el sistema destaca el "Kit para sismos" como recomendación principal,</li>
                <li><b>And</b> muestra el contenido del kit: mochila de emergencia, botiquín, linterna, radio portátil, agua purificada, alimentos no perecibles, silbato, manta térmica, etc.,</li>
                <li><b>And</b> el precio del kit es S/249, mostrando que comprando por separado costaría S/310 (ahorro de S/61).</li>
            </ul>
            <b>Escenario 2:</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario está viendo el "Kit básico de primeros auxilios para hogar",</li>
                <li><b>When</b> selecciona la opción "Personalizar kit",</li>
                <li><b>Then</b> el sistema muestra la lista de productos incluidos con casillas de verificación para quitar productos y botones "+" para agregar productos adicionales,</li>
                <li><b>And</b> actualiza el precio en tiempo real según las modificaciones,</li>
                <li><b>And</b> mantiene el descuento porcentual sobre los productos finales seleccionados.</li>
            </ul>
            <b>Escenario 3:</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario quiere decidir entre dos kits diferentes,</li>
                <li><b>When</b> selecciona "Comparar" en el "Kit para RCP" y el "Kit avanzado de primeros auxilios",</li>
                <li><b>Then</b> el sistema abre una vista comparativa mostrando lado a lado: precio, número de productos, lista de contenidos y especificaciones,</li>
                <li><b>And</b> permite al usuario agregar cualquiera de los dos al carrito directamente desde la comparación.</li>
            </ul>
        </td>
    </tr>
</table>

<table align="center">
    <tr>
        <td><b>User Story ID</b></td>
        <td>US30</b></td>
        <td><b>Epic ID</b></td>
        <td>EP04</b></td>
    </tr>
    <tr>
        <td><b>Título</b></td>
        <td colspan="3">Notificaciones de ofertas y stock bajo</b></td>
    </tr>
    <tr>
        <td><b>Descripción</b></td>
        <td colspan="3">Como usuario, quiero recibir notificaciones push y por correo electrónico sobre ofertas especiales, descuentos por tiempo limitado y productos con stock bajo que sean de mi interés, para aprovechar oportunidades de compra y no quedarme sin productos importantes para mi preparación en emergencias.</b></td>
    </tr>
    <tr>
        <td colspan="4">
            <b>Criterios de aceptación:</b> <br/>
            <ol>
                <li>El sistema debe permitir al usuario activar o desactivar las notificaciones de ofertas y stock bajo desde el panel de configuración de la app (opciones separadas para "Ofertas" y "Stock bajo").</li>
                <li>El usuario debe poder elegir el canal de notificación: push (app móvil), correo electrónico, o ambos.</li>
                <li>Cuando un producto que el usuario ha marcado como "favorito" o "interesado" entra en oferta (descuento ≥15%), el sistema debe enviar una notificación automática.</li>
                <li>Cuando el stock de un producto favorito baja de 5 unidades, el sistema debe enviar una alerta de "Stock bajo - ¡Últimas unidades!".</li>
                <li>El sistema debe enviar notificaciones masivas sobre ofertas generales (Cyber Monday, Black Friday, aniversario de SafeStep) solo a usuarios que tengan activada la opción de "Ofertas".</li>
                <li>Las notificaciones deben incluir: nombre del producto, precio original, precio con descuento (si aplica), stock restante (si aplica) y un enlace directo a la página del producto.</li>
                <li>El usuario debe poder hacer clic en la notificación y ser redirigido automáticamente a la página del producto o a la sección de ofertas.</li>
                <li>El sistema no debe enviar más de 3 notificaciones por día al mismo usuario para evitar saturación.</li>
                <li>El usuario debe poder ver un historial de notificaciones recibidas dentro de la app en una sección "Mis alertas".</li>
                <li>Si el usuario ha estado inactivo por más de 30 días, el sistema debe pausar las notificaciones automáticamente (requiriendo re-confirmación).</li>
                <li>Las notificaciones de stock bajo deben cesar una vez que el producto se agota o el usuario lo compra.</li>
                <li>El sistema debe permitir al usuario silenciar notificaciones por un período específico (1 día, 1 semana, 1 mes).</li>
            </ol>
            <b>Escenario 1:</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario ha marcado como favorito el producto "Mochila de emergencia 72h",</li>
                <li><b>And</b> tiene activadas las notificaciones de ofertas,</li>
                <li><b>When</b> el administrador aplica un descuento del 20% a ese producto por tiempo limitado,</li>
                <li><b>Then</b> el sistema envía una notificación push al dispositivo del usuario,</li>
                <li><b>And</b> el mensaje dice: "¡Oferta! Mochila de emergencia 72h con 20% de descuento. S/240 → S/192. ¡Aprovecha esta oferta por tiempo limitado!",</li>
                <li><b>And</b> al hacer clic, el usuario es redirigido a la página del producto.</li>
            </ul>
            <b>Escenario 2:</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario tiene activadas las notificaciones de stock bajo para sus productos favoritos,</li>
                <li><b>And</b> el producto "Torniquete táctico" tiene un stock de 4 unidades,</li>
                <li><b>When</b> el sistema detecta que el stock bajó a 4 (umbral configurado en 5),</li>
                <li><b>Then</b> envía una alerta: "¡Stock bajo! Torniquete táctico - Solo quedan 4 unidades. ¡Compra ahora antes de que se agoten!",</li>
                <li><b>And</b> no vuelve a enviar otra notificación por el mismo producto a menos que el stock baje a 2 o 1 unidad después de un tiempo.</li>
            </ul>
            <b>Escenario 3:</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario recibe notificaciones pero considera que son demasiado frecuentes,</li>
                <li><b>When</b> accede a "Configuración → Notificaciones" y selecciona "Silenciar por 7 días",</li>
                <li><b>Then</b> el sistema pausa el envío de cualquier notificación de ofertas y stock bajo durante 7 días,</li>
                <li><b>And</b> muestra un mensaje de confirmación: "Las notificaciones estarán silenciadas hasta el [fecha]",</li>
                <li><b>And</b> al finalizar el período, las notificaciones se reactivan automáticamente.</li>
            </ul>
        </td>
    </tr>
</table>

<table align="center">
    <tr>
        <td><b>User Story ID</b></td>
        <td>US31</b></td>
        <td><b>Epic ID</b></td>
        <td>EP05</b></td>
    </tr>
    <tr>
        <td><b>Título</b></td>
        <td colspan="3">Sistema de puntos y experiencia (XP)</b></td>
    </tr>
    <tr>
        <td><b>Descripción</b></td>
        <td colspan="3">Como usuario, quiero ganar puntos de experiencia (XP) por cada actividad que realizo en SafeStep (simulaciones, micro-lecciones, evaluaciones, participación comunitaria), para ver mi progreso reflejado numéricamente, subir de nivel y sentirme motivado a seguir aprendiendo y practicando primeros auxilios.</b></td>
    </tr>
    <tr>
        <td colspan="4">
            <b>Criterios de aceptación:</b> <br/>
            <ol>
                <li>El sistema debe asignar puntos de experiencia (XP) por cada acción completada, con valores diferenciados según el tipo y dificultad: simulación básica (50 XP), simulación avanzada (100 XP), micro-lección (20 XP), evaluación final aprobada (200 XP), participar en foro (10 XP), completar evento comunitario (150 XP).</li>
                <li>El sistema debe mostrar un contador de XP total acumulado en el dashboard, junto con el nivel actual del usuario.</li>
                <li>Cada vez que el usuario gana XP, debe mostrarse una notificación emergente no intrusiva (ejemplo: "+50 XP por completar RCP Básico") con una animación de número flotante.</li>
                <li>El sistema debe definir una tabla de niveles (ejemplo: Nivel 1: 0 XP, Nivel 2: 500 XP, Nivel 3: 1200 XP, etc., hasta Nivel 50 o más), calculando automáticamente el progreso hacia el siguiente nivel con una barra de progreso visual.</li>
                <li>El usuario debe poder ver un desglose de XP ganados por categoría (simulaciones, aprendizaje, comunidad) en la sección "Mi progreso / Gamificación".</li>
                <li>El sistema debe otorgar XP bonus por rachas: +10 XP por día adicional de racha (acumulativo hasta un máximo de +100 XP diarios después de 10 días).</li>
                <li>Los XP deben registrarse en tiempo real y sincronizarse entre dispositivos, sin pérdida de datos por problemas de conexión (sincronización offline al reconectar).</li>
                <li>El sistema debe evitar que el usuario pueda "farmear" XP repitiendo la misma simulación fácil, estableciendo un límite de XP por simulación (ejemplo: la primera vez otorga XP completo, las repeticiones otorgan 50% menos, y después de 5 repeticiones ya no otorgan XP).</li>
                <li>El sistema debe mostrar una tabla de líderes (Leaderboard) semanal y general basada en XP acumulado, con opción de filtrar por amigos, comunidad o global.</li>
                <li>El usuario debe poder compartir su nivel y XP en redes sociales con un mensaje predefinido: "¡Acabo de alcanzar el nivel X en SafeStep! Aprende primeros auxilios conmigo".</li>
            </ol>
            <b>Escenario 1 (Ganar XP por completar simulación):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario "Juan" tiene 320 XP acumulados (Nivel 1, próximo nivel en 500 XP),</li>
                <li><b>When</b> completa exitosamente la simulación "RCP Básico" por primera vez,</li>
                <li><b>Then</b> el sistema otorga 100 XP,</li>
                <li><b>And</b> muestra una notificación: "+100 XP por completar RCP Básico",</li>
                <li><b>And</b> el contador de XP se actualiza a 420 XP,</li>
                <li><b>And</b> la barra de progreso hacia el Nivel 2 avanza del 64% al 84% (faltan 80 XP).</li>
            </ul>
            <b>Escenario 2 (Subir de nivel - celebración y recompensa):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario tiene 480 XP (faltan 20 XP para Nivel 2),</li>
                <li><b>When</b> completa una micro-lección que otorga 20 XP, alcanzando 500 XP,</li>
                <li><b>Then</b> el sistema muestra una animación de celebración en pantalla completa: "¡FELICIDADES! Has alcanzado el Nivel 2",</li>
                <li><b>And</b> reproduce un sonido de logro,</li>
                <li><b>And</b> otorga una recompensa adicional: 50 XP bonus y un descuento del 5% en la tienda (EP04),</li>
                <li><b>And</b> desbloquea una insignia especial "Aprendiz constante",</li>
                <li><b>And</b> muestra el nuevo nivel y la barra de progreso hacia el Nivel 3 (requiere 1200 XP).</li>
            </ul>
            <b>Escenario 3 (Desglose de XP por categoría):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario ha completado múltiples actividades durante el mes,</li>
                <li><b>When</b> accede a la sección "Mi progreso / Gamificación" y selecciona "Desglose de XP",</li>
                <li><b>Then</b> el sistema muestra un gráfico circular con: "Simulaciones: 1200 XP (60%)", "Micro-lecciones: 400 XP (20%)", "Evaluaciones: 300 XP (15%)", "Participación comunitaria: 100 XP (5%)",</li>
                <li><b>And</b> una tabla detallada con cada actividad, fecha y XP otorgado,</li>
                <li><b>And</b> permite filtrar por período (semanal, mensual, total).</li>
            </ul>
            <b>Escenario 4 (Límite de XP por repetición - evitar farmeo):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario completa la simulación "Quemaduras Básico" por primera vez y gana 50 XP,</li>
                <li><b>When</b> repite la misma simulación por segunda vez,</li>
                <li><b>Then</b> el sistema otorga 25 XP (50% del original),</li>
                <li><b>And</b> muestra un mensaje: "+25 XP por repaso (la primera vez otorga XP completo)",</li>
                <li><b>When</b> repite la simulación por sexta vez (después de 5 repeticiones),</li>
                <li><b>Then</b> el sistema no otorga XP, mostrando: "Ya no ganas XP por esta simulación. ¡Prueba nuevos escenarios para seguir ganando XP!",</li>
                <li><b>And</b> el contador de XP no se modifica.</li>
            </ul>
            <b>Escenario 5 (Tabla de líderes - Leaderboard semanal):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario accede a la sección "Ranking" desde el menú de gamificación,</li>
                <li><b>When</b> selecciona "Leaderboard Semanal - Amigos",</li>
                <li><b>Then</b> el sistema muestra una lista de hasta 20 amigos del usuario ordenados por XP ganados en la semana actual,</li>
                <li><b>And</b> resalta la posición del usuario (ejemplo: "3° lugar - 450 XP esta semana"),</li>
                <li><b>And</b> muestra un botón "Ver ranking global" que muestra a todos los usuarios de la comunidad,</li>
                <li><b>And</b> si el usuario está entre los 10 primeros del ranking global al final de la semana, recibe una insignia especial "Top 10 semanal" y XP bonus.</li>
            </ul>
        </b></td>
    </tr>
</table>

<table align="center">
    <tr>
        <td><b>User Story ID</b></td>
        <td>US32</b></td>
        <td><b>Epic ID</b></td>
        <td>EP05</b></td>
    </tr>
    <tr>
        <td><b>Título</b></td>
        <td colspan="3">Insignias y logros</b></td>
    </tr>
    <tr>
        <td><b>Descripción</b></td>
        <td colspan="3">Como usuario, quiero desbloquear insignias y logros al alcanzar hitos específicos en mi aprendizaje (completar módulos, mantener rachas, obtener altas calificaciones, participar en eventos), para sentirme reconocido por mis logros, coleccionar trofeos virtuales y compartir mis avances con la comunidad.</b></td>
    </tr>
    <tr>
        <td colspan="4">
            <b>Criterios de aceptación:</b> <br/>
            <ol>
                <li>El sistema debe definir un catálogo de insignias clasificadas por categorías: "Aprendizaje" (completar módulos), "Constancia" (rachas), "Excelencia" (calificaciones altas), "Comunidad" (participación), "Especiales" (eventos limitados).</li>
                <li>Cada insignia debe tener: nombre único, descripción del requisito para desbloquearla, icono o imagen representativa, rareza (común, rara, épica, legendaria) y fecha de obtención.</li>
                <li>El sistema debe mostrar una "Vitrina de insignias" en el perfil del usuario, organizada visualmente (ejemplo: cuadrícula de iconos) con insignias desbloqueadas en color y bloqueadas en gris/oscuro.</li>
                <li>Al desbloquear una insignia, el sistema debe mostrar una animación de celebración (efecto de confeti, sonido de logro) y una notificación destacada: "¡Nueva insignia desbloqueada: [Nombre]!", con opción de compartir automáticamente en redes sociales.</li>
                <li>El sistema debe notificar al usuario cuando está cerca de desbloquear una insignia (ejemplo: "¡Estás a solo 2 días de racha para desbloquear la insignia 'Constancia Semanal'!").</li>
                <li>Las insignias deben ser acumulativas y visibles para otros usuarios en el perfil público, con opción de privacidad (mostrar/ocultar vitrina).</li>
                <li>El sistema debe permitir a los usuarios "fijar" hasta 3 insignias destacadas en su perfil público para mostrar sus mayores logros.</li>
                <li>Las insignias de eventos especiales (ejemplo: "Semana de la RCP", "Día Mundial de los Primeros Auxilios") deben estar disponibles solo durante períodos limitados, incentivando la participación oportuna.</li>
                <li>El sistema debe otorgar XP bonus adicional al desbloquear insignias (ejemplo: insignia común: +50 XP, rara: +100 XP, épica: +250 XP, legendaria: +500 XP).</li>
                <li>El usuario debe poder ver una lista de todas las insignias disponibles (incluso las no desbloqueadas) con sus requisitos, para saber qué debe hacer para obtenerlas.</li>
            </ol>
            <b>Escenario 1 (Desbloqueo de insignia por completar módulo):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario "María" ha completado todas las simulaciones del módulo "RCP Básico" y aprobado la evaluación final con 85%,</li>
                <li><b>When</b> el sistema procesa la finalización del módulo,</li>
                <li><b>Then</b> detecta que cumple los requisitos para la insignia "Socorrista en RCP" (rareza común),</li>
                <li><b>And</b> muestra una animación de confeti en pantalla con el mensaje: "¡Nueva insignia desbloqueada: Socorrista en RCP!",</li>
                <li><b>And</b> la insignia aparece en color en su vitrina de insignias,</li>
                <li><b>And</b> otorga 50 XP bonus,</li>
                <li><b>And</b> pregunta si desea compartir el logro en redes sociales.</li>
            </ul>
            <b>Escenario 2 (Insignia de racha - constancia):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario ha practicado en SafeStep durante 7 días consecutivos (sin falta),</li>
                <li><b>When</b> completa una actividad en el séptimo día,</li>
                <li><b>Then</b> el sistema desbloquea la insignia "Constancia Semanal" (rareza común),</li>
                <li><b>And</b> al alcanzar 30 días consecutivos, desbloquea la insignia "Constancia Mensual" (rareza rara),</li>
                <li><b>And</b> al alcanzar 100 días consecutivos, desbloquea la insignia "Leyenda de la Constancia" (rareza legendaria),</li>
                <li><b>And</b> cada una otorga XP bonus progresivo (50, 150, 500 XP respectivamente).</li>
            </ul>
            <b>Escenario 3 (Insignia de excelencia - calificación perfecta):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario "Carlos" completa la evaluación final del módulo "Hemorragias" obteniendo un 100% de respuestas correctas,</li>
                <li><b>When</b> el sistema registra el resultado,</li>
                <li><b>Then</b> desbloquea la insignia "Maestro en Hemorragias" (rareza rara),</li>
                <li><b>And</b> muestra un mensaje especial: "¡Perfecto! Obtuviste el 100%. Eres un Maestro en Hemorragias",</li>
                <li><b>And</b> otorga 150 XP bonus y un descuento del 10% en productos relacionados en la tienda,</li>
                <li><b>And</b> la insignia aparece con un borde dorado para denotar su rareza.</li>
            </ul>
            <b>Escenario 4 (Vitrina de insignias - visualización y filtros):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario accede a su perfil público,</li>
                <li><b>When</b> selecciona la pestaña "Insignias",</li>
                <li><b>Then</b> el sistema muestra una cuadrícula con todas las insignias que ha desbloqueado (en color) y las que le faltan (en gris, con el requisito escrito al hacer hover o clic),</li>
                <li><b>And</b> permite filtrar por categoría: "Todas", "Aprendizaje", "Constancia", "Excelencia", "Comunidad", "Especiales",</li>
                <li><b>And</b> muestra un contador: "12/50 insignias desbloqueadas".</li>
            </ul>
            <b>Escenario 5 (Insignia de evento especial - tiempo limitado):</b> <br/>
            <ul>
                <li><b>Given</b> que SafeStep organiza la "Semana de la RCP" del 1 al 7 de junio,</li>
                <li><b>When</b> el usuario completa al menos 3 simulaciones de RCP durante esa semana,</li>
                <li><b>Then</b> el sistema desbloquea la insignia especial "Campeón de la RCP 2025" (rareza épica),</li>
                <li><b>And</b> esta insignia solo está disponible durante ese período, volviéndose "no obtenible" después del 7 de junio,</li>
                <li><b>And</b> los usuarios que no participaron ven la insignia en gris con el texto: "Disponible solo durante la Semana de la RCP 2025",</li>
                <li><b>And</b> otorga 250 XP bonus por ser un evento especial.</li>
            </ul>
        </b></td>
    </tr>
</table>

<table align="center">
    <tr>
        <td><b>User Story ID</b></td>
        <td>US33</b></td>
        <td><b>Epic ID</b></td>
        <td>EP05</b></td>
    </tr>
    <tr>
        <td><b>Título</b></td>
        <td colspan="3">Rachas de práctica (Streaks)</b></td>
    </tr>
    <tr>
        <td><b>Descripción</b></td>
        <td colspan="3">Como usuario, quiero mantener una racha de práctica diaria (streak) en SafeStep, para desarrollar el hábito de aprender primeros auxilios de manera constante, recibir recompensas por mi consistencia y sentirme motivado a no romper mi cadena de días consecutivos de aprendizaje.</b></td>
    </tr>
    <tr>
        <td colspan="4">
            <b>Criterios de aceptación:</b> <br/>
            <ol>
                <li>El sistema debe registrar automáticamente la actividad diaria del usuario (completar cualquier simulación, micro-lección, evaluación o participar en comunidad) y contar un día de racha por cada día calendario con al menos una actividad completada.</li>
                <li>El contador de racha debe mostrarse prominentemente en el dashboard, con un ícono de fuego o llama, el número de días consecutivos y un mensaje motivacional (ejemplo: "🔥 7 días de racha. ¡Sigue así!").</li>
                <li>El sistema debe otorgar XP bonus diarios por mantener la racha: Día 1-3: +5 XP, Día 4-7: +10 XP, Día 8-14: +15 XP, Día 15-30: +20 XP, Día 30+: +25 XP.</li>
                <li>Si el usuario completa actividades en diferentes horarios pero dentro del mismo día calendario (00:00 a 23:59), solo cuenta como un día de racha (no se acumulan múltiples por día).</li>
                <li>El sistema debe permitir al usuario usar un "Escudo de racha" (item consumible obtenible por logros o compra en tienda) para proteger su racha en caso de un día de inactividad, manteniendo el contador sin reiniciarse.</li>
                <li>Si el usuario pierde un día sin actividad y no tiene escudo de racha, el contador se reinicia a 0, mostrando un mensaje: "Tu racha de X días terminó. ¡Comienza una nueva racha hoy!", pero sin penalizar XP ni niveles.</li>
                <li>El sistema debe mostrar un calendario visual de racha en la sección "Mi progreso", marcando los días con actividad (verde) e inactividad (gris), permitiendo al usuario ver su historial.</li>
                <li>El sistema debe enviar notificaciones recordatorio opcionales: "¡No rompas tu racha! Completa una actividad hoy para mantener tus X días consecutivos".</li>
                <li>Al alcanzar hitos de racha (7, 14, 30, 60, 100, 365 días), el sistema debe desbloquear insignias especiales y otorgar XP bonus significativos.</li>
                <li>El usuario debe poder compartir su racha actual en redes sociales con un mensaje automático: "¡Llevo X días seguidos aprendiendo primeros auxilios en SafeStep! Únete a mí".</li>
            </ol>
            <b>Escenario 1 (Inicio y mantenimiento de racha):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario "Ana" completa una micro-lección el lunes,</li>
                <li><b>Then</b> el sistema registra el día 1 de racha, mostrando "🔥 1 día",</li>
                <li><b>When</b> completa una simulación el martes,</li>
                <li><b>Then</b> la racha aumenta a 2 días, mostrando "🔥 2 días",</li>
                <li><b>And</b> otorga +5 XP bonus por mantener la racha,</li>
                <li><b>When</b> continúa hasta el séptimo día consecutivo,</li>
                <li><b>Then</b> al alcanzar el día 7, desbloquea la insignia "Racha Semanal" y otorga +50 XP bonus adicional.</li>
            </ul>
            <b>Escenario 2 (Pérdida de racha por inactividad):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario tenía una racha de 15 días,</li>
                <li><b>When</b> no realiza ninguna actividad durante el día 16,</li>
                <li><b>Then</b> al día siguiente (día 17), el sistema detecta la inactividad del día anterior,</li>
                <li><b>And</b> muestra un mensaje en el dashboard: "¡Oh no! Tu racha de 15 días terminó. ¡Comienza una nueva racha hoy!",</li>
                <li><b>And</b> el contador se reinicia a 0,</li>
                <li><b>And</b> el usuario conserva todas sus insignias y XP previamente ganados (no hay penalización).</li>
            </ul>
            <b>Escenario 3 (Uso de escudo de racha):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario tiene una racha de 30 días y posee un "Escudo de racha" en su inventario (ganado por un logro previo),</li>
                <li><b>When</b> no puede practicar durante un día por motivos personales,</li>
                <li><b>Then</b> al día siguiente, el sistema detecta la inactividad pero automáticamente consume un escudo de racha,</li>
                <li><b>And</b> muestra un mensaje: "Tu racha está protegida. Has usado 1 Escudo de racha. Tu racha continúa en 31 días",</li>
                <li><b>And</b> el contador no se reinicia,</li>
                <li><b>And</b> el usuario recibe una notificación: "Se ha consumido un escudo. Puedes obtener más escudos completando logros o en la tienda".</li>
            </ul>
            <b>Escenario 4 (Calendario visual de racha):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario accede a la sección "Mi progreso / Racha",</li>
                <li><b>When</b> selecciona la vista "Calendario mensual",</li>
                <li><b>Then</b> el sistema muestra un calendario donde cada día tiene un color: verde (actividad completada), gris (sin actividad), dorado (día con racha protegida por escudo),</li>
                <li><b>And</b> al hacer clic en un día verde, muestra las actividades realizadas ese día y el XP ganado,</li>
                <li><b>And</b> permite navegar a meses anteriores para ver el historial completo.</li>
            </ul>
            <b>Escenario 5 (Notificaciones recordatorio de racha):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario tiene activadas las notificaciones push y tiene una racha activa de 10 días,</li>
                <li><b>When</b> son las 8:00 PM y el usuario aún no ha completado ninguna actividad en el día actual,</li>
                <li><b>Then</b> el sistema envía una notificación push: "⏰ ¡No rompas tu racha de 10 días! Completa una actividad hoy para mantener tu progreso",</li>
                <li><b>And</b> al hacer clic en la notificación, la aplicación abre el dashboard mostrando las actividades recomendadas,</li>
                <li><b>And</b> si el usuario ignora la notificación y no completa actividad, al día siguiente se muestra el mensaje de racha perdida.</li>
            </ul>
        </b></td>
    </tr>
</table>

<table align="center">
    <tr>
        <td><b>User Story ID</b></td>
        <td>US34</b></td>
        <td><b>Epic ID</b></td>
        <td>EP05</b></td>
    </tr>
    <tr>
        <td><b>Título</b></td>
        <td colspan="3">Tabla de líderes (Leaderboard)</b></td>
    </tr>
    <tr>
        <td><b>Descripción</b></td>
        <td colspan="3">Como usuario, quiero ver una tabla de líderes que compare mi progreso (XP, nivel, racha, logros) con el de mis amigos y con la comunidad global de SafeStep, para fomentar una competencia saludable, motivarme a mejorar mis hábitos de aprendizaje y celebrar los logros de otros usuarios.</b></td>
    </tr>
    <tr>
        <td colspan="4">
            <b>Criterios de aceptación:</b> <br/>
            <ol>
                <li>El sistema debe incluir una sección "Ranking" accesible desde el menú principal o desde la sección de gamificación.</li>
                <li>La tabla de líderes debe ofrecer múltiples vistas: "Amigos" (solo usuarios que el usuario sigue o tiene como amigos), "Comunidad" (todos los usuarios de la misma ciudad o país, configurable), y "Global" (todos los usuarios de SafeStep).</li>
                <li>El sistema debe permitir filtrar el ranking por diferentes métricas: XP total (general), XP ganado en la semana, racha más larga, número de insignias desbloqueadas, o nivel alcanzado.</li>
                <li>Cada entrada en la tabla debe mostrar: posición (1°, 2°, 3°...), nombre de usuario (o nombre real según privacidad), avatar, nivel, XP total (o métrica seleccionada), y un indicador visual de tendencia (↑ subiendo, ↓ bajando, → estable respecto a la semana anterior).</li>
                <li>El sistema debe resaltar la posición del usuario actual con un color de fondo diferente o un ícono especial, mostrando su rango exacto y cuántos puntos necesita para superar al siguiente usuario.</li>
                <li>La tabla debe actualizarse diariamente (o en tiempo real, según carga del sistema), mostrando la fecha y hora de la última actualización.</li>
                <li>El sistema debe otorgar recompensas semanales a los mejores clasificados en diferentes categorías: Top 1-3, Top 10, Top 100, etc. (ejemplo: insignias especiales, XP bonus, descuentos en tienda).</li>
                <li>El usuario debe poder "dar like" o "felicitar" a otros usuarios desde la tabla de líderes, enviándoles una notificación de reconocimiento.</li>
                <li>El sistema debe incluir una sección "Mi progreso en el ranking" que muestre la evolución del usuario en el tiempo (gráfico de línea con su posición semana a semana).</li>
                <li>La tabla debe ser responsiva, mostrando menos columnas en móvil (solo posición, nombre y XP) y más detalles en escritorio.</li>
            </ol>
            <b>Escenario 1 (Ver ranking de amigos - XP semanal):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario "Carlos" tiene 5 amigos en SafeStep,</li>
                <li><b>When</b> accede a "Ranking / Amigos" y selecciona la métrica "XP esta semana",</li>
                <li><b>Then</b> el sistema muestra una lista ordenada de sus amigos según XP ganado en los últimos 7 días,</li>
                <li><b>And</b> Carlos ve que está en 2° lugar con 450 XP, detrás de "Ana" con 520 XP,</li>
                <li><b>And</b> se muestra un mensaje: "Te faltan 70 XP para superar a Ana. ¡Completa una simulación avanzada para ganar 100 XP!",</li>
                <li><b>And</b> Carlos puede hacer clic en el perfil de Ana para ver sus logros.</li>
            </ul>
            <b>Escenario 2 (Ranking global - posición destacada):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario "María" tiene 3500 XP y está en el nivel 8,</li>
                <li><b>When</b> accede a "Ranking / Global / XP total",</li>
                <li><b>Then</b> el sistema muestra una tabla paginada con los primeros 100 usuarios de SafeStep,</li>
                <li><b>And</b> María se encuentra en la posición #234, pero la tabla muestra un botón "Ir a mi posición" que la lleva directamente al lugar donde está su nombre,</li>
                <li><b>And</b> su fila se resalta en azul claro, mostrando que está en la posición 234,</li>
                <li><b>And</b> se muestra un mensaje: "¡Estás en el top 12% de usuarios! Sigue así para alcanzar el top 10%".</li>
            </ul>
            <b>Escenario 3 (Recompensas semanales para top clasificados):</b> <br/>
            <ul>
                <li><b>Given</b> que la semana de ranking termina el domingo a las 23:59,</li>
                <li><b>When</b> el sistema calcula las posiciones finales el lunes a las 00:00,</li>
                <li><b>Then</b> otorga recompensas automáticas: 1° lugar: insignia "Campeón Semanal" + 500 XP + 15% descuento en tienda, 2° y 3° lugar: insignia "Podio Semanal" + 250 XP + 10% descuento, Top 10: insignia "Top 10" + 100 XP,</li>
                <li><b>And</b> los usuarios reciben una notificación con sus recompensas,</li>
                <li><b>And</b> el ranking semanal se reinicia para la nueva semana, manteniendo el ranking histórico accesible.</li>
            </ul>
            <b>Escenario 4 (Dar like o felicitar a otro usuario):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario "Luis" ve que su amigo "Pedro" está en el 1° lugar del ranking semanal,</li>
                <li><b>When</b> hace clic en el botón "Felicitar" junto al nombre de Pedro,</li>
                <li><b>Then</b> el sistema envía una notificación push y por correo a Pedro: "¡Luis te ha felicitado por tu puesto #1 en el ranking semanal!",</li>
                <li><b>And</b> el contador de felicitaciones de Pedro aumenta en su perfil,</li>
                <li><b>And</b> Luis puede escribir un mensaje opcional de hasta 100 caracteres.</li>
            </ul>
            <b>Escenario 5 (Evolución en el ranking - gráfico histórico):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario accede a "Ranking / Mi progreso",</li>
                <li><b>When</b> selecciona "Ver evolución",</li>
                <li><b>Then</b> el sistema muestra un gráfico de líneas con su posición en el ranking global durante las últimas 8 semanas,</li>
                <li><b>And</b> se ven puntos donde mejoró (posición más baja = mejor) y donde empeoró,</li>
                <li><b>And</b> al hacer clic en un punto, muestra la semana específica y su XP ganado,</li>
                <li><b>And</b> un mensaje motivacional: "Has mejorado 150 posiciones en las últimas 4 semanas. ¡Excelente progreso!".</li>
            </ul>
        </b></td>
    </tr>
</table>

<table align="center">
    <tr>
        <td><b>User Story ID</b></td>
        <td>US35</b></td>
        <td><b>Epic ID</b></td>
        <td>EP05</b></td>
    </tr>
    <tr>
        <td><b>Título</b></td>
        <td colspan="3">Recompensas y tienda virtual</b></td>
    </tr>
    <tr>
        <td><b>Descripción</b></td>
        <td colspan="3">Como usuario, quiero ganar monedas virtuales (puntos de recompensa) al completar actividades y canjearlas en una tienda virtual por artículos cosméticos (avatars, temas, efectos) o beneficios reales (descuentos en productos físicos de primeros auxilios), para sentir que mi esfuerzo tiene recompensas tangibles y personalizar mi experiencia en SafeStep.</b></td>
    </tr>
    <tr>
        <td colspan="4">
            <b>Criterios de aceptación:</b> <br/>
            <ol>
                <li>El sistema debe introducir una moneda virtual llamada "SafeCoins" (o similar), que los usuarios ganan al completar actividades, mantener rachas, subir de nivel y desbloquear insignias.</li>
                <li>Las tasas de conversión deben ser claras: simulación básica: 10 SafeCoins, avanzada: 20, evaluación aprobada: 50, racha de 7 días: 30 bonus, insignia común: 25, insignia rara: 75, insignia épica: 150, insignia legendaria: 300.</li>
                <li>El sistema debe incluir una "Tienda virtual" accesible desde el dashboard, donde los usuarios pueden canjear SafeCoins por artículos digitales: avatares exclusivos, marcos de perfil, temas de color (modo oscuro personalizado), efectos de animación para logros, y "Escudos de racha" (para proteger la racha por un día).</li>
                <li>La tienda virtual también debe ofrecer beneficios reales canjeables: cupones de descuento para la tienda física de SafeStep (EP04), acceso anticipado a nuevos módulos, participación en sorteos exclusivos, o donaciones a organizaciones de primeros auxilios (con certificado).</li>
                <li>El usuario debe poder ver su saldo actual de SafeCoins en el dashboard (junto al XP y nivel), con un acceso directo a la tienda virtual.</li>
                <li>El sistema debe mostrar un catálogo de artículos disponibles con imagen, nombre, costo en SafeCoins, descripción, y si es "limitado" (disponible solo por tiempo determinado).</li>
                <li>Al comprar un artículo, el sistema deduce automáticamente los SafeCoins, otorga el artículo al usuario, y muestra un mensaje de confirmación con animación.</li>
                <li>El sistema debe permitir al usuario "regalar" artículos virtuales a otros usuarios (con su consentimiento), descontando los SafeCoins del comprador.</li>
                <li>El sistema debe mostrar un historial de transacciones: SafeCoins ganados (con origen) y gastados (con artículo canjeado), accesible desde el perfil.</li>
                <li>Los SafeCoins no deben ser canjeables por dinero real ni transferibles entre cuentas (excepto regalos de artículos), para evitar abusos y mantener la integridad del sistema.</li>
            </ol>
            <b>Escenario 1 (Ganar SafeCoins por actividades):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario "Laura" tiene 150 SafeCoins acumulados,</li>
                <li><b>When</b> completa una simulación avanzada de "RCP" por primera vez,</li>
                <li><b>Then</b> el sistema otorga 20 SafeCoins, mostrando una notificación: "+20 SafeCoins por completar RCP Avanzado",</li>
                <li><b>And</b> su saldo se actualiza a 170 SafeCoins,</li>
                <li><b>And</b> el ícono de moneda en el dashboard muestra el nuevo saldo.</li>
            </ul>
            <b>Escenario 2 (Canje en tienda virtual - avatar exclusivo):</b> <br/>
            <ul>
                <li><b>Given</b> que Laura tiene 200 SafeCoins,</li>
                <li><b>When</b> accede a la "Tienda virtual" y ve un avatar exclusivo de "Paramédico" con costo de 150 SafeCoins,</li>
                <li><b>Then</b> hace clic en "Canjear", y el sistema muestra un mensaje de confirmación: "¿Canjear 'Avatar Paramédico' por 150 SafeCoins?",</li>
                <li><b>When</b> confirma,</li>
                <li><b>Then</b> el sistema deduce 150 SafeCoins (nuevo saldo: 50),</li>
                <li><b>And</b> el avatar se agrega automáticamente a su colección de avatares,</li>
                <li><b>And</b> Laura puede cambiarlo inmediatamente desde "Mi perfil / Avatares".</li>
            </ul>
            <b>Escenario 3 (Artículo limitado por tiempo - urgencia):</b> <br/>
            <ul>
                <li><b>Given</b> que la tienda virtual ofrece un "Marco de perfil Especial Halloween" por 100 SafeCoins, disponible solo del 20 al 31 de octubre,</li>
                <li><b>When</b> el usuario "Carlos" accede el 30 de octubre y tiene 120 SafeCoins,</li>
                <li><b>Then</b> ve un indicador "¡Disponible por 1 día!" y un contador regresivo,</li>
                <li><b>When</b> canjea el marco,</li>
                <li><b>Then</b> lo recibe permanentemente, y después del 31 de octubre el artículo ya no está disponible para nuevos compradores,</li>
                <li><b>And</b> Carlos puede presumir su marco exclusivo en su perfil.</li>
            </ul>
            <b>Escenario 4 (Canje por beneficio real - descuento en tienda física):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario "Ana" tiene 500 SafeCoins,</li>
                <li><b>When</b> accede a la tienda virtual y selecciona "Cupón 15% descuento en tienda SafeStep" con costo de 400 SafeCoins,</li>
                <li><b>Then</b> el sistema genera un código único de cupón (ejemplo: SAFESTEP-ANA-15-ABC123),</li>
                <li><b>And</b> envía el código por correo electrónico y lo muestra en pantalla,</li>
                <li><b>And</b> el código tiene una vigencia de 30 días para ser utilizado en la tienda de productos físicos (EP04),</li>
                <li><b>And</b> Ana puede copiarlo o usarlo directamente en el checkout de la tienda.</li>
            </ul>
            <b>Escenario 5 (Regalar artículo a otro usuario):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario "Pedro" tiene 300 SafeCoins,</li>
                <li><b>When</b> en la tienda virtual, selecciona un "Escudo de racha" (costo 50 SafeCoins) y elige la opción "Regalar",</li>
                <li><b>Then</b> ingresa el nombre de usuario "Laura" y un mensaje opcional: "¡Para que no pierdas tu racha!",</li>
                <li><b>When</b> confirma,</li>
                <li><b>Then</b> el sistema deduce 50 SafeCoins de Pedro,</li>
                <li><b>And</b> Laura recibe una notificación: "¡Pedro te ha regalado un Escudo de racha! Recíbelo en tu inventario",</li>
                <li><b>And</b> Laura acepta el regalo y el escudo aparece en su perfil.</li>
            </ul>
        </b></td>
    </table>
</tr>

<table align="center">
    <tr>
        <td><b>User Story ID</b></td>
        <td>US36</b></td>
        <td><b>Epic ID</b></td>
        <td>EP05</b></td>
    </tr>
    <tr>
        <td><b>Título</b></td>
        <td colspan="3">Misiones y desafíos diarios/semanales</b></td>
    </tr>
    <tr>
        <td><b>Descripción</b></td>
        <td colspan="3">Como usuario, quiero recibir misiones y desafíos diarios y semanales (completar ciertas simulaciones, ganar XP, ayudar en el foro, etc.), para tener objetivos claros a corto plazo, sentirme motivado diariamente y recibir recompensas adicionales por completarlos, manteniendo mi compromiso con el aprendizaje.</b></td>
    </tr>
    <tr>
        <td colspan="4">
            <b>Criterios de aceptación:</b> <br/>
            <ol>
                <li>El sistema debe generar automáticamente 3 misiones diarias diferentes para cada usuario (ejemplo: "Completa 1 simulación de RCP", "Gana 100 XP hoy", "Comparte un logro en redes sociales"), renovándose cada día a las 00:00 (hora local del usuario).</li>
                <li>El sistema debe generar 5 misiones semanales (ejemplo: "Completa 5 simulaciones", "Mantén racha de 7 días", "Ayuda a 3 usuarios en el foro"), renovándose cada lunes a las 00:00.</li>
                <li>Cada misión debe mostrar: nombre, descripción, requisito específico, recompensa (XP, SafeCoins, insignia especial) y barra de progreso (ejemplo: "2/3 simulaciones completadas").</li>
                <li>Las misiones deben ser personalizadas según el nivel y progreso del usuario (ejemplo: usuarios avanzados reciben misiones más desafiantes que principiantes).</li>
                <li>Al completar una misión, el sistema debe mostrar una notificación de logro, otorgar la recompensa automáticamente y marcar la misión como "Completada".</li>
                <li>Si el usuario completa todas las misiones diarias, recibe un bonus adicional de "Misión maestro diario" (ejemplo: +50 XP extra).</li>
                <li>El sistema debe mostrar una sección "Misiones activas" en el dashboard, con cuenta regresiva para las que expiran al final del día/semana.</li>
                <li>El usuario debe poder "saltar" o "reemplazar" una misión hasta 1 vez por día (gastando SafeCoins o viendo un anuncio opcional), si considera que es demasiado difícil o no le interesa.</li>
                <li>El sistema debe registrar el historial de misiones completadas, mostrando estadísticas: "Has completado 45 de 60 misiones diarias en los últimos 30 días (75% de cumplimiento)".</li>
                <li>Las misiones especiales por eventos (ejemplo: "Semana de la RCP") deben tener recompensas aumentadas y estar disponibles solo durante el período del evento.</li>
            </ol>
            <b>Escenario 1 (Misiones diarias - visualización y progreso):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario "Carlos" inicia sesión un martes a las 9:00 AM,</li>
                <li><b>When</b> accede a su dashboard,</li>
                <li><b>Then</b> ve una sección "Misiones diarias" con 3 tarjetas: "Completa 1 simulación (0/1) - Recompensa: 30 XP", "Gana 150 XP hoy (0/150) - Recompensa: 2 SafeCoins", "Comparte un logro en redes (0/1) - Recompensa: Insignia 'Compartido'",</li>
                <li><b>And</b> una cuenta regresiva: "Estas misiones expiran en 15 horas",</li>
                <li><b>When</b> completa una simulación de hemorragias,</li>
                <li><b>Then</b> la primera misión se actualiza a "1/1" y se marca como completada, otorgando 30 XP instantáneamente.</li>
            </ul>
            <b>Escenario 2 (Misiones semanales - bonus por completar todas):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario "Ana" está en su dashboard un miércoles,</li>
                <li><b>When</b> despliega la sección "Misiones semanales",</li>
                <li><b>Then</b> ve 5 misiones: "Completa 5 simulaciones (3/5)", "Mantén racha de 7 días (4/7)", "Ayuda a 2 usuarios en el foro (1/2)", "Obtén 3 insignias nuevas (2/3)", "Completa una evaluación final (0/1)",</li>
                <li><b>When</b> al final de la semana (domingo) ha completado las 5 misiones,</li>
                <li><b>Then</b> el sistema otorga un bonus adicional de 200 XP + 10 SafeCoins + una insignia especial "Misión Semanal Cumplida",</li>
                <li><b>And</b> el lunes se generan nuevas misiones semanales.</li>
            </ul>
            <b>Escenario 3 (Misiones personalizadas por nivel):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario "Luis" es nivel 15 (avanzado) y el usuario "Pedro" es nivel 2 (principiante),</li>
                <li><b>When</b> ambos acceden a sus misiones diarias,</li>
                <li><b>Then</b> Luis recibe misiones más desafiantes: "Completa 2 simulaciones avanzadas", "Gana 500 XP", "Responde 5 preguntas en el foro",</li>
                <li><b>And</b> Pedro recibe misiones más sencillas: "Completa 1 simulación básica", "Gana 50 XP", "Mira 1 micro-lección",</li>
                <li><b>And</b> las recompensas son proporcionales a la dificultad (Luis gana más XP y SafeCoins que Pedro).</li>
            </ul>
            <b>Escenario 4 (Saltar misión - usar SafeCoins):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario "María" tiene una misión diaria que no le gusta: "Completa simulación de atragantamiento en bebés",</li>
                <li><b>When</b> hace clic en "Saltar misión" (opción disponible una vez por día),</li>
                <li><b>Then</b> el sistema muestra un mensaje: "Saltar esta misión cuesta 5 SafeCoins o puedes ver un anuncio de 30 segundos. ¿Continuar?",</li>
                <li><b>When</b> elige pagar 5 SafeCoins,</li>
                <li><b>Then</b> la misión se reemplaza por una nueva misión aleatoria (mismo nivel de dificultad),</li>
                <li><b>And</b> el saldo de SafeCoins de María se reduce en 5 unidades.</li>
            </ul>
            <b>Escenario 5 (Misión especial por evento - Semana de la RCP):</b> <br/>
            <ul>
                <li><b>Given</b> que SafeStep está celebrando la "Semana de la RCP" del 1 al 7 de junio,</li>
                <li><b>When</b> el usuario accede a sus misiones durante esa semana,</li>
                <li><b>Then</b> ve misiones especiales adicionales: "Completa 3 simulaciones de RCP (recompensa: 150 XP + insignia 'Guardián del Corazón')", "Comparte un dato sobre RCP en redes (recompensa: 50 XP)",</li>
                <li><b>And</b> las recompensas de estas misiones son el doble de lo habitual,</li>
                <li><b>And</b> después del 7 de junio, estas misiones desaparecen y no están disponibles.</li>
            </ul>
        </b></td>
    </tr>
</table>

<table align="center">
    <tr>
        <td><b>User Story ID</b></td>
        <td>US37</b></td>
        <td><b>Epic ID</b></td>
        <td>EP05</b></td>
    </tr>
    <tr>
        <td><b>Título</b></td>
        <td colspan="3">Eventos y torneos comunitarios</b></td>
    </tr>
    <tr>
        <td><b>Descripción</b></td>
        <td colspan="3">Como miembro de la comunidad, quiero participar en eventos y torneos organizados por SafeStep (competencias por equipos, desafíos de velocidad, retos de conocimiento), para competir con otros usuarios en un ambiente divertido, ganar recompensas exclusivas y sentirme parte de una comunidad activa que valora la preparación en primeros auxilios.</b></td>
    </tr>
    <tr>
        <td colspan="4">
            <b>Criterios de aceptación:</b> <br/>
            <ol>
                <li>El sistema debe permitir a los administradores crear eventos y torneos con: nombre, descripción, fechas de inicio y fin, tipo (individual o por equipos), reglas, sistema de puntuación, y recompensas para los ganadores.</li>
                <li>Los usuarios deben poder ver un calendario de eventos próximos y activos en la sección "Comunidad / Eventos", con opción de registrarse o unirse a un equipo.</li>
                <li>Los torneos pueden ser de diferentes tipos: "Desafío de velocidad" (quien complete más simulaciones en tiempo récord), "Batalla de conocimiento" (preguntas rápidas), "Competencia por equipos" (colaboración para sumar XP).</li>
                <li>Durante un torneo, el sistema debe mostrar un leaderboard en tiempo real con las posiciones actualizadas, y notificaciones push cuando un competidor supere al usuario.</li>
                <li>Al finalizar un evento, el sistema debe anunciar a los ganadores, otorgar las recompensas (XP, SafeCoins, insignias exclusivas, descuentos) y mostrar un resumen de resultados.</li>
                <li>Los usuarios deben poder crear sus propios eventos privados (ejemplo: "Torneo entre amigos de la universidad") con hasta 20 participantes, configurando sus propias reglas y recompensas (con un costo de SafeCoins para el organizador).</li>
                <li>El sistema debe enviar recordatorios automáticos a los inscritos: "El torneo 'RCP Challenge' comienza en 1 hora. ¡Prepárate!", y notificaciones de hitos durante el evento.</li>
                <li>Los eventos deben tener categorías por nivel (principiante, intermedio, avanzado) para garantizar competencias justas.</li>
                <li>El sistema debe mostrar un historial de eventos pasados del usuario, incluyendo su posición y recompensas obtenidas.</li>
                <li>Los eventos especiales (ejemplo: "Torneo Anual de Primeros Auxilios") deben tener cobertura destacada en el dashboard y en las redes sociales de SafeStep.</li>
            </ol>
            <b>Escenario 1 (Registro y participación en torneo individual):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario "Carlos" ve en el calendario un torneo "Desafío RCP - 24 horas" que comienza mañana,</li>
                <li><b>When</b> hace clic en "Registrarse",</li>
                <li><b>Then</b> el sistema confirma su inscripción y agrega el evento a su calendario personal,</li>
                <li><b>When</b> al día siguiente, durante el torneo, Carlos completa 5 simulaciones de RCP,</li>
                <li><b>Then</b> el leaderboard en tiempo real muestra: "Carlos - 5 simulaciones (3° lugar)",</li>
                <li><b>When</b> el torneo termina y Carlos queda en 3° lugar,</li>
                <li><b>Then</b> recibe una insignia "Bronce en RCP Challenge", 100 XP, 20 SafeCoins, y un mensaje de felicitación.</li>
            </ul>
            <b>Escenario 2 (Torneo por equipos - colaboración):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario "Ana" se une a un equipo llamado "Los Socorristas" para el torneo "Copa SafeStep",</li>
                <li><b>When</b> el torneo comienza y cada miembro del equipo completa actividades,</li>
                <li><b>Then</b> el sistema suma los XP de todos los miembros del equipo y muestra un leaderboard por equipos,</li>
                <li><b>When</b> el equipo "Los Socorristas" gana el torneo,</li>
                <li><b>Then</b> cada miembro recibe una insignia "Campeón por Equipos", 500 XP, 50 SafeCoins, y un marco de perfil especial por 30 días,</li>
                <li><b>And</b> el líder del equipo recibe un bonus adicional por su liderazgo.</li>
            </ul>
            <b>Escenario 3 (Creación de evento privado entre amigos):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario "Luis" quiere organizar un torneo amistoso con 5 amigos,</li>
                <li><b>When</b> accede a "Crear evento privado", configura: nombre "Torneo de Amigos", tipo "Batalla de conocimiento", duración "3 horas", y paga 100 SafeCoins como costo de organización,</li>
                <li><b>Then</b> el sistema genera un código de invitación único,</li>
                <li><b>When</b> Luis comparte el código con sus amigos, ellos se unen,</li>
                <li><b>Then</b> durante el torneo, los participantes responden preguntas rápidas y el leaderboard se actualiza,</li>
                <li><b>And</b> al finalizar, Luis (organizador) puede asignar recompensas personalizadas (ejemplo: "El ganador recibe 200 XP de mi cuenta").</li>
            </ul>
            <b>Escenario 4 (Notificaciones y recordatorios del torneo):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario "María" se registró en el torneo "RCP Express",</li>
                <li><b>When</b> faltan 30 minutos para el inicio del torneo,</li>
                <li><b>Then</b> el sistema envía una notificación push: "⏰ ¡El torneo 'RCP Express' comienza en 30 minutos! Prepárate",</li>
                <li><b>When</b> durante el torneo, otro usuario supera a María en el leaderboard,</li>
                <li><b>Then</b> recibe otra notificación: "⚠️ 'Juan' te ha superado en el torneo. ¡Completa más actividades para recuperar tu posición!",</li>
                <li><b>And</b> al finalizar el torneo, recibe un resumen con su posición final y recompensas.</li>
            </ul>
            <b>Escenario 5 (Evento especial - Torneo Anual):</b> <br/>
            <ul>
                <li><b>Given</b> que SafeStep organiza el "Torneo Anual de Primeros Auxilios" con grandes recompensas,</li>
                <li><b>When</b> el torneo dura una semana y participan más de 10,000 usuarios,</li>
                <li><b>Then</b> el sistema muestra un banner destacado en el dashboard con cuenta regresiva,</li>
                <li><b>And</b> los top 10 finalistas reciben premios reales: libros de primeros auxilios, kits de emergencia (de EP04), y una membresía premium gratuita por un año,</li>
                <li><b>And</b> todos los participantes reciben una insignia conmemorativa "Participante Torneo Anual 2025".</li>
            </ul>
        </b></td>
    </tr>
</table>

<table align="center">
    <tr>
        <td><b>User Story ID</b></td>
        <td>US38</b></td>
        <td><b>Epic ID</b></td>
        <td>EP05</b></td>
    </tr>
    <tr>
        <td><b>Título</b></td>
        <td colspan="3">Niveles de prestigio y desbloqueables</b></td>
    </tr>
    <tr>
        <td><b>Descripción</b></td>
        <td colspan="3">Como usuario avanzado, quiero alcanzar niveles de prestigio después de superar el nivel máximo estándar (ejemplo: Nivel 50), para seguir teniendo metas a largo plazo, desbloquear contenido exclusivo y demostrar mi maestría en primeros auxilios a la comunidad.</b></td>
    </tr>
    <tr>
        <td colspan="4">
            <b>Criterios de aceptación:</b> <br/>
            <ol>
                <li>El sistema debe definir un sistema de "Niveles de prestigio" (Prestigio 1, 2, 3, etc.) que se activan cuando el usuario alcanza el nivel máximo estándar (ejemplo: Nivel 50).</li>
                <li>Al alcanzar un nivel de prestigio, el XP del usuario se reinicia a 0 para el siguiente prestigio, pero conserva todas sus insignias, avatares y SafeCoins, y su nivel se muestra como "Prestigio 1 - Nivel 1" (ejemplo: P1-L1).</li>
                <li>Cada nivel de prestigio debe requerir más XP que el anterior (ejemplo: Prestigio 1: 10,000 XP por nivel, Prestigio 2: 15,000 XP, Prestigio 3: 20,000 XP).</li>
                <li>Al alcanzar un nuevo nivel de prestigio, el sistema debe mostrar una animación especial, otorgar una insignia exclusiva de prestigio, un avatar legendario, y 500 SafeCoins como recompensa.</li>
                <li>El sistema debe desbloquear contenido exclusivo por prestigio: marcos de perfil especiales, efectos visuales en el dashboard (ejemplo: fondo dorado), acceso a módulos avanzados exclusivos, y descuentos permanentes en la tienda física.</li>
                <li>El perfil del usuario debe mostrar su nivel de prestigio visiblemente (ícono de corona, estrella o llamas), para que otros usuarios reconozcan su experiencia.</li>
                <li>El sistema debe mostrar una sección "Hitos de prestigio" con los requisitos para el siguiente prestigio y una lista de desbloqueables obtenidos en cada prestigio.</li>
                <li>Los niveles de prestigio deben ser acumulativos sin límite máximo teórico, permitiendo a los usuarios más dedicados seguir progresando indefinidamente.</li>
                <li>El sistema debe ajustar las misiones diarias/semanales para usuarios de prestigio, ofreciendo desafíos más avanzados y recompensas proporcionalmente mayores.</li>
                <li>Los usuarios de prestigio deben poder "mentorizar" a usuarios nuevos, recibiendo XP bonus por cada aprendiz que complete su primer módulo.</li>
            </ol>
            <b>Escenario 1 (Alcanzar nivel máximo y primer prestigio):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario "Carlos" ha alcanzado el Nivel 50 (máximo estándar) con 50,000 XP,</li>
                <li><b>When</b> completa una simulación que le otorga 100 XP, superando el límite,</li>
                <li><b>Then</b> el sistema muestra una animación de transformación: "¡FELICIDADES! Has alcanzado el Prestigio 1",</li>
                <li><b>And</b> su XP se reinicia a 0/10,000 para el siguiente nivel dentro del Prestigio 1,</li>
                <li><b>And</b> su nivel se muestra como "P1-L1" (Prestigio 1, Nivel 1),</li>
                <li><b>And</b> recibe una insignia "Prestigio 1 - Leyenda", un avatar "Socorrista Legendario", 500 SafeCoins, y un marco de perfil dorado,</li>
                <li><b>And</b> su dashboard ahora tiene un efecto visual de partículas doradas.</li>
            </ul>
            <b>Escenario 2 (Desbloqueables por prestigio):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario "Ana" alcanza el Prestigio 2 (P2-L1),</li>
                <li><b>Then</b> además de las recompensas estándar, desbloquea: un módulo avanzado exclusivo "RCP en situaciones extremas", un descuento del 15% permanente en la tienda de productos físicos, y un efecto de hover especial en su perfil público,</li>
                <li><b>When</b> accede a la sección "Hitos de prestigio",</li>
                <li><b>Then</b> ve una lista de todos los desbloqueables por prestigio: "Prestigio 1: Avatar legendario", "Prestigio 2: Módulo exclusivo + descuento 15%", "Prestigio 3: Título 'Maestro de la vida'", etc.</li>
            </ul>
            <b>Escenario 3 (Visibilidad del prestigio en perfil público):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario "Luis" es Prestigio 3 - Nivel 15 (P3-L15),</li>
                <li><b>When</b> otro usuario visita su perfil público,</li>
                <li><b>Then</b> ve un ícono de tres llamas junto a su nombre, indicando su alto nivel de prestigio,</li>
                <li><b>And</b> el marco de su foto de perfil tiene un borde dorado con diamantes,</li>
                <li><b>And</b> se muestra un contador: "Este usuario ha completado 500 simulaciones y ha ayudado a 23 nuevos aprendices".</li>
            </ul>
            <b>Escenario 4 (Mentoría - XP bonus por ayudar a nuevos usuarios):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario "María" (Prestigio 2) acepta ser mentora del nuevo usuario "Pedro" (Nivel 1),</li>
                <li><b>When</b> Pedro completa su primera simulación de RCP,</li>
                <li><b>Then</b> el sistema otorga a María un bonus de 50 XP por su labor de mentoría,</li>
                <li><b>And</b> cuando Pedro completa su primer módulo completo, María recibe 200 XP adicionales y una insignia "Mentor Ejemplar",</li>
                <li><b>And</b> Pedro también recibe XP bonus por tener un mentor.</li>
            </ul>
            <b>Escenario 5 (Misiones adaptadas a prestigio):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario "Carlos" es Prestigio 1 - Nivel 25,</li>
                <li><b>When</b> recibe sus misiones diarias,</li>
                <li><b>Then</b> son más desafiantes que para usuarios sin prestigio: "Completa 3 simulaciones avanzadas en menos de 15 minutos", "Gana 800 XP hoy", "Responde 10 preguntas en el foro con alta calidad",</li>
                <li><b>And</b> las recompensas son proporcionalmente mayores (ejemplo: 200 XP por misión en lugar de 50 XP).</li>
            </ul>
        </b></td>
    </table>
</table>

<table align="center">
    <tr>
        <td><b>User Story ID</b></td>
        <td>US39</b></td>
        <td><b>Epic ID</b></td>
        <td>EP05</b></td>
    </tr>
    <tr>
        <td><b>Título</b></td>
        <td colspan="3">Avatares y personalización de perfil</b></td>
    </tr>
    <tr>
        <td><b>Descripción</b></td>
        <td colspan="3">Como usuario, quiero personalizar mi perfil con avatares, marcos, fondos y temas exclusivos que puedo desbloquear mediante logros, comprar en la tienda virtual o ganar en eventos, para expresar mi identidad única dentro de SafeStep y mostrar mi estilo personal a la comunidad.</b></td>
    </tr>
    <tr>
        <td colspan="4">
            <b>Criterios de aceptación:</b> <br/>
            <ol>
                <li>El sistema debe ofrecer una galería de avatares predeterminados (al menos 20 opciones básicas) que todos los usuarios pueden usar sin costo.</li>
                <li>Los usuarios pueden desbloquear avatares adicionales mediante: logros (ejemplo: avatar "Socorrista" por completar RCP), compra en tienda virtual con SafeCoins, participación en eventos especiales, o alcanzando niveles de prestigio.</li>
                <li>El sistema debe permitir a los usuarios subir su propia foto de perfil, con moderación básica para evitar contenido inapropiado.</li>
                <li>Además de avatares, debe ofrecer elementos de personalización: marcos de perfil (ejemplo: dorado, plateado, de eventos), fondos de perfil (imagen de fondo en la página de perfil), y temas de color para el dashboard (modo oscuro personalizado, colores acento).</li>
                <li>El usuario debe poder previsualizar los cambios antes de aplicarlos, y aplicarlos instantáneamente sin recargar la página.</li>
                <li>El sistema debe mostrar una sección "Mi colección" donde el usuario ve todos los elementos de personalización que ha desbloqueado (avatares, marcos, fondos, temas).</li>
                <li>Los elementos de personalización deben estar categorizados por rareza (común, raro, épico, legendario) y mostrar el método de desbloqueo en el tooltip.</li>
                <li>El sistema debe permitir a los usuarios "equipar" combinaciones (avatar + marco + fondo + tema) y guardarlas como "atuendos" para cambiar rápidamente entre configuraciones.</li>
                <li>El perfil público del usuario debe mostrar su avatar, marco y fondo seleccionados, junto con su nivel y prestigio.</li>
                <li>El sistema debe rotar avatares y marcos de temporada (ejemplo: Halloween, Navidad) disponibles por tiempo limitado en la tienda virtual.</li>
            </ol>
            <b>Escenario 1 (Selección y cambio de avatar):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario "Carlos" accede a "Mi perfil / Personalización",</li>
                <li><b>When</b> selecciona la pestaña "Avatares",</li>
                <li><b>Then</b> ve una cuadrícula con todos los avatares que ha desbloqueado (en color) y los bloqueados (en gris),</li>
                <li><b>When</b> hace clic en el avatar "Paramédico" (desbloqueado por logro),</li>
                <li><b>Then</b> el sistema muestra una previsualización de cómo se verá su perfil con ese avatar,</li>
                <li><b>When</b> confirma "Aplicar",</li>
                <li><b>Then</b> su avatar se actualiza instantáneamente en todo SafeStep (dashboard, foro, ranking).</li>
            </ul>
            <b>Escenario 2 (Desbloqueo de marco por evento):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario "Ana" participó en el evento "Semana de la RCP" y completó las misiones,</li>
                <li><b>When</b> el evento termina,</li>
                <li><b>Then</b> recibe un marco de perfil exclusivo "Marco RCP 2025" como recompensa,</li>
                <li><b>When</b> accede a su colección de marcos,</li>
                <li><b>Then</b> ve el nuevo marco disponible y lo aplica,</li>
                <li><b>And</b> su foto de perfil ahora aparece con un borde que tiene iconos de corazón y manos (temática RCP).</li>
            </ul>
            <b>Escenario 3 (Compra de tema de color en tienda virtual):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario "Luis" tiene 300 SafeCoins,</li>
                <li><b>When</b> accede a la tienda virtual y ve un "Tema nocturno - Fondo estrellado" con costo de 150 SafeCoins,</li>
                <li><b>Then</b> lo compra, deduciendo los SafeCoins,</li>
                <li><b>When</b> aplica el tema en su configuración de personalización,</li>
                <li><b>Then</b> su dashboard cambia a un fondo oscuro con estrellas animadas, los botones tienen un color azul noche, y la tipografía se ajusta para legibilidad,</li>
                <li><b>And</b> el cambio persiste entre sesiones.</li>
            </ul>
            <b>Escenario 4 (Guardar atuendos - combinaciones rápidas):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario "María" ha personalizado su perfil con avatar "Socorrista", marco "Dorado", fondo "Atardecer", tema "Clásico",</li>
                <li><b>When</b> guarda esta combinación como "Atuendo diario",</li>
                <li><b>Then</b> el sistema almacena la configuración,</li>
                <li><b>When</b> más tarde quiere cambiar a una configuración festiva,</li>
                <li><b>Then</b> puede seleccionar "Atuendo festivo" que había guardado previamente, aplicando avatar "Navidad", marco "Copo de nieve", fondo "Invierno",</li>
                <li><b>And</b> cambiar entre atuendos toma un solo clic.</li>
            </ul>
            <b>Escenario 5 (Avatar de prestigio legendario):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario "Carlos" alcanza el Prestigio 5,</li>
                <li><b>When</b> desbloquea el avatar legendario "Ángel Guardián",</li>
                <li><b>Then</b> este avatar tiene una animación especial (efecto de brillo alrededor),</li>
                <li><b>When</b> otros usuarios visitan su perfil,</li>
                <li><b>Then</b> ven el avatar animado, reconociendo su alto nivel de prestigio,</li>
                <li><b>And</b> el avatar aparece en la cima de la galería como "Legendario - Desbloqueado".</li>
            </ul>
        </b></td>
    </tr>
</table>

<table align="center">
    <tr>
        <td><b>User Story ID</b></td>
        <td>US40</b></td>
        <td><b>Epic ID</b></td>
        <td>EP05</b></td>
    </tr>
    <tr>
        <td><b>Título</b></td>
        <td colspan="3">Retroalimentación y celebración de logros</b></td>
    </tr>
    <tr>
        <td><b>Descripción</b></td>
        <td colspan="3">Como usuario, quiero recibir retroalimentación visual y auditiva cuando alcanzo un hito importante (subir de nivel, desbloquear insignia, completar racha), para sentirme celebrado y reconocido, reforzando positivamente mi comportamiento de aprendizaje y motivándome a seguir practicando.</b></td>
    </tr>
    <tr>
        <td colspan="4">
            <b>Criterios de aceptación:</b> <br/>
            <ol>
                <li>El sistema debe mostrar animaciones de celebración para hitos importantes: subir de nivel (XP), desbloquear insignia, completar racha de 7/30/100 días, alcanzar nuevo prestigio, ganar un torneo.</li>
                <li>Las animaciones deben incluir efectos visuales: confeti, estrellas, fuegos artificiales, brillos, según la magnitud del logro (más espectacular para prestigio que para nivel común).</li>
                <li>El sistema debe reproducir sonidos de celebración específicos para cada tipo de logro (ejemplo: fanfarria para nivel, campana para insignia, aplausos para torneo).</li>
                <li>El usuario debe poder desactivar los efectos de sonido desde configuración, manteniendo los efectos visuales, o desactivar ambos por completo si prefiere una experiencia silenciosa.</li>
                <li>El sistema debe mostrar tarjetas de resumen de logros al final de cada sesión: "Hoy ganaste: +250 XP, 2 insignias, racha de 10 días".</li>
                <li>Las celebraciones deben ser no intrusivas: la animación aparece en una esquina o modal pequeño que no bloquea completamente la interfaz, y se puede cerrar con un clic.</li>
                <li>El sistema debe permitir al usuario "revivir" la animación de un logro desde la sección "Historial de logros", por si la cerró accidentalmente o quiere verla de nuevo.</li>
                <li>Los logros importantes (prestigio, torneo ganado) deben activar una notificación push adicional fuera de la aplicación, para celebrar incluso cuando el usuario no está activo.</li>
                <li>El sistema debe mostrar mensajes motivacionales personalizados según el logro: "¡Increíble! Has completado 100 simulaciones. Eres un ejemplo para la comunidad".</li>
                <li>La retroalimentación debe incluir un resumen de lo que sigue: "¡Subiste a Nivel 15! Te faltan 500 XP para el Nivel 16. La siguiente insignia está a solo 2 días de racha".</li>
            </ol>
            <b>Escenario 1 (Celebración por subir de nivel):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario "Carlos" completa una simulación que le otorga los últimos XP necesarios para pasar del Nivel 8 al Nivel 9,</li>
                <li><b>When</b> el sistema detecta el cambio de nivel,</li>
                <li><b>Then</b> muestra una animación de confeti en la esquina superior derecha de la pantalla,</li>
                <li><b>And</b> reproduce una fanfarria corta (3 segundos),</li>
                <li><b>And</b> muestra una tarjeta: "🎉 ¡FELICIDADES! Has alcanzado el Nivel 9. ¡Sigue así! Te faltan 800 XP para el Nivel 10",</li>
                <li><b>And</b> la tarjeta tiene un botón "Compartir" para publicar el logro en redes sociales, y un botón "Cerrar".</li>
            </ul>
            <b>Escenario 2 (Celebración por desbloquear insignia épica):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario "Ana" completa el requisito para la insignia "Maestro en RCP" (rareza épica),</li>
                <li><b>When</b> el sistema desbloquea la insignia,</li>
                <li><b>Then</b> muestra una animación más espectacular: fuegos artificiales en toda la pantalla (con duración de 5 segundos),</li>
                <li><b>And</b> reproduce un sonido de trompeta épica,</li>
                <li><b>And</b> muestra una tarjeta destacada con el icono de la insignia y el mensaje: "🏆 ¡LOGRO ÉPICO! Has desbloqueado la insignia 'Maestro en RCP'. Solo el 5% de los usuarios la tienen",</li>
                <li><b>And</b> ofrece compartir automáticamente en LinkedIn (para profesionales de la salud).</li>
            </ul>
            <b>Escenario 3 (Resumen de logros al final de sesión):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario "Luis" ha estado practicando durante 2 horas, completando 3 simulaciones, 2 micro-lecciones, y desbloqueando 1 insignia,</li>
                <li><b>When</b> presiona el botón "Salir" o cierra la aplicación,</li>
                <li><b>Then</b> el sistema muestra un resumen modal: "Resumen de tu sesión: ✅ +350 XP, 🏅 1 insignia nueva, 🔥 Racha de 12 días, 📊 Subiste al puesto #45 en el ranking",</li>
                <li><b>And</b> un mensaje motivacional: "¡Gran sesión! Vuelve mañana para mantener tu racha",</li>
                <li><b>And</b> un botón "Cerrar" o "Ver detalles".</li>
            </ul>
            <b>Escenario 4 (Configuración de sonidos - desactivar):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario "María" está en un entorno silencioso (biblioteca, oficina),</li>
                <li><b>When</b> accede a "Configuración / Gamificación / Sonidos",</li>
                <li><b>Then</b> desactiva la opción "Reproducir sonidos de celebración",</li>
                <li><b>When</b> luego alcanza un nuevo nivel,</li>
                <li><b>Then</b> solo ve la animación visual (confeti, tarjeta) pero no se reproduce ningún sonido,</li>
                <li><b>And</b> la configuración se guarda para futuras sesiones.</li>
            </ul>
            <b>Escenario 5 (Revivir animación de logro):</b> <br/>
            <ul>
                <li><b>Given</b> que el usuario "Carlos" desbloqueó una insignia importante pero cerró la animación accidentalmente antes de verla bien,</li>
                <li><b>When</b> accede a "Mi perfil / Historial de logros",</li>
                <li><b>Then</b> encuentra la insignia "Héroe de la Comunidad" y junto a ella un botón "Revivir celebración",</li>
                <li><b>When</b> hace clic,</li>
                <li><b>Then</b> el sistema reproduce nuevamente la animación y el sonido (si está activado) de ese logro específico, permitiendo al usuario disfrutarlo de nuevo o compartirlo en redes.</li>
            </ul>
        </b></td>
    </tr>
</table>

<table align="center">
    <tr>
        <td><b>User Story ID</b></td>
        <td>US41</b></td>
        <td><b>Epic ID</b></td>
        <td>EP06</b></td>
    </tr>
    <tr>
        <td><b>Título</b></td>
        <td colspan="3">Acceso a la Landing Page Informativa</b></td>
    </tr>
    <tr>
        <td><b>Descripción</b></td>
        <td colspan="3">Como visitante y potencial usuario interesado en primeros auxilios, quiero acceder a una Landing Page pública, centralizada y visualmente atractiva para informarme rápida y claramente sobre qué es SafeStep, qué beneficios ofrece y cómo funciona antes de decidir crear una cuenta.</b></td>
    </tr>
    <tr>
        <td colspan="4">
            <b>Criterios de aceptación:</b> <br/>
            <ol>
                <li>La Landing Page debe estar disponible sin necesidad de iniciar sesión.</li> 
                <li>El diseño debe reflejar la identidad visual de la marca (colores primarios, tipografías y el logotipo oficial).</li>
                <li>La Landing Page debe mantener una estructura que sigue un flujo de conversion de usuarios.</li>
                <li>El rendimiento de la Landing Page debe estar optimizado para cargar rápidamente, utilizando imágenes e iconos eficientes y código limpio, para evitar que el visitante abandone el sitio.</li>
                <li>El Footer debe contener la informacion corporativa basica, enlaces a redes sociales, politicas de privacidad y terminos de servicio para legitimidad institucional al producto.</li>
            </ol>
            <b>Escenario 1 (Acceso exitoso al contenido de la Landing Page):</b> <br/>
            <ul>
                <li><b>Given</b> que un visitante ingresa la URL de la Landing Page de SafeStep en su navegador,</li>
                <li><b>When</b> la página web termina de cargar,</li>
                <li><b>Then</b> el sistema le muestra de forma inmediata la propuesta de valor de la plataforma y le permite hacer scroll libremente para explorar todas las secciones informativas.</li>
            </ul>
            <b>Escenario 2 (Verificación de identidad institucional):</b> <br/>
            <ul>
                <li><b>Given</b> que el visitante está evaluando la credibilidad de la plataforma,</li>
                <li><b>When</b> se desplaza hasta la parte inferior de la Landing Page,</li>
                <li><b>Then</b> visualiza los enlaces legales (Privacidad, Términos), los canales de contacto y los íconos de las redes sociales oficiales de SafeStep.</li>
            </ul>
        </td>
    </tr>
</table>

<table align="center">
    <tr>
        <td><b>User Story ID</b></td>
        <td>US42</b></td>
        <td><b>Epic ID</b></td>
        <td>EP06</b></td>
    </tr>
    <tr>
        <td><b>Título</b></td>
        <td colspan="3">Navegación Global y Adaptabilidad Móvil</b></td>
    </tr>
    <tr>
        <td><b>Descripción</b></td>
        <td colspan="3">Como visitante y potencial usuario interesado en primeros auxilios, quiero un menú de navegación intuitivo que se adapte a mi dispositivo móvil o computadora para poder explorar rápidamente las secciones de la página o acceder a mi cuenta desde cualquier lugar.</b></td>
    </tr>
    <tr>
        <td colspan="4">
            <b>Criterios de aceptación:</b> <br/>
            <ol>
                <li>La barra de navegación superior debe estar siempre visible al hacer scroll.</li> 
                <li>La navegación debe incluir accesos directos a las secciones: Características, Simulaciones, Tienda, Gamificación y FAQ.</li>
                <li>El clic en los enlaces internos debe ejecutar un desplazamiento suave hacia la sección correspondiente.</li>
                <li>En dispositivos móviles, los enlaces de texto deben ocultarse y reemplazarse por un menú tipo "Hamburguesa".</li>
                <li>Al hacer clic en el menú móvil, debe desplegarse un panel lateral (drawer) con las opciones y los botones de autenticación.</li>
            </ol>
            <b>Escenario 1 (Uso del menú en versión móvil):</b> <br/>
            <ul>
                <li><b>Given</b> que el visitante está viendo la landing page desde un smartphone,</li>
                <li><b>When</b> hace clic en el ícono de menú (hamburguesa) en la esquina superior derecha,</li>
                <li><b>Then</b> el sistema despliega un panel lateral derecho con todos los enlaces de navegación y la opción "Comenzar Gratis".</li>
            </ul>
            <b>Escenario 2 (Navegación por la página (Smooth Scroll)):</b> <br/>
            <ul>
                <li><b>Given</b> que el visitante está en la parte superior de la página,</li>
                <li><b>When</b> hace clic en uno de los enlaces de la barra de navegación,</li>
                <li><b>Then</b> la pantalla se desplaza suavemente hasta la sección seleccionada sin recargar la página web.</li>
            </ul>
        </td>
    </tr>
</table>

<table align="center">
    <tr>
        <td><b>User Story ID</b></td>
        <td>US43</b></td>
        <td><b>Epic ID</b></td>
        <td>EP06</b></td>
    </tr>
    <tr>
        <td><b>Título</b></td>
        <td colspan="3">Presentación de Beneficios y Gamificación</b></td>
    </tr>
    <tr>
        <td><b>Descripción</b></td>
        <td colspan="3">Como visitante evaluando la plataforma, quiero conocer las características principales y cómo funciona el sistema de gamificación para entender por qué SafeStep es mejor que un curso tradicional en video.</b></td>
    </tr>
    <tr>
        <td colspan="4">
            <b>Criterios de aceptación:</b> <br/>
            <ol>
                <li>El sistema debe renderizar una cuadrícula interactiva con 6 tarjetas de características (Simulaciones, Feedback, Aprendizaje, Gamificación, Tienda, Multi-dispositivo).</li> 
                <li>Las tarjetas deben tener un efecto visual de elevación al pasar el cursor sobre ellas.</li>
                <li>Debe existir una sección de "Cómo Funciona" que explique el flujo en 3 pasos (Crear cuenta, Practicar, Obtener certificados).</li>
                <li>La sección de Gamificación debe explicar visualmente el concepto de Experiencia (XP), Insignias, Rachas y Rankings.</li>
                <li>Debe incluirse un componente visual que simule el perfil de un usuario mostrando una barra de progreso real.</li>
            </ol>
            <b>Escenario 1 (Interacción con las tarjetas de beneficios):</b> <br/>
            <ul>
                <li><b>Given</b> que el visitante hace scroll hasta la sección "Características Principales",</li>
                <li><b>When</b> posiciona el puntero del mouse sobre la tarjeta "Simulaciones Interactivas",</li>
                <li><b>Then</b> la tarjeta se eleva ligeramente y proyecta una sombra, indicando que es un elemento interactivo y de importancia.</li>
            </ul>
        </td>
    </tr>
</table>

<table align="center">
    <tr>
        <td><b>User Story ID</b></td>
        <td>US44</b></td>
        <td><b>Epic ID</b></td>
        <td>EP06</b></td>
    </tr>
    <tr>
        <td><b>Título</b></td>
        <td colspan="3">Exploración del Catálogo (Simulaciones y Tienda)</b></td>
    </tr>
    <tr>
        <td><b>Descripción</b></td>
        <td colspan="3">Como visitante y potencial usuario, quiero ver ejemplos concretos de las simulaciones disponibles y los productos que venden para asegurarme de que el contenido es relevante para mis necesidades de prevención.</b></td>
    </tr>
    <tr>
        <td colspan="4">
            <b>Criterios de aceptación:</b> <br/>
            <ol>
                <li>La sección "Simulaciones" debe mostrar tarjetas representativas de los módulos (RCP, Atragantamiento, Quemaduras, Sismos, Hemorragias).</li> 
                <li>Cada tarjeta de simulación debe indicar su tiempo estimado de duración y su calificación por estrellas.</li>
                <li>La sección de la "Tienda de Emergencia" debe mostrar un mínimo de 4 productos de muestra.</li>
                <li>Las tarjetas de productos deben mostrar el nombre, precio actual, precio tachado (si hay descuento), etiquetas de estado ("Nuevo", "Bestseller") y un botón para añadir al carrito.</li>
                <li>Ambas secciones deben incluir un botón secundario para "Ver todos los productos".</li>
            </ol>
            <b>Escenario 1 (Visualización de productos en descuento):</b> <br/>
            <ul>
                <li><b>Given</b> que el visitante revisa la sección de la Tienda,</li>
                <li><b>When</b> algun producto posee un descuento,</li>
                <li><b>Then</b> el sistema le muestra una etiqueta con el porcentaje de descuento, el precio rebajado en texto grande y el precio original tachado.</li>
            </ul>
        </td>
    </tr>
</table>

<table align="center">
    <tr>
        <td><b>User Story ID</b></td>
        <td>US45</b></td>
        <td><b>Epic ID</b></td>
        <td>EP06</b></td>
    </tr>
    <tr>
        <td><b>Título</b></td>
        <td colspan="3">Testimonios y Preguntas Frecuentes (FAQ)</b></td>
    </tr>
    <tr>
        <td><b>Descripción</b></td>
        <td colspan="3">Como visitante con dudas sobre la plataforma, quiero leer testimonios de otros usuarios y encontrar respuestas a preguntas comunes para ganar confianza y decidirme a crear una cuenta.</b></td>
    </tr>
    <tr>
        <td colspan="4">
            <b>Criterios de aceptación:</b> <br/>
            <ol>
                <li>La sección de testimonios debe mostrar 3 reseñas destacadas, incluyendo el nombre, rol, ciudad y calificación en estrellas del usuario.</li> 
                <li>La sección FAQ debe funcionar mediante un sistema de acordeón interactivo.</li>
                <li>Al hacer clic en una pregunta del FAQ, su respuesta debe desplegarse hacia abajo suavemente.</li>
                <li>Si el usuario abre una pregunta, cualquier otra pregunta que estuviese abierta debe cerrarse automáticamente para mantener la pantalla limpia.</li>
            </ol>
            <b>Escenario 1 (Interacción con el acordeón de Preguntas Frecuentes):</b> <br/>
            <ul>
                <li><b>Given</b> que el visitante está en la sección FAQ y todas las respuestas están ocultas,</li>
                <li><b>When</b> hace clic en alguna pregunta,</li>
                <li><b>Then</b> el sistema despliega la respuesta correspondiente y el ícono de la flecha rota 180 grados.</li>
            </ul>
            <b>Escenario 2 (Auto-cierre de respuestas en el FAQ):</b> <br/>
            <ul>
                <li><b>Given</b> que el visitante tiene abierta la primera pregunta del FAQ.,</li>
                <li><b>When</b> hace clic en otra pregunta,</li>
                <li><b>Then</b> la respuesta de la segunda pregunta se abre, y la respuesta de la primera pregunta se contrae y oculta automáticamente.</li>
            </ul>
        </td>
    </tr>
</table>

<table align="center">
<tr>
<td><b>User Story ID</b></td>
<td>US46</b></td>
<td><b>Epic ID</b></td>
<td>EP07</b></td>
</tr>
<tr>
<td><b>Título</b></td>
<td colspan="3">Autenticación Segura y Sesiones Activas</b></td>
</tr>
<tr>
<td><b>Descripción</b></td>
<td colspan="3">Como desarrollador, quiero implementar un sistema de inicio de sesión seguro que mantenga la sesión del usuario activa, para proteger sus datos personales y evitar que tenga que ingresar su correo y contraseña cada vez que entra a la plataforma.</b></td>
</tr>
<tr>
<td colspan="4">
<b>Criterios de aceptación:</b>

<ol>
<li>Las contraseñas de los usuarios deben guardarse de forma encriptada e ilegible en la base de datos.</li>
<li>Una vez que el usuario inicia sesión, el sistema debe recordarlo automáticamente durante varios días.</li>
<li>Si un usuario no registrado intenta entrar a una página privada (como el perfil o sus compras), el sistema debe redirigirlo a la pantalla de inicio de sesión.</li>
<li>El sistema debe diferenciar claramente entre un "Usuario" normal y un "Administrador", bloqueando opciones administrativas a usuarios comunes.</li>
</ol>
<b>Escenario 1 (Mantener la sesión):</b>

<ul>
<li><b>Given</b> que un usuario inició sesión ayer desde su celular y cerró el navegador,</li>
<li><b>When</b> vuelve a ingresar a la página web hoy,</li>
<li><b>Then</b> el sistema lo reconoce automáticamente y lo deja en su perfil sin pedirle la contraseña.</li>
</ul>
<b>Escenario 2 (Protección de rutas privadas):</b>

<ul>
<li><b>Given</b> que una persona sin cuenta tiene el enlace directo a un carrito de compras guardado,</li>
<li><b>When</b> intenta abrir ese enlace en su navegador,</li>
<li><b>Then</b> el sistema bloquea el acceso y le muestra la pantalla para iniciar sesión o registrarse.</li>
</ul>
</b></td>
</tr>
</table>

<table align="center">
<tr>
<td><b>User Story ID</b></td>
<td>US47</b></td>
<td><b>Epic ID</b></td>
<td>EP07</b></td>
</tr>
<tr>
<td><b>Título</b></td>
<td colspan="3">Automatización de Pruebas y Actualizaciones</b></td>
</tr>
<tr>
<td><b>Descripción</b></td>
<td colspan="3">Como desarrollador, quiero automatizar la revisión del código y la publicación de nuevas versiones, para asegurar que no se introduzcan errores cuando agregamos nuevas funciones y para que las actualizaciones lleguen más rápido a los usuarios.</b></td>
</tr>
<tr>
<td colspan="4">
<b>Criterios de aceptación:</b>

<ol>
<li>Todo código nuevo debe pasar por pruebas automáticas antes de poder unirse a la versión principal de la plataforma.</li>
<li>El sistema no debe permitir publicar cambios si las pruebas automáticas detectan que algo dejó de funcionar.</li>
<li>Una vez aprobados los cambios, el sistema debe publicarlos automáticamente en un entorno de pruebas para que el equipo los revise antes de lanzarlos al público.</li>
</ol>
<b>Escenario 1 (Bloqueo de código con errores):</b>

<ul>
<li><b>Given</b> que un desarrollador sube una nueva función para la tienda, pero contiene un error que rompe el carrito de compras,</li>
<li><b>When</b> el sistema automático revisa ese nuevo código,</li>
<li><b>Then</b> detecta la falla y bloquea la actualización, avisando al desarrollador para que lo corrija.</li>
</ul>
<b>Escenario 2 (Publicación ágil):</b>

<ul>
<li><b>Given</b> que se corrigió un texto en la landing page y pasó todas las revisiones,</li>
<li><b>When</b> el equipo aprueba el cambio,</li>
<li><b>Then</b> el sistema actualiza la página automáticamente sin que el equipo tenga que apagar o reiniciar los servidores manualmente.</li>
</ul>
</b></td>
</tr>
</table>

<table align="center">
<tr>
<td><b>User Story ID</b></td>
<td>US48</b></td>
<td><b>Epic ID</b></td>
<td>EP07</b></td>
</tr>
<tr>
<td><b>Título</b></td>
<td colspan="3">Respaldo de Datos y Alta Disponibilidad</b></td>
</tr>
<tr>
<td><b>Descripción</b></td>
<td colspan="3">Como administrador, quiero configurar copias de seguridad automáticas y garantizar que la plataforma siempre esté en línea, para no perder el progreso ni las compras de los usuarios ante cualquier falla del servidor.</b></td>
</tr>
<tr>
<td colspan="4">
<b>Criterios de aceptación:</b>

<ol>
<li>El sistema debe realizar una copia de seguridad automática de toda la base de datos al menos una vez al día, en un horario de poco tráfico (ej. madrugada).</li>
<li>Las copias de seguridad deben guardarse de forma segura durante al menos 30 días.</li>
<li>Si el servidor principal falla por algún motivo, un servidor de respaldo debe activarse automáticamente para que la página siga funcionando.</li>
</ol>
<b>Escenario 1 (Recuperación ante caídas):</b>

<ul>
<li><b>Given</b> que el servidor de base de datos principal sufre un apagón repentino,</li>
<li><b>When</b> el sistema detecta que no responde,</li>
<li><b>Then</b> activa el servidor de respaldo en menos de un minuto para que los usuarios puedan seguir usando la aplicación sin notar la caída.</li>
</ul>
<b>Escenario 2 (Restauración de información):</b>

<ul>
<li><b>Given</b> que por error humano se borraron datos importantes del catálogo a las 3:00 PM,</li>
<li><b>When</b> el administrador interviene,</li>
<li><b>Then</b> puede utilizar la copia de seguridad de la madrugada para restaurar la información perdida rápidamente.</li>
</ul>
</b></td>
</tr>
</table>

<table align="center">
<tr>
<td><b>User Story ID</b></td>
<td>US49</b></td>
<td><b>Epic ID</b></td>
<td>EP07</b></td>
</tr>
<tr>
<td><b>Título</b></td>
<td colspan="3">Monitoreo de Errores y Alertas del Sistema</b></td>
</tr>
<tr>
<td><b>Descripción</b></td>
<td colspan="3">Como desarrollador, quiero un sistema que registre los errores ocultos de la plataforma y me avise en tiempo real, para poder investigar y solucionar los problemas antes de que los usuarios se quejen o abandonen la página.</b></td>
</tr>
<tr>
<td colspan="4">
<b>Criterios de aceptación:</b>

<ol>
<li>El sistema debe guardar un registro automático cada vez que ocurra un error inesperado (pantalla en blanco, botón que no funciona, etc.).</li>
<li>Los registros de errores nunca deben incluir información privada del usuario, como sus contraseñas o números de tarjeta.</li>
<li>El sistema debe enviar una notificación urgente al equipo (por correo o chat) si los errores aumentan de golpe o si la página principal deja de cargar.</li>
</ol>
<b>Escenario 1 (Captura de un error silencioso):</b>

<ul>
<li><b>Given</b> que un usuario intenta abrir una simulación y la pantalla se queda cargando por un fallo interno,</li>
<li><b>When</b> ocurre ese error,</li>
<li><b>Then</b> el sistema guarda todos los detalles técnicos del problema de fondo y avisa al equipo de desarrollo para que lo arreglen en la siguiente actualización.</li>
</ul>
<b>Escenario 2 (Alerta de caída general):</b>

<ul>
<li><b>Given</b> que la página de la tienda deja de funcionar para todos los visitantes,</li>
<li><b>When</b> el sistema detecta múltiples fallos seguidos al intentar cargar los productos,</li>
<li><b>Then</b> envía una alerta inmediata con prioridad alta al celular o correo de los técnicos encargados.</li>
</ul>
</b></td>
</tr>
</table>

<table align="center">
<tr>
<td><b>User Story ID</b></td>
<td>US50</b></td>
<td><b>Epic ID</b></td>
<td>EP07</b></td>
</tr>
<tr>
<td><b>Título</b></td>
<td colspan="3">Optimización de Carga y Protección contra Saturación</b></td>
</tr>
<tr>
<td><b>Descripción</b></td>
<td colspan="3">Como desarrollador, quiero optimizar el tiempo que tardan en cargar las páginas y limitar las acciones repetitivas masivas, para que la plataforma sea muy rápida y esté protegida contra ataques informáticos o saturación por exceso de visitantes.</b></td>
</tr>
<tr>
<td colspan="4">
<b>Criterios de aceptación:</b>

<ol>
<li>La información que se consulta mucho y cambia poco (como la lista de productos de la tienda) debe guardarse en una memoria rápida para que cargue al instante.</li>
<li>Si se agrega un producto nuevo, esa memoria rápida debe actualizarse automáticamente.</li>
<li>El sistema debe bloquear temporalmente a cualquier usuario o robot que intente hacer demasiadas acciones por segundo (como intentar adivinar una contraseña muchas veces seguidas).</li>
</ol>
<b>Escenario 1 (Carga rápida del catálogo):</b>

<ul>
<li><b>Given</b> que cientos de personas entran a la tienda al mismo tiempo por una promoción,</li>
<li><b>When</b> cargan la lista de "Kits de Emergencia",</li>
<li><b>Then</b> el sistema les muestra la lista casi al instante sacándola de la memoria rápida, evitando que la base de datos colapse por el esfuerzo.</li>
</ul>
<b>Escenario 2 (Protección contra ataques):</b>

<ul>
<li><b>Given</b> que un programa malicioso intenta adivinar la contraseña de un administrador ingresando 20 palabras diferentes en 5 segundos,</li>
<li><b>When</b> el sistema detecta esta actividad anormal,</li>
<li><b>Then</b> bloquea temporalmente la conexión de esa persona o robot, protegiendo la cuenta.</li>
</ul>
</b></td>
</tr>
</table>
