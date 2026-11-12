# Laboratorio 6: Reconocimiento de partes y funcionamiento de una máquina de anestesia

## Integrantes
* Laura Valentina Velásquez Castiblanco (5600846)
* Carlos Felipe Moreno Guzmán (5600881)
* Juan Andrés Mateus Durán (5600787)

## Objetivos

### Objetivo General
Comprender el funcionamiento de una máquina de anestesia y la relevancia de su correcto mantenimiento para la seguridad del paciente durante un procedimiento quirúrgico, a partir del reconocimiento de sus componentes, sus modos de operación y sus fallas más frecuentes en la máquina WATO EX-20.

### Objetivos Específicos
- Identificar los componentes principales de la máquina de anestesia WATO EX-20 (vaporizador, válvula APL, recipiente absorbente de CO2 y fuelle) y la función que cumple cada uno dentro del sistema.
- Describir el recorrido de los gases desde su suministro hasta el paciente, y los modos de operación del ventilador, a partir de la consulta de los manuales del equipo.
- Analizar las fallas que pueden presentarse en cada subsistema y sus causas, y reconocer cómo las labores de inspección y mantenimiento ayudan a prevenirlas.
  
> ### Parte C

### 1. Procedimiento General

La práctica fue de tipo demostrativo y se desarrolló sobre la máquina de anestesia WATO EX-20, con acompañamiento del técnico del laboratorio y siguiendo las normas de seguridad de la guía (no encender ni manipular el equipo sin su presencia). El trabajo se organizó en dos etapas: una revisión de la literatura y del manual para reconocer los subsistemas de la máquina y su funcionamiento, y una identificación de sus partes principales (vaporizador, válvula APL, recipiente absorbente de CO<sub>2</sub> y fuelle) con la explicación de su función.

Para la documentación (Parte C) se consultaron el manual de servicio de la serie WATO EX-20/30/35 [1], en particular su capítulo de resolución de problemas, donde las fallas y las alarmas se presentan por módulo o subsistema, el manual de operación de la EX-20 [2] y la información publicada por el fabricante sobre el modelo EX-35 [3]. Del capítulo de resolución de problemas se extrajeron las fallas descritas y sus causas posibles, y se agruparon según los títulos que usa el propio manual. Con esa información se elaboraron el análisis de fallas por subsistema, el ordenamiento de los subsistemas según el número de fallas asociadas y la respuesta a las preguntas para la discusión. Los resultados se organizaron en este informe y en el repositorio de GitHub de la práctica.

### 2. Resultados Obtenidos

Del manual de servicio se obtuvo la descripción del recorrido del gas en la máquina. Los gases de trabajo son O<sub>2</sub>, N<sub>2</sub>O y aire. Cuando provienen de la tubería ingresan a presiones de 280 a 600 kPa; cuando provienen de cilindros (O<sub>2</sub> y aire entre 6.9 y 15 MPa, N<sub>2</sub>O entre 4.2 y 6 MPa) un regulador los reduce a cerca de 400 kPa. Una segunda etapa de regulación los lleva a unos 200 kPa antes del flujómetro, que controla cada gas entre 0 y 10 L/min y cuenta con un enlace O<sub>2</sub>-N<sub>2</sub>O que limita la proporción de N<sub>2</sub>O. A continuación, la mezcla pasa por el múltiple de vaporizadores, donde el sistema de interbloqueo Selectatec impide usar dos vaporizadores a la vez, y llega al sistema de respiración, donde el ventilador y el fuelle entregan el volumen corriente al paciente. La máquina incluye además la descarga de O<sub>2</sub> (O<sub>2</sub> flush) y un dispositivo de succión por presión negativa, accionado por un generador Venturi con frasco colector [1].

Según la documentación del fabricante para la EX-20 [2], el equipo cuenta con pantalla a color de 7 pulgadas, dos posiciones de vaporizador, ventilación controlada por volumen de 40 a 1500 ml con compensación del volumen corriente, monitorización de presión de la vía aérea y de oxígeno inspirado, y batería de litio de 90 minutos. La misma documentación indica que la monitorización de CO<sub>2</sub> no está disponible en este modelo.

En el capítulo de resolución de problemas del manual de servicio se identificaron fallas descritas en siete secciones: alarmas técnicas de la unidad principal y el ventilador, hardware y sistema eléctrico, entrega de gas anestésico, suministro de gases y gas motriz, circuito del paciente, módulo de control auxiliar e imprecisión del volumen corriente. El detalle de causas y el ordenamiento por número de fallas se presentan en la sección siguiente.

