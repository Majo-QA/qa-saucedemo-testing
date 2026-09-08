# Test Plan - SauceDemo

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

- Al ser un sitio de demo público y de uso libre, SauceDemo podría sufrir cambios sin previo aviso por parte de Sauce Labs, lo cual afectaría la vigencia de los casos documentados.
- No se cuenta con documentación oficial de requerimientos: el testing se basa en exploración propia, por lo que algunos comportamientos podrían interpretarse como bug cuando en realidad son intencionales (por ejemplo, el producto "Test.allTheThings() T-Shirt (Red)", que es un nombre intencional y no un error de carga de datos).
- No se cuenta con acceso a base de datos ni logs del servidor, por lo que no es posible validar la persistencia real de los datos más allá del comportamiento visible en la interfaz.

## 8. Usuarios de Prueba Disponibles

| Usuario | Contraseña | Comportamiento esperado |
|---|---|---|
| standard_user | secret_sauce | Login exitoso, funcionamiento normal |
| locked_out_user | secret_sauce | Login bloqueado con mensaje de error |
| problem_user | secret_sauce | Login exitoso, pero con fallos visuales conocidos (imágenes incorrectas) |
| performance_glitch_user | secret_sauce | Login exitoso, con demora simulada en la carga |
