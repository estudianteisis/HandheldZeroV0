# Proyecto: Handheld Zero — V0

Prompt versión en proyecto:

> Este chat hace parte del proyecto macro **Handheld Lab**.  
El objetivo de este chat es desarrollar específicamente la consola **Handheld Zero — V0**, entendida como el primer prototipo funcional del proyecto.

> La meta de esta versión no es todavía crear una consola final, bonita o perfectamente portable, sino entender el pipeline completo: arquitectura, componentes, costos, proveedores, compatibilidad, energía, controles, pantalla, software y riesgos reales de fabricación.*




---

---
## 0. Concepto, vibra e ideas locas

Esta sección recoge ideas conceptuales, estéticas o funcionales que pueden ser difíciles, poco prácticas o incluso imposibles en esta versión, pero que capturan algo importante sobre lo que quiero que esta consola sea.

| Decisión conceptual | Pregunta guía | Respuesta inicial |
|---|---|---|
| Vibra general | Se debe sentir como un **Game Boy modernizado**: simple, reconocible, portable y nostálgico, pero con una sensación más premium, más capaz y más personalizable. No debe sentirse como una mini PC metida en una carcasa, sino como una consola con identidad propia. |  |
| Idea insignia | **¿Qué pasaría si el Game Boy fuera teletransportado a la modernidad?** La consola debe combinar feel retro con performance y versatilidad modernas. Debe parecer una evolución directa de las consolas que homenajea, no una imitación barata ni un gadget genérico. |  |
| Fantasía de uso | Debe vivir entre dos mundos: uso casual “on the move” y uso más cómodo en casa. Debe poder sacarse rápidamente en una fila, en una sala de espera o en un trayecto corto, pero también sostener sesiones más largas en viajes, escritorio o sofá. Idealmente debe tener una transición tipo Switch entre portabilidad y uso en casa, aunque en V0 esto pueda ser más conceptual que completamente resuelto.  |  |
| Ritual de uso | Debe tener rituales propios: boot screen, loading screens, sonidos, home visual, perfiles o modos. La idea de cartridges modernos es central: no necesariamente un cartucho con un solo juego, sino un módulo físico que pueda representar una colección, una categoría, un modo, un perfil, una estética o una experiencia. El ritual debe reforzar que esto es una consola, no simplemente Linux abriendo un emulador. |  |
| Relación con lo retro | Debe tener un feel **retro plus**: nostálgica, directa, física y sencilla, pero sin heredar innecesariamente las malas limitaciones de las consolas antiguas. Puede homenajear los parlantes modestos, los botones físicos, los cartuchos, el arranque dedicado y la simplicidad de interfaz, pero no debe justificar una pantalla mala, mal rendimiento o una experiencia incómoda bajo la excusa de “lo retro”. |  |
| Sistema físico especial | Los cartridges son la idea física insignia. También se deben explorar: docking, tapa para pantalla, módulos reemplazables, controles modificables, almacenamiento expandible, carcasa reparable y posibilidades de upgrade. El form factor base debe inspirarse en la familiaridad de un Game Boy, pero con mejoras de calidad de vida modernas: mejor ergonomía, controles más cómodos y layout personalizado según estándares de memoria muscular/visual modernos (íconos de los botones). |  |
| Sistema digital especial | El sistema debe arrancar en una experiencia tipo consola: home claro, visualmente cuidado, navegable con controles, con acceso rápido a juegos, sistemas, favoritos y ajustes. Si hay un sistema operativo tipo PC debajo, debe quedar escondido o relegado a un modo técnico. La experiencia por defecto no debe ser “prender un computador y abrir un programa”, sino “prender una consola”. Debe poder usarse con teclado/mouse cuando sea necesario para mantenimiento, configuración o cambios técnicos. |  |
| Personalización | La consola debe ser altamente personalizable con suficiente esfuerzo: botones, joysticks, almacenamiento, carcasa, temas visuales, boot screens, layouts, módulos físicos y formas de input/output. Debe favorecer estándares abiertos o comunes del mundo DIY: USB, Bluetooth, microSD, HDMI, audio externo y componentes reemplazables. La personalización no tiene que estar toda lista en V0, pero la arquitectura no debería bloquearla desde el inicio. |  |
| Restricción creativa | ¿Qué limitación quiero abrazar como parte de la identidad del proyecto? Las limitaciones deben ser mejorables para el usuario que lo quiera. Por ejemplo, en principio parlantes cheap como tenían las de inspiración (Igual los SFX de estos juegos suenan mejor y más auténticos en parlantes mediocres como los de la época), pero debe haber forma de mejorar el sonido por lo menos conectándose a algo externo. Lo mismo para los controles y la imagen. Ojo, las restricciones creativas deben intentar no ser un cop-out para bajar la calidad de los componentes (e.g. no usar una pantalla mediocre, que quita feel premium, excusado en que así son las consolas retro). |  |
| Línea roja conceptual | No puede ser no portátil. No puede rendir peor que una R36S de referencia. No puede sentirse excesivamente DIY, frágil, improvisada o como un computador genérico. No puede requerir demasiado setup para jugar. No puede sacrificar la experiencia de consola por facilidad técnica. |  |
| Otras ideas para explorar después | Cartridges como perfiles físicos, cartridges como almacenamiento, cartridges como llaves de modo, dock de sobremesa, módulos de controles, tapa/protector de pantalla y estuche, sistema de temas, sonidos propios, edición de boot screens, carcasa intercambiable, módulo de audio mejorado, módulo de batería extendida y modos de uso “casa / viaje / rápido”, en específico con Power Plan default correspondiente. |  |

### 0.5. Principios Conceptuales

| Principio                        | Significado                                                                                                                                     |
| -------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| **Consola antes que computador** | Aunque use hardware genérico o Linux, la experiencia debe sentirse dedicada, cerrada y lista para jugar.                                        |
| **Retro sin mediocridad**        | La nostalgia debe aparecer en los rituales, el formato y la simplicidad, no en baja calidad de pantalla, controles malos o bajo rendimiento.    |
| **Modular donde tenga sentido**  | Lo físico y lo digital deben permitir exploración del usuario/comunidad: almacenamiento, controles, temas, pantallas externas, audio externo, dock y futuros módulos. |


---

---

## 1. Identidad del proyecto

| Decisión | Definición |
|---|---|
| Nombre del proyecto | Handheld Zero |
| Versión actual | V0 |
| Tipo de consola | Retro experimental |
| Inspiración principal | R36S |
| Objetivo principal | Entender el pipeline de desarrollo de una handheld retro: componentes, costos, proveedores, compatibilidad técnica, ensamblaje, software y riesgos reales. |
| Criterio de éxito | Tener un prototipo funcional, aunque no sea todavía práctico ni estéticamente final, que demuestre que la arquitectura escogida puede convertirse en una consola portable real. |

---

---

## 2. Alcance técnico

| Decisión | Pregunta clave | Respuesta inicial |
|---|---|---|
| Juegos objetivo | ¿Hasta qué sistemas quiero correr de forma razonable? | Retro ligero: 8-bit, 16-bit, GBC/GBA y, si es viable, 5ta generación. |
| Plataforma principal | ¿Qué placa, SoC, mini PC, arquitectura o sistema base podría usar? |Pendiente de plataforma específica. Se evaluarán plataformas reales comprables y desarrollables, priorizando SBC compacto o compute module con carrier board comercial. No se escogerá chipset en abstracto ni se empezará con carrier board propia en V0. |
| Sistema operativo | ¿Qué software/base usaré? | Pendiente según plataforma. Debe soportar experiencia tipo consola, pick-up-and-play, boot razonable, save/load automático o mitigaciones equivalentes. |
| Pantalla | ¿Qué tamaño, resolución, relación de aspecto y tipo de pantalla? | Pendiente. |
| Controles | ¿Qué botones, joysticks, gatillos y distribución tendrá? | Pendiente. |
| Audio | ¿Parlantes, jack 3.5 mm, Bluetooth o ambos? | Pendiente. |
| Conectividad | ¿Wi-Fi, Bluetooth, USB-C, HDMI, microSD? | Pendiente. |

