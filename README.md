<p align="center">
  <img src="./static/img/logo-green.png" alt="MediFast logo" width="260"/>
</p>

<h1 align="center">MediFast · Backend</h1>

<p align="center">
  API REST y panel administrativo para la dispensación digital de medicamentos.<br/>
  <sub>REST API and admin dashboard for digital medication dispensing.</sub>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/type-Degree%20project-22C55E?style=flat" alt="Degree project"/>
  <img src="https://img.shields.io/badge/license-All%20rights%20reserved-6B7280?style=flat" alt="All rights reserved"/>
  <img src="https://img.shields.io/badge/year-2025-495057?style=flat" alt="2025"/>
</p>

<p align="center">
  <a href="#español">Español</a> · <a href="#english">English</a> ·
  <a href="https://github.com/Drey0911/TG-MediFast-Dispensario-FRONTEND">App móvil · Mobile app</a>
</p>

## Tech stack

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.8%2B-3776AB?style=flat&logo=python&logoColor=white" alt="Python"/>
  <img src="https://img.shields.io/badge/Flask-2.3-000000?style=flat&logo=flask&logoColor=white" alt="Flask"/>
  <img src="https://img.shields.io/badge/SQLAlchemy-ORM-D71F00?style=flat&logo=sqlalchemy&logoColor=white" alt="SQLAlchemy"/>
  <img src="https://img.shields.io/badge/MySQL-Database-4479A1?style=flat&logo=mysql&logoColor=white" alt="MySQL"/>
  <img src="https://img.shields.io/badge/Jinja2-Admin%20panel-B41717?style=flat&logo=jinja&logoColor=white" alt="Jinja2"/>
  <br/>
  <img src="https://img.shields.io/badge/JWT-Auth-000000?style=flat&logo=jsonwebtokens&logoColor=white" alt="JWT"/>
  <img src="https://img.shields.io/badge/Socket.IO-Realtime-010101?style=flat&logo=socketdotio&logoColor=white" alt="Socket.IO"/>
  <img src="https://img.shields.io/badge/APScheduler-Jobs-2F855A?style=flat" alt="APScheduler"/>
  <img src="https://img.shields.io/badge/WhatsApp%20Business-API-25D366?style=flat&logo=whatsapp&logoColor=white" alt="WhatsApp Business API"/>
  <img src="https://img.shields.io/badge/Gemini-Chatbot-8E75B2?style=flat&logo=googlegemini&logoColor=white" alt="Gemini"/>
</p>

## Screenshots

<table>
  <tr>
    <td width="50%" align="center">
      <img src="https://drey.is-a.dev/img/projects/project2/project2-6.png" alt="Dashboard"/>
      <br/><b>Dashboard</b><br/><sub>Resumen de usuarios, medicamentos, sedes y recolecciones</sub>
    </td>
    <td width="50%" align="center">
      <img src="https://drey.is-a.dev/img/projects/project2/project2-7.png" alt="Medication details"/>
      <br/><b>Detalle de medicamento · Medication details</b><br/><sub>Información, imagen y acciones rápidas</sub>
    </td>
  </tr>
</table>

---

## Español

> MediFast es el proyecto de grado tecnológico para gestionar un dispensario de medicamentos: inventario por sede, agenda de recolecciones y recordatorios automáticos por WhatsApp. Este repositorio contiene la API que consume la app móvil y el panel web de administración.

### Funcionalidades

| Área | Descripción |
|---|---|
| **API REST** | Usuarios, medicamentos, disponibilidad por sede, recolecciones y favoritos. |
| **Panel admin** | Dashboard web con Jinja2 para gestionar medicamentos, sedes, disponibilidad, recolecciones y usuarios. |
| **Tiempo real** | WebSockets (Flask-SocketIO) para reflejar cambios de stock, recolecciones y usuarios al instante. |
| **Tareas programadas** | APScheduler envía recordatorios diarios y monitorea el stock. |
| **WhatsApp** | Notificaciones de disponibilidad, recordatorios, cambios de estado y cambio de contraseña. |
| **Chatbot (beta)** | Consulta de medicamentos disponibles con Gemini. |
| **Seguridad** | JWT en todas las rutas de la API excepto login y registro. |

### Cómo ejecutarlo

1. Requisitos: **Python 3.8+** y MySQL (local o en la nube). Las tablas se crean solas.
2. Instala dependencias:
   ```bash
   pip install -r requirements.txt
   ```
