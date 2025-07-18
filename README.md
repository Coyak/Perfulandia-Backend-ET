# Perfulandia - Sistema de Microservicios

Este proyecto es una solución de backend basada en microservicios para la gestión de productos, ventas y usuarios en Perfulandia. Cada microservicio está desarrollado en Java con Spring Boot y utiliza PostgreSQL como base de datos, desplegado en Railway.

## Microservicios

### 1. ms-products
- **Función:** Gestión de productos.
- **URL pública:** [https://ms-products-production-ae7a.up.railway.app](https://ms-products-production-ae7a.up.railway.app)

#### Endpoints
| Método | Endpoint                         | Descripción                  | Ejemplo completo |
|--------|----------------------------------|------------------------------|------------------|
| GET    | /api/products                    | Listar todos los productos   | [GET](https://ms-products-production-ae7a.up.railway.app/api/products) |
| GET    | /api/products/{id}               | Obtener producto por ID      | [GET](https://ms-products-production-ae7a.up.railway.app/api/products/1) |
| POST   | /api/products                    | Crear un producto            | [POST](https://ms-products-production-ae7a.up.railway.app/api/products) |

**Ejemplo de body para POST:**
```json
{
  "nombre": "Perfume",
  "precio": 50000
}
```

---

### 2. ms-sales
- **Función:** Gestión de ventas.
- **URL pública:** [https://ms-sales-production.up.railway.app](https://ms-sales-production.up.railway.app)

#### Endpoints
| Método | Endpoint                         | Descripción                  | Ejemplo completo |
|--------|----------------------------------|------------------------------|------------------|
| GET    | /api/sales                       | Listar todas las ventas      | [GET](https://ms-sales-production.up.railway.app/api/sales) |
| POST   | /api/sales                       | Registrar una venta          | [POST](https://ms-sales-production.up.railway.app/api/sales) |

**Ejemplo de body para POST:**
```json
{
  "productId": 1,
  "cantidad": 2
}
```

---

### 3. ms-user
- **Función:** Gestión de usuarios.
- **URL pública:** [https://ms-user-production-029a.up.railway.app](https://ms-user-production-029a.up.railway.app)

#### Endpoints (disponibles en el link público)
| Método | Endpoint           | Descripción                | Ejemplo completo |
|--------|--------------------|----------------------------|------------------|
| GET    | /api/usuarios      | Listar todos los usuarios  | [GET](https://ms-user-production-029a.up.railway.app/api/usuarios) |
| GET    | /api/usuarios/{id} | Obtener usuario por ID     | [GET](https://ms-user-production-029a.up.railway.app/api/usuarios/1) |
| POST   | /api/usuarios      | Crear un usuario           | [POST](https://ms-user-production-029a.up.railway.app/api/usuarios) |
| DELETE | /api/usuarios/{id} | Eliminar usuario por ID    | [DELETE](https://ms-user-production-029a.up.railway.app/api/usuarios/1) |

**Ejemplo de body para POST:**
```json
{
  "nombre": "Miguel",
  "correo": "miguel@gmail.com",
  "rol": "Usuario"
}
```

---

## Despliegue
- Todos los microservicios están desplegados en Railway.
- Cada microservicio tiene su propia base de datos PostgreSQL en Railway.
- La configuración de conexión se encuentra en el archivo `application.properties` de cada microservicio.

## Notas técnicas
- Arquitectura basada en microservicios.
- Spring Boot + Spring Data JPA + PostgreSQL.
- Docker y Railway para despliegue.
- CORS habilitado para facilitar integración con frontends.

---