---

---

## 3. Energía y seguridad

| Decisión | Pregunta clave | Respuesta inicial |
|---|---|---|
| Tipo de batería | ¿LiPo plana, 18650, powerbank interna u otra solución? | Pendiente por diseño de carcasa (V1). |
| Capacidad objetivo | ¿Cuántas horas de uso busco? | Trip largo, alrededor de 6 horas, negociable con modulo extra. |
| Carga | ¿USB-C, módulo de carga, PD, carga balanceada? | Pendiente por diseño. |
| Protección | ¿Cómo evito sobrecarga, sobredescarga, cortos y calor excesivo? | Pendiente por diseño. |
| Consumo estimado | ¿Cuánta corriente consume el sistema en uso real? | Pendiente por diseño. |

---

---

## 4. Diseño físico

| Decisión | Pregunta clave | Respuesta inicial |
|---|---|---|
| Formato | ¿Horizontal, vertical, plegable, tipo tablet, tipo clamshell? | Vertical, una pantalla, controles no touch, tipo GB. |
| Tamaño objetivo | ¿Bolsillo, mochila, escritorio? | Bolsillo/maleta. |
| Ergonomía | ¿Cómo se sostiene durante 30-60 minutos? | Cómodo a dos manos. |
| Carcasa | ¿Impresa en 3D, modificada de otra consola, acrílico, CNC? | Impresa 3D. |
| Ensamble | ¿Tornillos, clips, inserts, módulos reemplazables? | Buscar evitar ensamble destructivo (pegante). |
| Reparabilidad | ¿Qué tan fácil es abrirla y cambiar piezas? | Pendiente por diseño. |

---

---

## 5. Fabricación y herramientas

| Decisión | Pregunta clave | Respuesta inicial |
|---|---|---|
| Herramientas disponibles | ¿Qué tengo: cautín, multímetro, impresora 3D, fuente, osciloscopio? | Cautín, multímetro, impresora 3D, herramientas lab IELE. |
| Habilidades a aprender | ¿Qué necesito aprender para esta versión? | 1. Diseño correcto de PCBs. |
| Piezas compradas | ¿Qué componentes compraré listos? | 1. Pantalla 2. Cerebro / SBC simple con chipset escogido. Módulo compute. |
| Piezas diseñadas | ¿Qué diseñaré yo mismo? | Pendiente por diseño. |
| Riesgos de fabricación | ¿Qué parte es más probable que falle? | Pendiente por diseño. |

---

---

## 6. Presupuesto y compras

| Decisión | Pregunta clave | Respuesta inicial |
|---|---|---|
| Presupuesto máximo | ¿Cuánto puedo gastar en esta versión? | 500.000 COP entre diseño y BOM. |
| Presupuesto de error | ¿Cuánto puedo perder si algo sale mal? | Sin techo. |
| Componentes críticos | ¿Qué piezas definen el éxito del proyecto? | Chipset. |
| Componentes reutilizables | ¿Qué puedo usar luego en otra versión? | Idealmente todo. |
| Proveedores | ¿Dónde compraré las piezas? | Mercados online, zonas de electrónicos en Bogotá. |

---

---

## 7. Roadmap de esta consola

| Fase | Objetivo | Resultado esperado |
|---|---|---|
| V0 | Prototipo funcional de aprendizaje | Sistema corriendo fuera de una carcasa final, con pantalla, controles, audio y energía resueltos al menos de forma básica. |
| V1 | Primera versión portable | Consola cerrada, usable y con carcasa funcional. |
| V1.5 | Refinamiento | Mejor ergonomía, autonomía, distribución interna y acabado. |
| V2 | Segunda generación | Diseño más limpio, modular, reparable y potencialmente replicable. |

### 7.1 Definición de versión: V0

Esta sección define qué debe lograr V0, qué puede quedar provisional y qué decisiones deben mantenerse abiertas para no bloquear el aprendizaje del proyecto.

#### Qué debe demostrar V0

- Que la arquitectura escogida puede correr el objetivo mínimo de juegos.
- Que la plataforma puede convertirse razonablemente en una handheld real.
- Que pantalla, controles, audio y energía pueden integrarse en un sistema funcional.
- Que la experiencia puede sentirse más como consola que como mini PC.
- Que los riesgos principales de software, energía, controles y form factor pueden identificarse temprano.

#### Qué puede quedar provisional en V0

- La carcasa puede ser impresa, abierta, fea o experimental.
- La batería puede empezar como alimentación externa o solución modular.
- Los controles pueden usar PCBs simples, módulos o soluciones intermedias.
- El sistema de cartridges puede ser conceptual o parcialmente funcional.
- El dock puede quedar como idea, mockup o prueba limitada.
- La distribución interna puede no estar optimizada.

#### Qué no puede fallar en V0

- No puede rendir peor que una R36S como referencia mínima.
- No puede depender de una arquitectura sin camino razonable hacia una consola portable.
- No puede sentirse totalmente como un mini PC que requiere demasiado setup.
- No puede bloquear futuras mejoras de controles, almacenamiento, energía o carcasa.
- No puede ahogar el proyecto en una motherboard propia demasiado temprano.

#### Qué queda para V1

- Carcasa cerrada y usable.
- Batería interna mejor integrada.
- Mejor ergonomía.
- Mejor distribución interna.
- Integración más limpia de pantalla, botones, audio e I/O.
- Posible carrier board propia si V0 valida la arquitectura.

#### Principio rector de V0

V0 debe ser suficientemente simple para existir, pero suficientemente parecido a la consola soñada para que lo aprendido sirva.

### 7.2 Plan de desarrollo por etapas de V0

Esta sección organiza el desarrollo de Handheld Zero V0 en etapas prácticas.  
El objetivo no es avanzar de manera perfectamente lineal, sino evitar que el proyecto se bloquee por tiempos de compra, envíos internacionales, falta de herramientas o decisiones tomadas demasiado tarde.

Como muchos componentes pueden venir de proveedores internacionales y tener tiempos largos de espera, el proyecto debe priorizar temprano las decisiones que habilitan compras críticas. Durante los tiempos de espera se debe avanzar en documentación, pruebas, herramientas, diseño preliminar, software y preparación técnica.

El principio general de esta etapa es:

> Decidir y pedir temprano lo que bloquea el proyecto; usar los tiempos de espera para llegar preparado al momento en que lleguen los componentes.

---

#### Etapa 0 — Conceptualización y brújula de diseño

**Estado:**  
Prácticamente completada.

**Objetivo:**  
Definir qué es Handheld Zero, qué quiere ser, qué no debe traicionar y qué criterios guiarán las decisiones técnicas.

**Trabajo principal:**

- Definir la vibra general del proyecto.
- Definir la relación con lo retro.
- Definir los principios conceptuales.
- Definir el alcance mínimo de performance.
- Identificar líneas rojas conceptuales.
- Separar decisiones conceptuales, bitácora de diseño y decisiones cerradas.

**Resultado esperado:**

Un documento suficientemente claro para evitar compras incoherentes o decisiones técnicas que contradigan el concepto.

**Criterio de salida:**

Esta etapa se considera suficiente cuando el proyecto puede responder:

- Qué tipo de consola se quiere construir.
- Qué experiencia debe sentirse como consola y no como mini PC.
- Qué cosas son obligatorias para V0.
- Qué cosas pueden esperar a V1 o V2.

---

#### Etapa 1 — Cierre de arquitectura mínima comprable

