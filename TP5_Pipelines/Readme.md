# TP5 - Pipelines de Despliegue Azure

## Descripción del Proyecto

Este proyecto implementa un sistema de CI/CD completo utilizando Azure DevOps para el despliegue automático de una aplicación web con frontend y backend separados, incluyendo base de datos MySQL.

## Arquitectura del Sistema

- **Frontend**: Aplicación React desplegada en Azure App Service
- **Backend**: API Node.js desplegada en Azure App Service  
- **Base de Datos**: Azure Database for MySQL Flexible Server
- **CI/CD**: Azure DevOps Pipelines con ambientes QA y Producción

## URLs de Acceso

### Ambiente QA (Testing)
- **Frontend QA**: http://repuestera-web-qa.azurewebsites.net
- **Backend QA**: http://repuestera-api-qa.azurewebsites.net

### Ambiente Producción
- **Frontend PROD**: http://repuestera-web-prod.azurewebsites.net
- **Backend PROD**: http://repuestera-api-prod.azurewebsites.net

## Proceso de Despliegue

### 1. Despliegue Automático a QA
- **Trigger**: Push a la rama `main` del repositorio remoto de azure
- **Proceso**: 
  1. Build automático del código
  2. Ejecución de tests
  3. Despliegue automático a ambiente QA
- **Tiempo estimado**: 5-10 minutos

### 2. Despliegue a Producción
- **Trigger**: Aprobación manual requerida
- **Proceso**:
  1. Despliegue exitoso en QA
  2. Solicitud de aprobación automática
  3. Aprobación por administradores del proyecto
  4. Despliegue automático a Producción
- **Tiempo estimado**: 10-15 minutos

## Repositorio

🔗 **GitHub Repository**: https://github.com/mfrias42/Repuestera.git