3. Crea un `.env` en la raíz con `DB_HOST`, `DB_USER`, `DB_PASSWORD`, `DB_NAME`, `JWT_SECRET_KEY`, `WHATSAPP_API_URL`, `WHATSAPP_API_TOKEN`, `WHATSAPP_PHONE_ID`, `PORT=8000` y, para el chatbot, `GEMINI_API_KEY` y `GEMINI_API_URL`.
4. Ejecuta:
   ```bash
   python app.py
   ```

> [!TIP]
> Para probar con la app móvil en local, expón el puerto con `ngrok http 8000` y pega la URL en `config/apiBase.ts` del frontend.

> [!NOTE]
> WhatsApp funciona con el número de prueba de Meta: el usuario debe escribir primero para abrir la ventana de 24 horas. En producción se necesita la API verificada con plantillas.

### Estructura

```
app.py               Punto de entrada
config/              Conexión a la base de datos
models/              Modelos SQLAlchemy
routes/              Rutas de la API y del panel admin
services/            Lógica de negocio, recordatorios y WhatsApp
templates/  static/  Panel de administración (Jinja2)
socketsExtends.py    Configuración de WebSockets
```

---

## English

> MediFast is a technologist degree project to run a medication dispensary: inventory per branch, pickup scheduling and automatic WhatsApp reminders. This repository contains the API used by the mobile app and the web admin dashboard.

### Features

| Area | Description |
|---|---|
| **REST API** | Users, medications, availability per branch, pickups and favorites. |
| **Admin panel** | Jinja2 web dashboard to manage medications, branches, availability, pickups and users. |
| **Real time** | WebSockets (Flask-SocketIO) to reflect stock, pickup and user changes instantly. |
| **Scheduled jobs** | APScheduler sends daily reminders and monitors stock. |
| **WhatsApp** | Notifications for availability, reminders, status changes and password changes. |
| **Chatbot (beta)** | Ask for available medications, powered by Gemini. |
| **Security** | JWT on every API route except login and sign-up. |

### Getting started

1. Requirements: **Python 3.8+** and MySQL (local or cloud). Tables are created automatically.
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Create a `.env` file with `DB_HOST`, `DB_USER`, `DB_PASSWORD`, `DB_NAME`, `JWT_SECRET_KEY`, `WHATSAPP_API_URL`, `WHATSAPP_API_TOKEN`, `WHATSAPP_PHONE_ID`, `PORT=8000` and, for the chatbot, `GEMINI_API_KEY` and `GEMINI_API_URL`.
4. Run:
   ```bash
   python app.py
   ```

> [!TIP]
> To test with the mobile app locally, expose the port with `ngrok http 8000` and paste the URL into the frontend's `config/apiBase.ts`.

## ChatBOT (Simple BETA)

**Config .env**: Add .env la GEMINI_API_KEY y GEMINI_API_URL para usar el LLM de gemini 

### API Routes

| Módulo / Module | Método | Endpoint | Descripción / Description |
| :--- | :---: | :--- | :--- |
| **ChatBot** | `GET` | `/api/chatbot/medicamentos-disponibles` | Get medications within the chatbot |
| **ChatBot** | `GET` | `/api/chatbot/mensaje` | Send message to bot |
| **Users** | `GET` | `/api/users` | Get all users |
| **Users** | `GET` | `/api/users/<id>` | Get a user by ID |
| **Users** | `POST` | `/api/users` | Create a new user |
| **Users** | `PUT` | `/api/users/<id>` | Update a user |
| **Users** | `DELETE` | `/api/users/<id>` | Delete a user |
| **Users** | `POST` | `/api/users/login` | User authentication (generates a JWT token) |
| **Users** | `POST` | `/api/users/register` | Register a new user |
| **Users** | `GET` | `/api/me` | Get the currently authenticated user in the active session |
| **Medicines** | `GET` | `/api/medicamentos` | Get all medicines |
| **Medicines** | `GET` | `/api/medicamentos/<id>` | Get a medicine by ID |
| **Medicines** | `POST` | `/api/medicamentos` | Create a new medicine |
| **Medicines** | `PUT` | `/api/medicamentos/<id>` | Update a medicine |
| **Medicines** | `DELETE` | `/api/medicamentos/<id>` | Delete a medicine |
| **Medicines** | `GET` | `/api/medicamentos/search` | Search medicines by name or description |
| **Availability**| `GET` | `/api/disponibilidad` | Get all availability records |
| **Availability**| `GET` | `/api/disponibilidad/<id>` | Get an availability record by ID |
| **Availability**| `POST` | `/api/disponibilidad` | Create a new availability record |
| **Availability**| `PUT` | `/api/disponibilidad/<id>` | Update an availability record |
| **Availability**| `DELETE` | `/api/disponibilidad/<id>` | Delete an availability record |
| **Collections** | `GET` | `/api/recolecciones` | Get all collections |
| **Collections** | `GET` | `/api/recolecciones/<id>` | Get a collection by ID |
| **Collections** | `POST` | `/api/recolecciones` | Create a new collection |
| **Collections** | `PUT` | `/api/recolecciones/<id>` | Update a collection |
| **Collections** | `DELETE` | `/api/recolecciones/<id>` | Delete a collection |
| **Favorites** | `GET` | `/api/favoritos/user/<user_id>` | Get a user's favorites |
| **Favorites** | `POST` | `/api/favoritos` | Add a medicine to favorites |
| **Favorites** | `DELETE` | `/api/favoritos/<id>` | Remove a favorite |

