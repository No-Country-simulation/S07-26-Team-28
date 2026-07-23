# S07-26-Team-28


Arquitectura del Proyecto

Para este proyecto se utilizará un stack completamente basado en Node.js, con el objetivo de mantener una arquitectura simple, consistente y fácil de escalar.

Tecnologías
Backend: NestJS + TypeScript
Base de datos: PostgreSQL
Cache y colas: Redis + BullMQ
Generación de PDF: Puppeteer
Autenticación: JWT + captura de email
ORM: Prisma
Despliegue: Docker + ambiente de Staging
Justificación

Se utilizará NestJS como API Gateway para centralizar toda la lógica del sistema y conectar la calculadora, el benchmark, el generador de PDF y el sistema de outreach.

PostgreSQL almacenará toda la información del benchmark, calculadora, usuarios y campañas de outreach, mientras que Redis junto con BullMQ administrará las tareas en segundo plano, como la generación de PDFs y el envío de invitaciones.

El PDF Generator se desarrollará con Puppeteer, ya que ofrece un control completo sobre HTML y CSS, permitiendo generar documentos institucionales con el branding de la empresa.

El cálculo de KPIs, scoring y percentiles se implementará directamente en TypeScript, ya que son operaciones matemáticas simples y no requieren un servicio adicional en Python. Si en el futuro se incorporan modelos de Machine Learning o análisis avanzados, se podrá añadir un microservicio independiente sin modificar la arquitectura principal.

Este enfoque permite compartir modelos, tipos y lógica entre la API y los workers, reduciendo la duplicación de código y facilitando el mantenimiento del sistema.
