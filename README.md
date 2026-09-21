# Cuaderno Digital / Pizarra Online 🎨📚

Aplicación web interactiva y colaborativa en tiempo real diseñada como un cuaderno digital y pizarra virtual avanzada. Permite a múltiples usuarios crear, organizar y editar pizarras simultáneamente con herramientas profesionales de dibujo, gestión de proyectos y control de acceso.

se puede probar en https://cuaderno-digital-1.onrender.com

---

## 🚀 Tecnologías Principales (Stack)

- **Backend:** Node.js, Express, Socket.io (WebSockets).
- **Base de Datos:** MongoDB (con Mongoose).
- **Autenticación y Seguridad:** JSON Web Tokens (JWT), bcryptjs para encriptación de contraseñas.
- **Frontend:** HTML5 Canvas, CSS3, JavaScript (Vanilla), PDF.js (renderizado de documentos PDF).

---

## ⭐ Funcionalidades Importantes

### 1. Sistema de Autenticación y Seguridad
- **Registro e Inicio de Sesión:** Cuentas de usuario protegidas con contraseñas encriptadas mediante `bcryptjs` y sesiones manejadas con tokens JWT (expiración de 7 días).
- **Gestión de Perfil:** Opción segura para cambiar la contraseña actual desde el panel de usuario.
- **Control de Acceso por Roles:** Las salas/pizarras tienen un **propietario (dueño)** y **invitados**. Los invitados deben solicitar acceso y esperar la aprobación en tiempo real del dueño de la sala.

### 2. Gestión de Proyectos y Organización por Carpetas
- **Dashboard Personal (`index.html`):** Visualización de todas las pizarras creadas en una cuadrícula moderna.
- **Organización en Carpetas:** Clasificación de proyectos por carpetas personalizadas (ej. *Principal*, *Álgebra*, *General*, etc.) con filtrado dinámico desde la barra lateral.
- **Operaciones CRUD:** Renombrar pizarras, cambiar de carpeta, eliminar proyectos y **clonar copias** (permite a los invitados guardar una copia personal de una sala colaborativa en su cuenta).

### 3. Colaboración Multijugador en Tiempo Real (Socket.io)
- **Sincronización Instantánea:** Todos los trazos, formas, textos e imágenes se actualizan en tiempo real para todos los participantes de la sala.
- **Cursores Fantasma:** Visualización en vivo de la posición y nombre de los colaboradores conectados en la pizarra.
- **Modo Seguimiento:** Posibilidad de seguir la vista y el cursor de cualquier usuario activo en tiempo real.
- **Aprobación de Invitados:** Notificaciones flotantes (toasts) para que el dueño de la sala acepte o rechace la entrada de nuevos usuarios.

### 4. Herramientas Avanzadas de Dibujo y Pizarra
- **Lápiz y Goma:** Trazos fluidos con control de color y grosor de línea ajustable.
- **Puntero Láser:** Herramienta de anotación temporal en tiempo real con efecto brillante y desvanecimiento automático.
- **Notas Adhesivas (Sticky Notes):** Creación de notas de colores con ajuste automático de texto.
- **Texto Flotante:** Inserción y edición de texto tipográfico directamente sobre el lienzo.
- **Formas Geométricas Inteligentes:** Popup flotante adaptativo con selección de líneas, flechas, rectángulos (normales y redondeados), círculos/elipses, rombos, triángulos y estrellas.

### 5. Importación y Procesamiento Multimedia
- **Subida de Imágenes:** Compresión automática y posicionamiento dinámico de imágenes en el lienzo.
- **Importación de PDFs:** Carga y conversión de documentos PDF multipágina directamente en la pizarra utilizando **PDF.js**, ordenando las páginas verticalmente.
- **Herramienta de Recorte (Crop):** Selección de áreas específicas de imágenes o PDFs para recortar y conservar sólo la sección deseada.

### 6. Navegación, Minimapa y Capas
- **Minimapa Interactivo:** Vista general en miniatura del lienzo completo con indicador de la cámara actual y navegación mediante clics.
- **Zoom y Pandeo (Pan):** Desplazamiento fluido por el lienzo infinito y zoom mediante rueda del mouse o gestos táctiles (pinch).
- **Control de Capas y Historial:** Opciones para traer elementos al frente o enviar al fondo, además de un sistema robusto de **Deshacer (Undo)** y **Rehacer (Redo)** (Ctrl+Z / Ctrl+Y).
- **Exportación:** Función para exportar la pizarra completa a formato JPG de alta calidad centrada en el contenido.

---

## 🛠️ Instalación y Configuración

1. **Clonar el repositorio e instalar dependencias:**
   ```bash
   npm install
   ```

2. **Configurar las variables de entorno:**
   Crea un archivo `.env` en la raíz del proyecto con la siguiente estructura:
   ```env
   PORT=3000
   MONGO_URI=tu_cadena_de_conexion_mongodb
   JWT_SECRET=tu_llave_secreta_jwt
   ```

3. **Ejecutar el servidor:**
   ```bash
   npm start
   ```
   Abre tu navegador en `http://localhost:3000`.
