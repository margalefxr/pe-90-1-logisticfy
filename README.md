# PE 90.1 — Marco de protección y programa de concienciación · Logisticfy

**Autor:** Xavier Margalef Riestra · **Módulo:** PE 90.1 · **Fecha:** 25/11/2026

Marco de protección, programa de concienciación y material M-01 para la empresa ficticia Logisticfy (logística B2B, 20 personas), como primer paso hacia un SGSI alineado con ISO/IEC 27001:2022.

---

## Índice

1. [Para Dirección](#para-dirección)
2. [Marco de protección](#1-marco-de-protección)
   - [1.1 Análisis del contexto](#11-análisis-del-contexto-y-necesidades-de-protección)
   - [1.2 Principios de ciberseguridad](#12-principios-generales-de-ciberseguridad)
   - [1.3 Normativa del puesto](#13-normativa-de-protección-del-puesto-de-trabajo)
   - [1.4 Obligaciones RGPD / LOPD-GDD](#14-obligaciones-legales-complementarias--rgpd--lopd-gdd)
   - [1.5 Herramientas recomendadas](#15-herramientas-de-implementación-recomendadas)
3. [Programa de concienciación](#2-programa-de-concienciación)
   - [2.1 Objetivos y destinatarios](#21-objetivos-y-destinatarios)
   - [2.2 Plan de acciones](#22-plan-de-acciones-de-concienciación)
   - [2.3 Seguimiento e indicadores](#23-seguimiento-y-evaluación-del-programa)
4. [Material de concienciación — M-01](#3-material-de-concienciación)
5. [Decisiones](#decisiones)
6. [Fuentes, supuestos y autoría](#4-fuentes-supuestos-y-autoría)

---

## Resumen

| | |
|---|---|
| **Objetivo** | Proponer el marco de protección, programa de concienciación y material M-01 para Logisticfy (20 personas, 80-120 expediciones/día, 25 clientes B2B) |
| **Resultado** | Completado. Todos los criterios del checklist cubiertos |
| **Marcos aplicados** | ISO/IEC 27001:2022 · ISO/IEC 27002:2022 · ISO/IEC 27005:2022 · ISO 22301:2019 · RGPD (EU 2016/679) · LOPD-GDD (LO 3/2018) |

| Criterio (PE 90.1 checklist) | ✅ | Sección |
|---|---|---|
| Procesos, funciones y activos relevantes seleccionados con justificación | ✅ | 1.1 |
| Principios de ciberseguridad claros y justificados | ✅ | 1.2 |
| Respaldo de Dirección: procedimiento, documentación y comunicación | ✅ | 1.2 |
| Normas con conductas, destinatarios, responsabilidades, verificación, comunicación, revisión y excepciones | ✅ | 1.3 |
| Objetivos de concienciación con destinatarios adecuados a las funciones | ✅ | 2.1 |
| Acciones relacionadas con objetivos: canal, temporalización, responsable y material | ✅ | 2.2 |
| Indicadores, evidencias y momentos de revisión definidos | ✅ | 2.3 |
| Al menos un material terminado y usable vinculado a objetivo y acción | ✅ | 3 (M-01) |
| Material técnicamente correcto, comprensible y adecuado al canal | ✅ | 3.1 (M-01) |
| Hechos, supuestos y propuestas diferenciados | ✅ | 4.2 |
| Identificadores de activos coherentes con la descripción de Logisticfy | ✅ | 1.1 |
| Sin datos personales reales ni credenciales | ✅ | — |
| Fuentes revisadas, autoría identificada | ✅ | 4.1 · 4.3 |

---

## Para Dirección

**Para:** CEO / Responsable de Operaciones  
**De:** Área de Seguridad de la Información  
**Asunto:** Propuesta de marco de protección y programa de concienciación

Logisticfy gestiona entre 80 y 120 expediciones diarias para 25 clientes B2B. La operativa depende de tres sistemas críticos — plataforma web, API de transportistas y base de datos — y de un equipo de 20 personas que maneja datos de clientes, envíos y facturación de forma continua.

Este documento propone el marco de protección y el programa de concienciación como primer paso estructurado hacia un SGSI alineado con ISO/IEC 27001:2022. No es el resultado de una auditoría técnica: es una propuesta basada en el análisis del contexto, los activos identificados y los riesgos de mayor probabilidad de impacto para el negocio.

**Estado de partida**

| Área | Estado | Observación |
|---|---|---|
| Gestión de identidades y accesos (IAM-01) | 🔴 | Sin proceso documentado de offboarding. Riesgo de cuentas huérfanas activas de ex-empleados |
| Copias de seguridad (BKP-01) | 🔴 | Backup existente sin prueba de restauración documentada. La continuidad no está garantizada |
| Normativa de seguridad del puesto | 🔴 | No existe normativa formal. El equipo no tiene referencia clara de conductas requeridas |
| Concienciación del personal | 🔴 | Sin programa activo. El vector humano (phishing, ingeniería social) no está mitigado |
| Plataforma web y API (SW-01, SW-02) | 🟡 | En funcionamiento sin revisión de seguridad formal documentada |
| Infraestructura (INF-01) | 🟡 | Servidor único sin redundancia. Punto único de fallo para todos los servicios digitales |

**Lo que propone este documento**

1. **Marco de protección** — seis principios de ciberseguridad, diez normas operativas con destinatarios y mecanismos de verificación, y el procedimiento para que Dirección respalde y comunique el marco al equipo.
2. **Programa de concienciación** — cuatro objetivos priorizados por riesgo, cuatro acciones concretas con responsable y temporalización, e indicadores para medir si el programa funciona.
3. **Material M-01** — guía de conductas seguras lista para distribuir, formato A4 una cara.

**Próximos pasos**

| Prioridad | Acción | Plazo |
|---|---|---|
| 🔴 Alta | Checklist de offboarding (IAM-01) | Semana 1 |
| 🔴 Alta | Prueba de restauración de backup (BKP-01) | Semana 2 |
| 🔴 Alta | Sesión de lanzamiento con todo el equipo | Semana 1 |
| 🔴 Alta | Registro de actividades de tratamiento (RGPD Art. 30) | Semana 2 |
| 🔴 Alta | Desplegar Bitwarden for Business | Semana 2 |
| 🟡 Media | Revisar accesos y privilegios por rol | Mes 1 |
| 🟡 Media | Configurar SPF + DKIM + DMARC | Mes 1 |
| 🟡 Media | Simulacro de phishing con feedback grupal | Mes 2 |

El coste de estas acciones es bajo. El riesgo de no hacerlas — una brecha de datos de clientes, una caída sin recuperación, un ex-empleado con acceso activo — es alto y golpea directo en la operativa y en la relación con los clientes.

Un SGSI se construye por capas. Todo lo que hay aquí se puede hacer con los recursos actuales y es la base sobre la que seguir construyendo.

---

## 1. Marco de protección

### 1.1 Análisis del contexto y necesidades de protección

Logisticfy gestiona entre 80 y 120 expediciones diarias para 25 clientes B2B. Los datos de clientes, transportistas y facturación circulan entre la plataforma web, la API de integración y el equipo de trabajo. Cualquier fallo en la confidencialidad, integridad o disponibilidad de esa información afecta la operativa, la relación con los clientes y la facturación al mismo tiempo.

El marco de protección parte de ese contexto, no de una obligación normativa. ISO/IEC 27001:2022 da el criterio para decidir qué proteger, cuánto esfuerzo dedicar a cada activo y cómo documentarlo de forma verificable. Las normas complementarias ISO/IEC 27002:2022 (guía de implementación de controles), ISO/IEC 27005:2022 (gestión del riesgo) e ISO 22301:2019 (continuidad de negocio) concretan cómo aplicar ese criterio en cada área.

| ID | Activo | Necesidad de protección | Proceso o función relacionada |
|---|---|---|---|
| DAT-01 | Base de datos (clientes, envíos, facturación) | **C/I/D críticas.** Una filtración, corrupción o pérdida afecta a la operativa, la relación con el cliente y la facturación al mismo tiempo. Es el activo de mayor riesgo acumulado | Gestión de expediciones · Facturación · Atención al cliente |
| IAM-01 | Identidades y mecanismos de acceso | **C/I altas.** El acceso no controlado es el vector de ataque más probable en empresas de este tamaño. Las cuentas huérfanas o privilegios excesivos son el hallazgo de mayor riesgo del análisis | Todos los procesos internos |
| BKP-01 | Copias de seguridad | **D/I altas.** Sin prueba de restauración documentada, el backup no garantiza la continuidad. Un backup no probado no existe funcionalmente | Continuidad del servicio ante incidente o fallo técnico |
| SW-01 | Plataforma web y backoffice | **I/D altas.** Es la interfaz principal del negocio para clientes y equipo. Una caída o manipulación para la operativa completa | Creación y seguimiento de expediciones · Gestión de incidencias |
| SW-02 | API de integración con transportistas | **I/D altas.** El canal entre Logisticfy y los tres transportistas expone datos de expediciones en cada intercambio si no está bien asegurado | Asignación de transportistas · Actualización de estados de seguimiento |
| INF-01 | Servidor Ubuntu de aplicación | **D alta.** Si cae el servidor, cae todo lo que depende de él. Es el punto único de fallo de los servicios digitales | Soporte de todos los servicios de la plataforma |
| EXT-01 | Integraciones con transportistas externos | **D/I medias.** Dependencia de terceros sin control directo sobre su seguridad. Un fallo en su lado afecta la operativa de Logisticfy | Asignación de envíos · Estados de seguimiento |
| COM-01 | Correo corporativo | **C alta.** Es el principal vector de entrada de ataques de ingeniería social. También se usa para intercambio de información sensible con clientes y proveedores | Comunicación interna y externa · Envío de documentación |
| HW-01 | Equipos Windows del personal | **C/I medias.** Los equipos acceden a DAT-01 y al backoffice. Un equipo comprometido es una puerta de entrada al resto de sistemas | Trabajo diario de todos los departamentos |
| SW-03 | Repositorios de código fuente | **I media.** El código contiene lógica de negocio, configuraciones y potencialmente credenciales. Una modificación no autorizada puede introducir vulnerabilidades en producción | Desarrollo y mantenimiento de la plataforma |
| MON-01 | Registros y sistema de monitorización | **I media.** Sin logs fiables no hay capacidad de detectar ni investigar incidentes. Son la evidencia principal ante cualquier auditoría | Auditoría y respuesta a incidentes |
| NET-01 | Red de oficina y Wi-Fi | **D media.** La conectividad es condición necesaria para operar. Una red sin segmentación amplifica el impacto de cualquier incidente interno | Trabajo de todos los puestos corporativos |
| PHY-01 | Oficina, accesos físicos y equipos compartidos | **C media.** El acceso físico no controlado expone equipos, documentación impresa y el servidor si está en las instalaciones | Protección del entorno de trabajo |

> **C** = Confidencialidad · **I** = Integridad · **D** = Disponibilidad

---

### 1.2 Principios generales de ciberseguridad

Los principios siguientes orientan las decisiones de protección. No son normas operativas: son los criterios detrás de ellas. Cuando hay que decidir si una medida nueva tiene sentido, cómo priorizar recursos o cómo resolver una excepción, estos principios son la referencia.

| ID | Principio | Aplicación en Logisticfy | Justificación |
|---|---|---|---|
| P-01 | **Mínimo privilegio** | Cada persona accede únicamente a los sistemas y datos que necesita para su función. Operaciones no necesita acceso a datos de facturación; Comercial no necesita acceso técnico al backoffice | DAT-01 e IAM-01: el acceso excesivo es la causa principal de brechas internas y el hallazgo de mayor riesgo del análisis. Control 8.2, ISO/IEC 27002:2022 |
| P-02 | **Responsabilidad en la custodia** | Cada activo tiene un propietario designado que responde de su protección. No es responsabilidad colectiva difusa: si es de todos, no es de nadie | ISO/IEC 27001:2022, control 5.9. Sin propietario asignado, ningún activo se protege de forma sostenida. Aplica a todos los activos del inventario |
| P-03 | **Proporcionalidad al riesgo** | Las medidas de seguridad se dimensionan al riesgo que mitigan. Una empresa de 20 personas no necesita los controles de un operador de infraestructuras críticas, pero sí los que protegen DAT-01 y la continuidad del servicio | Evita la burocracia que paraliza el negocio y el gasto en controles que no aportan valor real. Base metodológica: ISO/IEC 27005:2022 |
| P-04 | **Continuidad operativa** | Los sistemas críticos (DAT-01, SW-01, INF-01) tienen un plan de recuperación ante fallo con RTO y RPO definidos y probados. Si algo cae, se sabe cuánto tarda en volver y cómo | BKP-01: el backup existe, pero si la restauración no se ha probado y documentado, no hay garantía de continuidad. Referencia: ISO 22301:2019 |
| P-05 | **Concienciación como primer control** | El equipo es la primera y más efectiva línea de defensa. Ningún control técnico compensa un clic en un phishing o una contraseña compartida | COM-01 y HW-01: el vector humano es el más probable en una empresa de este tamaño. Es además el de menor coste de mitigación. Control 6.3, ISO/IEC 27002:2022 |
| P-06 | **Gestión proactiva del riesgo** | Los riesgos se identifican y tratan antes de que se materialicen, no después. Revisión periódica del registro de riesgos | Fundamento del SGSI según ISO/IEC 27001:2022, cláusula 6.1. Sin este principio, los demás son reactivos |

#### Conocimiento y respaldo de Dirección

Los principios anteriores y la normativa que los desarrolla necesitan el visto bueno explícito del CEO y del responsable de operaciones antes de llegar al equipo. Sin ese respaldo visible, la normativa se queda como un documento técnico que el equipo ignora.

**Procedimiento propuesto:**

1. **Presentación a Dirección** (semana 1) — sesión de 30 minutos con el CEO y el responsable de operaciones. Se presentan los seis principios, su justificación en el contexto de Logisticfy y las normas derivadas. El objetivo es que Dirección entienda por qué existen estos criterios, no solo que los apruebe.

2. **Documentación del respaldo** — acta de reunión firmada por el CEO que recoge su conocimiento y aprobación del marco de protección. Queda archivada como evidencia de liderazgo visible (ISO/IEC 27001:2022, cláusula 5.1).

3. **Comunicación al personal** — el CEO comunica al equipo el lanzamiento del marco de seguridad en un mensaje breve (email o reunión general), dejando claro que viene de Dirección. Esa comunicación marca la diferencia entre una norma que se sigue y una que se ignora.

---

### 1.3 Normativa de protección del puesto de trabajo

**Ámbito de aplicación:** toda la plantilla de Logisticfy (19 empleados y la persona en prácticas). Algunas normas aplican específicamente al departamento de Tecnología/IT por sus responsabilidades técnicas; se indica en cada caso.

**Responsabilidades:**
- **Responsable IT:** coordina la aplicación de la normativa técnica, gestiona excepciones y actualiza el documento anualmente o ante cambios relevantes.
- **Dirección (CEO / Responsable de operaciones):** valida y comunica la normativa. Aprueba excepciones que afecten a la operativa del negocio.
- **Todo el personal:** cumple las normas que les corresponden por función y reporta cualquier incidencia o duda al Responsable IT.

| ID | Norma | Destinatarios | Aplicación y verificación | Excepciones |
|---|---|---|---|---|
| N-01 | Cada persona utiliza sus propias credenciales. Está prohibido compartir contraseñas o acceder a sistemas con la cuenta de otra persona | Todo el personal | Verificable mediante logs de autenticación (MON-01). IT revisa accesos activos trimestralmente | Ninguna. Las cuentas son personales e intransferibles |
| N-02 | Las contraseñas de acceso a sistemas corporativos tienen un mínimo de 12 caracteres con letras, números y un carácter especial. Cambio obligatorio en el primer acceso | Todo el personal | IT verifica la política de contraseñas en el sistema de autenticación | El Responsable IT puede establecer un plazo de adaptación de hasta 30 días para cuentas existentes |
| N-03 | El acceso remoto al backoffice requiere autenticación de doble factor (MFA) | Todo el personal con acceso remoto; obligatorio para IT y Administración | IT verifica la activación de MFA en el panel de gestión de accesos (IAM-01) | No aplica a accesos exclusivamente desde la red de oficina mientras no exista segmentación de red documentada |
| N-04 | El puesto de trabajo se bloquea al ausentarse. El bloqueo automático se configura a un máximo de cinco minutos de inactividad | Todo el personal | IT puede verificar la configuración de bloqueo en HW-01 mediante inventario de configuraciones | Excepciones técnicas puntuales requieren aprobación escrita del Responsable IT |
| N-05 | Los documentos con información de clientes, expediciones o facturación no se dejan visibles en la mesa ni en pantalla cuando no se trabaja con ellos. Los impresos con datos sensibles se guardan o destruyen de forma segura al finalizar su uso | Todo el personal; especialmente Operaciones y Administración | Verificable mediante revisiones informales del responsable de departamento | Ninguna |
| N-06 | Los equipos corporativos (HW-01) no se utilizan para actividades personales. No se instala software sin autorización previa del Responsable IT | Todo el personal | IT verifica software instalado en inventarios periódicos de HW-01 | El Responsable IT puede autorizar instalaciones puntuales con justificación documentada |
| N-07 | Cualquier incidente de seguridad sospechoso (correo inusual, acceso no reconocido, comportamiento extraño del sistema) se comunica al Responsable IT en un máximo de una hora desde su detección | Todo el personal | Registro de incidencias gestionado por IT. Revisión mensual | Ninguna. La duda se comunica; IT determina si es un incidente real. No se penaliza el reporte de falsos positivos |
| N-08 | La información de clientes, expediciones y facturación se intercambia exclusivamente por canales corporativos aprobados (correo corporativo, plataforma). No se utiliza mensajería personal ni servicios de almacenamiento no corporativos para información de trabajo | Todo el personal; especialmente Operaciones y Atención al Cliente | Verificable ante incidentes mediante revisión de logs de COM-01 | Situaciones de emergencia operativa con autorización expresa del Responsable de Operaciones, documentada |
| N-09 | IT recibe notificación de baja de cualquier empleado con un mínimo de 24 horas de antelación para revocar accesos antes de la salida efectiva | Dirección y Responsable IT | Checklist de offboarding firmado como evidencia de cada baja. IT verifica cuentas activas trimestralmente | Bajas urgentes: el Responsable IT revoca todos los accesos en un máximo de dos horas desde la comunicación |
| N-10 | Todo empleado nuevo recibe una sesión básica de seguridad y la normativa de protección antes de acceder a los sistemas corporativos por primera vez | Responsable IT (entrega); todo el personal nuevo (recepción) | Firma del acuse de recibo de la normativa como evidencia de onboarding | No aplica a contratistas externos con acceso limitado y supervisado directamente por IT |

#### Comunicación y revisión de la normativa

- **Comunicación inicial:** el Responsable IT distribuye esta normativa por correo corporativo en la semana de lanzamiento. El correo incluye un resumen de las normas más relevantes para cada departamento y solicita acuse de lectura. Los acuses se archivan como evidencia.
- **Gestión de excepciones:** las excepciones que requieren autorización (N-03, N-06, N-08) se solicitan al Responsable IT por escrito. IT las registra y comunica la decisión en un plazo de 24 horas.
- **Revisión y actualización:** el Responsable IT revisa esta normativa anualmente o cuando haya un cambio relevante en la organización, los sistemas o el contexto de amenazas. Las actualizaciones las aprueba el CEO antes de distribuirlas al equipo.

---

### 1.4 Obligaciones legales complementarias — RGPD / LOPD-GDD

ISO/IEC 27001:2022 no reemplaza las obligaciones del Reglamento General de Protección de Datos (RGPD, Reglamento EU 2016/679) ni de su transposición española en la Ley Orgánica 3/2018 (LOPD-GDD). Son marcos paralelos que se solapan en los controles técnicos pero tienen exigencias propias que hay que cumplir.

**Por qué aplica a Logisticfy:** la empresa trata datos personales de forma habitual — datos de contacto de clientes B2B, datos de destinatarios de envíos, registros de comunicaciones. DAT-01, COM-01 y EXT-01 son los activos directamente implicados.

| Obligación | Base legal | Activo implicado | Estado estimado |
|---|---|---|---|
| **RAT** — Registro de Actividades de Tratamiento: qué datos se tratan, con qué finalidad, quién los trata y durante cuánto tiempo | RGPD Art. 30 | DAT-01 · COM-01 · EXT-01 | 🔴 Sin evidencia |
| **Base legal por tratamiento** — cada tratamiento de datos necesita una base legal documentada (ejecución de contrato, interés legítimo, consentimiento, etc.) | RGPD Art. 6 | DAT-01 · COM-01 | 🔴 No verificado |
| **Acuerdos con encargados** — los transportistas (EXT-01) tratan datos de destinatarios. Necesitan contrato de encargo de tratamiento con cláusulas de seguridad | RGPD Art. 28 | EXT-01 | 🔴 Sin evidencia |
| **Canal de derechos de interesados** — los destinatarios pueden ejercer derechos de acceso, supresión, rectificación y portabilidad. Debe haber canal y plazo de respuesta (1 mes) | RGPD Art. 15-22 | DAT-01 · COM-01 | 🔴 Sin procedimiento |
| **Notificación de brechas** — una brecha que afecte a datos personales hay que notificarla a la AEPD en 72 horas | RGPD Art. 33-34 | Todos | 🔴 Sin procedimiento |
| **Período de conservación** — definir por cuánto tiempo se guardan los datos de expediciones, clientes y facturación | RGPD Art. 5.1.e | DAT-01 | 🔴 No definido |
| **Privacidad desde el diseño** — los sistemas nuevos incorporan privacidad desde el diseño y por defecto | RGPD Art. 25 | SW-01 · SW-02 | 🟡 A validar |

> **Nota sobre el DPD:** la LOPD-GDD no obliga a designar un Delegado de Protección de Datos para empresas del perfil de Logisticfy (actividad no incluida en el Art. 37 RGPD). Conviene designar un responsable interno de privacidad — puede ser el mismo Responsable IT — para centralizar las obligaciones y ser el punto de contacto con la AEPD si hace falta.

**Relación entre ISO 27001 y RGPD**

| Qué cubre ISO 27001 | Qué exige RGPD además |
|---|---|
| Control de accesos a DAT-01 (8.3) | Registro de Actividades de Tratamiento (RAT) |
| Gestión de incidentes y notificación interna (5.24-5.26) | Notificación a AEPD en 72h con plantilla estructurada |
| Gestión de proveedores y terceros (5.19-5.22) | Contrato de encargo de tratamiento con cada proveedor que toca datos personales |
| Clasificación y protección de la información (5.12-5.13) | Período de conservación definido y aplicado |
| Seguridad en el desarrollo (8.25-8.31) | Privacy by design documentado como requisito de cada desarrollo |

---

### 1.5 Herramientas de implementación recomendadas

Las normas de la sección 1.3 y los controles de ISO/IEC 27002:2022 que las respaldan definen el *qué*. Esta sección concreta el *con qué*: las herramientas que hacen que esas normas sean operativas y verificables, no solo papel.

| Control ISO 27002:2022 | Norma asociada | Herramienta recomendada | Coste aprox. | Justificación |
|---|---|---|---|---|
| **5.17** — Información de autenticación | N-01 / N-02 | **Bitwarden for Business** (open source, self-hosteable o cloud) | ~3 €/u/mes | Gestor de contraseñas corporativo. Elimina contraseñas débiles, reutilizadas o compartidas. Genera contraseñas fuertes y las centraliza bajo control IT. Alternativa: 1Password Teams |
| **8.5** — Autenticación segura | N-03 | **Microsoft Authenticator** (si tienen M365) o **Authy** | Gratuito | MFA por TOTP. Se integra con cualquier sistema que soporte 2FA estándar |
| **5.14** — Transferencia de información | N-08 / COM-01 | **SPF + DKIM + DMARC** (configuración DNS del dominio de correo) | 0 € — solo configuración | Hardening del correo corporativo. Previene spoofing del dominio de Logisticfy y reduce el phishing entrante. Verificable con MXToolbox o mail-tester.com |
| **8.8** — Gestión de vulnerabilidades técnicas | INF-01 / SW-01 | **unattended-upgrades** (Ubuntu) + **Lynis** | 0 € | Parches automáticos del SO en INF-01. Lynis genera un informe de hardening del servidor con recomendaciones priorizadas |
| **5.18** — Derechos de acceso | N-01 / IAM-01 | **Checklist de revisión de accesos** (hoja de cálculo) + auditoría trimestral | 0 € | Revisión manual trimestral: IT compara cuentas activas en cada sistema contra la lista de empleados vigente. Detecta cuentas huérfanas |
| **8.13** — Copias de seguridad | BKP-01 | **Procedimiento de prueba de restauración documentado** + backup existente con logs verificables | 0 € adicional | El problema de BKP-01 no es de herramienta sino de proceso. Se necesita un procedimiento firmado con fecha, resultado y responsable |
| **5.30** — Preparación para la continuidad | BKP-01 / INF-01 | **Restic** o **BorgBackup** (open source) | 0 € | Verifican la integridad de cada copia automáticamente. Para evaluar si la solución actual lo hace |
| **8.16** — Monitorización de actividades | MON-01 | **Syslog centralizado** en INF-01 + **Fail2ban** | 0 € | Logs centralizados con retención mínima de 90 días. Fail2ban bloquea automáticamente IPs con intentos de acceso fallidos repetidos |

> Criterio de selección: se priorizan herramientas de código abierto o con tier gratuito funcional, siguiendo el principio P-03 (proporcionalidad al riesgo) y el tamaño real de la empresa. Las comerciales aparecen como alternativa cuando el coste compensa.

---

## 2. Programa de concienciación

### 2.1 Objetivos y destinatarios

| ID | Objetivo | Destinatarios | Justificación |
|---|---|---|---|
| O-01 | El equipo identifica y reporta intentos de phishing o ingeniería social en lugar de interactuar con ellos | Todo el personal (20 personas) | COM-01 es el principal vector de ataque externo. 25 clientes B2B y tres transportistas generan comunicación regular que puede usarse como anzuelo. Un solo clic compromete DAT-01 |
| O-02 | Operaciones y Atención al Cliente aplican hábitos de acceso seguro (bloqueo de pantalla, credenciales propias, canales corporativos) en su trabajo diario | Operaciones (6) · Atención al Cliente (4) | Estos departamentos manejan información de expediciones con más frecuencia y en entornos más dinámicos. Mayor probabilidad de error humano bajo presión operativa. Directamente relacionado con N-01, N-04 y N-08 |
| O-03 | Dirección y IT ejecutan el checklist de onboarding y offboarding en el 100% de altas y bajas, sin excepciones | Dirección (2) · Responsable IT | IAM-01 tiene el riesgo más alto del análisis: cuentas de ex-empleados activas. Este objetivo lo cierra directamente. No es un problema técnico sino de proceso |
| O-04 | Todo el personal sabe cómo y a quién reportar un incidente de seguridad | Todo el personal (20 personas) | Sin canal claro de reporte, los incidentes no se gestionan a tiempo. N-07 define la obligación; este objetivo garantiza que el equipo sabe cómo cumplirla |

---

### 2.2 Plan de acciones de concienciación

| ID | Objetivo | Destinatarios | Acción y canal | Temporalización | Responsable | Material |
|---|---|---|---|---|---|---|
| A-01 | O-01 · O-02 · O-03 · O-04 | Todo el personal | **Sesión de lanzamiento del marco de seguridad.** Reunión presencial de 45 minutos. Se presentan los principios, las normas y el canal de reporte de incidentes. Se distribuye M-01 en papel. El CEO abre la sesión | Semana 1, antes de publicar la normativa | Responsable IT (conduce) · CEO (abre) | M-01 |
| A-02 | O-01 | Todo el personal | **Simulacro de phishing.** Email simulado enviado sin previo aviso. Se registra quién interactúa con él. Sesión de feedback grupal de 20 minutos con resultados anonimizados al mes siguiente | Mes 2, sin comunicación previa | Responsable IT | Informe de resultados (interno) |
| A-03 | O-03 | Dirección · Responsable IT | **Implementación del checklist de onboarding/offboarding.** Sesión de trabajo de 30 minutos para revisar, validar y dejar operativo el checklist antes de la próxima alta o baja | Semana 2 | Responsable IT | Checklist de altas y bajas (documento de proceso interno) |
| A-04 | O-01 · O-04 | Todo el personal | **Recordatorio trimestral por correo corporativo.** Email breve con recordatorio de las conductas clave y el canal de reporte. Se adjunta M-01 actualizado si hay cambios | Cada trimestre, primer lunes del mes | Responsable IT | M-01 (versión actualizada si aplica) |

---

### 2.3 Seguimiento y evaluación del programa

| Objetivo / Acción | Indicador | Evidencia prevista | Momento de revisión |
|---|---|---|---|
| O-01 / A-02 | % de personas que interactuaron con el phishing simulado. Objetivo: reducción >50% respecto al primer simulacro en el siguiente ciclo | Informe de resultados del simulacro (anónimo por grupo, no individual) | Tras cada simulacro. Revisión comparativa a los 6 meses |
| O-02 / A-01 | Número de incidentes relacionados con credenciales compartidas o uso de canales no autorizados (N-01, N-08) | Registro de incidencias gestionado por IT | Revisión mensual del registro de incidencias |
| O-03 / A-03 | % de altas y bajas con checklist completado y firmado. Objetivo: 100% desde la implantación | Checklists firmados archivados por IT | Revisión tras cada alta o baja. Auditoría semestral del archivo |
| O-04 / A-01 | Número de incidentes reportados por el equipo vs. incidencias detectadas posteriormente en logs sin reporte previo | Comparativa entre reportes recibidos e incidencias encontradas en MON-01 | Trimestral, en la reunión de revisión del programa |

**Revisión y mejora**

La revisión del programa es trimestral, coincidiendo con A-04. El Responsable IT presenta a Dirección los indicadores en una reunión de 30 minutos. Si algún indicador no cumple el objetivo, se analiza la causa: si es de formación (repetir o ajustar la acción), de proceso (revisar la norma asociada) o de herramienta (cambio técnico necesario). Los ajustes y la decisión quedan documentados en el registro de revisiones del programa.

---

## 3. Material de concienciación

### 3.1 M-01 — Guía de conductas seguras

**ID:** M-01 · **Formato:** A4 una cara · **Distribución:** papel (A-01) + PDF adjunto (A-04)

---

> Este documento resume las conductas de seguridad que aplican a todo el equipo. No son recomendaciones: son parte de cómo trabajamos.

---

**Tus credenciales, solo tuyas**

- Tu usuario y contraseña son personales. No los compartas, ni con IT ni con tu responsable.
- Si alguien te pide tu contraseña, es un intento de ataque. Repórtalo a IT.
- Contraseña mínima: 12 caracteres con letras, números y un símbolo (`@`, `#`, `!`...).
- Si tienes dudas sobre tu contraseña, cámbiala y avisa a IT.

---

**Bloquea el equipo. Siempre.**

- Cuando te levantes de la mesa, bloquea la pantalla (`Windows + L`).
- El bloqueo automático está configurado a 5 minutos, pero no esperes a que salte.
- Documentos con datos de clientes: ciérralos o ponlos boca abajo si son en papel cuando no los usas.

---

**Correo: piensa antes de hacer clic**

Los ataques de phishing imitan correos de transportistas, clientes o compañeros. Señales de alerta:

- Te piden que hagas algo urgente o inusual ("verifica tu cuenta", "pago pendiente").
- El remitente tiene un dominio parecido al habitual pero no exacto.
- El enlace no lleva a donde dice cuando pasas el ratón por encima.

**Si tienes dudas, no hagas clic. Reenvía el correo a IT antes de hacer nada.**

---

**Canales corporativos para información de trabajo**

- Datos de clientes, expediciones y facturación: solo por correo corporativo o la plataforma.
- WhatsApp, Telegram o cuentas de correo personales no son canales válidos para información de trabajo.
- Duda sobre si algo puede enviarse por un canal → pregunta a IT antes de enviarlo.

---

**Cómo reportar un incidente**

Si detectas algo raro — un acceso que no reconoces, un correo sospechoso, un comportamiento extraño del sistema — avisa a IT en menos de una hora.

📧 **[dirección correo IT]** &nbsp;&nbsp; 📞 **[teléfono o extensión IT]**

No hace falta estar seguro de que es un problema. Si tienes dudas, reporta. No se penaliza el aviso.

---

*Versión 1.0 — noviembre 2026 — Responsable IT, Logisticfy*

---

### 3.2 Vinculación con el programa

| Campo | Contenido |
|---|---|
| **Objetivo relacionado** | O-01 (reconocimiento de phishing) · O-02 (hábitos de acceso seguro) · O-04 (reporte de incidentes) |
| **Acción relacionada** | A-01 (sesión de lanzamiento) · A-04 (recordatorio trimestral) |
| **Destinatarios** | Todo el personal de Logisticfy (20 personas) |
| **Canal** | A-01: papel al inicio de la sesión, una cara A4. A-04: adjunto PDF en el correo trimestral |
| **Uso previsto** | En A-01: el Responsable IT distribuye M-01 al inicio y lo usa como referencia para explicar N-01, N-04, N-07 y N-08 de forma no técnica. Al finalizar, cada persona se lo queda como referencia en su puesto. En A-04: se adjunta como PDF al correo de recordatorio trimestral, con una línea que indica si ha habido cambios respecto a la versión anterior |

---

## Decisiones

| Decisión | Motivo |
|---|---|
| 6 principios (P-01 a P-06), no más | Cubren los vectores de riesgo principales de Logisticfy: acceso, continuidad, vector humano y gestión del riesgo. Más principios generarían solapamiento sin añadir cobertura real |
| 10 normas (N-01 a N-10) | Una por riesgo prioritario identificado en el análisis. Sin normas redundantes ni genéricas que no se puedan verificar |
| Formato M-01: A4 una cara | Canal de distribución presencial y correo. Una cara para que se conserve en el puesto y no se descarte como documentación larga. Mayor densidad → menor retención |
| Capa RGPD/LOPD añadida (sección 1.4) | Logisticfy trata datos de destinatarios de envíos. RGPD aplica desde el primer día y tiene obligaciones propias que ISO 27001 no cubre. Ignorarlo no es una opción legal |
| Herramientas de implementación añadidas (sección 1.5) | El "qué" sin el "con qué" no es operativo para una empresa de 20 personas. Los controles de ISO 27002 son la guía; las herramientas concretan cómo se ejecutan |
| Bitwarden como gestor de contraseñas | Open source, self-hosteable si se quiere control total, ~3 €/u/mes en cloud. Elimina el problema de contraseñas débiles sin coste de licencia elevado. Alternativa validada: 1Password Teams |
| ENS, MAGERIT y NIS2 excluidos del alcance | Logisticfy es empresa privada sin contratos con administración pública y con menos de 50 empleados. Ninguno de los tres es de aplicación obligatoria en este perfil |

---

## 4. Fuentes, supuestos y autoría

### 4.1 Fuentes y recursos utilizados

| Fuente o recurso | Referencia | Uso realizado |
|---|---|---|
| PE 90.1 Logisticfy | Descripción de empresa, organización, procesos y stack técnico | Base del análisis de contexto y activos (sección 1.1) |
| ISO/IEC 27001:2022 | Cláusulas 5.1, 5.9, 6.1; controles del Anexo A (bloques 5, 6, 7, 8) | Marco de principios, estructura de la normativa y programa |
| ISO/IEC 27002:2022 | Guía de implementación de controles del Anexo A | Referencia para la aplicación práctica de cada norma y control |
| ISO/IEC 27005:2022 | Gestión del riesgo de seguridad de la información | Base metodológica del principio P-06 y el análisis de riesgos previo al documento |
| ISO 22301:2019 | Continuidad de negocio | Referencia para P-04 y los controles relacionados con BKP-01 e INF-01 |
| RGPD (Reglamento EU 2016/679) | Art. 5, 6, 25, 28, 30, 33-34 | Base de las obligaciones de protección de datos personales (sección 1.4) |
| LOPD-GDD (LO 3/2018) | Transposición española del RGPD | Obligaciones específicas en el contexto normativo español |

### 4.2 Supuestos y hechos diferenciados

**Hechos** (datos del brief de Logisticfy):
- Empresa de logística B2B, 20 personas, 80-120 expediciones/día, 25 clientes
- Stack técnico: plataforma web, API con tres transportistas, servidor Ubuntu, base de datos, repositorios de código, equipos Windows
- Backup existente, sin prueba de restauración documentada

**Supuestos** (no hay información en el brief, se asumen para hacer el análisis):
- **Stack técnico:** sin versiones ni configuraciones concretas de Ubuntu, PostgreSQL o Nginx, los controles tecnológicos se proponen por perfil de riesgo del activo, no por una configuración verificada
- **MFA:** se asume que el sistema de autenticación actual puede soportar MFA con una integración estándar. Si no fuera técnicamente posible con la configuración existente, N-03 necesita un trabajo previo de IT que está fuera del alcance de este documento
- **Contratos con transportistas:** no hay información sobre los contratos vigentes. Se asume que no incluyen cláusulas de seguridad de la información ni acuerdos de encargo de tratamiento (RGPD Art. 28), alineado con la valoración 🔴 de EXT-01

**Propuestas** (resultado del análisis, no controles implantados ni verificados):
- Los seis principios, las diez normas, el programa de concienciación, las herramientas recomendadas y el material M-01 son propuestas. Ninguno refleja un estado de implementación real. No hay hallazgos de auditoría técnica.

### 4.3 Autoría y herramientas

Documento elaborado como práctica profesional del módulo PE 90.1. Las decisiones de diseño — selección de principios, priorización de normas, estructura del programa de concienciación y contenido de M-01 — son propias, basadas en la lectura directa de ISO/IEC 27001:2022 e ISO/IEC 27002:2022 y en el uso de IA generativa como herramienta de estructuración, revisión de terminología técnica y verificación de coherencia del conjunto.