**Estado:**  
Etapa actual.

**Objetivo:**  
Tomar las decisiones mínimas necesarias para hacer las primeras compras críticas del proyecto.

Esta etapa no busca cerrar todo el diseño final. Busca decidir lo suficiente para pedir los componentes que más pueden bloquear el avance por tiempos de entrega.

**Decisiones prioritarias:**

| Prioridad | Decisión | Por qué desbloquea el proyecto |
|---|---|---|
| 1 | Plataforma principal / cerebro | Define chipset, formato, OS, consumo, tamaño, conectividad y posibilidades futuras. |
| 2 | Formato del cerebro | Define si se usará SBC compacto, compute module con carrier comercial o eventualmente otra ruta. |
| 3 | Pantalla inicial | Permite validar experiencia visual, resolución, relación de aspecto, consumo e integración. |
| 4 | Método inicial de input | Permite probar OS, frontend y juegos sin esperar controles finales. |
| 5 | Alimentación inicial | Permite encender y probar el sistema de forma segura. |
| 6 | Herramientas necesarias | Evita que los componentes lleguen y no se puedan usar, flashear, medir o conectar. |

**Resultado esperado:**

Una primera lista de compra organizada en cuatro grupos:

| Grupo | Descripción |
|---|---|
| Compra crítica inmediata | Componentes que definen arquitectura y tienen tiempos largos de entrega. |
| Compra secundaria | Componentes útiles, pero no indispensables para las primeras pruebas. |
| Compra local | Herramientas, cables, adaptadores y consumibles que se pueden conseguir rápido. |
| Compra diferible | Elementos de acabado, ergonomía o refinamiento que pueden esperar. |

**Criterio de salida:**

Esta etapa se considera completada cuando existe una lista de compra inicial con:

- Plataforma candidata escogida.
- Pantalla inicial definida o lista corta clara.
- Forma de alimentación inicial definida.
- Forma de input inicial definida.
- Herramientas mínimas identificadas.
- Pruebas de recepción preparadas antes de que lleguen los componentes.

---

#### Etapa 2 — Preparación durante tiempos de espera

**Estado:**  
Empieza apenas se hagan las compras críticas.

**Objetivo:**  
Evitar que el proyecto quede detenido mientras llegan componentes internacionales.

Durante esta etapa se debe hacer todo el trabajo que no depende de tener todavía el hardware final en la mano.

**Trabajo principal:**

| Área | Trabajo durante la espera |
|---|---|
| Documentación | Limpiar el documento, numeración, decisiones cerradas, bitácora y objetivos por versión. |
| Software | Investigar OS compatibles con la plataforma elegida, métodos de instalación, imágenes, flasheo y recuperación. |
| Pruebas | Diseñar los protocolos de prueba para boot, pantalla, input, audio, consumo, temperatura y pick-up-and-play. |
| Herramientas | Verificar que se tienen cables, adaptadores, lector microSD, fuente, multímetro, soldadura, conectores y consumibles. |
| Diseño físico | Bocetar form factor, layout de controles, ubicación tentativa de pantalla, batería, cerebro y PCBs hijas. |
| Controles | Investigar switches, membranas, joysticks, botones, layout y posibles microcontroladores HID. |
| Energía | Investigar power path, cargadores, protección de batería, boost/buck converters y medición de consumo. |
| Cartridge | Definir niveles posibles de cartridge: microSD físico, EEPROM, NFC, USB, perfil o modo. |
| BOM | Construir lista de materiales con precios, proveedores, tiempos de entrega y riesgos. |
| PCB preliminar | Diseñar PCBs simples no críticas como ejercicio: botones, breakout, LEDs o adaptadores. |

**Checklist obligatorio antes de que llegue la plataforma:**

| Elemento | Pregunta |
|---|---|
| OS | ¿Sé exactamente qué imagen o sistema voy a intentar instalar primero? |
| Flasheo | ¿Tengo lector microSD, tarjetas adecuadas y software para grabar imágenes? |
| Recuperación | ¿Sé cómo recuperar la placa si no bootea? |
| Energía | ¿Tengo una fuente o powerbank capaz de alimentar la placa de forma segura? |
| Video | ¿Tengo pantalla, cable o adaptador compatible con la salida inicial? |
| Input | ¿Tengo teclado, mouse, control USB o adaptador para navegar el sistema? |
| Red | ¿Sé si necesito Wi-Fi, Ethernet, adaptador USB o acceso a internet durante setup? |
| Medición | ¿Tengo forma de medir voltaje, corriente y temperatura aproximada? |
| Documentación | ¿Tengo descargados manuales, pinouts, esquemáticos, imágenes de OS y guías básicas? |
| Consumibles | ¿Tengo cables, headers, jumpers, conectores, cinta Kapton, tornillos, separadores y herramientas básicas? |

**Resultado esperado:**

Cuando lleguen los componentes, el proyecto debe estar listo para probarlos en vez de empezar a investigar desde cero.

**Criterio de salida:**

Esta etapa se considera exitosa si, al recibir la plataforma, ya existe:

- Protocolo de bring-up.
- Herramientas listas.
- OS preparado.
- Lista de pruebas.
- Plan de conexión inicial.
- Criterios de aceptación o descarte.

---

#### Etapa 3 — Recepción y bring-up de plataforma

**Objetivo:**  
Verificar que el cerebro de la consola funciona, puede arrancar un sistema operativo y permite correr las primeras pruebas.

Esta etapa debe ser metódica. No se debe empezar conectando todo al mismo tiempo. Primero se valida lo mínimo y luego se agregan subsistemas.

**Orden de prueba recomendado:**

| Paso | Prueba | Resultado esperado |
|---|---|---|
| 1 | Inspección física | La placa llegó en buen estado, sin daños visibles. |
| 2 | Alimentación básica | La placa enciende con fuente estable y sin calentamiento anormal. |
| 3 | Boot inicial | La placa arranca de forma repetible. |
| 4 | Video | Hay salida estable a pantalla o monitor. |
| 5 | Input básico | Se puede controlar con teclado, mouse o gamepad. |
| 6 | OS | Se instala o arranca el sistema operativo elegido. |
| 7 | Almacenamiento | microSD/eMMC/USB funcionan de forma confiable. |
| 8 | Audio | Hay salida de audio básica por HDMI, jack, USB o módulo. |
| 9 | Red | Wi-Fi, Bluetooth o Ethernet funcionan si aplican. |
| 10 | Emulación inicial | Corre sistemas objetivo básicos. |
| 11 | Consumo | Se mide consumo aproximado en idle, frontend y juego. |
| 12 | Temperatura | Se mide comportamiento térmico en uso real. |

**Pruebas de pick-up-and-play:**

| Prueba | Criterio de aceptación |
|---|---|
| Boot frío hasta frontend | Medir tiempo real. |
| Boot frío hasta último juego | Medir si el sistema lo permite. |
| Sleep o fake suspend de 5 minutos | Debe volver confiablemente. |
| Sleep o fake suspend de 30 minutos | Debe conservar sesión o apagarse de forma limpia. |
| Drenaje en pausa | Medir pérdida aproximada de batería por hora o consumo en modo pausa. |
| Shutdown desde juego | Debe evitar corrupción de almacenamiento o pérdida de progreso. |
| Encendido sin teclado | Debe poder usarse con controles o input simple. |
| Auto-save / auto-load | Validar si existe o si puede configurarse. |

**Resultado esperado:**

Una conclusión clara sobre la plataforma:

| Veredicto | Significado |
|---|---|
| Viable | La plataforma puede seguir como base de V0. |
| Viable con riesgos | Funciona, pero hay problemas que deben documentarse y mitigarse. |
| No viable | El problema afecta demasiado performance, software, energía, disponibilidad o experiencia de uso. |

---

