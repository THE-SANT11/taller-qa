# INFORME DE PRUEBAS DE SOFTWARE

## 1. Objetivo

Seleccionar y documentar pruebas ágiles, pruebas en la nube y pruebas de seguridad para identificar errores, mejorar la calidad del software y prevenir posibles fallos futuros.

## 2. Descripción del caso de estudio

Este apartado debe completarse con la descripción del caso trabajado en las unidades 1 y 2, incluyendo el funcionamiento del sistema y los errores identificados originalmente.

**Caso de estudio:** [Escribir aquí la descripción del caso de las unidades 1 y 2].

**Errores originales:** [Indicar aquí los errores descritos en el caso].

## 3. Herramientas seleccionadas

- **GitHub Actions:** permite automatizar la ejecución de flujos de trabajo cada vez que se realizan cambios en el repositorio.
- **Dependabot:** identifica vulnerabilidades conocidas en las dependencias y puede proponer actualizaciones de seguridad.
- **CodeQL:** analiza código compatible para identificar posibles vulnerabilidades y errores de programación.

## 4. Pruebas seleccionadas

| Tipo de prueba | Error que busca detectar | Solución o prevención |
|---|---|---|
| Prueba ágil: regresión automatizada | Cambios que puedan afectar funciones que anteriormente funcionaban correctamente. | Ejecutar pruebas después de cada modificación y corregir los fallos antes de integrar los cambios. |
| Prueba en la nube: automatización con GitHub Actions | Fallos en los pasos automatizados y problemas que puedan aparecer durante la ejecución en un entorno controlado. | Ejecutar comprobaciones en un entorno alojado en la nube y revisar los resultados de cada ejecución. |
| Prueba de seguridad: Dependabot y CodeQL | Dependencias con vulnerabilidades conocidas y patrones de código potencialmente inseguros. | Actualizar las dependencias afectadas, corregir el código y volver a ejecutar el análisis de seguridad. |

## 5. Procedimiento realizado

### 5.1. Automatización con GitHub Actions

Se creó el archivo `.github/workflows/pruebas.yml` para ejecutar comprobaciones automatizadas cuando se realizan cambios en el repositorio.

Durante el proceso se presentó un error de configuración debido a que la propiedad `permissions` estaba definida dos veces. Se corrigió el archivo eliminando la declaración duplicada y se comprobó que la ejecución posterior finalizara correctamente.

### 5.2. Prueba en la nube

Se utilizó GitHub Actions para ejecutar el flujo de trabajo en un entorno alojado en la nube.

Se revisaron las ejecuciones del repositorio y se comprobó que el flujo de demostración finalizara correctamente. Esta prueba verifica la ejecución de las comprobaciones configuradas, pero no demuestra por sí sola que una aplicación completa funcione correctamente.

### 5.3. Prueba de seguridad

Se activaron las alertas de Dependabot y las actualizaciones de seguridad. También se habilitó CodeQL para analizar el repositorio.

Dependabot mostró el mensaje «No open alerts», lo que indica que no había alertas abiertas de esta herramienta en el momento de la consulta.

CodeQL detectó inicialmente una alerta de severidad media denominada «Workflow does not contain permissions», relacionada con la declaración de permisos del flujo de trabajo. Se modificó el archivo y se verificó que las ejecuciones posteriores finalizaran correctamente.

La resolución definitiva de la alerta debe comprobarse en los resultados actualizados de Code scanning.

## 6. Resultados obtenidos

- GitHub Actions ejecutó correctamente el flujo de demostración después de corregir el error de configuración.
- Dependabot no mostró alertas abiertas de vulnerabilidades en la revisión realizada.
- CodeQL permitió identificar un problema de configuración de seguridad en el flujo de trabajo.
- Se comprobó que la automatización podía ejecutarse nuevamente después de modificar el archivo.

**Limitación:** las pruebas realizadas corresponden principalmente a la configuración del repositorio y a un flujo de demostración. Para evaluar la aplicación del caso de estudio, es necesario ejecutar pruebas sobre su código y sus funciones reales.

## 7. Cómo estas pruebas solucionan y previenen errores

Las pruebas de regresión ayudan a comprobar que las modificaciones no afecten funcionalidades existentes. La automatización en la nube facilita la repetición de comprobaciones en un entorno controlado y permite detectar fallos con mayor rapidez. Por su parte, Dependabot y CodeQL contribuyen a identificar riesgos relacionados con dependencias y código potencialmente inseguro.

La combinación de estas herramientas permite detectar problemas antes de que lleguen a producción, reducir el riesgo de introducir nuevos errores y facilitar el mantenimiento del software.

## 8. Conclusiones

La utilización de GitHub Actions, Dependabot y CodeQL permitió configurar un proceso inicial de automatización y seguridad en el repositorio. Durante la actividad se identificó y corrigió un error de configuración, y se comprobó el funcionamiento posterior del flujo.

Estas herramientas contribuyen a mejorar la calidad del software y a prevenir posibles fallos. Sin embargo, los resultados obtenidos no garantizan que la aplicación esté libre de errores. Para completar la evaluación es necesario aplicar las pruebas a las funciones reales del caso trabajado en las unidades 1 y 2.

## 9. Evidencias

Se adjuntarán capturas de pantalla de:

1. Las ejecuciones satisfactorias de GitHub Actions.
2. La configuración de seguridad con Dependabot activado.
3. La sección de Dependabot sin alertas abiertas.
4. La alerta detectada por CodeQL y la comprobación posterior a la corrección.
