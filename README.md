SplitWise Pro: Enterprise Expense Management System
SplitWise Pro es una plataforma robusta diseñada para la gestión y liquidación de gastos compartidos en grupos de usuarios. El sistema se enfoca en la integridad transaccional, la escalabilidad mediante contenedores y la automatización de flujos financieros, resolviendo problemas de balance de saldos en entornos multiusuario.

Demo en vivo | Documentación de API

Arquitectura del Sistema
El sistema implementa una arquitectura desacoplada diseñada para facilitar el mantenimiento y el despliegue continuo:

Frontend: Desarrollado en React.js con gestión de estado centralizada.

Backend: API REST construida bajo principios de arquitectura limpia (Clean Architecture).

Base de Datos: PostgreSQL para garantizar el cumplimiento de propiedades ACID en todas las transacciones financieras.

Cache: Implementación de Redis para la optimización de consultas de tipos de cambio y sesiones de usuario.

Infraestructura: Orquestación de servicios mediante Docker y Docker Compose para entornos de desarrollo y producción.

Especificaciones Funcionales
Motor de Liquidación de Deudas

Implementación de algoritmos de optimización de grafos para minimizar el flujo de transferencias entre miembros del grupo.

Soporte para múltiples criterios de división: equitativo, porcentual y por montos específicos.

Integración de Servicios Externos

Sincronización con APIs bancarias o de divisas para la conversión automática de moneda en tiempo real.

Motor de notificaciones asíncronas para el recordatorio de saldos pendientes y confirmación de pagos.

Seguridad y Auditoría

Autenticación basada en estándares JWT (JSON Web Tokens).

Sistema de Control de Acceso Basado en Roles (RBAC).

Registro de auditoría inmutable para el seguimiento de modificaciones en registros de gastos.

Stack Tecnológico
Capa	Tecnología Seleccionada
Backend	Spring Boot (Java) / Node.js
Frontend	React.js / TypeScript
Base de Datos	PostgreSQL
DevOps	Docker, GitHub Actions (CI/CD)
Monitoreo	Prometheus / Grafana
Guía de Despliegue Local
El proyecto está configurado para ser ejecutado en cualquier entorno con Docker instalado:

Clonación del repositorio:

Bash
git clone https://github.com/tu-usuario/splitwise-pro.git
cd splitwise-pro
Configuración de entorno:
Definir las variables necesarias en el archivo .env.example y renombrarlo a .env.

Ejecución de servicios:

Bash
docker-compose up -d
Roadmap de Desarrollo
Fase 1: Persistencia de datos y motor básico de balance.

Fase 2: Implementación de microservicio de notificaciones y reportes PDF.

Fase 3: Integración con pasarelas de pago (Stripe Connect).

Fase 4: Optimización de infraestructura para despliegue en Kubernetes.

Autores
Cruz Hernandez Tristan Javier
Lopez Garcia Said Eduardo
