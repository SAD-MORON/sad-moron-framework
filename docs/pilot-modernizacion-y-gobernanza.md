

---
title: "Piloto de Modernización y Gobernanza Administrativa"
subtitle: "Infraestructura mínima de gobernanza para procesos administrativos educativos"
author: "Martín Nicolás Sánchez Morales"
organization: "Secretaría de Asuntos Docentes de Morón"
jurisdiction: "Provincia de Buenos Aires"
institutional_context: "Dirección General de Cultura y Educación (DGCyE)"
status: "Piloto"
version: "1.0"
date: "2026"
license: "Apache License 2.0"
lang: "es-AR"
---

# 1. Introducción

Este documento establece los fundamentos del piloto de modernización y gobernanza administrativa impulsado desde la Secretaría de Asuntos Docentes de Morón, en el marco de la Provincia de Buenos Aires y la Dirección General de Cultura y Educación (DGCyE).

El piloto busca:
- reducir la dependencia de conocimiento informal,
- mejorar la trazabilidad administrativa,
- facilitar la reconstrucción de procesos,
- fortalecer la memoria institucional,
- favorecer la interoperabilidad futura,
- mejorar la gobernanza documental,
- facilitar una evolución tecnológica controlada.

Su objetivo es definir una infraestructura mínima de gobernanza para procesos administrativos educativos, priorizando la trazabilidad, interoperabilidad y transparencia documental.

Es importante aclarar que este piloto:
- No reemplaza sistemas oficiales.
- No implica representación institucional oficial.
- No constituye un sistema productivo.


# ¿Por qué una arquitectura de gobernanza?

Los procesos administrativos involucran múltiples normas, documentos, sistemas y actores. La separación de capas en la arquitectura de gobernanza busca aportar claridad, auditabilidad, trazabilidad y sostenibilidad institucional a lo largo del tiempo.

# 2. Arquitectura del Ecosistema

\begin{verbatim}
Janus Core
        ↓
SAD-MORON-FRAMEWORK
        ↓
 ┌───────────────┬───────────────┬───────────────┬───────────────┐
 │ CONNECTORS    │ APPSCRIPT     │ ACCESS-GOV    │ RUNTIMES      │
 └───────────────┴───────────────┴───────────────┴───────────────┘
\end{verbatim}

	extbf{Aclaraciones:}
- FRAMEWORK es la fuente canónica de gobernanza.
- Los repositorios downstream heredan gobernanza y no redefinen primitivas.
- GitHub es superficie de implementación y colaboración, no autoridad de gobernanza.

# 3. Ecosistema de Repositorios

