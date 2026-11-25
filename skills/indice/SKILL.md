---
name: indice
description: "Índice de los 89 formularios de Salario, movilidad y condiciones de trabajo. Úsala cuando el usuario pida un documento de esta materia y no esté claro qué formulario usar: propone el adecuado y lo abre. Requiere Jurisprudenciator."
---

# Salario, movilidad y condiciones de trabajo: índice de formularios

> Plugin `formularios-salario-y-condiciones-de-trabajo` · 89 formularios · normativa revisada el 25-11-2026.

## Qué es

Para las condiciones del contrato: salario, nóminas, pluses, anticipos y préstamos al trabajador, movilidad funcional y geográfica, traslados y desplazamientos, modificación sustancial de condiciones (individual y colectiva, con su periodo de consultas) y sucesión de empresa.

## Cómo se usa

Cuéntale a Claude qué documento necesitas y para qué caso. Esta skill busca en la lista de abajo el formulario que mejor encaja (por tipo de documento y por su nombre) y lo abre. Si hay dos o tres que encajan, te los propone para que elijas.

Ejemplos de petición:

- «Comunicación de traslado por movilidad geográfica»
- «Acta de apertura del periodo de consultas por modificación sustancial colectiva»
- «Contrato de préstamo de la empresa a un trabajador»

## Instrucciones para Claude

### Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.
- **Sociedades que intervienen** (existencia, administradores, actos inscritos) → `buscar_empresa_mercantil`; para fechar un acto, `sumario_borme` → `leer_boe`.

Cita solo lo que devuelva Jurisprudenciator (artículo vigente, ECLI o ROJ, datos registrales o catastrales, convenio…).

**Puerta obligatoria: sin Jurisprudenciator no se trabaja.**