### 3. Análisis de Resultados

**Análisis 1: Fallas que pueden presentarse en los subsistemas y sus causas**

El manual agrupa las fallas por subsistema y asocia a cada una causas concretas, lo que permite ubicar el origen de un problema a partir de su síntoma [1]:

- **Suministro de gases y gas motriz:** fugas por tubos o sellos dañados, conectores rápidos, la entrada de gas de tubería o la línea de gas motriz; lecturas imprecisas o fluctuantes del manómetro de tubería; y alarmas [O2 Supply Failure] o [Drive Gas Pressure Low] que no se activan cuando corresponde, por un interruptor de presión defectuoso.
- **Entrega de gas anestésico:** fugas en el botón de O<sub>2</sub> flush, en el interruptor del sistema y en el vaporizador (mal instalado, sello entre el múltiple y el vaporizador dañado, sellos o arandelas internas sucias o dañadas); flujómetro con flotador impreciso o atascado y enlace O<sub>2</sub>-N<sub>2</sub>O sin efecto; y válvula de corte O<sub>2</sub>-N<sub>2</sub>O dañada, de modo que el N<sub>2</sub>O no se corta ante una falla del suministro de O<sub>2</sub>.
- **Circuito del paciente:** fugas por recipiente absorbente mal instalado o con sellos dañados, brazo de la bolsa, copa de agua floja, adaptador del circuito, fuelle o su carcasa mal montados, tapa de válvulas y sensor de O<sub>2</sub> mal instalado. También figuran la medición de O<sub>2</sub> errónea (agua en el sensor, falta de calibración o sensor dañado) y las lecturas imprecisas de flujo o volumen por sensor de flujo mal instalado, con agua o con la membrana deformada o sucia.
- **Hardware y sistema eléctrico:** pantalla apagada o ventilador que no arranca por falta de corriente alterna, batería insuficiente o fusible dañado; tarjeta de potencia, botones o perilla de control con fallas; y ausencia de gas en ventilación mecánica cuando el interruptor bolsa/ventilador falla o el interruptor ACGO está activo.

> [!NOTE]
> En el circuito del paciente predominan las fugas, y la mayoría de sus causas corresponden a componentes que se desmontan y se vuelven a instalar en cada limpieza (recipiente absorbente, fuelle, sensor de O<sub>2</sub>, sensores de flujo). Esto señala la correcta reinstalación de estas piezas como un punto de control en la rutina de uso.

**Análisis 2: Ordenamiento de los subsistemas según el número de fallas asociadas (de mayor a menor)**

Se contó el número de fallas o mensajes de alarma descritos en cada sección del capítulo de resolución de problemas del manual de servicio [1]. No se incluyeron los módulos de CO<sub>2</sub> y de calefacción, por no corresponder a la configuración básica de la EX-20 (la documentación del fabricante indica monitorización de CO<sub>2</sub> no disponible [2]).

| Posición | Subsistema | Fallas descritas | Observación |
|---|---|---|---|
| 1 | Unidad principal y ventilador (alarmas técnicas) | 40 | Incluye alarmas de gas motriz, sensores y batería |
| 2 | Hardware y sistema eléctrico | 14 | Alimentación, fusibles, tarjetas, botones y pantalla |
| 3 | Entrega de gas anestésico | 13 | Flujómetros, vaporizador y válvula de corte O<sub>2</sub>-N<sub>2</sub>O |
| 4 | Suministro de gases y gas motriz | 8 | Fugas, manómetros e interruptores de presión |
| 5 | Circuito del paciente | 5 | Reúne más de 20 causas posibles, casi todas fugas |
| 6 | Módulo de control auxiliar | 3 | Errores de hardware y pérdida de comunicación |
| 7 | Medición del volumen corriente | 1 | Una falla con 11 causas posibles |

El criterio de conteo (fallas descritas por sección) favorece a los subsistemas que el manual documenta mediante alarmas, como el ventilador. Si se contaran las causas posibles, el circuito del paciente pasaría a ocupar uno de los primeros lugares.

### 4. Preguntas para la Discusión

**Pregunta 1: ¿Qué tipos de anestésicos son los más usados en cirugía?**

