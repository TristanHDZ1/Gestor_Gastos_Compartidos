# SplitWise Pro: Enterprise Expense Management System

SplitWise Pro es una plataforma robusta diseñada para la gestión y liquidación de gastos compartidos. El sistema se enfoca en la integridad transaccional, la escalabilidad mediante contenedores y la automatización de flujos financieros, resolviendo la complejidad de balances de saldos en entornos multiusuario.

---

## 1. Arquitectura del Sistema

El sistema implementa una arquitectura desacoplada diseñada para facilitar el mantenimiento y el despliegue continuo (CI/CD).

* **API Gateway:** Punto de entrada único que gestiona el ruteo hacia los servicios.
* **Business Logic (Backend):** Implementado con Java (Spring Boot) siguiendo principios de Clean Architecture.
* **Data Persistence:** PostgreSQL para garantizar el cumplimiento de propiedades ACID en transacciones financieras.
* **Infrastructure:** Orquestación de servicios mediante Docker y Docker Compose para asegurar paridad entre entornos.

---

## 2. Modelo de Datos (Esquema Relacional)

Para asegurar la integridad de los saldos, se ha diseñado el siguiente esquema en PostgreSQL:

* **Users:** Identidad y credenciales (id, username, email, password_hash).
* **Groups:** Entidades que agrupan usuarios (id, name, description, created_at).
* **Memberships:** Tabla relacional N:M entre Users y Groups con roles (user_id, group_id, role).
* **Expenses:** Registro de cada gasto (id, group_id, payer_id, amount, currency, description, date).
* **Debts:** Tabla de cálculo de saldos (id, debtor_id, creditor_id, amount, status).

---

## 3. Especificaciones Funcionales

### Motor de Liquidación de Deudas
* Implementación de algoritmos de optimización para minimizar el flujo de transferencias entre miembros del grupo.
* Soporte para múltiples criterios de división: equitativo, porcentual y por montos específicos.

### Integración de Servicios y Seguridad
* Sincronización con APIs de divisas para la conversión automática de moneda en tiempo real.
* Autenticación basada en estándares JWT (JSON Web Tokens) y Control de Acceso Basado en Roles (RBAC).
* Registro de auditoría (Audit Log) para el seguimiento de modificaciones en registros de gastos.

---

## 4. Stack Tecnológico

| Capa | Tecnología Seleccionada |
| :--- | :--- |
| Backend | Java (Spring Boot) |
| Base de Datos | PostgreSQL |
| Cache / Queue | Redis (para tipos de cambio y sesiones) |
| DevOps | Docker, Docker Compose, GitHub Actions |
| Documentación | OpenAPI / Swagger |

---

## 5. Guía de Despliegue Local

El proyecto está configurado para ser ejecutado en cualquier entorno con Docker instalado:

1. **Clonación del repositorio:**
   ```bash
   git clone [https://github.com/tu-usuario/splitwise-pro.git](https://github.com/tu-usuario/splitwise-pro.git)
   cd splitwise-pro
