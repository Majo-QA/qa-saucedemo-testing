# Test Plan - SauceDemo

| Campo | Valor |
|---|---|
| Proyecto | SauceDemo Testing |
| Módulo | General (Login, Inventario, Carrito, Checkout) |
| Autor | María Pimentel |
| Fecha de creación | 08/09/2026 |
| Versión | 1.1 |
| Estado | En ejecución |

## 1. Objetivo

Validar el correcto funcionamiento de los módulos principales del sitio SauceDemo (https://www.saucedemo.com/), garantizando que los flujos de inicio de sesión, gestión de productos, carrito de compras y checkout se comporten según lo esperado.

## 2. Alcance

### Dentro del alcance
- **Login**: autenticación con distintos usuarios de prueba, validación de campos y mensajes de error.
- **Inventario**: listado de productos, ordenamiento, agregado/quitado de productos al carrito.
- **Carrito de compras**: gestión de productos agregados, navegación desde/hacia el carrito.
- **Checkout**: formulario de datos del comprador, validación de campos, resumen y finalización de la compra.

### Fuera del alcance
- Testing de performance o carga.
- Testing de seguridad avanzado.
- Compatibilidad con navegadores obsoletos o dispositivos móviles.
- Testing de accesibilidad (WCAG).
- Validaciones de backend/base de datos.

## 3. Estrategia de Testing

Se aplicará testing manual funcional, combinando:
- **Testing exploratorio inicial**, para conocer el comportamiento real del sistema antes de diseñar casos formales.
- **Diseño de casos de prueba estructurados**, cubriendo:
  - Casos positivos (happy path): flujos exitosos con datos válidos.
  - Casos negativos: inputs inválidos, campos vacíos, credenciales incorrectas.
  - Edge cases: comportamientos límite o atípicos.

Cada caso de prueba documentará: ID, título, tipo, priodridad, escenario (formato Gherkin: Given/When/Then), estado y fecha.
## 4. Técnicas de Diseño de Pruebas Aplicadas

Al tratarse de un sistema ya construido, sin acceso al código fuente ni a documentación de requerimientos, las técnicas aplicadas corresponden a **Caja Negra** y **Basadas en Experiencia**:

- Partición de Equivalencia
- Análisis de Valores Límite
- Tablas de Decisión
- Testing Exploratorio / Basado en Experiencia

## 5. Criterios de Entrada

- El sitio SauceDemo se encuentra accesible y operativo.
- Se cuenta con las credenciales de los usuarios de prueba provistos por el sitio (standard_user, locked_out_user, problem_user, performance_glitch_user).
- Los casos de prueba fueron diseñados a partir de una fase exploratoria previa.

## 6. Criterios de Salida

- Se ejecutó el 100% de los casos de prueba planificados.
- Todas las inconsistencias o comportamientos inesperados detectados fueron documentados en el reporte de bugs.
- Se generó evidencia de los casos ejecutados.
- Los resultados fueron volcados en el resumen final del proyecto.

## 7. Riesgos

| # | Riesgo | Impacto | Probabilidad | Mitigación |
|---|---|---|---|---|
| R-01 | SauceDemo podría sufrir cambios sin previo aviso por parte de Sauce Labs | Medio | Baja | Revalidar casos periódicamente si se detectan cambios |
| R-02 | Comportamientos intencionales podrían confundirse con bugs, al no contar con documentación oficial de requerimientos | Medio | Media | Investigar y confirmar antes de reportar (ej. caso "Test.allTheThings()") |
| R-03 | No se cuenta con acceso a base de datos ni logs del servidor, limitando la validación de persistencia real de datos | Bajo | Alta | Limitar el alcance a comportamiento visible en la interfaz |

## 8. Usuarios de Prueba Disponibles

| Usuario | Contraseña | Comportamiento esperado |
|---|---|---|
| standard_user | secret_sauce | Login exitoso, funcionamiento normal |
| locked_out_user | secret_sauce | Login bloqueado con mensaje de error |
| problem_user | secret_sauce | Login exitoso, pero con fallos visuales conocidos (imágenes incorrectas) |
| performance_glitch_user | secret_sauce | Login exitoso, con demora simulada en la carga |

## 9. Historial de Cambios

| Versión | Fecha | Autor | Cambios realizados |
|---|---|---|---|
| 1.0 | 08/09/2026 | María Pimentel | Creación inicial del Test Plan |
| 1.1 | 24/09/2026 | María Pimentel | Se agrega sección de Técnicas de Diseño de Pruebas Aplicadas; se convierte sección de Riesgos a formato de tabla; se agrega tabla de metadata e Historial de Cambios |