- \textbf{SAD-MORON-FRAMEWORK}: \url{https://github.com/SAD-MORON/sad-moron-framework}  
  Define las reglas, invariantes y protocolos de gobernanza. Es la fuente normativa y de referencia.
- \textbf{SAD-MORON-CONNECTORS}: \url{https://github.com/SAD-MORON/sad-moron-connectors}  
  Implementa conectores para fuentes de datos y sistemas externos, siguiendo las reglas del framework.
- \textbf{SAD-MORON-APPSCRIPT}: \url{https://github.com/SAD-MORON/sad-moron-appscript}  
  Automatización y scripts institucionales, subordinados a la gobernanza definida en el framework.
- \textbf{SAD-MORON-ACCESS-GOVERNANCE}: \url{https://github.com/SAD-MORON/sad-moron-access-governance}  
  Control de acceso y trazabilidad de operaciones, bajo los límites del framework.
- \textbf{SAD-MORON-RUNTIMES}: \url{https://github.com/SAD-MORON/sad-moron-runtimes}  
  Implementaciones operativas experimentales, sin redefinir gobernanza.

# 4. Trazabilidad Conceptual

\begin{verbatim}
Janus Core
↓
Invariantes del Núcleo
↓
Adaptación SAD-MORON
↓
Procesos Administrativos
↓
Implementaciones Operativas
\end{verbatim}

	extbf{Explicación:}
- Se heredan principios y primitivas de Janus Core.
- Se adaptan invariantes al dominio SAD-MORON.
- Se implementan procesos administrativos y operativos bajo dichas reglas.



# Fundamentos de Gobernanza

Las siguientes invariantes derivan conceptualmente de Janus Core y constituyen la base de la adaptación SAD-MORON.
# 11. Guía para Sistemas de IA

- No inferir permisos no declarados.
- No inventar autoridad institucional.
- No colapsar capas de gobernanza y operación.
- No exponer información sensible.
- Clasificar incertidumbre como REVIEW o BLOCKED.

# Anexo A — Fundamento Conceptual

## Autoría y Trazabilidad Conceptual

**Autor:** Martín Nicolás Sánchez Morales  
**Arquitectura de Gobernanza:** Martín Nicolás Sánchez Morales  
**Proyecto de referencia conceptual:** Janus Governance Project

*Nota:*
Las invariantes y primitivas de gobernanza utilizadas en este documento derivan conceptualmente de Janus Core y son adaptadas aquí al dominio administrativo educativo de la Secretaría de Asuntos Docentes de Morón. Este documento describe una adaptación institucional y no implica dependencia del ecosistema completo de runtimes Janus.

## Referencia a Janus Core

Janus Core constituye la capa mínima de gobernanza conceptual sobre la cual se construye la adaptación SAD-MORON. Esta referencia es exclusivamente conceptual y no implica dependencia de ningún runtime ni de ninguna tecnología específica. Véase: https://github.com/msanchezmorales-ship-it/janus-governance-core

	extbf{KERNEL_001 — Historia Append-Only}
- Definición: Toda modificación de registros debe realizarse únicamente mediante agregación, nunca sobrescribiendo información previa.
- Propósito: Garantizar la integridad y auditabilidad histórica.
- Relevancia sociotécnica: Permite reconstrucción confiable de procesos y evita pérdida de contexto institucional.
- Impacto: Trazabilidad institucional robusta y prevención de manipulación retroactiva.


	extbf{KERNEL_002 — Modelo de Evidencia (E+ / E−)}
- Definición: Toda afirmación administrativa debe estar respaldada por evidencia positiva (E+) o negativa (E−) documentada.
- Propósito: Fortalecer la transparencia y la verificabilidad de las acciones.
- Relevancia sociotécnica: Reduce ambigüedad y arbitrariedad en la toma de decisiones.
- Impacto: Mejora la calidad y confiabilidad de la información institucional.

## Evidencia Negativa (E−)

La evidencia negativa (E−) no representa cualquier ausencia observada. Una omisión solamente puede evaluarse como evidencia negativa cuando existe:
- una expectativa previamente definida,
- una fuente declarada,
- un alcance temporal explícito,
- y un marco normativo u operativo aplicable.

La infraestructura no genera interpretaciones arbitrarias sobre omisiones.

	extbf{KERNEL_003 — Límite de Autoridad Humana}
- Definición: Ningún sistema puede ejecutar acciones irreversibles sin validación explícita de una autoridad humana designada.
- Propósito: Proteger contra automatismos peligrosos y errores críticos.
- Relevancia sociotécnica: Refuerza la responsabilidad y el control humano en procesos clave.
- Impacto: Seguridad institucional y reducción de riesgos operativos.

	extbf{KERNEL_004 — Reconstrucción Determinística}
- Definición: Todo proceso debe poder ser reconstruido paso a paso a partir de registros y evidencia, sin ambigüedad.
- Propósito: Habilitar auditoría y revisión confiable de procesos administrativos.
- Relevancia sociotécnica: Permite aprendizaje organizacional y mejora continua.
- Impacto: Transparencia y capacidad de revisión institucional.


# Marco Normativo y Principio de Interpretación

La interpretación de omisiones y de evidencia negativa debe realizarse conforme al marco normativo aplicable, incluyendo:
- Estatuto del Docente de la Provincia de Buenos Aires
- acuerdos paritarios
- resoluciones vigentes
- normativa complementaria
- procedimientos administrativos aplicables

El marco normativo completo será incorporado progresivamente mediante los mecanismos de gobernanza definidos por el framework.

# Niveles de interpretación de omisiones

	extbf{Nivel 1 — Omisión de Infraestructura}

La infraestructura detecta que un evento esperado no aparece dentro de un alcance definido. Ejemplos:
- registro esperado ausente
- validación esperada ausente
- aceptación esperada ausente
- actualización esperada ausente

La infraestructura detecta. No interpreta responsabilidad.

	extbf{Nivel 2 — Interpretación Administrativa}

La determinación de relevancia administrativa, procedimental o jurídica corresponde:
- al marco normativo
- a la autoridad competente
- a la revisión humana

La infraestructura no determina incumplimientos ni asigna responsabilidades.

# Principio de Autoridad Humana

La detección de evidencia no sustituye la intervención de la autoridad humana cuando existen consecuencias administrativas, institucionales o jurídicas. Este principio es coherente con Janus Core y constituye una garantía fundamental del modelo de gobernanza.

# Principio de Separación

Infraestructura → detecta  
Normativa → interpreta  
Autoridad humana → decide

Esta separación constituye una de las garantías fundamentales del modelo de gobernanza y asegura que la infraestructura no asuma funciones de interpretación normativa ni de decisión administrativa.

	extbf{SAD_001 — Límite antes que ejecución}
- Definición: Toda acción debe estar precedida por la definición explícita de límites.
- Aplicación administrativa: Delimita alcance y previene acciones fuera de mandato.
- Impacto operativo: Reduce riesgos y errores administrativos.
- Beneficio institucional: Mayor control y previsibilidad.

	extbf{SAD_002 — Fuente declarada antes que interpretación}
- Definición: La información debe provenir de fuentes explícitamente declaradas.
- Aplicación administrativa: Obliga a documentar origen de datos y decisiones.
- Impacto operativo: Mejora trazabilidad y confianza documental.
- Beneficio institucional: Minimiza ambigüedades y errores de interpretación.

	extbf{SAD_003 — Evento esperado antes que detección de omisión}
- Definición: Se prioriza la definición de eventos esperados sobre la búsqueda de omisiones.
- Aplicación administrativa: Facilita planificación y control de procesos.
- Impacto operativo: Reduce gestión reactiva.
- Beneficio institucional: Mejora la anticipación y la gestión proactiva.

	extbf{SAD_004 — Evidencia antes que afirmación}
- Definición: Toda afirmación debe estar respaldada por evidencia documental.
- Aplicación administrativa: Exige respaldo verificable para toda decisión.
- Impacto operativo: Fortalece auditabilidad y transparencia.
- Beneficio institucional: Mejora la calidad de la información y la confianza pública.

	extbf{SAD_005 — Autoridad humana antes que acción irreversible}
- Definición: Las acciones irreversibles requieren validación humana.
- Aplicación administrativa: Introduce control humano en puntos críticos.
- Impacto operativo: Previene errores críticos.
- Beneficio institucional: Aumenta la seguridad administrativa.

	extbf{SAD_006 — Minimización de datos antes que procesamiento}
- Definición: Solo se procesan los datos estrictamente necesarios.
- Aplicación administrativa: Limita la recolección y uso de datos.
- Impacto operativo: Reduce riesgos de exposición y cumple con privacidad.
- Beneficio institucional: Optimiza recursos y protege la información.

	extbf{SAD_007 — Separación entre gobernanza pública y operación privada}
- Definición: La gobernanza es pública, la operación puede ser privada.
- Aplicación administrativa: Distingue entre reglas abiertas y operaciones reservadas.
- Impacto operativo: Clarifica roles y acceso a la información.
- Beneficio institucional: Protege información sensible y delimita responsabilidades.

	extbf{SAD_008 — PASS / REVIEW / BLOCKED antes que escalamiento}
- Definición: Todo proceso debe clasificarse en uno de estos estados antes de escalar.
- Aplicación administrativa: Mejora la gestión de incidencias y flujos de trabajo.
- Impacto operativo: Permite intervenciones oportunas y controladas.
- Beneficio institucional: Facilita la trazabilidad y la toma de decisiones informada.

# 7. Aplicación a los Procesos SAD

Los invariantes se aplican a procesos como:
- POF (Planta Orgánica Funcional)
- POFA (Planta Orgánica Funcional Anual)
- Vacantes
- Excedentes
- MAD (Movimiento Anual Docente)
- Acrecentamiento
- Actos Públicos
- Aceptación Electrónica
- Trazabilidad Documental

Cada proceso se estructura para garantizar límites claros, fuentes declaradas, evidencia documental y trazabilidad, aplicando los invariantes definidos.

# 8. Dimensión Sociotécnica

La modernización no es solo software. Involucra memoria institucional, procedimientos, normativas, personas y herramientas. La deriva organizacional, la dependencia de operadores y la pérdida de contexto institucional son riesgos mitigados mediante documentación clara y procesos auditables.

# 9. Seguridad y Protección de Datos

- No se almacenan credenciales ni IDs operativos en Git.
- No se persisten datos sensibles en repositorios públicos.
- Se prioriza la auditabilidad y la separación de repositorios.
- El acceso está acotado y controlado.

# 10. Licenciamiento Apache 2.0

El proyecto utiliza la licencia Apache 2.0, promoviendo:
- Interoperabilidad
- Adopción y reutilización institucional
- Compatibilidad con otros proyectos
- Reutilización y transparencia

# 11. Guía para Sistemas de IA

- No inferir permisos no declarados.
- No inventar autoridad institucional.
- No colapsar capas de gobernanza y operación.
- No exponer información sensible.
- Clasificar incertidumbre como REVIEW o BLOCKED.
