# Decisiones Técnicas - TP7 Code Coverage, Análisis Estático y Pruebas de Integración

## Aplicación Seleccionada
- **Repositorio**: [Repuestera](https://github.com/mfrias42/Repuestera.git)
- **Stack Tecnológico**:
  - Frontend: React
  - Backend: Node.js
  - Base de datos: MySQL
  - Testing: Jest (tanto para frontend como backend)

## 1. Configuración de Code Coverage

### Decisiones de Implementación
1. **Herramienta elegida**: Jest
   - Jest es la herramienta de testing nativa tanto para React como para Node.js
   - Proporciona métricas de cobertura integradas
   - Se integra bien con Azure DevOps para mostrar reportes

2. **Configuración Backend**:
   - Umbral de cobertura establecido en 70% para cumplir con los requisitos del TP
   - Configuración en `jest.config.js`:
     ```javascript
     coverageThreshold: {
       global: {
         branches: 70,
         functions: 70,
         lines: 70,
         statements: 70
       }
     }
     ```
   - Múltiples formatos de reporte configurados:
     - text: para visualización en consola
     - lcov: para integración con herramientas de análisis
     - cobertura: para integración con Azure DevOps

3. **Configuración Frontend**:
   - Mismos umbrales de 70% requeridos
   - Exclusión de archivos no relevantes para la cobertura:
     - index.js (punto de entrada)
     - reportWebVitals.js
     - setupTests.js
   - Configuración específica para React:
     - Entorno jsdom para simular el DOM
     - Manejo de imports de archivos estáticos

4. **Scripts NPM Configurados**:
   - Backend:
     ```json
     "test:coverage": "jest --coverage --silent --colors"
     "test:ci": "jest --ci --coverage --testResultsProcessor=jest-junit"
     ```
   - Frontend:
     ```json
     "test:coverage": "react-scripts test --coverage --watchAll=false"
     "test:ci": "CI=true react-scripts test --coverage --watchAll=false --testResultsProcessor=jest-junit"
     ```

### Justificación de Decisiones
1. **¿Por qué Jest?**
   - Herramienta estándar en el ecosistema JavaScript/Node.js
   - Configuración unificada para frontend y backend
   - Excelente integración con React y Node.js
   - Generación de reportes en múltiples formatos

2. **¿Por qué 70% como umbral?**
   - Requisito específico del TP
   - Balance entre calidad y factibilidad
   - Suficiente para detectar cambios críticos

3. **¿Por qué múltiples formatos de reporte?**
   - text: facilita revisión local y debug
   - lcov: formato estándar para herramientas de análisis
   - cobertura: integración nativa con Azure DevOps

### Estado Actual
Los cambios de configuración de code coverage han sido implementados en una rama feature del repositorio Repuestera:
- Rama: `feature/tp7-coverage-sonar-cypress`
- Estado: Cambios commiteados y pusheados al repositorio
- Pull Request: Pendiente de revisión

## Próximos Pasos
1. **Configuración de SonarCloud**:
   - Integrar análisis estático
   - Configurar quality gates

2. **Implementación de Cypress**:
   - Configurar pruebas de integración
   - Integrar con el pipeline

3. **Pipeline CI/CD**:
   - Integrar todas las herramientas
   - Configurar quality gates
   - Automatizar la ejecución de pruebas

[Este documento se irá actualizando a medida que avancemos con la implementación]
