# Salario, movilidad y condiciones de trabajo

> Plugin de Claude Code `formularios-salario-y-condiciones-de-trabajo` · **89 formularios** · Laboral · normativa revisada el 25-11-2026 · requiere Jurisprudenciator

## Para qué sirve

Para las condiciones del contrato: salario, nóminas, pluses, anticipos y préstamos al trabajador, movilidad funcional y geográfica, traslados y desplazamientos, modificación sustancial de condiciones (individual y colectiva, con su periodo de consultas) y sucesión de empresa.

Cada formulario es una skill: Claude lo rellena contigo paso a paso y te entrega el documento en Word, con las normas comprobadas en el BOE. Cada skill explica en su `SKILL.md` qué es el formulario, para qué sirve, cómo se usa, qué datos necesita y qué avisos normativos lleva; el formulario seco, listo para rellenar, está en `assets/formulario.md` dentro de la carpeta de la skill.

## Qué puedes hacer con él

Estos son los tipos de documento que trae, con algunos ejemplos (la lista completa de los 89 está al final):

- **Demandas, peticiones y solicitudes iniciales** (3). Por ejemplo: Demanda de traslado por violencia de género, sexual o terrorismo, salud o traslado del cónyuge; Demanda reclamando la diferencia salarial por hacer funciones de categoría superior; Demanda del trabajador que impugna la modificación sustancial de sus condiciones de trabajo.
- **Contratos, pactos y cláusulas** (12). Por ejemplo: Contrato de préstamo de la empresa a un trabajador; Cesión de vivienda al trabajador - acuerdo de uso; Pacto entre empresa y trabajador para cambiar su clasificación profesional.
- **Estatutos, actas, certificaciones y escrituras** (9). Por ejemplo: Acta de apertura de consultas con los representantes sobre modificación colectiva de condiciones; Acta de apertura del periodo de consultas sobre traslados colectivos; Acta del periodo de consultas sobre traslados colectivos que termina sin acuerdo.
- **Comunicaciones, requerimientos y cartas** (26). Por ejemplo: Aviso fehaciente a los representantes de que se iniciará una modificación sustancial colectiva; Aviso fehaciente a los trabajadores sin representantes de una modificación sustancial colectiva; Aviso fehaciente a los representantes de que se iniciará un traslado colectivo.
- **Escritos de trámite y otros** (39). Por ejemplo: Designación de trabajadores para negociar una modificación sustancial colectiva - acta; Modificación sustancial - comunicación de los miembros de la comisión negociadora; Modificación sustancial colectiva - petición de la empresa para constituir comisión negociadora.

## Cómo se usa

1. **Pídelo con tus palabras.** Cuéntale a Claude qué documento necesitas y para qué caso; él elige el formulario. Por ejemplo:
   - «Comunicación de traslado por movilidad geográfica»
   - «Acta de apertura del periodo de consultas por modificación sustancial colectiva»
   - «Contrato de préstamo de la empresa a un trabajador»
2. **Si no da con el formulario**, empieza por el índice del plugin: escribe `/formularios-salario-y-condiciones-de-trabajo:indice` y cuéntale lo que necesitas. Te propondrá el formulario que mejor encaja (o dos o tres para que elijas).
3. **Si ya sabes cuál quieres**, llámalo por su nombre de skill, por ejemplo `/formularios-salario-y-condiciones-de-trabajo:contrato-prestamo-empresa-trabajador-lab-0001`. Los nombres están en la lista de formularios de abajo.

## Qué hace Claude cuando usas un formulario

