# Bootcamp Back - API Contracts

Este repositorio contiene los contratos de APIs síncronas (OpenAPI) y asíncronas (AsyncAPI) del sistema bancario distribuido desarrollado como parte del bootcamp profesional impartido por **Ninkovski**.

## 📦 Estructura del Proyecto

```bash
/resources
  ├── schemas/                  # Schemas comunes reutilizables
  │     ├── headers.yaml
  │     ├── validations.yaml
  │     ├── user-common.yaml
  │     ├── account-common.yaml
  │     └── transaction-common.yaml
  │
  ├── kafka-topics/            # Definiciones por tópico Kafka
  │     ├── transaccion-solicitada.yaml
  │     ├── saldo-actualizado.yaml
  │     ├── transaccion-enviada.yaml
  │     ├── notificacion-creada.yaml
  │     └── deuda-vencida.yaml
  │
  ├── openapi/                 # Contratos de APIs síncronas
  │     ├── sync-user-service.yaml
  │     ├── sync-account-service.yaml
  │     ├── sync-transaction-initiator.yaml
  │     └── sync-transaction-query.yaml
  │
  └── asyncapi/                # Contratos de microservicios event-driven
        ├── async-transaction-writer.yaml
        ├── async-transaction-reader.yaml
        ├── async-notification-service.yaml
        └── async-debt-service.yaml
```

## ✅ Propósito

Este repositorio proporciona una fuente de información centralizada para los contratos de comunicación entre microservicios para nuestro bootcamp-back:

* 📘 OpenAPI para operaciones síncronas
* 📗 AsyncAPI para eventos en Kafka
* 🔁 Reutilización de headers, validaciones y estructuras comunes

## 📌 Convenciones utilizadas

* Todos los endpoints expuestos por servicios síncronos deben tener los headers:

  * `X-Transaction-Id`
  * `X-Origin-Service`
* Todos los mensajes asíncronos están modelados siguiendo la especificación **AsyncAPI 2.6.0**
* Cada tópico Kafka tiene su propio archivo YAML en `/kafka-topics/`

## 🚀 Cómo utilizar este repositorio

1. Clonar el repo:

   ```bash
   git clone https://github.com/ninkovski/bootcamp-back-util-api-contracts.git
   ```
2. Usar Swagger UI o Redoc para visualizar los OpenAPI specs

3. Usar herramientas como **AsyncAPI Studio**, **Microcks** o **eventcatalog.dev** para validar e inspeccionar contratos Kafka

4. Generar mocks, pruebas o SDKs según tus herramientas preferidas

## 👨‍🏫 Autor

**Ninkovski Morales**

## Bootcamp Backend 

Preparación de backend java semisenior

---

Si te resultó útil este repositorio, puedes compartirlo, o basarte en estos archivos para crear tus propios proyectos, la idea es que puedas aprender a manejar un grupo de contratos y puedas modelar servicios sin necesidad de implementarlos antes.
