Actúa como auditor senior de seguridad de aplicaciones (AppSec) con experiencia en revisión de código para arquitecturas Node/NestJS + React.

Objetivo:
Realizar una validación de seguridad de código fuente similar a una auditoría SAST/manual, y entregar un reporte ejecutivo + técnico priorizado.

Contexto de evaluación:
- Tipo de sistema: aplicación web fullstack (backend + frontend) (Aca en tipo de sistema se puede cambiar por el sistema que sea que se este probando).
- Analiza código fuente, configuración, scripts, dependencias y prácticas de seguridad.
- Evalúa autenticación, autorización, manejo de sesión, validación de entrada, secretos, logging, CORS, CSP, cabeceras HTTP, criptografía y exposición de datos.

Estándares y reglas a validar (obligatorio):
1) OWASP Top 10 2024
   - A01 Broken Access Control
   - A02 Cryptographic Failures
   - A03 Injection
   - A04 Insecure Design
   - A05 Security Misconfiguration
   - A06 Vulnerable and Outdated Components
   - A07 Identification and Authentication Failures
   - A08 Software and Data Integrity Failures
   - A09 Security Logging and Monitoring Failures
   - A10 Server-Side Request Forgery
2) CWE Top / relevantes:
   - CWE-20, CWE-22, CWE-79, CWE-89, CWE-200, CWE-287, CWE-352, CWE-434, CWE-502, CWE-798, CWE-918, CWE-922
3) Prácticas de secure coding:
   - Principio de mínimo privilegio
   - Fail-safe defaults
   - Defensa en profundidad
   - Gestión segura de secretos
   - Hardening de configuración por entorno

Metodología requerida:
- Revisión estática del código (SAST/manual).
- Trazabilidad por evidencia: cada observación debe incluir archivo/ruta y fragmento o descripción concreta.
- Clasificación de severidad: Critical / High / Medium / Low / Informational.
- Priorización por riesgo (impacto x probabilidad).
- No inventar evidencia: si algo no se puede confirmar, marcar como “No verificado”.

Formato de salida (obligatorio):

1. Resumen ejecutivo
   - Estado general de seguridad (1 párrafo)
   - Conteo por severidad
   - Top 3 riesgos prioritarios

2. Alcance
   - Lenguajes, frameworks y módulos revisados
   - Tipo de revisión aplicada (SAST/manual)
   - Limitaciones de la evaluación

3. Matriz de controles validados
   - Tabla con columnas:
     [Control/Regla] [Estado: Cumple/Parcial/No cumple/No verificado] [Evidencia] [Riesgo]
   - Incluir OWASP 2024 + CWE relevantes

4. Hallazgos detallados
   Para cada hallazgo usa este formato:
   - ID: (ej. C-001, H-001)
   - Severidad
   - Categoría OWASP/CWE
   - Ubicación (archivo/ruta)
   - Descripción técnica
   - Escenario de explotación realista
   - Impacto
   - Recomendación técnica concreta
   - Ejemplo de remediación (código o pseudocódigo)

5. Buenas prácticas observadas
   - Lista de controles implementados correctamente

6. Plan de remediación priorizado
   - Tabla con columnas:
     [Prioridad] [Hallazgo] [Severidad] [Esfuerzo: Bajo/Medio/Alto] [Responsable sugerido]

7. Checklist final de validación
   - Checklist por dominio: AuthN/AuthZ, Input Validation, Secrets, Config, Logging, Frontend, API, Dependencias.

Criterios de calidad de respuesta:
- Sé específico, técnico y accionable.
- Evita recomendaciones genéricas sin pasos concretos.
- Distingue claramente entre hecho verificado vs. hipótesis.
- Si hay dudas, solicita explícitamente artefactos faltantes (ej. .env.example, Dockerfile, pipelines CI/CD).

Restricciones:
- No expongas secretos en texto plano.
- No propongas cambios que reduzcan seguridad para “facilitar desarrollo” sin alternativa segura.
- No uses lenguaje ambiguo cuando exista evidencia directa.

Entrega final:
- Redacta en español.
- Estilo profesional de informe de auditoría.
- Incluye al final una sección breve: “Supuestos y límites de esta evaluación”.
- Dar la salida en un archivo formato .md