### Administration Panel Routes

| Área / Area | Endpoint | Descripción / Description |
| :--- | :--- | :--- |
| **Dashboard** | `/` | Main dashboard |
| **Auth** | `/login` | Administrator login |
| **Medicines** | `/medicamentos` | Medicine management |
| **Medicines** | `/medicamentos/add` | Add a new medicine |
| **Medicines** | `/medicamentos/edit/<id>` | Edit a medicine |
| **Medicines** | `/medicamentos/view/<id>` | View medicine details |
| **Availability**| `/disponibilidad` | Availability management |
| **Availability**| `/disponibilidad/add` | Add a new availability record |
| **Availability**| `/disponibilidad/edit/<id>` | Edit availability |
| **Collections** | `/recolecciones` | Collection management |
| **Collections** | `/recolecciones/edit/<id>` | Edit a collection |
| **Branches** | `/sedes` | Branch management |
| **Branches** | `/sedes/add` | Add a new branch |
| **Branches** | `/sedes/edit/<id>` | Edit a branch |
| **Users** | `/users` | User management |
| **Users** | `/users/add` | Add a new user |
| **Users** | `/users/edit/<id>` | Edit a user |

## Security

All API routes require JWT token authentication, except for login routes. The token must be included in the request header as `Authorization: Bearer <token>`. If you want to test it with Postman or another tool, you must first log in through `/api/login`.

## WebSockets

The system uses WebSockets to provide real-time updates on:
- Changes in medicine availability
- New collections
- Updates to collection status
- User updates or real-time modifications
- Tasks and views in real time (medicines, collections, users, etc...)

## Scheduled Services

The system uses APScheduler to run scheduled tasks:
- Daily reminder delivery for pending collections
- Medicine stock monitoring
- Automatic availability notifications

## WhatsApp Integration

The system integrates with the [WhatsApp Business API](https://developers.facebook.com/docs/whatsapp/api/overview) to send automatic notifications to users about:
- Medicine availability
- Collection reminders
- Changes in collection status
- Password changes

( It is recommended to use the verified API in production, using templates for functionality. Currently, the test WhatsApp number is used and a message must be written beforehand for sending within the 24-hour window. This is only for development or prototype mode in a real environment; the verified WhatsApp Business API would be required.)

## Default Administrator User

To use the application correctly for testing, we provide a default user:

DNI: 10101010
Password: Admin.123456789

In your local or deployed database engine, paste the following SQL statement in the SQL editor or creation section:

INSERT INTO `usuarios` (`id`, `nombre`, `apellidos`, `dni`, `telefono`, `password`, `rol`) VALUES
(1, 'MediFast', 'Dispensario', '10101010', '+573000000000', '$2b$12$8uNWOICxpZPmFb84U.8D9eGiGslHPHUd4aDT9.uvjTs9ZT1tBnvYG', 'admin');

---

## Licencia · License

Todos los derechos reservados · All rights reserved. © 2025 Andrey Stteven Mantilla Leon y Daniel Esteban Pinzon Cardenas. No puede ser reproducido, distribuido o utilizado sin autorización expresa · It may not be reproduced, distributed or used without express permission.
