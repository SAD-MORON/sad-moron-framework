# CLAUDE EXTERNAL GOVERNANCE AUDIT V2

**Repositorio auditado:** [SAD-MORON/sad-moron-framework](https://github.com/SAD-MORON/sad-moron-framework)
**Auditoría previa:** `reports/CLAUDE_EXTERNAL_GOVERNANCE_AUDIT_V1.md`
**Relación con V1:** V1 produjo los documentos ancla declarados en el README como remediación mínima. Esta auditoría (V2) revisa el estado actual del repositorio raíz y amplía el alcance a una revisión cruzada del ecosistema completo.
**Fecha:** 2026-05-28
**Auditor externo:** Claude (Anthropic) — análisis basado en contenido público
**Estado general:** `REVIEW REQUIRED`
**Alcance:** `sad-moron-framework` (primario) + `sad-moron-connectors`, `sad-moron-appscript`, `sad-moron-access-governance` (contexto cruzado)
**Documentos revisados:** README.md de los cuatro repositorios; `docs/governance-inheritance.md`, `docs/AI_AGENT_GUIDE.md`, `docs/pilot-context-and-governance-primitives.md` de `connectors` y `appscript`

---

## 1. Descripción general del repositorio

`sad-moron-framework` es el repositorio raíz del ecosistema SAD-MORON. Su rol declarado es ser la fuente canónica de:

- principios de gobernanza heredados de Janus Core
- estándares de repositorio para todas las capas downstream
- definición de la arquitectura por capas del ecosistema
- fuentes declaradas, eventos esperados y reglas de omisión
- protocolos normativos y de control de cambios

Es, por diseño, el repositorio que debe preceder y delimitar a todos los demás (`appscript`, `connectors`, `access-governance`). Tiene **13 commits** y es el único del ecosistema con una carpeta `normative/` y una carpeta `declared-sources/`. El README es el más completo y arquitecturalmente detallado de los cuatro repositorios públicos disponibles.

---

## 2. Estructura declarada

```
.
├── declared-sources/
├── docs/
├── normative/
├── protocols/
├── reports/
├── workflows/
├── .gitignore
├── LICENSE
├── NOTICE
└── README.md
```

El README declara los siguientes **documentos ancla de gobernanza**:

| Documento declarado | Ruta |
|---|---|
| Governance Core | `docs/governance-core.md` |
| Repository Governance Standard | `docs/repository-governance-standard.md` |
| Governance Inheritance | `docs/governance-inheritance.md` |
| Declared Sources Catalog | `docs/declared-sources-catalog.md` |
| Change Control Protocol | `protocols/change-control-protocol.md` |
| Normative Document Registry | `docs/normative-document-registry.md` |
| Sensitive Data Protection Protocol | `protocols/sensitive-data-protection-protocol.md` |
| Claude External Governance Audit V1 | `reports/CLAUDE_EXTERNAL_GOVERNANCE_AUDIT_V1.md` |
| SAD Moron Janus Adaptation Review V1 | `reports/SAD_MORON_JANUS_ADAPTATION_REVIEW_V1.md` |

---

## 3. Hallazgos

---

### F-01 — Ciclo V1 → remediación documentado; trazabilidad externa incompleta

**Estado:** `REVIEW`
**Severidad:** Media
**Relación con V1:** hallazgo nuevo en V2; V1 no podía referenciarse a sí mismo.

El README declara explícitamente que los documentos ancla de gobernanza fueron creados como respuesta mínima a los hallazgos de `CLAUDE_EXTERNAL_GOVERNANCE_AUDIT_V1.md`. Eso es positivo: el ecosistema tiene un ciclo real de auditoría → remediación → evidencia. Sin embargo, el README referencia esos documentos ancla solo mediante rutas relativas, sin enlaces directos a los archivos en GitHub. Para lectores externos o colaboradores nuevos, la trazabilidad entre hallazgos V1 y las remediaciones aplicadas no es navegable sin autenticación o conocimiento previo de la estructura.

Esta auditoría V2 no pudo verificar el contenido de V1 ni de los documentos ancla generados como respuesta, ya que GitHub bloquea el acceso directo a subdirectorios sin sesión. La continuidad del ciclo de auditoría queda registrada aquí como evidencia de que V2 reconoce V1 como antecedente.

**Recomendación:** Agregar en el README enlaces directos a cada documento ancla (formato `[nombre](./docs/nombre.md)`) para que la trazabilidad sea navegable públicamente. Considerar agregar en cada documento ancla una línea `remediation-for: CLAUDE_EXTERNAL_GOVERNANCE_AUDIT_V1.md` en el front-matter cuando se adopte versionado (ver F-05).

---

### F-02 — Arquitectura por capas bien definida, pero sin mecanismo de enforcement entre capas

**Estado:** `REVIEW`
**Severidad:** Media-Alta

El README define con claridad siete capas del ecosistema:

| Capa | Responsabilidad declarada |
|---|---|
| Framework | Gobernanza, protocolos, límites, significado normativo |
| Normativa | Documentos legales e institucionales |
| Workflow | Procesos operacionales derivados del alcance normativo |
| Declared sources | Sheets, Drive, Forms, instructivos aprobados |
| Runtime | Ejecución de ingesta y normalización (repos separados) |
| Connectors | Adaptadores de fuentes (repos separados) |
| Audit | Revisión append-only y reconstrucción (repos separados) |

Sin embargo, no existe un mecanismo técnico ni documental que impida que una capa downstream redefina principios de gobernanza de esta capa. El README lo declara como regla ("lower layers may not redefine governance"), pero no hay un protocolo de verificación de cumplimiento, no hay un changelog de divergencias, y no hay un artefacto de "conformance check" entre este repo y sus downstream.

Como ya se observó en la auditoría cruzada: `sad-moron-access-governance` (capa de gobernanza de acceso) tiene solo 4 commits y `audit/` como placeholder, mientras que `sad-moron-appscript` (capa operacional) ya tiene 18 commits y auditoría activa. Esa inversión de madurez es detectable desde este repositorio, pero no está registrada como hallazgo formal en ningún documento accesible.

**Recomendación:** Agregar a `reports/` un documento de estado de madurez por capa (tabla con capa, repo asociado, commits, estado de audit, fecha de última revisión de alineación). Esto haría visible la inversión de madurez y daría base para que la autoridad humana institucional priorice el desarrollo de `access-governance`.

---

### F-03 — El principio append-only no tiene enforcement técnico en el repositorio raíz

**Estado:** `OPEN`
**Severidad:** Alta

`sad-moron-framework` hereda el principio `Append-only evidence` de Janus Core y lo adapta como `Append-only institutional history` y `deterministic reconstruction of review context`. Como repositorio raíz del ecosistema, su postura sobre este principio tiene efecto normativo sobre todas las capas downstream.

Sin embargo, igual que en los repos downstream, no existe evidencia de que el propio repositorio raíz tenga configuradas branch protection rules, restricción de force-push, o firma de commits obligatoria. Un repositorio que declara append-only como principio central debe aplicarlo a sí mismo primero.

**Recomendación:** Documentar en `protocols/change-control-protocol.md` (que ya existe según el README) las configuraciones de GitHub requeridas para preservar la integridad del historial: protección del branch `main`, desactivación de force-push, y opcionalmente firma de commits. Verificar que esas configuraciones estén activas.

---

### F-04 — Janus Core referenciado como fuente raíz, pero sin acceso público verificable

**Estado:** `REVIEW`
**Severidad:** Media

El README declara que este repositorio hereda principios de Janus Core sin depender de su runtime completo. Esa distinción es legítima y bien formulada. Sin embargo, Janus Core no es un repositorio público disponible en la organización `SAD-MORON`. La herencia es conceptual, pero ningún documento del ecosistema apunta a una fuente pública, una versión, o un snapshot de los principios de Janus Core que fueron seleccionados.

Esto significa que si Janus Core evoluciona o desaparece, la gobernanza de este ecosistema queda con una cadena raíz sin ancla verificable.

**Recomendación:** En `docs/governance-inheritance.md`, incluir un snapshot de los principios de Janus Core efectivamente adoptados (con fecha de captura) o bien un SHA/URL a la fuente pública de donde fueron extraídos, de manera que la herencia sea reproducible sin acceso a Janus Core en el futuro.

---

### F-05 — Sin versionado de documentos ancla

**Estado:** `OPEN`
**Severidad:** Media

Los siete documentos ancla listados en el README no tienen un esquema de versionado documentado. El README define estos documentos como "minimum governance anchors" resultado de una remediación, pero no indica cuándo fueron creados, qué versión representan, ni cuándo fueron revisados por última vez.

Dado que este es el repositorio raíz del cual los downstream heredan, un documento ancla desactualizado o en revisión silenciosa puede producir inconsistencias en cascada.

**Recomendación:** Adoptar un front-matter mínimo en todos los documentos ancla:

```yaml
---
version: 1.0
status: ACTIVE
last-reviewed: YYYY-MM-DD
reviewed-by: [rol institucional]
---
```

Documentar la convención en `docs/repository-governance-standard.md`.

---

### F-06 — La distinción `E+` / `E-` de Janus no está operacionalizada localmente

**Estado:** `REVIEW`
**Severidad:** Media

El README menciona explícitamente la distinción `E+` (evidencia positiva) / `E-` (evidencia negativa / omisión) de Janus Core como uno de los principios seleccionados. Esta distinción es arquitecturalmente importante: permite separar "el evento ocurrió y hay registro" de "el evento era esperado y no ocurrió (omisión detectable)".

Sin embargo, no existe en los materiales accesibles un protocolo que defina cómo se clasifica, registra y escala una omisión en el contexto SAD-MORON. El concepto de "omission" aparece en `sad-moron-connectors/docs/pilot-context-and-governance-primitives.md`, pero no se puede verificar si está operacionalizado en `sad-moron-framework` de manera normativa.

**Recomendación:** Asegurarse de que `docs/governance-core.md` o un protocolo en `protocols/` defina formalmente el ciclo de vida de una omisión: detección, clasificación, registro en `audit/`, escalado a estado `REVIEW` o `BLOCKED`.

---

### F-07 — Ausencia de repositorio `audit/` activo en el repo raíz

**Estado:** `OPEN`
**Severidad:** Media

A diferencia de `sad-moron-appscript`, que tiene una carpeta `audit/` con actividad real, `sad-moron-framework` no tiene una carpeta `audit/` en su estructura declarada. El README recomienda que los repositorios SAD tengan `audit/` como área recomendada, pero el repo raíz mismo no la tiene.

Dado que este repositorio ya tiene un ciclo de auditoría externa documentado (`CLAUDE_EXTERNAL_GOVERNANCE_AUDIT_V1.md` en `reports/`), la diferencia entre `reports/` y un `audit/` append-only no está explicitada. Si `reports/` cumple el rol de evidencia de auditoría, eso debe estar declarado.

**Recomendación:** Aclarar en `docs/governance-core.md` si `reports/` cumple el rol de evidencia append-only de auditoría para este repositorio, o si se planea agregar `audit/` en una iteración futura. La ambigüedad entre `reports/` (evidencia y resultados) y `audit/` (registros append-only) existe en todo el ecosistema y debe resolverse desde la capa raíz.

---

## 4. Fortalezas identificadas

Además de los hallazgos, el repositorio presenta varias características positivas respecto al resto del ecosistema:

- **Arquitectura por capas explícita y consistente.** La distinción entre framework, normativa, workflow, runtime y connectors es la más clara del ecosistema y constituye una referencia válida para todas las capas downstream.

- **Reconocimiento de auditoría previa.** El README documenta que los documentos ancla fueron agregados como respuesta a hallazgos de una auditoría externa. Esto demuestra un ciclo de mejora documentado, lo cual es coherente con el principio de gobernanza-primero.

- **Separación de responsabilidades bien formulada.** El README distingue explícitamente entre documentos legales/normativos (alta autoridad) y artefactos operacionales de Google Workspace (baja autoridad). Esa distinción evita la confusión común de tratar un Google Sheet como fuente normativa.

- **Non-goals explícitos.** La lista de "non-goals" es precisa y operacionalmente útil: impide que colaboradores futuros expandan el scope del repositorio sin una decisión de gobernanza explícita.

- **Licencia y atribución documentadas.** Presencia de `LICENSE`, `NOTICE` y atribución de arquitectura inicial, alineado con buenas prácticas de continuidad institucional.

---

## 5. Tabla resumen de hallazgos

| ID | Descripción | Principio en riesgo | Severidad | Estado |
|---|---|---|---|---|
| F-01 | Auditoría previa referenciada pero no trazable externamente | Auditabilidad | Media | `REVIEW` |
| F-02 | Sin enforcement entre capas del ecosistema | Governance-before-execution | Media-Alta | `REVIEW` |
| F-03 | Append-only sin enforcement técnico en el repo raíz | Append-only evidence | Alta | `OPEN` |
| F-04 | Janus Core sin fuente pública ni snapshot anclado | No hidden authority | Media | `REVIEW` |
| F-05 | Documentos ancla sin versionado | Governance alignment | Media | `OPEN` |
| F-06 | Distinción E+/E- no operacionalizada localmente | Audit-before-execution | Media | `REVIEW` |
| F-07 | Sin carpeta `audit/` en el repo raíz; distinción con `reports/` no declarada | Append-only evidence | Media | `OPEN` |

---

## 6. Conclusión

`sad-moron-framework` es el repositorio más arquitecturalmente maduro del ecosistema SAD-MORON. Tiene la estructura más completa, el README más detallado, y es el único que documenta un ciclo de remediación basado en auditoría previa. Eso lo posiciona como una base sólida.

Los hallazgos no son de naturaleza crítica ni implican exposición de credenciales o datos personales. Todos son brechas de configuración, versionado, o formalización que son coherentes con el estado declarado de "base scaffold" del repositorio.

La brecha más relevante sistémicamente es la ausencia de un mecanismo de enforcement de la arquitectura por capas (F-02): el repositorio raíz declara que las capas downstream no pueden redefinir su gobernanza, pero no hay ningún artefacto que verifique o registre si eso se cumple. Esa brecha es la que genera la inversión de madurez observable en `sad-moron-access-governance`.

**Clasificación global del repositorio:** `REVIEW` — apto para uso como referencia de gobernanza conceptual; no apto aún como fuente normativa operacionalmente vinculante hasta que se cierren F-03, F-05 y F-07.

---

---

## 7. Relación con auditorías anteriores

| Versión | Archivo | Alcance | Resultado declarado |
|---|---|---|---|
| V1 | `reports/CLAUDE_EXTERNAL_GOVERNANCE_AUDIT_V1.md` | `sad-moron-framework` (inicial) | Remediación mínima: documentos ancla creados |
| V2 | `reports/CLAUDE_EXTERNAL_GOVERNANCE_AUDIT_V2.md` | `sad-moron-framework` + ecosistema cruzado | 7 hallazgos, estado `REVIEW REQUIRED` |

La próxima auditoría (V3) debería verificar el cierre de F-03, F-05 y F-07, y confirmar si la inversión de madurez entre capas (F-02) fue atendida.

---

*Auditoría V2 realizada externamente sobre contenido público de cuatro repositorios. No se accedió a contenido privado, credenciales, ni datos institucionales. Fecha: 2026-05-28.*