#### Etapa 4 — Prototipo funcional abierto

**Objetivo:**  
Unir plataforma, pantalla, input, audio y alimentación en un sistema jugable, aunque todavía sea abierto, feo o provisional.

Esta etapa no busca una consola final. Busca responder:

> ¿Puedo jugar realmente en esto como si fuera una consola?

**Subsistemas mínimos:**

| Subsistema | Versión aceptable en V0 abierto |
|---|---|
| Cerebro | SBC compacto o compute module con carrier comercial. |
| Pantalla | Pantalla funcional, aunque no sea la final. |
| Input | Control USB, teclado temporal, microcontrolador HID o PCB simple. |
| Energía | Fuente USB-C, powerbank o alimentación estable provisional. |
| Audio | HDMI, jack, USB audio o módulo amplificador simple. |
| Software | Frontend navegable y emulación funcional. |
| Montaje | Base abierta, impresión 3D simple, acrílico, separadores o estructura provisional. |

**Resultado esperado:**

Un sistema jugable que permita evaluar:

- Performance real.
- Latencia percibida.
- Pantalla.
- Controles.
- Audio.
- Calor.
- Consumo.
- Boot.
- Pick-up-and-play.
- Tamaño físico.
- Sensación de consola vs mini PC.

---

#### Etapa 5 — PCBs hijas y módulos propios

**Objetivo:**  
Reemplazar soluciones improvisadas por módulos diseñados para Handheld Zero, sin diseñar todavía una motherboard completa.

Esta es una etapa central para el aprendizaje de ingeniería electrónica del proyecto.

**PCBs candidatas:**

| PCB / módulo | Prioridad | Razón |
|---|---|---|
| PCB de botones frontales | Alta | Define sensación de consola y ergonomía. |
| PCB de D-pad | Alta | Crítica para juegos retro. |
| PCB de Start/Select/Menu/Power | Alta | Necesaria para experiencia de consola. |
| PCB de gatillos | Media | Importante para PS1/GBA y comodidad. |
| PCB de joysticks | Media | Deseable según sistemas objetivo. |
| PCB de audio/amplificador | Media | Mejora experiencia y reduce dependencia de HDMI/jack. |
| PCB de cartridge experimental | Alta conceptual | Conecta con la idea insignia del proyecto. |
| PCB de distribución de energía | Alta, con cuidado | Crítica para portabilidad, pero debe abordarse metódicamente. |
| PCB de LEDs/estado | Baja-media | Útil para feedback de power, carga, modo o cartridge. |
| PCB de I/O o dock | Media | Permite explorar transición casa/portabilidad. |

**Criterio de diseño:**

Las PCBs hijas deben permitir aprender y mejorar la consola sin poner en riesgo todo el sistema. Se priorizan módulos reemplazables, documentados y fáciles de depurar.

---

#### Etapa 6 — Integración física V0

**Objetivo:**  
Montar los subsistemas en un cuerpo portable provisional.

La carcasa puede ser experimental, pero la consola debe poder agarrarse, prenderse y jugarse como un objeto único.

**Aspectos a validar:**

| Aspecto | Pregunta |
|---|---|
| Ergonomía | ¿Se puede sostener durante 30–60 minutos? |
| Peso | ¿Se siente razonable para una handheld? |
| Distribución interna | ¿Los componentes caben sin forzar cables o conectores? |
| Calor | ¿La zona de las manos y batería se mantiene aceptable? |
| Controles | ¿La posición y tactilidad funcionan en juego real? |
| Pantalla | ¿La relación tamaño/resolución/distancia es cómoda? |
| Energía | ¿La alimentación funciona sin desconexiones o reinicios? |
| Reparabilidad | ¿Se puede abrir, revisar y modificar sin destruirla? |

**Resultado esperado:**

Una Handheld Zero V0 física, funcional y documentada, aunque no sea todavía bonita ni final.

---

#### Etapa 7 — Evaluación de V0 y preparación de V1

**Objetivo:**  
Usar lo aprendido en V0 para decidir qué arquitectura, subsistemas y decisiones pasan a la siguiente versión.

**Preguntas de cierre:**

| Área | Pregunta |
|---|---|
| Plataforma | ¿El chipset/formato elegido debe mantenerse? |
| Software | ¿El OS permite experiencia de consola suficiente? |
| Performance | ¿Se cumplió o superó el benchmark R36S? |
| Pick-up-and-play | ¿Boot, sleep, resume y auto-save son aceptables? |
| Pantalla | ¿La pantalla debe mantenerse o cambiar? |
| Controles | ¿El layout y tactilidad funcionaron? |
| Energía | ¿La batería/alimentación es viable para una versión cerrada? |
| Carcasa | ¿El form factor debe mantenerse? |
| Modularidad | ¿Qué módulos valen la pena y cuáles no? |
| Carrier propia | ¿Tiene sentido diseñar una carrier board propia para V1? |

**Resultado esperado:**

Una lista clara de decisiones para V1:

- Qué se mantiene.
- Qué se rediseña.
- Qué se descarta.
- Qué se compra distinto.
- Qué se diseña como PCB propia.
- Qué problemas deben resolverse antes de cerrar una carcasa final.
---

---

## 8. Preguntas abiertas iniciales

- ¿Qué placa conviene usar para una handheld retro barata y suficientemente capaz?
- ¿Es mejor empezar con una pantalla estándar fácil de conseguir o escoger desde ya una pantalla cercana al formato final?
- ¿Conviene resolver primero energía/batería o dejar V0 alimentada externamente?
- ¿Qué tanto debo diseñar desde cero y qué tanto debo comprar como módulos ya hechos?
- ¿Qué componentes puedo conseguir fácilmente desde Colombia sin que el costo de importación destruya el proyecto?

---

---

## 9. Decisiones de concepto tomadas

| Fecha      | Decisión / Riesgo                                                                            | Razón                                                                                                     |
| ---------- | -------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| 2026-05-23 | Se añade pick-up-and-play como criterio crítico de plataforma | La consola debe poder usarse en sesiones cortas sin setup ni ansiedad por batería. |
| 2026-05-23 | RK3566 queda marcado con riesgo en sleep/resume y standby | Reportes de comunidad y documentación de fake suspend sugieren que la suspensión real puede no ser ideal. |
| 2026-05-23 | Se evaluarán mitigaciones con fake suspend, auto-save, auto-load y power management dedicado | El proyecto puede resolver parte del problema desde diseño de hardware/software propio.                   |
| 2026-05-23 | La arquitectura se evaluará en tres rutas: SBC compacto, compute module con carrier existente, y compute module con carrier propia | Permite comparar velocidad, riesgo, integración, aprendizaje y continuidad hacia la consola final. |
| 2026-05-23 | La carrier propia no será el primer paso por defecto | Antes conviene validar plataforma, OS, pantalla, controles, consumo y experiencia handheld.                 |
| 2026-05-23 | El diseño de PCBs propias se enfocará primero en subsistemas de riesgo controlado | Controles, botones, audio, energía, cartridge e I/O ofrecen aprendizaje real sin bloquear todo el proyecto. |

---

---

## 10. Bitácora de diseño / Decisiones en desarrollo

Esta sección es el espacio vivo de diseño del proyecto.

No está pensada como una tabla de decisiones cerradas, sino como un lugar para pensar en voz alta: registrar ideas, comparar caminos, anotar intuiciones, dudas, restricciones, riesgos y decisiones preliminares.

Cada bloque corresponde a un tema de diseño que se está trabajando. Algunos bloques terminarán en decisiones cerradas; otros quedarán como ideas aplazadas, descartadas o pendientes de validación.

---

### 10.1 Tema de diseño: Chipset / board

**Área relacionada:**  

Plataforma

**Pregunta central:**  

Chipset específico a utilizar