1. Comprueba que Jurisprudenciator está conectado. Si no lo está, se para y te dice cómo conectarlo: no redacta nada sin él. Todos los datos jurídicos del documento (artículos vigentes, sentencias con su ECLI, datos registrales) salen de Jurisprudenciator; nunca de memoria.
2. Te pide en una sola tanda los datos del caso (partes, órgano, fechas, importes…). Lo que no sepas queda como hueco visible.
3. Resuelve contigo las opciones que el formulario deja abiertas y decide qué párrafos opcionales entran según los hechos.
4. Aplica las notas de actualización de la revisión del 25-11-2026 (reformas legales, órganos judiciales de la LO 1/2025, plazos).
5. Comprueba en el BOE, con Jurisprudenciator, cada norma que cita el documento; si alguna ha cambiado, usa la redacción vigente y te lo dice.
6. Te entrega el documento en Word **tal cual es el formulario**: empieza por su primera línea, sin títulos, notas ni explicaciones añadidas, en Times New Roman 11, interlineado 1,15 y texto justificado. En el chat te dice lo que queda pendiente y, si es un escrito, el plazo y ante quién se presenta.

El resultado es un borrador para que lo revise un profesional antes de usarlo.

## Antes de empezar

- **Dónde funciona:** en Claude Code y en Claude (web, escritorio y Cowork). Se instala desde este repositorio de GitHub o subiendo el ZIP del plugin.
- **Jurisprudenciator es imprescindible:** el plugin trae el conector y cada skill trabaja siempre con él. Sin una cuenta de Jurisprudenciator conectada, las skills se paran y no redactan nada. La primera vez hay que iniciar sesión (en Claude Code, con `/mcp`; o con tu URL personal: https://jurisprudenciator.lexiaipro.org/instalacion). Si ya tienes Jurisprudenciator conectado en Claude, las skills usan ese.
- **Espacio que ocupa:** unos 5.378 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable formularios-salario-y-condiciones-de-trabajo@formularios-salario-y-condiciones-de-trabajo`).

## Instalación

En Claude Code, añade el catálogo (solo la primera vez) e instala el plugin:

```
/plugin marketplace add DerechoVirtual/formularios-salario-y-condiciones-de-trabajo
/plugin install formularios-salario-y-condiciones-de-trabajo@formularios-salario-y-condiciones-de-trabajo
```

En Claude (web, escritorio o Cowork): **Personalizar → Plugins → Añadir marketplace** con la dirección `https://github.com/DerechoVirtual/formularios-salario-y-condiciones-de-trabajo`, o sube el ZIP del plugin ([descargar ZIP](https://github.com/DerechoVirtual/formularios-salario-y-condiciones-de-trabajo/releases/latest/download/formularios-salario-y-condiciones-de-trabajo.zip)).

Para comprobar que está instalado: `claude plugin list`.

## Lista completa de formularios (89)

| Código | Formulario | Skill |
|---|---|---|
| LAB-0001 | Contrato de préstamo de la empresa a un trabajador | `contrato-prestamo-empresa-trabajador-lab-0001` |
| LAB-0143 | Demanda de traslado por violencia de género, sexual o terrorismo, salud o traslado del cónyuge | `demanda-traslado-violencia-genero-sexual-terrorismo-lab-0143` |
| LAB-0144 | Designación de trabajadores para negociar una modificación sustancial colectiva - acta | `designacion-trabajadores-negociar-modificacion-lab-0144` |
| LAB-0145 | Modificación sustancial - comunicación de los miembros de la comisión negociadora | `modificacion-sustancial-comunicacion-miembros-comision-lab-0145` |
| LAB-0146 | Modificación sustancial colectiva - petición de la empresa para constituir comisión negociadora | `modificacion-sustancial-colectiva-peticion-empresa-lab-0146` |
| LAB-0147 | Extinguir el contrato por modificación sustancial de condiciones - demanda | `extinguir-contrato-modificacion-sustancial-condiciones-lab-0147` |
| LAB-0148 | Daños en vehículo de empresa - demanda de indemnización | `danos-vehiculo-empresa-demanda-indemnizacion-lab-0148` |
| LAB-0149 | Pedir anticipo de salario | `pedir-anticipo-salario-lab-0149` |
| LAB-0150 | Reconocimiento de deuda de la empresa al trabajador - acuerdo | `reconocimiento-deuda-empresa-trabajador-acuerdo-lab-0150` |
| LAB-0151 | Reconocimiento de deuda del trabajador a la empresa - acuerdo | `reconocimiento-deuda-trabajador-empresa-acuerdo-lab-0151` |
| LAB-0152 | Cesión de vivienda al trabajador - acuerdo de uso | `cesion-vivienda-trabajador-acuerdo-uso-lab-0152` |
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
| LAB-0163 | Aviso fehaciente a los representantes de que se iniciará una modificación sustancial colectiva | `aviso-fehaciente-representantes-iniciara-modificacion-lab-0163` |
| LAB-0164 | Aviso fehaciente a los trabajadores sin representantes de una modificación sustancial colectiva | `aviso-fehaciente-trabajadores-sin-representantes-lab-0164` |
| LAB-0165 | Aviso fehaciente a los representantes de que se iniciará un traslado colectivo | `aviso-fehaciente-representantes-iniciara-traslado-lab-0165` |
| LAB-0166 | Escrito a la plantilla de un centro sin representantes anunciando un traslado colectivo | `escrito-plantilla-centro-sin-representantes-anunciando-lab-0166` |
| LAB-0167 | Escrito a los representantes legales anunciando la modificación sustancial colectiva de condiciones | `escrito-representantes-legales-anunciando-modificacion-lab-0167` |
| LAB-0169 | Pacto entre empresa y trabajador para cambiar su clasificación profesional | `pacto-entre-empresa-trabajador-cambiar-clasificacion-lab-0169` |
| LAB-0170 | Demanda reclamando la diferencia salarial por hacer funciones de categoría superior | `demanda-reclamando-diferencia-salarial-hacer-funciones-lab-0170` |
| LAB-0171 | Petición del trabajador al comité de empresa de un informe sobre su clasificación profesional | `peticion-trabajador-comite-empresa-informe-sobre-lab-0171` |
| LAB-0172 | Comunicación de la empresa al trabajador de su traslado por movilidad geográfica | `comunicacion-empresa-trabajador-traslado-movilidad-lab-0172` |
| LAB-0173 | Petición del trabajador de su salario cuando no pudo trabajar por causas imputables a la empresa | `peticion-trabajador-salario-cuando-no-pudo-trabajar-lab-0173` |
| LAB-0174 | Cláusula del contrato de trabajo que fija un salario a comisión | `clausula-contrato-trabajo-fija-salario-comision-lab-0174` |
| LAB-0175 | Cláusula del contrato de trabajo que fija la retribución del trabajador | `clausula-contrato-trabajo-fija-retribucion-trabajador-lab-0175` |
| LAB-0176 | Acta de apertura de consultas con los representantes sobre modificación colectiva de condiciones | `acta-apertura-consultas-representantes-sobre-lab-0176` |
| LAB-0177 | Carta de la empresa a la plantilla que comunica la subrogación por sucesión en la contrata | `carta-empresa-plantilla-comunica-subrogacion-sucesion-lab-0177` |
| LAB-0178 | Carta de la empresa que convoca al trabajador a los cursos de formación programados | `carta-empresa-convoca-trabajador-cursos-formacion-lab-0178` |
| LAB-0179 | Petición del trabajador a la empresa de que reconozca su reclasificación profesional | `peticion-trabajador-empresa-reconozca-reclasificacion-lab-0179` |
| LAB-0180 | Carta de la empresa que encarga al trabajador funciones de categoría superior | `carta-empresa-encarga-trabajador-funciones-categoria-lab-0180` |
| LAB-0181 | Carta de la empresa que asigna al trabajador funciones distintas dentro de su grupo profesional | `carta-empresa-asigna-trabajador-funciones-distintas-lab-0181` |
| LAB-0182 | Acta de apertura del periodo de consultas sobre traslados colectivos | `acta-apertura-periodo-consultas-sobre-traslados-lab-0182` |
| LAB-0183 | Acta del periodo de consultas sobre traslados colectivos que termina sin acuerdo | `acta-periodo-consultas-sobre-traslados-colectivos-lab-0183` |
| LAB-0184 | Acta del periodo de consultas sobre traslados colectivos que termina con acuerdo | `acta-periodo-consultas-sobre-traslados-colectivos-lab-0184` |
| LAB-0185 | Carta a la plantilla que comunica el aplazamiento de la paga extraordinaria | `carta-plantilla-comunica-aplazamiento-paga-lab-0185` |
| LAB-0186 | Demanda del trabajador que impugna la modificación sustancial de sus condiciones de trabajo | `demanda-trabajador-impugna-modificacion-sustancial-lab-0186` |
| LAB-0187 | Carta de la empresa que comunica una modificación sustancial individual de condiciones | `carta-empresa-comunica-modificacion-sustancial-lab-0187` |
| LAB-0188 | Carta individual a cada trabajador afectado por una modificación sustancial colectiva | `carta-individual-cada-trabajador-afectado-modificacion-lab-0188` |
| LAB-0189 | Recibo de salario del empleado del hogar familiar | `recibo-salario-empleado-hogar-familiar-lab-0189` |
| LAB-0190 | Notificación a la empresa afectada y a la Inspección de una subcontratación en construcción | `notificacion-empresa-afectada-inspeccion-lab-0190` |
| LAB-0191 | Comunicación a los representantes de la subrogación empresarial por cambio de contrata | `comunicacion-representantes-subrogacion-empresarial-lab-0191` |
| LAB-0192 | Carta de la empresa que informa al trabajador de la orden de embargo de su salario | `carta-empresa-informa-trabajador-orden-embargo-salario-lab-0192` |
| LAB-0193 | Recibo del representante de comercio por el cobro de sus comisiones | `recibo-representante-comercio-cobro-comisiones-lab-0193` |
| LAB-0194 | Comunicación al trabajador de su traslado individual por razones económicas u organizativas | `comunicacion-trabajador-traslado-individual-razones-lab-0194` |
| LAB-0195 | Escrito del trabajador que opta por extinguir su contrato ante una modificación sustancial | `escrito-trabajador-opta-extinguir-contrato-ante-lab-0195` |
| LAB-0196 | Acta de cierre de consultas con la representación sobre modificación sustancial, con o sin acuerdo | `acta-cierre-consultas-representacion-sobre-lab-0196` |
| LAB-0197 | Carta de la empresa que comunica a la persona trabajadora un desplazamiento temporal | `carta-empresa-comunica-persona-trabajadora-lab-0197` |
| LAB-0198 | Información a la representación legal sobre una modificación sustancial individual de condiciones | `informacion-representacion-legal-sobre-modificacion-lab-0198` |
| LAB-0199 | Escrito de la empresa que abre el periodo de consultas por modificación sustancial colectiva | `escrito-empresa-abre-periodo-consultas-modificacion-lab-0199` |
| LAB-0200 | Comunicación de cedente y cesionaria al comité de empresa sobre la subrogación empresarial | `comunicacion-cedente-cesionaria-comite-empresa-sobre-lab-0200` |
| LAB-0201 | Petición de traslado por violencia de género, violencia sexual, terrorismo o para proteger la salud | `peticion-traslado-violencia-genero-violencia-sexual-lab-0201` |
| LAB-0202 | Notificación individual a cada trabajador del traslado colectivo acordado | `notificacion-individual-cada-trabajador-traslado-lab-0202` |
| LAB-0203 | Acta de apertura del periodo de consultas sobre modificación sustancial de condiciones de trabajo | `acta-apertura-periodo-consultas-sobre-modificacion-lab-0203` |
| LAB-0204 | Comunicación a los representantes de la apertura de consultas por traslado colectivo | `comunicacion-representantes-apertura-consultas-lab-0204` |
| LAB-0205 | Comunicación a la autoridad laboral del fin del periodo de consultas del traslado colectivo | `comunicacion-autoridad-laboral-fin-periodo-consultas-lab-0205` |
| LAB-0206 | Nómina o recibo individual de salarios con el formato oficial | `nomina-recibo-individual-salarios-formato-oficial-lab-0206` |
| LAB-0207 | Acuerdo individual para modificar el sistema de retribución del trabajador | `acuerdo-individual-modificar-sistema-retribucion-lab-0207` |
| LAB-0208 | Pacto de polivalencia funcional entre la empresa y el trabajador | `pacto-polivalencia-funcional-entre-empresa-trabajador-lab-0208` |
| LAB-0209 | Petición de desplazamiento temporal de la trabajadora víctima de violencia de género | `peticion-desplazamiento-temporal-trabajadora-victima-lab-0209` |
| LAB-0210 | Escrito del trabajador que acepta el traslado y la compensación de gastos | `escrito-trabajador-acepta-traslado-compensacion-gastos-lab-0210` |
| LAB-0211 | Escrito del trabajador que opta por extinguir el contrato a raíz del traslado | `escrito-trabajador-opta-extinguir-contrato-raiz-lab-0211` |
| LAB-0212 | Notificación a la autoridad laboral de la apertura de consultas por movilidad geográfica | `notificacion-autoridad-laboral-apertura-consultas-lab-0212` |
| LAB-0213 | Acta de reunión del periodo de consultas por movilidad geográfica | `acta-reunion-periodo-consultas-movilidad-geografica-lab-0213` |
| LAB-0214 | Acta de cierre del periodo de consultas por movilidad geográfica | `acta-cierre-periodo-consultas-movilidad-geografica-lab-0214` |
| LAB-0215 | Petición del trabajador para examinar los libros de cuentas sobre sus comisiones | `peticion-trabajador-examinar-libros-cuentas-sobre-lab-0215` |
| LAB-0216 | Pacto para prorratear las pagas extraordinarias | `pacto-prorratear-pagas-extraordinarias-lab-0216` |
| LAB-0217 | Pacto de no compensación ni absorción del salario | `pacto-no-compensacion-ni-absorcion-salario-lab-0217` |
| LAB-0218 | Pacto sobre la estructura del salario del trabajador | `pacto-sobre-estructura-salario-trabajador-lab-0218` |
| LAB-0219 | Pacto que declara consolidables los complementos salariales | `pacto-declara-consolidables-complementos-salariales-lab-0219` |
| LAB-0220 | Pacto para compensar con descansos la retribución del trabajo nocturno | `pacto-compensar-descansos-retribucion-trabajo-nocturno-lab-0220` |
| LAB-0221 | Comunicación de movilidad funcional a funciones del mismo grupo profesional | `comunicacion-movilidad-funcional-funciones-mismo-grupo-lab-0221` |
| LAB-0222 | Comunicación de movilidad funcional a funciones inferiores a las del grupo profesional | `comunicacion-movilidad-funcional-funciones-inferiores-lab-0222` |
| LAB-0223 | Comunicación a la autoridad laboral de la postura final de las partes sobre la movilidad geográfica | `comunicacion-autoridad-laboral-postura-final-partes-lab-0223` |
| LAB-0224 | Petición de traslado del trabajador para seguir a su cónyuge trasladado | `peticion-traslado-trabajador-seguir-conyuge-trasladado-lab-0224` |
| LAB-0225 | Petición de días de permiso durante un desplazamiento temporal | `peticion-dias-permiso-durante-desplazamiento-temporal-lab-0225` |
| LAB-0226 | Petición de gastos de viaje y dietas por desplazamiento temporal | `peticion-gastos-viaje-dietas-desplazamiento-temporal-lab-0226` |
| LAB-0227 | Escrito del trabajador que manifiesta su disconformidad con la modificación sustancial | `escrito-trabajador-manifiesta-disconformidad-lab-0227` |
| LAB-0228 | Acta de reunión de consultas sobre modificación sustancial que convoca la siguiente sesión | `acta-reunion-consultas-sobre-modificacion-sustancial-lab-0228` |
| LAB-0229 | Requerimiento a la subcontratista para que justifique el pago de salarios y cotizaciones | `requerimiento-subcontratista-justifique-pago-salarios-lab-0229` |
| LAB-0230 | Anexo II del contrato de puesta a disposición con el cálculo del salario del puesto | `anexo-ii-contrato-puesta-disposicion-calculo-salario-lab-0230` |
| LAB-0231 | Requerimiento al nuevo empresario para que cumpla las obligaciones anteriores a la transmisión | `requerimiento-nuevo-empresario-cumpla-obligaciones-lab-0231` |

## Privacidad

Ver `PRIVACY.md`.