En cirugía se emplean tres grupos de anestésicos, que suelen combinarse según el procedimiento. Los anestésicos inhalatorios, que se administran desde la máquina de anestesia mediante el vaporizador, incluyen los halogenados (sevoflurano, isoflurano y desflurano) y el óxido nitroso (N<sub>2</sub>O), que se suministra como gas desde el flujómetro y no desde el vaporizador. Los anestésicos intravenosos, como el propofol, se usan para la inducción y el mantenimiento de la anestesia general. Los anestésicos locales, como la lidocaína y la bupivacaína, se emplean en técnicas locales y regionales, que bloquean la sensibilidad de una zona del cuerpo sin producir inconsciencia.

En el caso de la WATO EX-20, la documentación del fabricante indica que sus posiciones de vaporizador admiten halotano, enflurano, isoflurano, sevoflurano y desflurano [2], de modo que la máquina cubre los agentes inhalatorios de uso habitual. Las máquinas de anestesia trabajan con los anestésicos inhalatorios; los intravenosos y los locales se administran por otras vías.

**Pregunta 2: ¿Qué diferencias plantea el modelo EX-35 con respecto al EX-20?**

Según la documentación del fabricante de ambos modelos [2], [3], las diferencias principales son las siguientes:

| Característica | WATO EX-20 | WATO EX-35 |
|---|---|---|
| Pantalla | Color, 7 pulgadas | Táctil, 10.4 pulgadas, con hasta tres formas de onda y lazo de espirometría simultáneos |
| Modos de ventilación | VCV como modo estándar; modo por presión opcional | VCV, PCV, presión de soporte con ventilación de apnea, SIMV por volumen y SIMV por presión |
| Volumen corriente mínimo | 40 ml | 20 ml, con compensación dinámica del volumen corriente |
| Población de pacientes | Desde pacientes pediátricos hasta adultos | Desde neonatos hasta adultos |
| Monitorización de gases | Presión de la vía aérea y oxígeno inspirado; monitorización de CO<sub>2</sub> no disponible | Módulo de CO<sub>2</sub> o módulo de agentes anestésicos (FiO<sub>2</sub>, EtO<sub>2</sub>, CO<sub>2</sub> y N<sub>2</sub>O), con detección automática de cinco agentes |

Además, la ficha de la EX-35 describe un cambio automático del gas motriz del ventilador, que mantiene la ventilación mecánica si falla el gas motriz principal, y un sistema de alarmas inteligente con un registro que guarda los parámetros asociados a cada evento [3].

### 5. Conclusiones

Las máquinas de anestesia concentran en un solo equipo el suministro de gases, la dosificación del anestésico y el soporte ventilatorio, por lo que su correcto estado depende de que cada subsistema cumpla su función de forma coordinada. En esta práctica se reconocieron las partes principales de la WATO EX-20 y se revisaron, a partir de los manuales, las fallas que pueden presentarse en cada subsistema y sus causas. Al ordenar los subsistemas por el número de fallas descritas, los mensajes de alarma de la unidad principal y el ventilador resultaron los más numerosos, seguidos de las fallas de hardware y eléctricas y las del sistema de entrega de gas anestésico. En el circuito del paciente, aunque se describen menos fallas, se reúne el mayor número de causas posibles, casi todas relacionadas con fugas por sellos y componentes mal instalados, sensores con agua o sensores sin calibrar. Esto permite concluir que las fallas más frecuentes al operar la máquina se originan en el montaje de las piezas desmontables, en la calibración de los sensores y en la continuidad del suministro eléctrico y de gases, aspectos que la inspección previa a cada uso y el mantenimiento programado pueden verificar. Como siguiente paso, sería conveniente comparar este ordenamiento con las pruebas previas a la operación del manual de operación de la EX-20 y con el registro de mantenimiento del equipo del laboratorio, para contrastar las fallas descritas con las que realmente se presentan en uso.

### 6. Referencias

[1] Shenzhen Mindray Bio-Medical Electronics Co., Ltd., *WATO EX-20/30/35 Anesthesia Machine Service Manual*, Rev. 6.0, nov. 2012. [En línea]. Disponible en: https://isurplus.com.au/manuals/Mindray%20WATO%20ex35%20Service%20Manual.pdf.

[2] Mindray, *Manual del operador WATO EX-20*. [En línea]. Disponible en: https://es.scribd.com/document/660017883/tuxdoc-com-manual-usuario-mindray-wato-ex-20. 

[3] Mindray, "WATO EX-35 Anesthesia Machine". [En línea]. Disponible en: https://www.mindray.com/in/products/anesthesia/wato-ex-35/.
