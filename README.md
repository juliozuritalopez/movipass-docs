<div align="center">

# 🚌 MoviPass

### Un proyecto. Todo el recorrido.

**Documentación de una aplicación web para la gestión y venta de pasajes interprovinciales en Ecuador.**

Universidad Técnica de Ambato · FISEI · Carrera de Software  
Manejo y Configuración de Software

[![Documentación web](https://img.shields.io/badge/ABRIR_DOCUMENTACI%C3%93N_WEB-1765AD?style=for-the-badge&logo=github&logoColor=white)](https://juliozuritalopez.github.io/movipass-docs/)
[![Código fuente](https://img.shields.io/badge/VER_C%C3%93DIGO_FUENTE-142D43?style=for-the-badge&logo=github&logoColor=white)](https://github.com/kmoyolema3929/MoviPass)
[![Aplicación](https://img.shields.io/badge/IR_A_LA_APLICACI%C3%93N-206B4A?style=for-the-badge&logo=netlify&logoColor=white)](https://movipass.netlify.app)

---

[El proyecto](#proyecto) · [Roles](#roles) · [Tecnologías](#tecnologias) · [Instalación](#instalacion) · [Datos](#datos) · [Documentos](#documentos) · [Equipo](#equipo)

</div>

> **Acerca de este repositorio:** aquí se presenta la documentación de MoviPass. El código de la aplicación y los documentos originales se mantienen en [kmoyolema3929/MoviPass](https://github.com/kmoyolema3929/MoviPass).

<a id="proyecto"></a>
## 🌎 El proyecto

**MoviPass conecta la administración del transporte con el proceso de compra de un pasaje.** El proyecto contempla la gestión de buses, frecuencias y hojas de ruta para las cooperativas, y la búsqueda de viajes, elección de asientos y obtención de boletos con código QR para los viajeros.

<table>
<tr>
<td width="50%" valign="top">
<h3>🏢 Para las cooperativas</h3>
<p>Organizar vehículos, rutas, horarios, precios y la operación de venta de boletos.</p>
</td>
<td width="50%" valign="top">
<h3>🎒 Para los viajeros</h3>
<p>Consultar opciones de viaje y recorrer el proceso de compra hasta la consulta del boleto.</p>
</td>
</tr>
</table>

El alcance se resume a partir del README y la documentación del equipo. El estado de implementación de las tareas se consulta en [Issues](https://github.com/kmoyolema3929/MoviPass/issues) y [Pull requests](https://github.com/kmoyolema3929/MoviPass/pulls).

<a id="roles"></a>
## 👥 Roles y funcionamiento

| Rol | Responsabilidad descrita |
| :--- | :--- |
| **Administrador** | Crea cooperativas y su usuario gerente. |
| **Cooperativa** | Gestiona buses, frecuencias, rutas y precios. |
| **Oficinista** | Vende boletos y aprueba comprobantes de pago. |
| **Usuario final** | Busca viajes, compra boletos y consulta su historial. |
| **Usuario bus** | Valida boletos y realiza cobros en ruta. |

### 🎫 Recorrido de compra

| 🔎 01 · Buscar | 💺 02 · Elegir | 💳 03 · Pagar | 🎟️ 04 · Consultar |
| :--- | :--- | :--- | :--- |
| Consultar las opciones de viaje. | Seleccionar el viaje y el asiento. | Registrar el pago y continuar con la revisión del comprobante. | Obtener el boleto con código QR para su validación. |

<a id="tecnologias"></a>
## 🧰 Tecnologías y arquitectura

<div align="center">

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS](https://img.shields.io/badge/CSS-1572B6?style=for-the-badge&logo=css&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Bootstrap](https://img.shields.io/badge/Bootstrap_5-7952B3?style=for-the-badge&logo=bootstrap&logoColor=white)
![Supabase](https://img.shields.io/badge/Supabase-3ECF8E?style=for-the-badge&logo=supabase&logoColor=142D43)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)

</div>

| Capa o componente | Tecnología | Función |
| :--- | :--- | :--- |
| Interfaz | HTML5, CSS3, JavaScript y Bootstrap 5 | Pantallas y recursos del frontend. |
| Datos | PostgreSQL en Supabase | Base de datos relacional. |
| Autenticación | Supabase Auth | Gestión de sesiones y autenticación. |
| Archivos | Supabase Storage | Comprobantes y fotos de buses. |
| Acceso a datos | supabase-js | Comunicación entre la interfaz y Supabase. |
| Migraciones | Supabase CLI | Cambios versionados de la base de datos. |
| Boletos | Librería JavaScript qrcode | Generación del código QR. |
| Aplicación publicada | Netlify | Despliegue del frontend desde la rama estable, según la decisión D-008. |
| Documentación web | GitHub Pages | Publicación de la página de documentación de este repositorio. |

📌 Las decisiones del equipo se registran en [DECISIONES.md](https://github.com/kmoyolema3929/MoviPass/blob/develop/docs/DECISIONES.md).

<details>
<summary><b>📂 Ver estructura del repositorio de la aplicación</b></summary>

| Carpeta | Contenido |
| :--- | :--- |
| `frontend/` | Páginas HTML, estilos, JavaScript e imágenes. |
| `supabase/` | Migraciones y datos de prueba en SQL. |
| `scripts/` | Scripts relacionados con el despliegue. |
| `docs/` | Documentación técnica y capturas. |
| `.github/` | Plantillas y configuración de colaboración. |

</details>

<a id="instalacion"></a>
## ⚙️ Instalación local de la aplicación

**Requisitos:** Git, VS Code con Live Server y acceso al proyecto de Supabase del equipo. Node.js se utiliza para las tareas de la Supabase CLI.

### 1. Clonar el proyecto

```bash
git clone https://github.com/kmoyolema3929/MoviPass.git
cd MoviPass
git checkout develop
```

### 2. Configurar la conexión del frontend

Duplica `frontend/js/config.example.js` y nombra la copia `config.js` en la misma carpeta. En macOS o Linux:

```bash
cp frontend/js/config.example.js frontend/js/config.js
```

Completa `SUPABASE_URL` y `SUPABASE_ANON_KEY` con la configuración proporcionada por el equipo, respetando el formato del archivo de ejemplo.

### 3. Ejecutar con Live Server

1. Abre la carpeta `frontend/` en VS Code.
2. Dentro de `frontend/pages/`, haz clic derecho sobre la página que quieras probar.
3. Selecciona **Open with Live Server**.
4. Abre la dirección local indicada por la extensión.

> **Configuración del equipo:** según las reglas del repositorio, `config.js` y `.env` permanecen fuera de Git. No publiques contraseñas, tokens ni claves de servicio.

<details>
<summary><b>🗃️ Si también vas a trabajar con migraciones</b></summary>

Esta tarea requiere el acceso proporcionado a la persona responsable de la base de datos. Copia `.env.example` como `.env` y sigue la [guía de migraciones](https://github.com/kmoyolema3929/MoviPass/blob/develop/docs/MIGRACIONES.md) para vincular el proyecto y aplicar cambios.

Para crear un archivo de migración:

```bash
npx supabase migration new nombre_descriptivo
```

Los cambios se versionan dentro de `supabase/migrations/`. No se edita una migración ya aplicada: las correcciones se registran en una nueva.

</details>

<a id="datos"></a>
## 🗄️ Modelo de datos

| Área del diseño | Entidades documentadas |
| :--- | :--- |
| Usuarios y avisos | `perfiles`, `notificaciones` |
| Transporte | `cooperativas`, `buses`, `tipos_bus`, `asientos` |
| Planificación | `frecuencias`, `paradas`, `hojas_ruta` |
| Operación y venta | `viajes`, `boletos`, `pasajeros`, `pagos` |

<details>
<summary><b>📐 Ver convenciones del modelo</b></summary>

- Tablas en español, en plural y con nombres `snake_case`.
- Clave primaria `id` de tipo `uuid`.
- Claves foráneas como `bus_id` y `viaje_id`.
- Fechas de tipo `timestamptz`, con nombres como `creado_en` y `salida_en`.
- RLS activado en cada tabla nueva, con políticas de acceso definidas en su migración.

</details>

📄 [Ver modelo documentado](https://github.com/kmoyolema3929/MoviPass/blob/develop/docs/MODELO_DATOS.md) · [Revisar migraciones del proyecto](https://github.com/kmoyolema3929/MoviPass/tree/develop/supabase)

<a id="flujo"></a>
## 🔀 Flujo de trabajo del equipo

En el **repositorio de la aplicación**, el equipo utiliza Gitflow, Conventional Commits y revisión por el comité de control de cambios.

| Etapa | Acción |
| :--- | :--- |
| **1 · Registrar** | Definir la tarea en un issue con responsable, etiquetas y milestone. |
| **2 · Desarrollar** | Crear una rama `feature/*` desde `develop` y registrar los cambios. |
| **3 · Revisar** | Abrir un pull request hacia `develop` y vincular el issue real. |
| **4 · Integrar** | Obtener la aprobación, resolver conversaciones y usar **Create a merge commit**. |

<details>
<summary><b>🌿 Ver ramas y formato de commits</b></summary>

| Rama | Uso |
| :--- | :--- |
| `main` | Versiones estables. |
| `develop` | Integración y rama predeterminada. |
| `feature/*` | Funcionalidades, correcciones y documentación. |
| `release/*` | Preparación de versiones; se integra en `main` y `develop`. |
| `hotfix/*` | Corrección urgente de una versión estable; se integra en `main` y `develop`. |

Formato: `tipo(ámbito): descripción`.

Ejemplo:

```text
docs(docs): actualizar documentacion del proyecto
```

El pull request incluye `Closes #N`, sustituyendo `N` por el número real del issue. El comité está formado por **Katherine Moyolema y Anahi Molina**. Nadie aprueba su propio PR y las ramas se conservan como evidencia del trabajo.

Consulta [CONTRIBUTING.md](https://github.com/kmoyolema3929/MoviPass/blob/develop/CONTRIBUTING.md) y [FLUJO_GIT.md](https://github.com/kmoyolema3929/MoviPass/blob/develop/docs/FLUJO_GIT.md).

</details>

<a id="documentos"></a>
## 📚 Documentos y evidencias

| Recurso | Contenido |
| :--- | :--- |
| [📘 README original](https://github.com/kmoyolema3929/MoviPass) | Presentación y organización del proyecto. |
| [🧭 Decisiones técnicas](https://github.com/kmoyolema3929/MoviPass/blob/develop/docs/DECISIONES.md) | Contexto, alternativas y decisiones del equipo. |
| [📝 Control de cambios](https://github.com/kmoyolema3929/MoviPass/blob/develop/docs/CONTROL_DE_CAMBIOS.md) | Seguimiento y trazabilidad de las solicitudes. |
| [🗄️ Modelo de datos](https://github.com/kmoyolema3929/MoviPass/blob/develop/docs/MODELO_DATOS.md) | Entidades, convenciones y permisos por rol. |
| [🛠️ Migraciones](https://github.com/kmoyolema3929/MoviPass/blob/develop/docs/MIGRACIONES.md) | Gestión de los cambios en la base de datos. |
| [📸 Capturas y evidencias](https://github.com/kmoyolema3929/MoviPass/tree/develop/docs/capturas) | Evidencias organizadas por módulos y tareas. |
| [📋 Historial de cambios](https://github.com/kmoyolema3929/MoviPass/blob/develop/CHANGELOG.md) | Registro de cambios del proyecto. |

<a id="equipo"></a>
## 🤝 Equipo de desarrollo

| Integrante | Rol de gestión |
| :--- | :--- |
| **Katherine Moyolema** | Líder · Desarrollo · Comité de cambios |
| **Anahi Molina** | Desarrollo · Comité de cambios |
| **Alisson Paredes** | Documentación · Desarrollo |
| **Alina Ortiz** | Documentación · Desarrollo |
| **Mateo Herrera** | Documentación · Desarrollo |
| **Julio Zurita** | Documentación · Desarrollo |

---

<div align="center">

**MoviPass · Documentación del proyecto**  
Universidad Técnica de Ambato · FISEI · Carrera de Software

[Documentación web](https://juliozuritalopez.github.io/movipass-docs/) · [Repositorio original](https://github.com/kmoyolema3929/MoviPass) · [Licencia del proyecto: GPL v3](https://github.com/kmoyolema3929/MoviPass/blob/develop/LICENSE)

<sub>Adaptado de la documentación de la rama develop consultada el 30 de octubre de 2026.</sub>

</div>