**Contexto:**  
El corazón del proyecto que decidirá el resto del desarrollo.

**Intención de diseño:**  
Cumplir los objetivos conceptuales con un chipset asequible, trabajable y utilizable en el form factor.

**Opciones, caminos o ideas posibles:**

- **Opción A:**  
  Raspberry Pi 4 (DESCARTADO POR FORM FACTOR Y POWER DELIVERY).

- **Opción B:**  
  Familia RK3366/68

- **Opción C:**  
  H700 (DESCARTADO POR FALTA DE RECURSOS PARA DIY, SOLO EXISTE PARA INDUSTRIA).

- **Opción D:**  
  RK3326

**Criterios que importan en esta decisión:**

- Utilidad fuera del prototipo (en producto real).
- Facilidad para conseguir y precio.
- Software: Power states, save states, booting.
- Hardware: FF pequeño, funcional en diseño con otros módulos PCB.

**Notas de análisis:**  
| Criterio              | Objetivo V0                                                            |
| --------------------- | ---------------------------------------------------------------------- |
| Boot frío             | Aceptable si no es el modo principal de uso                            |
| Sleep corto           | Debe permitir pausas de minutos sin drenar mucho                       |
| Resume                | Debe volver al juego de forma confiable                                |
| Auto-save / auto-load | Muy deseable                                                           |
| Apagado seguro        | Debe evitar corrupción de SD o pérdida de progreso                     |
| Standby largo         | Ideal, pero no obligatorio para V0 si existe auto-shutdown inteligente |

- RK3566

| Criterio                      | RK3566                         |
| ----------------------------- | ------------------------------ |
| Performance                   | Bueno para superar R36S/RK3326 |
| Consumo jugando               | Probablemente manejable        |
| Ecosistema handheld           | Bueno                          |
| Software CFW                  | Existente, pero variable       |
| Sleep/resume                  | Riesgo alto                    |
| Boot rápido                   | Riesgo medio                   |
| Pick-up-and-play              | No garantizado                 |
| Mitigable por hardware propio | Sí, parcialmente               |
| Sigue siendo candidato        | Sí, pero ya no automático      |

Prueba posible:

| Prueba                       | Criterio de aceptación                  |
| ---------------------------- | --------------------------------------- |
| Boot frío hasta frontend     | Medir segundos reales                   |
| Boot frío hasta último juego | Medir si es posible                     |
| Fake suspend 5 min           | Debe volver confiablemente              |
| Fake suspend 30 min          | Debe conservar sesión o apagar limpio   |
| Sleep real, si existe        | Debe despertar 10/10 veces              |
| Drenaje en pausa             | Medir pérdida de batería por hora       |
| Shutdown desde juego         | Debe guardar estado o evitar corrupción |
| Encendido sin teclado        | Debe ser 100% usable con controles      |


**Riesgos identificados:**

- Power drain en standby.
- Tiempo y facilidad de boot afecta pick-up-and-play, que es prioridad según objetivos conceptuales.

**Decisión actual:**  
La investigación llevó a descubrir que la prioridad antes de escoger el chipset es decidir el formato particular del chipset y que hay disponible en ese formato, para tomar una decisión en un pool de opciones más limitado y realista.

**Razón de la decisión:**  
Se descubrió que hay chipsets que no están disponibles o no son prácticos para un proyecto como este, llevando a que la decisión en escogerlo tenga que darse con más consideraciones.

**Qué queda por validar:**  

- Entender apropiadamente que formatos existen.
- Escoger el formato ideal para esta versión.

**Estado:**  
Completado.


**Next steps:**
Crear nueva entrada sobre el Tema de diseño "Formato del cerebro". Después si volver a la selección de chipset.

---

### 10.2 Tema de diseño: Formato del cerebro: SBC, CM con DIY CB, CM con CB comercial.

**Área relacionada:**  

Plataforma

**Pregunta central:**  
Decidir que formato debo usar para esta etapa del desarrollo.

**Contexto:**  
Definirá que chipset puedo usar dependiendo de su disponibilidad en el formato y afectará el alcance de los features y form factor final. Habrá que escoger entre sacrificar features o form factor al escoger un camino.

**Intención de diseño:**  
Encontrar el formato perfecto que permita una fabricación factible, adquisición factible de los componentes pero evitar sacrificar features del concepto.

**Opciones, caminos o ideas posibles:**

- **Opción A:**  
  SBC existente: placa única comercial que ya integra SoC, RAM, PMIC, almacenamiento/boot e I/O básico.

- **Opción B:**  
  CM con DIY CB, implicando el diseño de una motherboard.

- **Opción C:**  
  CM con CB comercial, quedando a la merced del tamaño y IO del CB.

**Criterios que importan en esta decisión:**

- Tamaño
- Mis habilidades de diseño
- Disponibilidad de componentes y de fabricación.

| Criterio                | Por qué importa                                            |
| ----------------------- | ---------------------------------------------------------- |
| Performance             | Debe igualar/superar R36S.                                 |
| Pick-up-and-play        | Boot, sleep, resume, autosave, drain.                      |
| Tamaño físico           | Debe caber en una handheld real.                           |
| Ubicación de conectores | Puede matar o salvar el form factor.                       |
| Pantalla soportada      | HDMI fácil vs MIPI/DSI más final.                          |
| Energía                 | Consumo, 5V/3.3V, batería, carga.                          |
| Documentación           | Esquemas, pinouts, OS, comunidad.                          |
| Disponibilidad          | Que se pueda comprar sin drama.                            |
| Modularidad             | Que permita controles, cartridge, dock, audio, etc.        |
| Riesgo de fabricación   | Qué tanto puede fallar por PCB propia.                     |
| Costo                   | El costo extra debe justificarse en aprendizaje o calidad. |


**Notas de análisis:**  
- Opción A:

Pros
| Ventaja                 | Por qué importa                                                 |
| ----------------------- | --------------------------------------------------------------- |
| Menor riesgo            | La placa ya trae casi todo resuelto.                            |
| Arranque rápido         | Puedes probar OS y emulación pronto.                            |
| Menos diseño crítico    | No tocas boot, RAM, PMIC, high-speed del SoC.                   |
| Puede ser compacta      | Si encuentras el SBC correcto, puede ser muy viable.            |
| Ideal para V0 funcional | Permite avanzar a consola real sin atascarse en la motherboard. |

Contras
| Riesgo                         | Comentario                                                  |
| ------------------------------ | ----------------------------------------------------------- |
| Dependes del SBC perfecto      | Tamaño, puertos, pantalla, consumo y soporte deben encajar. |
| Layout fijo                    | No eliges ubicación de conectores ni puertos.               |
| Puede tener cosas innecesarias | Headers, puertos, chips, LEDs, conectores altos.            |
| Difícil de optimizar           | La carcasa se adapta a la placa, no al revés.               |
| Menos aprendizaje de carrier   | Aprendes integración, pero no tanto diseño de placa madre.  |

- Opción B:

Pros
| Ventaja                 | Por qué importa                                                                      |
| ----------------------- | ------------------------------------------------------------------------------------ |
| Form factor a la medida | Puedes diseñar la consola desde la ergonomía y no desde la placa.                    |
| I/O exacto              | Solo sacas lo que necesitas: pantalla, controles, audio, carga, USB, cartridge, etc. |
| Mejor integración       | Menos cables, menos adaptadores, menos espacio perdido.                              |
| Más aprendizaje real    | Diseñas una placa madre de producto, no solo conectas módulos.                       |
| Más futuro              | Puede evolucionar a V1/V2 sin cambiar toda la arquitectura.                          |