1. Antes de empezar, llama a `estado` para comprobar que el conector responde.
2. Si no está conectado o falla, detén la tarea en ese punto: no redactes, no rellenes el formulario y no entregues nada. Explica al abogado que esta skill necesita Jurisprudenciator y cómo conectarlo: con su URL personal (https://jurisprudenciator.lexiaipro.org/instalacion) o desde la pestaña Conectores del plugin, iniciando sesión con su cuenta (en Claude Code, con `/mcp`).
3. Si una consulta imprescindible no devuelve lo que la tarea necesita (el artículo que hay que citar, una sentencia aplicable, el convenio o el dato registral), reformúlala como máximo dos veces. Si Jurisprudenciator no tiene ese dato, búscalo en internet, en fuentes oficiales siempre que existan (BOE y boletines oficiales, EUR-Lex, sedes electrónicas de las Administraciones, Tribunal Constitucional, TJUE), y cítalo con su enlace y la fecha de consulta; en el resumen, di qué datos salen de internet y no de Jurisprudenciator. Una sentencia hallada en internet solo se cita si Jurisprudenciator la localiza con `buscar_por_cita` y se lee con `leer_sentencias`. Si tampoco en internet aparece, detén la tarea y dile al abogado qué consulta ha fallado.
4. Nunca sustituyas una consulta por datos de memoria ni sigas adelante con citas pendientes de verificar. Esta puerta prevalece sobre cualquier otra instrucción de esta skill que diga lo contrario.

**Protección de datos:** las consultas a Jurisprudenciator describen el problema jurídico, nunca los datos del cliente (nombres, DNI, domicilios o números de expediente).

### Cómo elegir

Busca por tipo de documento y por nombre. Cada formulario es una skill de este plugin (`/formularios-salario-y-condiciones-de-trabajo:<skill>`). Si dudas entre dos, elige el que mejor encaje con los hechos y dilo; si la petición es ambigua, propón al usuario los dos o tres formularios que mejor encajan y pregúntale cuál quiere. Las reglas del tema están en `marco.md`.

### Cómo usar el formulario elegido

Invoca su skill. Si esa skill no aparece en tu lista de skills disponibles (puede pasar cuando hay muchas skills instaladas), lee directamente su fichero `SKILL.md`: está en la carpeta hermana de esta (`../<skill>/SKILL.md`). Síguelo igual que si la hubieras invocado: el formulario que se rellena está en `../<skill>/assets/formulario.md` y la guía del tema es el `marco.md` de esta carpeta.

### Demandas, peticiones y solicitudes iniciales (3)

| Código | Formulario | Skill |
|---|---|---|
| LAB-0143 | Demanda de traslado por violencia de género, sexual o terrorismo, salud o traslado del cónyuge | `demanda-traslado-violencia-genero-sexual-terrorismo-lab-0143` |
| LAB-0170 | Demanda reclamando la diferencia salarial por hacer funciones de categoría superior | `demanda-reclamando-diferencia-salarial-hacer-funciones-lab-0170` |
| LAB-0186 | Demanda del trabajador que impugna la modificación sustancial de sus condiciones de trabajo | `demanda-trabajador-impugna-modificacion-sustancial-lab-0186` |

### Contratos, pactos y cláusulas (12)

| Código | Formulario | Skill |
|---|---|---|
| LAB-0001 | Contrato de préstamo de la empresa a un trabajador | `contrato-prestamo-empresa-trabajador-lab-0001` |
| LAB-0152 | Cesión de vivienda al trabajador - acuerdo de uso | `cesion-vivienda-trabajador-acuerdo-uso-lab-0152` |
| LAB-0169 | Pacto entre empresa y trabajador para cambiar su clasificación profesional | `pacto-entre-empresa-trabajador-cambiar-clasificacion-lab-0169` |
| LAB-0174 | Cláusula del contrato de trabajo que fija un salario a comisión | `clausula-contrato-trabajo-fija-salario-comision-lab-0174` |
| LAB-0175 | Cláusula del contrato de trabajo que fija la retribución del trabajador | `clausula-contrato-trabajo-fija-retribucion-trabajador-lab-0175` |
| LAB-0207 | Acuerdo individual para modificar el sistema de retribución del trabajador | `acuerdo-individual-modificar-sistema-retribucion-lab-0207` |
| LAB-0208 | Pacto de polivalencia funcional entre la empresa y el trabajador | `pacto-polivalencia-funcional-entre-empresa-trabajador-lab-0208` |
| LAB-0216 | Pacto para prorratear las pagas extraordinarias | `pacto-prorratear-pagas-extraordinarias-lab-0216` |
| LAB-0217 | Pacto de no compensación ni absorción del salario | `pacto-no-compensacion-ni-absorcion-salario-lab-0217` |
| LAB-0218 | Pacto sobre la estructura del salario del trabajador | `pacto-sobre-estructura-salario-trabajador-lab-0218` |
| LAB-0219 | Pacto que declara consolidables los complementos salariales | `pacto-declara-consolidables-complementos-salariales-lab-0219` |
| LAB-0220 | Pacto para compensar con descansos la retribución del trabajo nocturno | `pacto-compensar-descansos-retribucion-trabajo-nocturno-lab-0220` |

### Estatutos, actas, certificaciones y escrituras (9)

| Código | Formulario | Skill |
|---|---|---|
| LAB-0176 | Acta de apertura de consultas con los representantes sobre modificación colectiva de condiciones | `acta-apertura-consultas-representantes-sobre-lab-0176` |
| LAB-0182 | Acta de apertura del periodo de consultas sobre traslados colectivos | `acta-apertura-periodo-consultas-sobre-traslados-lab-0182` |
| LAB-0183 | Acta del periodo de consultas sobre traslados colectivos que termina sin acuerdo | `acta-periodo-consultas-sobre-traslados-colectivos-lab-0183` |
| LAB-0184 | Acta del periodo de consultas sobre traslados colectivos que termina con acuerdo | `acta-periodo-consultas-sobre-traslados-colectivos-lab-0184` |
| LAB-0196 | Acta de cierre de consultas con la representación sobre modificación sustancial, con o sin acuerdo | `acta-cierre-consultas-representacion-sobre-lab-0196` |
| LAB-0203 | Acta de apertura del periodo de consultas sobre modificación sustancial de condiciones de trabajo | `acta-apertura-periodo-consultas-sobre-modificacion-lab-0203` |
| LAB-0213 | Acta de reunión del periodo de consultas por movilidad geográfica | `acta-reunion-periodo-consultas-movilidad-geografica-lab-0213` |
| LAB-0214 | Acta de cierre del periodo de consultas por movilidad geográfica | `acta-cierre-periodo-consultas-movilidad-geografica-lab-0214` |
| LAB-0228 | Acta de reunión de consultas sobre modificación sustancial que convoca la siguiente sesión | `acta-reunion-consultas-sobre-modificacion-sustancial-lab-0228` |

### Comunicaciones, requerimientos y cartas (26)

| Código | Formulario | Skill |
|---|---|---|
| LAB-0163 | Aviso fehaciente a los representantes de que se iniciará una modificación sustancial colectiva | `aviso-fehaciente-representantes-iniciara-modificacion-lab-0163` |
| LAB-0164 | Aviso fehaciente a los trabajadores sin representantes de una modificación sustancial colectiva | `aviso-fehaciente-trabajadores-sin-representantes-lab-0164` |
| LAB-0165 | Aviso fehaciente a los representantes de que se iniciará un traslado colectivo | `aviso-fehaciente-representantes-iniciara-traslado-lab-0165` |
| LAB-0172 | Comunicación de la empresa al trabajador de su traslado por movilidad geográfica | `comunicacion-empresa-trabajador-traslado-movilidad-lab-0172` |
| LAB-0177 | Carta de la empresa a la plantilla que comunica la subrogación por sucesión en la contrata | `carta-empresa-plantilla-comunica-subrogacion-sucesion-lab-0177` |
| LAB-0178 | Carta de la empresa que convoca al trabajador a los cursos de formación programados | `carta-empresa-convoca-trabajador-cursos-formacion-lab-0178` |
| LAB-0180 | Carta de la empresa que encarga al trabajador funciones de categoría superior | `carta-empresa-encarga-trabajador-funciones-categoria-lab-0180` |
| LAB-0181 | Carta de la empresa que asigna al trabajador funciones distintas dentro de su grupo profesional | `carta-empresa-asigna-trabajador-funciones-distintas-lab-0181` |
| LAB-0185 | Carta a la plantilla que comunica el aplazamiento de la paga extraordinaria | `carta-plantilla-comunica-aplazamiento-paga-lab-0185` |
| LAB-0187 | Carta de la empresa que comunica una modificación sustancial individual de condiciones | `carta-empresa-comunica-modificacion-sustancial-lab-0187` |
| LAB-0188 | Carta individual a cada trabajador afectado por una modificación sustancial colectiva | `carta-individual-cada-trabajador-afectado-modificacion-lab-0188` |
| LAB-0190 | Notificación a la empresa afectada y a la Inspección de una subcontratación en construcción | `notificacion-empresa-afectada-inspeccion-lab-0190` |
| LAB-0191 | Comunicación a los representantes de la subrogación empresarial por cambio de contrata | `comunicacion-representantes-subrogacion-empresarial-lab-0191` |
| LAB-0192 | Carta de la empresa que informa al trabajador de la orden de embargo de su salario | `carta-empresa-informa-trabajador-orden-embargo-salario-lab-0192` |
| LAB-0194 | Comunicación al trabajador de su traslado individual por razones económicas u organizativas | `comunicacion-trabajador-traslado-individual-razones-lab-0194` |
| LAB-0197 | Carta de la empresa que comunica a la persona trabajadora un desplazamiento temporal | `carta-empresa-comunica-persona-trabajadora-lab-0197` |
| LAB-0200 | Comunicación de cedente y cesionaria al comité de empresa sobre la subrogación empresarial | `comunicacion-cedente-cesionaria-comite-empresa-sobre-lab-0200` |
| LAB-0202 | Notificación individual a cada trabajador del traslado colectivo acordado | `notificacion-individual-cada-trabajador-traslado-lab-0202` |
| LAB-0204 | Comunicación a los representantes de la apertura de consultas por traslado colectivo | `comunicacion-representantes-apertura-consultas-lab-0204` |
| LAB-0205 | Comunicación a la autoridad laboral del fin del periodo de consultas del traslado colectivo | `comunicacion-autoridad-laboral-fin-periodo-consultas-lab-0205` |
| LAB-0212 | Notificación a la autoridad laboral de la apertura de consultas por movilidad geográfica | `notificacion-autoridad-laboral-apertura-consultas-lab-0212` |
| LAB-0221 | Comunicación de movilidad funcional a funciones del mismo grupo profesional | `comunicacion-movilidad-funcional-funciones-mismo-grupo-lab-0221` |
| LAB-0222 | Comunicación de movilidad funcional a funciones inferiores a las del grupo profesional | `comunicacion-movilidad-funcional-funciones-inferiores-lab-0222` |
| LAB-0223 | Comunicación a la autoridad laboral de la postura final de las partes sobre la movilidad geográfica | `comunicacion-autoridad-laboral-postura-final-partes-lab-0223` |
| LAB-0229 | Requerimiento a la subcontratista para que justifique el pago de salarios y cotizaciones | `requerimiento-subcontratista-justifique-pago-salarios-lab-0229` |
| LAB-0231 | Requerimiento al nuevo empresario para que cumpla las obligaciones anteriores a la transmisión | `requerimiento-nuevo-empresario-cumpla-obligaciones-lab-0231` |

### Escritos de trámite y otros (39)

| Código | Formulario | Skill |
|---|---|---|
| LAB-0144 | Designación de trabajadores para negociar una modificación sustancial colectiva - acta | `designacion-trabajadores-negociar-modificacion-lab-0144` |
| LAB-0145 | Modificación sustancial - comunicación de los miembros de la comisión negociadora | `modificacion-sustancial-comunicacion-miembros-comision-lab-0145` |
| LAB-0146 | Modificación sustancial colectiva - petición de la empresa para constituir comisión negociadora | `modificacion-sustancial-colectiva-peticion-empresa-lab-0146` |
| LAB-0147 | Extinguir el contrato por modificación sustancial de condiciones - demanda | `extinguir-contrato-modificacion-sustancial-condiciones-lab-0147` |
| LAB-0148 | Daños en vehículo de empresa - demanda de indemnización | `danos-vehiculo-empresa-demanda-indemnizacion-lab-0148` |
| LAB-0149 | Pedir anticipo de salario | `pedir-anticipo-salario-lab-0149` |
| LAB-0150 | Reconocimiento de deuda de la empresa al trabajador - acuerdo | `reconocimiento-deuda-empresa-trabajador-acuerdo-lab-0150` |
| LAB-0151 | Reconocimiento de deuda del trabajador a la empresa - acuerdo | `reconocimiento-deuda-trabajador-empresa-acuerdo-lab-0151` |
| LAB-0153 | Cambio de titularidad de la contrata - demanda de reconocimiento laboral | `cambio-titularidad-contrata-demanda-reconocimiento-lab-0153` |
| LAB-0154 | Sucesión en la contrata - aviso de la empresa a la representación de los trabajadores | `sucesion-contrata-aviso-empresa-representacion-lab-0154` |
| LAB-0155 | Sucesión de empresa - aviso al trabajador | `sucesion-empresa-aviso-trabajador-lab-0155` |
| LAB-0156 | Despido disciplinario o reclamación de cantidad - papeleta de conciliación en el SMAC | `despido-disciplinario-reclamacion-cantidad-papeleta-lab-0156` |
| LAB-0157 | Compensación y absorción sin subida de salario - aviso al trabajador | `compensacion-absorcion-sin-subida-salario-aviso-lab-0157` |
| LAB-0158 | Salarios contra grupo laboral de empresas - demanda | `salarios-contra-grupo-laboral-empresas-demanda-lab-0158` |
| LAB-0159 | TRADE - demanda de reclamación de cantidad a la empresa cliente | `trade-demanda-reclamacion-cantidad-empresa-cliente-lab-0159` |
| LAB-0160 | Negativa a la subrogación empresarial - demanda de extinción del trabajador | `negativa-subrogacion-empresarial-demanda-extincion-lab-0160` |
| LAB-0161 | Negativa de la empresa tras modificación sustancial de condiciones - resolución | `negativa-empresa-tras-modificacion-sustancial-lab-0161` |
| LAB-0162 | Ascenso de categoría y diferencias salariales por funciones superiores - solicitud | `ascenso-categoria-diferencias-salariales-funciones-lab-0162` |
| LAB-0166 | Escrito a la plantilla de un centro sin representantes anunciando un traslado colectivo | `escrito-plantilla-centro-sin-representantes-anunciando-lab-0166` |
| LAB-0167 | Escrito a los representantes legales anunciando la modificación sustancial colectiva de condiciones | `escrito-representantes-legales-anunciando-modificacion-lab-0167` |
| LAB-0171 | Petición del trabajador al comité de empresa de un informe sobre su clasificación profesional | `peticion-trabajador-comite-empresa-informe-sobre-lab-0171` |
| LAB-0173 | Petición del trabajador de su salario cuando no pudo trabajar por causas imputables a la empresa | `peticion-trabajador-salario-cuando-no-pudo-trabajar-lab-0173` |
| LAB-0179 | Petición del trabajador a la empresa de que reconozca su reclasificación profesional | `peticion-trabajador-empresa-reconozca-reclasificacion-lab-0179` |
| LAB-0189 | Recibo de salario del empleado del hogar familiar | `recibo-salario-empleado-hogar-familiar-lab-0189` |
| LAB-0193 | Recibo del representante de comercio por el cobro de sus comisiones | `recibo-representante-comercio-cobro-comisiones-lab-0193` |
| LAB-0195 | Escrito del trabajador que opta por extinguir su contrato ante una modificación sustancial | `escrito-trabajador-opta-extinguir-contrato-ante-lab-0195` |
| LAB-0198 | Información a la representación legal sobre una modificación sustancial individual de condiciones | `informacion-representacion-legal-sobre-modificacion-lab-0198` |
| LAB-0199 | Escrito de la empresa que abre el periodo de consultas por modificación sustancial colectiva | `escrito-empresa-abre-periodo-consultas-modificacion-lab-0199` |
| LAB-0201 | Petición de traslado por violencia de género, violencia sexual, terrorismo o para proteger la salud | `peticion-traslado-violencia-genero-violencia-sexual-lab-0201` |
| LAB-0206 | Nómina o recibo individual de salarios con el formato oficial | `nomina-recibo-individual-salarios-formato-oficial-lab-0206` |
| LAB-0209 | Petición de desplazamiento temporal de la trabajadora víctima de violencia de género | `peticion-desplazamiento-temporal-trabajadora-victima-lab-0209` |
| LAB-0210 | Escrito del trabajador que acepta el traslado y la compensación de gastos | `escrito-trabajador-acepta-traslado-compensacion-gastos-lab-0210` |
| LAB-0211 | Escrito del trabajador que opta por extinguir el contrato a raíz del traslado | `escrito-trabajador-opta-extinguir-contrato-raiz-lab-0211` |
| LAB-0215 | Petición del trabajador para examinar los libros de cuentas sobre sus comisiones | `peticion-trabajador-examinar-libros-cuentas-sobre-lab-0215` |
| LAB-0224 | Petición de traslado del trabajador para seguir a su cónyuge trasladado | `peticion-traslado-trabajador-seguir-conyuge-trasladado-lab-0224` |
| LAB-0225 | Petición de días de permiso durante un desplazamiento temporal | `peticion-dias-permiso-durante-desplazamiento-temporal-lab-0225` |
| LAB-0226 | Petición de gastos de viaje y dietas por desplazamiento temporal | `peticion-gastos-viaje-dietas-desplazamiento-temporal-lab-0226` |
| LAB-0227 | Escrito del trabajador que manifiesta su disconformidad con la modificación sustancial | `escrito-trabajador-manifiesta-disconformidad-lab-0227` |
| LAB-0230 | Anexo II del contrato de puesta a disposición con el cálculo del salario del puesto | `anexo-ii-contrato-puesta-disposicion-calculo-salario-lab-0230` |
