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

---

## Licencia · License

Todos los derechos reservados · All rights reserved. © 2025 Andrey Stteven Mantilla Leon y Daniel Esteban Pinzon Cardenas. No puede ser reproducido, distribuido o utilizado sin autorización expresa · It may not be reproduced, distributed or used without express permission.