Contras
| Riesgo                   | Comentario                                                                                          |
| ------------------------ | --------------------------------------------------------------------------------------------------- |
| Diseño más difícil       | Aunque el SoC/RAM estén en el módulo, la carrier puede tener señales delicadas.                     |
| Bring-up complejo        | Si algo no funciona, toca depurar alimentación, boot, USB, pantalla, etc.                           |
| Fabricación más exigente | Probablemente 4 capas, conectores finos y reglas de diseño más estrictas.                           |
| Documentación crítica    | Dependes muchísimo de que el módulo tenga buenos esquemáticos, datasheets y reference designs.      |
| Puede frenar el proyecto | Si se vuelve muy ambicioso, V0 se convierte en “hacer una motherboard” y no en “hacer una consola”. |

-Opción C:

Pros
| Ventaja                    | Por qué importa                                                               |
| -------------------------- | ----------------------------------------------------------------------------- |
| Reduce riesgo de fab       | El módulo y la carrier ya deberían bootear.                                   |
| Permite validar plataforma | Puedes probar OS, emulación, pantalla, USB, audio y consumo antes de diseñar. |
| Aprendizaje transferible   | Sigues usando el módulo que podría ir en una carrier propia futura.           |
| Buen paso hacia V1         | Luego puedes reemplazar la carrier existente por una propia.                  |
| Debug más fácil            | Si algo falla, tienes una configuración base conocida.                        |

Contras

| Riesgo                              | Comentario                                                              |
| ----------------------------------- | ----------------------------------------------------------------------- |
| Form factor impuesto                | La carrier puede ser grande o tener puertos en lugares incómodos.       |
| Espacio desperdiciado               | Ethernet, headers, puertos duplicados o conectores que no necesitas.    |
| Menos “handheld final”              | Puede parecer más devkit que consola.                                   |
| Algunas decisiones ya están tomadas | Alimentación, pantallas compatibles, puertos, etc.                      |
| Difícil de cerrar en carcasa        | Puede servir para V0 abierto, pero no para una consola portable limpia. |

**Riesgos identificados:**

- Ahogar el proyecto en el diseño de un módulo; esto es V0 todavía y debe probar la viabilidad del concepto al igual que identificar errores y retos esquivando problemas profundos de viabilidad o funcionamiento que puedan exigir un rediseño en siguientes versiones. No debe ser todavía un producto perfecto.
- Perder el flavor y la creatividad en mi proyecto pueden ser un efecto de hacer demasiados compromisos en el desarrollo.
- Tener que tomar decisiones de features o form factor antes de tener un producto real y experimentarlo puede llevarme a sacrificar cosas importantes por ignorancia o priorizar detalles que tendrán poco uso/serán mediocres desde la ignorancia de no haber pasado tiempo con el producto.
- Trabajar con productos que no tienen una solución clara a problemas de siguientes versiones puede ser una perdida de tiempo que cause tener que hacer cosas de V0 en V1.
- Estos retos de disponibilidad y fabricación han hecho que otros objetivos pasen a un segundo plano. Antes el chipset se iba a escoger por sus capacidades, pensando en detalles que ahora parecen mínimos como pick-up-and-playability, ahora se escoge por la disponibilidad y facilidad para su desarrollo. Esto puede hacer que el producto final tenga retos que ahora son dificiles de solucionar con lo escogido.

**Decisión actual:**  
Elegir entre dos opciones pensando en los productos disponibles: SBC y CM con CB comercial. El diseño de una CB puede quedar relegado a V1 donde debería haber menos priorización del funcionamiento al estar probados varios conceptos y más enfoque en el feel y la practicidad finales del producto. En este orden de ideas se debería dedicar tiempo a puntualizar los objetivos de cada versión en un documento aparte. La elección no será entre chipsets abstractos, sino entre plataformas comprables y desarrollables: SBCs, compute modules, carrier boards, devkits o handhelds donantes con documentación suficiente.

**Razón de la decisión:**  
Diseñar una CB desde esta etapa frena el proyecto y puede demorar lo importante de V0, que es probar su viabilidad e identificar retos en etapas más allá que solo esta.

**Qué queda por validar:**  

- Encontrar que hay disponible para decidir con que chipset ir y con cuál de los dos formatos.
- Ir pensando en que tan viable, desde el punto de vista de fabricación e información disponible, es diseñar la CB en el futuro como detalle informador de la elección del chipset.

**Estado:**  
Preliminar.

**Next Steps:**

El siguiente paso no es escoger chipset todavía, sino construir una lista corta de plataformas reales disponibles y clasificarlas según formato: SBC compacto, compute module con carrier comercial, o handheld donor/reference.

---

### 10.3 Tema de diseño: Selección de plataforma real comprable — Lote A

**Área relacionada:**  
Plataforma / Arquitectura principal / Compras críticas

**Pregunta central:**  
¿Qué plataforma real, comprable y desarrollable debe usarse como cerebro de Handheld Zero V0?

**Contexto:**  
Las decisiones anteriores establecieron que no se escogerá un chipset en abstracto y que V0 no debe empezar necesariamente diseñando una carrier board propia. Por eso, la decisión ahora debe pasar de familias de chips a plataformas concretas disponibles para comprar.

En esta etapa se está evaluando el **Lote A** de plataformas candidatas, compuesto principalmente por placas basadas en Rockchip RK3566/RK3568 o cercanas, porque esta familia parece ofrecer un equilibrio razonable entre performance, precio, disponibilidad, documentación y posibilidad de desarrollo.

Esta decisión es crítica porque define la primera compra importante del proyecto. Muchos componentes pueden venir de proveedores internacionales, por lo que elegir la plataforma temprano permite hacer el pedido y usar el tiempo de espera para preparar pruebas, herramientas, software, documentación y diseño preliminar.

**Intención de diseño:**  
Escoger una plataforma que permita avanzar hacia un prototipo funcional sin sacrificar innecesariamente la posibilidad de evolucionar hacia una handheld real, modular y reparable.

La plataforma debe ser suficientemente fácil de desarrollar en V0, pero no tan alejada del producto final que genere aprendizaje falso. También debe existir una ruta razonable de progreso hacia V1, idealmente reutilizando el cerebro o parte importante de la arquitectura, para no convertir V0 en un prototipo descartable.

---

**Supuestos nuevos de diseño:**

- El usuario se siente cómodo con soldadura y desoldadura relativamente simple. Por ejemplo, remover un puerto Ethernet o relocalizar conectores puede ser aceptable si reduce el perfil físico o mejora la integración.
- El tamaño objetivo debe mantenerse alrededor de las inspiraciones principales: R36S y Game Boy. No se busca una microconsola extrema, pero sí una handheld real y cómoda.
- Es importante que V0 tenga un camino de progreso hacia V1. Idealmente V1 debería poder construirse sobre aprendizajes y, si es posible, sobre componentes reutilizables de V0.
- La ruta compute module + carrier board sigue siendo conceptualmente atractiva porque permitiría reutilizar el módulo en V1 con una carrier propia, si diseñarla resulta factible.
- Un SBC compacto puede ganar valor si permite relocalizar puertos mediante cables, PCBs hijas o desoldadura de conectores altos. Esto no es tan limpio como un compute module, pero puede mejorar su viabilidad como base reutilizable.

---

**Opciones del Lote A a evaluar:**

- **Opción A1 — Radxa ROCK 3C / SBC RK3566**
- **Opción A2 — Orange Pi 3B / SBC RK3566**
- **Opción A3 — Orange Pi CM4 + carrier board / CM RK3566**
- **Opción A4 — Radxa CM3I + carrier board / CM RK3568**
- **Opción A5 — Geniatech XPI-3566-ZERO / SBC compacto RK3566**

---

**Criterios que importan en esta decisión:**

