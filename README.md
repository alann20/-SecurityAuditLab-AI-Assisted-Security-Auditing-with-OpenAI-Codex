
# SecurityAuditLab
## AI-Assisted Security Auditing with OpenAI Codex

![OpenAI Codex](https://img.shields.io/badge/AI-OpenAI%20Codex-412991)
![Security](https://img.shields.io/badge/Focus-Application%20Security-red)
![Analysis](https://img.shields.io/badge/Analysis-Static-blue)
![Status](https://img.shields.io/badge/Status-Experimental-orange)

## 1. Descripción del proyecto

**SecurityAuditLab** es un laboratorio experimental orientado a explorar el uso de inteligencia artificial aplicada a la auditoría de seguridad de código fuente, utilizando **OpenAI Codex CLI** como agente de análisis.

El proyecto implementa una metodología de revisión estática asistida por IA, apoyada en una skill especializada denominada `security-audit`, diseñada para identificar posibles vulnerabilidades, analizar evidencias técnicas, clasificar riesgos y proponer recomendaciones de remediación.

El objetivo es evaluar cómo un agente de IA puede apoyar las actividades de seguridad de aplicaciones, facilitando la identificación temprana de riesgos durante el ciclo de desarrollo de software.

## 2. Objetivos

- Implementar un laboratorio reproducible de auditoría de seguridad utilizando OpenAI Codex CLI.
- Incorporar una skill especializada para estandarizar los criterios de análisis.
- Identificar patrones de código potencialmente vulnerables.
- Evaluar riesgos relacionados con OWASP y buenas prácticas de desarrollo seguro.
- Generar informes técnicos con evidencias, severidad e instrucciones de remediación.
- Explorar el potencial de la IA como herramienta complementaria para actividades de AppSec y Secure SDLC.

## 3. Arquitectura del laboratorio

El laboratorio se compone de los siguientes elementos:

| Componente | Descripción |
|---|---|
| OpenAI Codex CLI | Agente de IA utilizado para analizar el código fuente. |
| Security Audit Skill | Instrucciones especializadas para ejecutar la auditoría. |
| SKILL.md | Define el alcance, criterios y metodología de revisión. |
| app.js | Aplicación de prueba con patrones de código deliberadamente inseguros. |
| Informe técnico | Resultado del análisis, evidencias y recomendaciones. |

### Estructura del proyecto

```text
SecurityAuditLab/
│
├── .agents/
│   └── skills/
│       └── security-audit/
│           └── SKILL.md
│
├── app.js
│
├── README.md
│
└── .gitignore
```

## 4. Tecnologías utilizadas

- OpenAI Codex CLI.
- JavaScript.
- Node.js.
- Security Audit Skill.
- Git y GitHub.
- OWASP Top 10 como referencia para la clasificación de riesgos.

## 5. Alcance de la auditoría

| Área | Objetivo |
|---|---|
| Injection | Identificar construcción insegura de consultas y comandos. |
| Authentication | Revisar posibles debilidades en mecanismos de autenticación. |
| Authorization | Identificar controles de acceso insuficientes. |
| Input Validation | Evaluar validación y sanitización de entradas. |
| Sensitive Data | Identificar posibles exposiciones de información sensible. |
| Security Configuration | Detectar configuraciones potencialmente inseguras. |
| Dependencies | Revisar riesgos de dependencias cuando exista evidencia disponible. |

## 6. Metodología de análisis

La auditoría se desarrolla mediante las siguientes etapas:

1. **Reconocimiento:** identificación de archivos y componentes del proyecto.
2. **Análisis estático:** revisión de patrones de código y posibles vulnerabilidades.
3. **Identificación de evidencias:** localización de archivos, líneas y fragmentos relevantes.
4. **Clasificación:** asignación de severidad a los hallazgos.
5. **Evaluación de impacto:** descripción de las consecuencias potenciales.
6. **Remediación:** propuesta de controles y correcciones.
7. **Reporte:** consolidación de resultados en un informe técnico.

## 7. Criterios de severidad

| Severidad | Descripción |
|---|---|
| Critical | Riesgo crítico con impacto potencial muy elevado. |
| High | Vulnerabilidad de alto impacto que requiere atención prioritaria. |
| Medium | Riesgo moderado que debe corregirse de acuerdo con su exposición. |
| Low | Debilidad de menor impacto o alcance limitado. |

La severidad deberá justificarse con base en la evidencia disponible y el contexto de la aplicación. No se deben presentar riesgos hipotéticos como vulnerabilidades explotables confirmadas.

## 8. Ejecución del laboratorio

### Requisitos

- Windows, Linux o macOS.
- OpenAI Codex CLI instalado y configurado.
- Acceso a una cuenta compatible con Codex.
- Skill `security-audit` disponible en el repositorio.

### Iniciar Codex

Desde la raíz del proyecto:

```bash
codex --sandbox read-only --ask-for-approval on-request
```

### Verificar la skill

Dentro de Codex:

```text
/skills
```

Buscar la skill:

```text
security-audit
```

### Ejecutar el análisis

Utilizar el siguiente prompt:

```text
Utiliza la skill security-audit para realizar una
auditoría estática de seguridad del proyecto actual.

Analiza los archivos disponibles e identifica posibles
vulnerabilidades de seguridad.

Para cada hallazgo presenta:

- ID del hallazgo.
- Nombre de la vulnerabilidad.
- Archivo y línea afectada.
- Severidad.
- Evidencia técnica.
- Impacto potencial.
- Recomendación de remediación.

Restricciones:

- Mantener el análisis en modo de solo lectura.
- No modificar archivos.
- No instalar dependencias.
- No ejecutar la aplicación.
- No realizar pruebas de explotación.
- No acceder a sistemas externos.
- No inventar hallazgos.

Distingue entre vulnerabilidades confirmadas,
riesgos potenciales y limitaciones de evidencia.
Presenta el informe directamente en pantalla.
```

## 9. Consideraciones de seguridad

Este laboratorio utiliza código deliberadamente inseguro con fines educativos y de experimentación.

Las pruebas deben realizarse exclusivamente sobre código propio o expresamente autorizado.

El análisis estático no sustituye pruebas dinámicas, revisión manual, análisis de dependencias ni una evaluación integral de seguridad.

Los resultados generados por IA deben ser revisados y validados por un profesional de seguridad antes de considerarse hallazgos definitivos.

## 10. Resultados esperados

El resultado del laboratorio será un informe técnico estructurado que permita:

- Identificar patrones de código potencialmente vulnerables.
- Comprender el impacto de los riesgos detectados.
- Obtener recomendaciones de remediación.
- Evaluar la utilidad de Codex en actividades de auditoría de seguridad.
- Establecer una base para comparar posteriormente distintos agentes de IA.

## 11. Evolución del laboratorio

Este proyecto constituye la primera implementación de una iniciativa experimental para evaluar agentes de IA aplicados a la seguridad de aplicaciones.

Como siguiente etapa se contempla comparar los resultados de OpenAI Codex con otros agentes, utilizando el mismo código fuente, criterios de auditoría y metodología de evaluación.

---

**Proyecto:** SecurityAuditLab  
**Enfoque:** AI-Assisted Application Security  
**Agente:** OpenAI Codex CLI  
**Tipo de análisis:** Static Code Security Analysis  
**Estado:** Experimental / Proof of Concept
