# Presentación de Tesis — Plataforma IoT Athenea

Guion de defensa para **2 presentadores (P1 y P2)**. Para cada diapositiva: **qué va en la diapositiva** y **qué decir** (con reparto de voces). El diálogo de la demo va en inglés (ver `DEMO_DIALOGO_FRONTEND.md`).

> **Marcas `[ajustar]`** = reemplazar con los datos exactos de tu tesis (objetivos, cifras, fechas).

**Estructura:** Antecedentes · Problemática · Objetivos · Metodología · Desarrollo · Resultados · Discusión · Conclusiones.

---

## Diapositiva 1 — Portada
**En la diapositiva:** Título de la tesis · Nombres de los 2 autores · Tutor · Universidad y facultad · Fecha · logo.

**Qué decir — P1:** "Buenos días. Somos [nombre] y [nombre]. Presentamos nuestra tesis: *Athenea — plataforma IoT de microservicios para la integración y monitoreo de medidores de agua*. Nos acompaña nuestro tutor [nombre]."

**Qué decir — P2:** "La presentación durará unos [X] minutos e incluye una demostración en vivo de la aplicación. Al final quedamos abiertos a sus preguntas."

---

## Diapositiva 2 — Antecedentes
**En la diapositiva:** 3–4 bullets: la medición tradicional de agua es manual; auge del IoT y LoRaWAN/LTE para telemetría; empresas de agua necesitan datos remotos; trabajo previo de M3 Verificaciones. Una imagen: medidor tradicional vs. medidor IoT.

**Qué decir — P1:** "El contexto: la lectura de medidores de agua se ha hecho históricamente de forma manual, medidor por medidor. Es costoso, lento y propenso a errores."

**Qué decir — P1:** "En paralelo, el Internet de las Cosas y protocolos de bajo consumo como LoRaWAN y LTE permiten que un medidor reporte su lectura de forma remota. Nuestra tesis parte de esa oportunidad, en el marco de la empresa M3 Verificaciones."

---

## Diapositiva 3 — Problemática
**En la diapositiva:** El problema en una frase grande + 3 dolores: (1) sin plataforma centralizada para integrar medidores multi-protocolo; (2) datos dispersos, sin consumo en tiempo real ni alertas; (3) soluciones comerciales caras y cerradas. Opcional: diagrama "antes" caótico.

**Qué decir — P2:** "El problema concreto: no existía una plataforma propia que integrara medidores de distintos fabricantes y protocolos en un solo lugar."

**Qué decir — P2:** "Esto genera tres dolores: datos dispersos y sin analítica en tiempo real; imposibilidad de detectar alarmas como fugas o batería baja; y dependencia de soluciones comerciales costosas y cerradas. La pregunta que guía la tesis: *¿cómo diseñar una plataforma escalable que integre estos medidores y entregue su información de forma útil?*"

---

## Diapositiva 4 — Objetivos
**En la diapositiva:** **Objetivo general** (1 frase) + **Objetivos específicos** (3–4 bullets). 

- General: *Desarrollar una plataforma web de microservicios para registrar, integrar y monitorear medidores IoT de agua.* `[ajustar]`
- Específicos: `[ajustar]` (1) Diseñar una arquitectura de microservicios; (2) Implementar adaptadores para LoRaWAN y LTE; (3) Construir un frontend para gestión de empresas, usuarios y medidores; (4) Visualizar consumos y alertas en tiempo real.

**Qué decir — P1:** "Nuestro objetivo general fue *desarrollar una plataforma web de microservicios para registrar, integrar y monitorear medidores IoT de agua*."

**Qué decir — P2:** "Y lo desglosamos en cuatro objetivos específicos: diseñar la arquitectura de microservicios; implementar los adaptadores de protocolo LoRaWAN y LTE; construir el frontend de gestión; y visualizar consumos y alarmas en tiempo real."

---

## Diapositiva 5 — Metodología
**En la diapositiva:** Metodología de desarrollo (p.ej. **iterativa incremental / Scrum** `[ajustar]`) con sus fases en línea de tiempo: Análisis → Diseño → Implementación → Pruebas → Despliegue. Stack en íconos: Angular, Spring Boot, PostgreSQL, Docker, Railway.

**Qué decir — P1:** "Trabajamos con una metodología [iterativa incremental / Scrum] `[ajustar]`, en ciclos cortos: análisis, diseño, implementación, pruebas y despliegue, iterando sobre cada microservicio."

**Qué decir — P2:** "El stack tecnológico: Angular 17 en el frontend; Java con Spring Boot en los microservicios; PostgreSQL como base de datos; y Docker con despliegue en Railway. Cada servicio se desarrolla, prueba y despliega de forma independiente."

---

## Diapositiva 6 — Desarrollo (Arquitectura)
**En la diapositiva:** **Diagrama de arquitectura de microservicios.** Frontend Angular a la izquierda; en el centro los servicios: user, company, userCompany, gateway, meters, consumption, messages; abajo los adaptadores lorawan y lte; a la derecha PostgreSQL. Flechas de flujo de un mensaje.