| Criterio | Por qué importa |
|---|---|
| Disponibilidad real | Debe poder comprarse sin convertir la adquisición en el primer gran bloqueo. |
| Tiempo de entrega | Si el envío tarda semanas, debe pedirse temprano. |
| Precio puesto en Colombia | El costo debe tener sentido frente al presupuesto y al valor de aprendizaje. |
| RAM disponible | 2GB es el mínimo aceptable; 4GB sigue siendo preferible. 1GB solo sirve como opción de validación barata. |
| Form factor | Debe poder integrarse alrededor de dimensiones tipo R36S/Game Boy. |
| Perfil físico | La altura de conectores puede afectar la carcasa, pero puede mitigarse parcialmente desoldando o relocalizando puertos simples. |
| Performance | Debe igualar o superar el benchmark R36S/RK3326. |
| Software / OS | Debe tener ruta razonable para Linux, emulación, frontend y configuración. |
| Pick-up-and-play | Boot, sleep/fake suspend, autosave, autoload y apagado seguro deben poder probarse. |
| Pantalla | Debe permitir una pantalla inicial viable y ojalá una ruta futura más integrada. |
| Input | Debe permitir controles por USB, GPIO, I2C, microcontrolador HID u otra ruta práctica. |
| Energía | Debe poder alimentarse de manera segura en pruebas y tener ruta hacia batería. |
| Documentación | Deben existir manuales, pinouts, imágenes, esquemáticos o comunidad suficiente. |
| Reutilización V0 → V1 | Importa si el cerebro puede seguir siendo útil en la siguiente versión. |
| Carrier futura | Idealmente debe existir una ruta razonable hacia integración más limpia en V1/V2. |
| Riesgo de fabricación | V0 no debe depender de una PCB crítica difícil de depurar. |
| Herramientas requeridas | No debe exigir herramientas imposibles o desconocidas para poder arrancar. |

---

## Análisis de candidatos

### Opción A1 — Radxa ROCK 3C

**Formato:**  
SBC existente.

**SoC:**  
Rockchip RK3566.

**Disponibilidad encontrada:**  
Disponible en Amazon y AliExpress. Amazon parece más confiable y rápido, pero por ahora solo se encontró claramente la versión de 1GB. En AliExpress aparecen opciones con 1GB y 2GB, pero con mayor incertidumbre de envío, tiempo, vendedor y disponibilidad real.

**Precio encontrado:**  
- Amazon: aproximadamente USD 48 para la versión de 1GB.
- AliExpress: opciones alrededor de 200.000–277.000 COP con envío, dependiendo de vendedor, RAM y condiciones.
- Algunas opciones de AliExpress tienen envío poco deseable o condiciones de compra al por mayor.

**Datos relevantes conocidos:**  
La ROCK 3C es una SBC basada en RK3566. Radxa documenta HDMI, MIPI DSI, MIPI CSI, jack 3.5 mm, USB, Ethernet, PCIe 2.0 y header de 40 pines. También documenta un tamaño de aproximadamente **85 mm × 56 mm** y alimentación por **5V**, recomendando fuente de **5V/3A** sin SSD y mayor capacidad si se usa SSD.

**Pros:**

| Ventaja | Comentario |
|---|---|
| RK3566 | Alineada con la familia que se está considerando para superar el benchmark R36S/RK3326. |
| Disponible en Amazon | Reduce riesgo de compra frente a AliExpress, especialmente para una primera validación. |
| Precio razonable para validación | USD 48 no es ideal si es 1GB, pero permite probar RK3566 sin saltar a un CM + carrier caro. |
| Documentación Radxa | Existe documentación oficial, guías y ecosistema Radxa. |
| SBC completa | Facilita bring-up: no requiere diseñar carrier board ni resolver conexiones críticas desde cero. |
| I/O abundante | HDMI, USB, audio, Ethernet, GPIO, MIPI DSI/CSI y PCIe permiten muchas pruebas de V0. |
| Buena para V0 abierto | Sirve para validar OS, emulación, pantalla, input, consumo, temperatura y riesgos RK3566. |
| Modificable parcialmente | Con desoldadura simple, algunos conectores altos podrían removerse o relocalizarse si interfieren con el perfil físico. |
| Tamaño no imposible | 85 × 56 mm no es pequeño, pero puede ser compatible con una consola alrededor del tamaño R36S/Game Boy si la distribución interna lo permite. |

**Contras:**

| Riesgo | Comentario |
|---|---|
| Amazon solo muestra 1GB | 1GB queda por debajo del mínimo preferido del proyecto. Puede servir para validar, pero no como cerebro ideal de V0. |
| SBC, no compute module | No ofrece el camino limpio de reutilizar un módulo en V1 con una carrier propia. |
| Layout fijo | La ubicación de puertos, conectores y headers ya está definida. La carcasa debe adaptarse a la placa. |
| Perfil alto | Los conectores incluidos elevan el perfil físico, aproximadamente alrededor de 20 mm según observación preliminar. |
| Modificación limitada | Aunque se puedan desoldar algunos conectores, no es igual de flexible que diseñar una carrier propia. |
| Riesgo de dañar la placa | Desoldar conectores puede mejorar perfil, pero también puede dañar pads o afectar la reutilización si se hace temprano. |
| Disponibilidad 2GB/4GB incierta | Las versiones más deseables parecen depender de AliExpress o vendedores menos cómodos. |
| Tiempo de envío | AliExpress puede implicar casi un mes de espera. |
| Pick-up-and-play no validado | RK3566 mantiene riesgo en boot, sleep/fake suspend, standby drain y experiencia de pausa/reanudación. |
| Puede quedarse como placa de validación | Puede probar la familia RK3566, pero no necesariamente convertirse en base óptima para V1. |

**Lectura actual:**  
La Radxa ROCK 3C gana valor como plataforma de validación porque es relativamente barata, documentada y disponible. Su formato SBC ya no queda descartado automáticamente, porque el usuario puede considerar desoldar conectores simples o relocalizar puertos si eso ayuda al perfil físico. Sin embargo, al no ser compute module, no ofrece el camino más limpio hacia una carrier board propia futura.

El mayor problema práctico es la RAM: la opción más confiable encontrada hasta ahora es la versión de 1GB por Amazon. Para Handheld Zero V0, 1GB solo debería considerarse una compra de validación o aprendizaje, no el cerebro ideal. La versión de 2GB por AliExpress puede ser aceptable si el vendedor, envío y costo total son razonables.

**Veredicto preliminar:**  
Candidata fuerte para **V0-A / validación de plataforma RK3566**.  
Candidata media para **cerebro principal de V0** si solo se consigue en 1GB.  
Candidata más seria si se consigue en **2GB o 4GB** a precio y envío razonables.  
No es la ruta más limpia hacia V1, pero podría ganar future-proofing si se valida que los conectores altos pueden removerse/relocalizarse y que la placa cabe dentro de un form factor cercano a R36S/Game Boy.

**Decisión temporal sobre este candidato:**  
Mantener en lista. No comprar todavía hasta compararla con Orange Pi 3B, Orange Pi CM4, Radxa CM3I y Geniatech XPI-3566-ZERO.

**Qué queda por validar:**

| Tema | Pregunta |
|---|---|
| RAM | ¿Existe una versión 2GB o 4GB comprable de forma confiable? |
| Precio total | ¿Cuál es el costo real puesto en Colombia? |
| Tiempo de entrega | ¿Amazon vs AliExpress cambia significativamente el calendario? |
| Perfil físico | ¿Qué conectores realmente generan los 20 mm de altura? |
| Modificabilidad | ¿Es viable desoldar Ethernet/USB/header sin comprometer la placa? |
| Video | ¿HDMI funciona fácilmente para bring-up? ¿MIPI DSI es viable después? |
| OS | ¿Qué imágenes oficiales y comunitarias existen? |
| Emulación | ¿Hay ruta clara a RetroArch/EmulationStation/Batocera/ROCKNIX u otra solución? |
| Alimentación | ¿Se tiene o se debe comprar fuente 5V/3A confiable? |
| Recovery | ¿Existe método claro de recuperación si no bootea? |
| Batería futura | ¿Se puede alimentar desde una power board externa de forma razonable? |
| V1 | ¿Puede realmente vivir dentro de una carcasa tipo R36S/Game Boy tras remover o relocalizar conectores? |

