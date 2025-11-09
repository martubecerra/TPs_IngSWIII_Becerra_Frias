# Decisiones del TP06 - Pruebas Unitarias

🔗 **Repositorio**: https://github.com/mfrias42/Repuestera.git

## Decisión Principal

Implementar una suite completa de pruebas unitarias para asegurar la calidad del código tanto en el backend como en el frontend de la aplicación Repuestera.



## Tecnologías Utilizadas

### Backend
- **Jest**: Framework principal de testing para Node.js
- **Supertest**: Para probar las APIs HTTP sin necesidad de levantar el servidor completo

### Frontend
- **Jest + React Testing Library**: Herramientas ya incluidas en React que permiten probar componentes y servicios

## Dónde Están Aplicados los Tests

### Backend
Los tests están organizados en la carpeta `backend/__tests__/`:

- **Modelos** (`unit/models/`): Tests para User, Product, Admin y Category
- **Rutas** (`unit/routes/`): Tests para endpoints de autenticación, productos y usuarios
- **Middleware** (`unit/middleware/`): Tests para validaciones, autenticación y manejo de archivos

### Frontend
Los tests están en `frontend/src/`:

- **Servicios** (`services/__tests__/`): Tests para las llamadas a la API
- **Contextos** (`context/__tests__/`): Tests para el manejo de autenticación
- **Componentes** (`components/__tests__/`): Tests para componentes como ProtectedRoute

## Cobertura de Tests

### Backend - 197 tests implementados

**Modelos (88 tests)**:
- User: 23 tests - **100% de cobertura**
- Product: 25 tests - **74% de cobertura**
- Admin: 20 tests - **77% de cobertura**
- Category: 20 tests - **91% de cobertura**

**Rutas (52 tests)**:
- Autenticación: 14 tests (registro, login, logout)
- Productos: 18 tests (CRUD completo, reportes de stock)
- Usuarios: 20 tests (gestión de usuarios, admins, categorías)

**Middleware (54 tests)**:
- Autenticación: 20+ tests
- Validación: 20+ tests
- Upload: 10+ tests

**Cobertura promedio de modelos**: **83.67%**

![Resultados de tests del backend](images/backend%20test.png)

### Frontend - 24+ tests implementados

- Servicios de API: 14 tests
- AuthContext: 12 tests

![Resultados de tests del frontend](images/front%20end%20test.png)

## Estado de Implementación


## Integración con CI/CD

Los tests se ejecutan automáticamente en el pipeline de Azure DevOps cada vez que se hace un push al repositorio. Esto asegura que:

- Los tests se corren antes de desplegar
- Se generan reportes de cobertura automáticamente
- Si algún test falla, el despliegue se detiene

## Estrategia de Testing

Para asegurar que los tests sean rápidos y no dependan de servicios externos, se utilizaron **mocks** (simulaciones) de:

- Base de datos MySQL
- Servicios de autenticación
- Llamadas HTTP externas
- Almacenamiento local del navegador

Esto permite que los tests sean:
- Rápidos de ejecutar
- Independientes entre sí
- Reproducibles en cualquier entorno

## Resumen

Se implementaron **más de 100 tests unitarios** que cubren:
- Toda la lógica de negocio del backend
- Los servicios principales del frontend
- Casos exitosos y casos de error
- Validaciones y casos límite

![Resumen de tests](images/tests%20summary.png)

---