**Qué decir — P1:** "Esta es la arquitectura. El frontend Angular consume nueve microservicios independientes: gestión de usuarios, empresas, relaciones usuario-empresa, gateways, medidores, consumos y mensajes."

**Qué decir — P2:** "Y dos adaptadores de protocolo, sin base de datos, que actúan como puentes: uno escucha LoRaWAN por WebSocket, y otro escucha LTE por UDP. Cuando llega un mensaje del medidor, el adaptador lo decodifica y lo distribuye a los servicios de mensajes, medidores y consumos. Todo persiste en PostgreSQL."

---

## Diapositiva 7 — Desarrollo (Flujo de un mensaje) *(opcional, si hay tiempo)*
**En la diapositiva:** Diagrama de secuencia: Medidor → Adaptador (decodifica payload por fabricante: BOVE/YOUNIO) → busca el medidor por Dev EUI → guarda mensaje decodificado, actualiza última comunicación y registra el consumo.

**Qué decir — P1:** "En detalle: el medidor emite una trama en hexadecimal. El adaptador la decodifica según el fabricante, identifica el medidor por su Dev EUI, y con eso guarda el mensaje decodificado, actualiza la última comunicación y calcula el consumo acumulado por hora, día, mes y año."

---

## Diapositiva 8 — Resultados (Demo en vivo)
**En la diapositiva:** Título "Demostración en vivo" + captura de respaldo del frontend por si falla la demo. 

**Qué decir — P2:** "Los resultados los mostramos en vivo. Vamos a recorrer el frontend completo en tres minutos."

> **Aquí corren la demo del frontend.** Sigan el guion bilingüe de `DEMO_DIALOGO_FRONTEND.md` (Login → empresa → usuario → medidor → detalle y consumo). El diálogo está en inglés con su traducción.

**Plan B (si la demo falla):** tener capturas o un video corto grabado del mismo flujo.

---

## Diapositiva 9 — Resultados (Logros medibles)
**En la diapositiva:** 4–5 métricas/logros en tarjetas: 
- Plataforma funcional con 9 microservicios + 2 adaptadores desplegados.
- Registro de medidores multi-protocolo (LoRaWAN, LTE, GPRS, NB-IoT, 4G).
- Ingesta y decodificación de mensajes en tiempo real.
- Consumos agregados (hora/día/mes/año) y alarmas (fuga, batería, etc.).
- `[ajustar: nº de medidores probados, nº de mensajes procesados, tiempo de respuesta]`.

**Qué decir — P1:** "Como resultados concretos: logramos una plataforma funcional con nueve microservicios y dos adaptadores desplegados; el registro de medidores en cinco protocolos; y la ingesta y decodificación de mensajes en tiempo real."

**Qué decir — P2:** "Además, la plataforma agrega el consumo por hora, día, mes y año, y detecta alarmas como fugas o batería baja. En pruebas procesamos `[ajustar]` mensajes de `[ajustar]` medidores."

---

## Diapositiva 10 — Discusión
**En la diapositiva:** 3 bullets de análisis crítico: ventajas (escalabilidad de microservicios, independencia de protocolo), limitaciones (`[ajustar]`, p.ej. cobertura LoRaWAN, dependencia de la nube Loriot), comparación con soluciones comerciales.

**Qué decir — P1:** "En la discusión: la arquitectura de microservicios nos dio escalabilidad e independencia — cada protocolo se integra sin tocar el resto del sistema. Frente a soluciones comerciales, la nuestra es propia, abierta y adaptable."

**Qué decir — P2:** "Como limitaciones honestas, identificamos `[ajustar]`: por ejemplo, la cobertura depende de la red LoRaWAN disponible y de la nube del operador. Son puntos que dejamos planteados para trabajo futuro."

---

## Diapositiva 11 — Conclusiones
**En la diapositiva:** 3–4 conclusiones alineadas 1:1 con los objetivos + 1 línea de trabajo futuro.

**Qué decir — P2:** "Concluimos que cumplimos los objetivos: diseñamos e implementamos una plataforma de microservicios que integra medidores multi-protocolo y entrega su información de forma útil, con consumo y alarmas en tiempo real."

**Qué decir — P1:** "Como trabajo futuro proponemos `[ajustar]`: por ejemplo, analítica predictiva de fugas, app móvil y soporte de más fabricantes. Con esto demostramos que una solución propia, escalable y de bajo costo es viable. Muchas gracias."

---

## Diapositiva 12 — Agradecimientos / Preguntas
**En la diapositiva:** "Gracias" + datos de contacto + "¿Preguntas?".

**Qué decir — P1/P2 (juntos o alternando):** "Gracias por su atención. Quedamos atentos a sus preguntas."

---

### Consejos de exposición
- **Reparto:** P1 abre (portada, objetivos, arquitectura) y P2 cierra (problemática, stack, resultados, conclusiones) — alternen para mantener el ritmo. Ajusten según con qué parte cada uno se sienta más cómodo.
- **Tiempo:** la demo de 3 min es el corazón; no la sacrifiquen. Recorten la teoría antes que la demo.
- **Ensayen la transición** entre presentadores en voz alta — es donde más se traba una defensa a dúo.
- **Plan B de la demo:** tengan video/capturas por si el frontend no levanta.