**Cambio de enfoque — mainstream supported board:**  
La disponibilidad local y el soporte profundo de software hacen que Raspberry Pi 4 vuelva a ser una candidata seria para V0. Aunque su form factor no es ideal para una handheld final, su soporte en Batocera, documentación, comunidad, accesorios y disponibilidad local pueden reducir mucho el riesgo del proyecto. La pregunta deja de ser si la Pi 4 es una placa handheld ideal y pasa a ser si puede “zombificarse”: remover o relocalizar conectores, diseñar PCBs hijas y construir una carcasa alrededor de una board mainstream sin perder el soporte de software.

### Opción A6 — Raspberry Pi 4

**Formato:**  
SBC mainstream.

**SoC:**  
Broadcom BCM2711.

**Disponibilidad encontrada:**  
Disponible localmente en Colombia por aproximadamente 380.000 COP.

**Software:**  
Batocera tiene build específico para Raspberry Pi 4 B. Además existe soporte amplio en Raspberry Pi OS, RetroPie, Recalbox, Lakka y otros ecosistemas retro.

**Pros:**

| Ventaja | Comentario |
|---|---|
| Disponibilidad local | Reduce tiempos muertos y riesgo de compra internacional. |
| Soporte Batocera claro | Permite empezar desde una experiencia tipo consola sin portar Linux. |
| Comunidad enorme | Facilita resolver problemas de pantalla, controles, audio, energía y software. |
| Accesorios abundantes | Pantallas, fuentes, disipadores, cables y adaptadores son fáciles de conseguir. |
| Buena performance | Debe cumplir el objetivo de retro ligero, GBA, PS1 y parte de 5ta generación. |
| Reutilizable | Si no queda en la consola final, sigue siendo útil para otros proyectos. |
| Zombificable | Se pueden remover o relocalizar algunos conectores para mejorar integración. |

**Contras:**

| Riesgo | Comentario |
|---|---|
| Form factor no handheld | La placa no nació para una consola portable. |
| Perfil alto | USB/Ethernet y otros conectores pueden obligar a una carcasa más gruesa. |
| Consumo mayor | Puede complicar batería y autonomía frente a SBCs más eficientes. |
| Calor | En carcasa cerrada puede requerir disipación cuidadosa. |
| Layout fijo | No se puede reorganizar como una carrier propia. |
| HDMI interno incómodo | Puede requerir adaptadores o cables cortos para pantalla interna. |
| Zombificación tiene riesgo | Desoldar conectores puede dañar la placa si no se hace con cuidado. |

**Lectura actual:**  
La Raspberry Pi 4 no es la opción más elegante desde hardware, pero puede ser la opción más inteligente para no matar el proyecto en software, disponibilidad o soporte. Su principal reto pasa a ser mecánico: hacerla caber, bajar perfil, manejar calor y mover puertos.

**Veredicto preliminar:**  
Candidata fuerte para V0 si el proyecto acepta una estrategia de zombificación física. Puede convertirse en la plataforma base si se confirma que el tamaño, perfil, pantalla, alimentación y disipación pueden resolverse dentro de dimensiones cercanas a R36S/Game Boy.

## 11. Decisiones cerradas

### Decisión 001 — La elección del chipset no se hará en abstracto

**Fecha:**  
2026-05-23

**Decisión:**  
No se escogerá primero un chipset ideal en abstracto. La selección del chipset se hará después de identificar plataformas reales, comprables y desarrollables para el proyecto: SBCs compactos, compute modules, carrier boards comerciales, devkits o posibles handhelds donantes/de referencia con documentación suficiente.

**Razón:**  
Durante la investigación inicial se encontró que algunos chipsets atractivos por performance, eficiencia o experiencia handheld no necesariamente están disponibles en formatos útiles para un proyecto DIY. Un chipset puede ser bueno dentro de una consola comercial, pero no servir como base de desarrollo si no existe como SBC, compute module, devboard o placa documentada. Por eso, para V0 la prioridad no será escoger “el mejor chip”, sino encontrar una plataforma que permita desarrollar, probar, alimentar, integrar y eventualmente evolucionar la consola.

**Alternativas consideradas:**  
- Escoger directamente un chipset por performance, como RK3566/RK3568.
- Escoger un chipset eficiente y moderno de handhelds comerciales, como H700.
- Usar RK3326 como punto de partida por ser el benchmark de la R36S.
- Usar Raspberry Pi 4 por comunidad y facilidad de prototipado.
- Elegir una plataforma Android más potente, como T610/T618, priorizando performance sobre integración.

**Impacto en el proyecto:**  
A partir de esta decisión, la investigación no se enfocará en comparar chipsets aislados, sino en construir una lista corta de plataformas reales disponibles. Cada opción deberá evaluarse por performance, documentación, disponibilidad, tamaño físico, consumo, software, soporte de pantalla, posibilidades de integración, costo y continuidad hacia versiones futuras. Esto puede hacer que un chipset teóricamente inferior gane si es más desarrollable, o que uno más potente quede descartado si no tiene una ruta DIY viable.

**Estado:**  
Cerrada por ahora / Reversible

---

### Decisión 002 — V0 no empezará con una carrier board propia

**Fecha:**  
2026-05-23

**Decisión:**  
Para Handheld Zero V0 no se empezará diseñando una carrier board propia para un compute module. La arquitectura inicial se enfocará en dos caminos más factibles: usar un SBC compacto existente o usar un compute module con una carrier board comercial. El diseño de una carrier board propia queda relegado como una posibilidad para V1 o una etapa posterior, cuando ya estén mejor definidos el form factor, la pantalla, energía, controles, I/O, cartridge, software y restricciones reales de uso.

**Razón:**  
Diseñar una carrier board propia desde V0 puede frenar el proyecto y convertirlo prematuramente en un problema de motherboard, fabricación, bring-up y depuración de señales. V0 todavía debe probar la viabilidad del concepto, identificar problemas reales de integración y permitir experimentar con el producto antes de cerrar decisiones profundas de form factor y arquitectura. Usar una plataforma ya funcional reduce el riesgo inicial sin eliminar el aprendizaje electrónico, porque todavía se podrán diseñar PCBs propias para controles, audio, energía, cartridges, botones de sistema, I/O y otros módulos.

**Alternativas consideradas:**  
- **SBC existente:** una placa comercial compacta que ya integra SoC, RAM, PMIC, almacenamiento/boot e I/O básico.
- **Compute module con carrier board propia:** usar un módulo con SoC/RAM/PMIC resueltos y diseñar una motherboard adaptada al form factor de la consola.
- **Compute module con carrier board comercial:** usar un módulo y una carrier existente para validar plataforma, OS, emulación, pantalla, USB, audio y consumo antes de diseñar algo propio.

**Impacto en el proyecto:**  
El siguiente paso será buscar plataformas reales disponibles y clasificarlas según formato: SBC compacto, compute module con carrier comercial o handheld donor/reference. La decisión reduce el riesgo de fabricación en V0 y aumenta la probabilidad de llegar rápido a un prototipo funcional. También implica aceptar que el form factor de V0 puede estar condicionado por la placa elegida y que algunas optimizaciones físicas quedarán para V1. La arquitectura deberá elegirse pensando no solo en que funcione ahora, sino en que tenga una ruta razonable hacia una carrier propia o integración más limpia en versiones posteriores.

**Estado:**  
Cerrada por ahora / Reversible

---
