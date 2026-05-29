# Piloto de Modernización y Gobernanza

\section*{1. Introducción}

El presente documento describe el piloto de modernización, gobernanza e interoperabilidad impulsado desde la Secretaría de Asuntos Docentes (SAD) de Morón, en el marco de la Provincia de Buenos Aires y la Dirección General de Cultura y Educación (DGCyE). Este piloto tiene carácter experimental, con alcance limitado, y busca sentar las bases para una modernización administrativa, fortaleciendo la gobernanza documental, la interoperabilidad y la trazabilidad de los procesos educativos.

Es importante aclarar que este piloto:
- No reemplaza sistemas oficiales.
- No implica representación institucional oficial.
- No constituye un sistema productivo.

\section*{2. Arquitectura del Ecosistema}

El ecosistema se estructura en capas, con los siguientes repositorios como referencia:
- [sad-moron-framework](https://github.com/SAD-MORON/sad-moron-framework)
- [sad-moron-connectors](https://github.com/SAD-MORON/sad-moron-connectors)
- [sad-moron-appscript](https://github.com/SAD-MORON/sad-moron-appscript)
- [sad-moron-access-governance](https://github.com/SAD-MORON/sad-moron-access-governance)

Jerarquía técnica:

Janus Core
↓
SAD-MORON-FRAMEWORK
↓
CONNECTORS / APPSCRIPT / ACCESS-GOVERNANCE

Aclaraciones:
- El framework es la fuente canónica de gobernanza.
- Los repositorios downstream no redefinen gobernanza.
- GitHub es superficie de implementación, no autoridad de gobernanza.

\section*{3. Invariantes del Núcleo de Gobernanza}

1. **Límite antes que ejecución**
   - Definición: Toda acción debe estar precedida por la definición explícita de límites.
   - Justificación: Evita acciones fuera de alcance o sin autorización.
   - Impacto: Reduce riesgos y errores administrativos.

2. **Fuente declarada antes que interpretación**
   - Definición: La información debe provenir de fuentes explícitamente declaradas.
   - Justificación: Minimiza ambigüedades y errores de interpretación.
   - Impacto: Mejora la trazabilidad y la confianza documental.

3. **Evento esperado antes que detección de omisión**
   - Definición: Se prioriza la definición de eventos esperados sobre la búsqueda de omisiones.
   - Justificación: Facilita la planificación y el control.
   - Impacto: Reduce la gestión reactiva.

4. **Evidencia antes que afirmación**
   - Definición: Toda afirmación debe estar respaldada por evidencia documental.
   - Justificación: Fortalece la auditabilidad y la transparencia.
   - Impacto: Mejora la calidad de la información.

5. **Autoridad humana antes que acción irreversible**
   - Definición: Las acciones irreversibles requieren validación humana.
   - Justificación: Previene errores críticos.
   - Impacto: Aumenta la seguridad administrativa.

6. **Historia append-only antes que sobrescritura**
   - Definición: Los registros deben ser solo agregados, no sobrescritos.
   - Justificación: Garantiza la integridad histórica.
   - Impacto: Facilita auditorías y reconstrucción de procesos.

7. **Minimización de datos antes que procesamiento**
   - Definición: Solo se procesan los datos estrictamente necesarios.
   - Justificación: Reduce riesgos de exposición y cumple con principios de privacidad.
   - Impacto: Optimiza recursos y protege la información.

8. **PASS / REVIEW / BLOCKED antes que escalamiento**
   - Definición: Todo proceso debe clasificarse en uno de estos estados antes de escalar.
   - Justificación: Mejora la gestión de incidencias.
   - Impacto: Permite intervenciones oportunas y controladas.

9. **Separación entre gobernanza pública y operación privada**
   - Definición: La gobernanza es pública, la operación puede ser privada.
   - Justificación: Protege información sensible y delimita responsabilidades.
   - Impacto: Clarifica roles y acceso a la información.

10. **Gobernanza agnóstica antes que enforcement específico**
    - Definición: Las reglas de gobernanza no dependen de implementaciones particulares.
    - Justificación: Facilita la interoperabilidad y la adaptación futura.
    - Impacto: Permite evolución tecnológica sin perder control normativo.

\section*{4. Aplicación a los Procesos SAD}

Los invariantes se aplican a procesos como:
- POF (Planta Orgánica Funcional)
- POFA (Planta Orgánica Funcional Anual)
- Vacantes
- Excedentes
- MAD (Movimiento Anual Docente)
- Acrecentamiento
- Actos Públicos
- Aceptación electrónica
- Trazabilidad documental

Cada proceso se estructura para garantizar límites claros, fuentes declaradas, evidencia documental y trazabilidad, aplicando los invariantes definidos.

\section*{5. Dimensión Sociotécnica}

La modernización no se limita al software. Involucra personas, procedimientos, normativas, responsabilidades y herramientas. La deriva organizacional, la dependencia de operadores y la pérdida de contexto institucional son riesgos mitigados mediante documentación clara y procesos auditables.

\section*{6. Seguridad}

- Las credenciales y los IDs operativos no se almacenan en Git.
- Los conectores operativos permanecen fuera de repositorios públicos.
- Se minimiza el uso y procesamiento de datos.
- Se prioriza la auditabilidad y la separación de capas.

\section*{7. Licenciamiento}

El proyecto utiliza la licencia Apache 2.0, promoviendo:
- Interoperabilidad
- Adopción y reutilización institucional
- Compatibilidad con otros proyectos
- Colaboración futura

\section*{8. Guía para IA}

- No inferir permisos no declarados.
- No asumir que el sistema está en producción.
- No inventar autoridad institucional.
- No colapsar capas de gobernanza y operación.
- Clasificar incertidumbre como REVIEW o BLOCKED.
