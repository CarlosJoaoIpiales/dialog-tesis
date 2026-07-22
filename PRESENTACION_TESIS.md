# Presentación de Tesis — Plataforma IoT Athenea

Guion de defensa para **2 presentadores (P1 y P2)**. Duración objetivo: **15 minutos** de exposición (más Q&A). Para cada diapositiva: **tiempo asignado**, **qué va en la diapositiva** y **qué decir** (con reparto de voces). El diálogo de la demo va en inglés (ver `DEMO_DIALOGO_FRONTEND.md`).

> **Marcas `[ajustar]`** = reemplazar con los datos exactos de tu tesis (objetivos, cifras, fechas).

**Estructura:** Antecedentes · Problemática · Objetivos · Metodología · Desarrollo · Resultados · Discusión · Conclusiones.

**Presupuesto de tiempo (15:00):** la demo de 3 min es el corazón; el resto de la teoría se reparte en ~12 min. Ver la tabla de tiempos al final.

---

## Diapositiva 1 — Portada · ⏱ 0:40
**En la diapositiva:** Título de la tesis · Nombres de los 2 autores · Tutor · Universidad y facultad · Fecha · logo.

**Qué decir — P1:** "Buenos días. Somos [nombre] y [nombre]. Presentamos nuestra tesis: *Athenea — plataforma IoT de microservicios para la integración y monitoreo de medidores de agua*. Nos acompaña nuestro tutor [nombre]."

**Qué decir — P2:** "La presentación incluye una demostración en vivo de la aplicación. Al final quedamos abiertos a sus preguntas."

---

## Diapositiva 2 — Antecedentes · ⏱ 1:15
**En la diapositiva:** 3–4 bullets: la medición tradicional de agua es manual; auge del IoT y LoRaWAN para telemetría; empresas de agua necesitan datos remotos; trabajo previo de M3 Verificaciones. Una imagen: medidor tradicional vs. medidor IoT.

**Qué decir — P1:** "El contexto: la lectura de medidores de agua se ha hecho históricamente de forma manual, medidor por medidor. Un operario recorre cada domicilio, anota la lectura y la carga después. Es costoso, lento y propenso a errores de transcripción."

**Qué decir — P1:** "En paralelo, el Internet de las Cosas y protocolos de bajo consumo como LoRaWAN permiten que un medidor reporte su lectura de forma remota, con años de autonomía de batería. Esa tecnología abre la puerta a la telemetría de agua a gran escala."

**Qué decir — P2:** "Nuestra tesis parte de esa oportunidad, en el marco de la empresa M3 Verificaciones, que ya trabajaba con medición y verificación de medidores y necesitaba dar el salto a una plataforma digital propia."

---

## Diapositiva 3 — Problemática · ⏱ 1:15
**En la diapositiva:** El problema en una frase grande + 3 dolores: (1) sin plataforma centralizada para integrar medidores LoRaWAN de distintos fabricantes; (2) datos dispersos, sin consumo en tiempo real ni alertas; (3) soluciones comerciales caras y cerradas. Opcional: diagrama "antes" caótico.

**Qué decir — P2:** "El problema concreto: no existía una plataforma propia que integrara medidores de distintos fabricantes y protocolos en un solo lugar. Cada dispositivo hablaba su propio idioma y sus datos quedaban aislados."

**Qué decir — P2:** "Esto genera tres dolores. Primero, datos dispersos y sin analítica en tiempo real. Segundo, imposibilidad de detectar alarmas como fugas o batería baja a tiempo. Y tercero, dependencia de soluciones comerciales costosas y cerradas, que no se adaptan al negocio."

**Qué decir — P1:** "La pregunta que guía toda la tesis es entonces: *¿cómo diseñar una plataforma escalable que integre estos medidores LoRaWAN y entregue su información de forma útil y en tiempo real?*"

---

## Diapositiva 4 — Objetivos · ⏱ 1:15
**En la diapositiva:** **Objetivo general** (1 frase) + **Objetivos específicos** (3–4 bullets).

- General: *Desarrollar una plataforma web de microservicios para registrar, integrar y monitorear medidores IoT de agua.* `[ajustar]`
- Específicos: `[ajustar]` (1) Diseñar una arquitectura de microservicios; (2) Implementar el adaptador para LoRaWAN; (3) Construir un frontend para gestión de empresas, usuarios y medidores; (4) Visualizar consumos y alertas en tiempo real.

**Qué decir — P1:** "Nuestro objetivo general fue *desarrollar una plataforma web de microservicios para registrar, integrar y monitorear medidores IoT de agua*."

**Qué decir — P2:** "Y lo desglosamos en cuatro objetivos específicos. Uno: diseñar una arquitectura de microservicios escalable. Dos: implementar el adaptador de protocolo LoRaWAN. Tres: construir el frontend de gestión de empresas, usuarios y medidores. Y cuatro: visualizar consumos y alarmas en tiempo real."

**Qué decir — P1:** "Cada conclusión que veremos al final responde uno a uno a estos objetivos."

---

## Diapositiva 5 — Metodología · ⏱ 1:15
**En la diapositiva:** Metodología de desarrollo (p.ej. **iterativa incremental / Scrum** `[ajustar]`) con sus fases en línea de tiempo: Análisis → Diseño → Implementación → Pruebas → Despliegue. Stack en íconos: Angular, Spring Boot, PostgreSQL, Docker, Railway.

**Qué decir — P1:** "Trabajamos con una metodología [iterativa incremental / Scrum] `[ajustar]`, en ciclos cortos: análisis, diseño, implementación, pruebas y despliegue. Iteramos microservicio por microservicio, lo que nos permitió entregar valor de forma temprana y corregir sobre la marcha."

**Qué decir — P2:** "El stack tecnológico: Angular 17 en el frontend; Java 21 con Spring Boot en los microservicios; PostgreSQL como base de datos; y Docker con despliegue continuo en Railway. Cada servicio se desarrolla, prueba y despliega de forma independiente, sin frenar al resto."

---

## Diapositiva 6 — Desarrollo (Arquitectura) · ⏱ 1:45
**En la diapositiva:** **Diagrama de arquitectura de microservicios.** Frontend Angular a la izquierda; en el centro los servicios: user, company, userCompany, gateway, meters, consumption, messages; abajo el adaptador lorawan; a la derecha PostgreSQL. Flechas de flujo de un mensaje.

**Qué decir — P1:** "Esta es la arquitectura, el corazón técnico de la tesis. El frontend Angular consume nueve microservicios independientes: gestión de usuarios, empresas, relaciones usuario-empresa, gateways, medidores, consumos y mensajes. Cada uno tiene su propia responsabilidad y su propia base de datos lógica."

**Qué decir — P2:** "A esos nueve se suma un adaptador de protocolo, sin base de datos, que actúa como puente: escucha LoRaWAN por WebSocket contra la nube del operador y traduce lo que llega del dispositivo."

**Qué decir — P2:** "Cuando llega un mensaje del medidor, el adaptador lo decodifica y lo distribuye a los servicios de mensajes, medidores y consumos. Todo persiste en PostgreSQL. La ventaja: si mañana aparece un protocolo nuevo, sumamos un adaptador sin tocar el resto del sistema."

---

## Diapositiva 7 — Desarrollo (Flujo de un mensaje) · ⏱ 1:05
**En la diapositiva:** Diagrama de secuencia: Medidor → Adaptador (decodifica payload por fabricante: BOVE/YOUNIO) → busca el medidor por Dev EUI → guarda mensaje decodificado, actualiza última comunicación y registra el consumo.

**Qué decir — P1:** "Veamos en detalle qué pasa con un mensaje. El medidor emite una trama en hexadecimal. El adaptador la decodifica según el fabricante — soportamos BOVE y YOUNIO — e identifica el medidor por su Dev EUI, que es su clave única."

**Qué decir — P2:** "Con esa identificación, la plataforma guarda el mensaje decodificado, actualiza la última comunicación del dispositivo y calcula el consumo acumulado por hora, día, mes y año. Todo esto ocurre en tiempo real, sin intervención manual."

---

## Diapositiva 8 — Resultados (Demo en vivo) · ⏱ 3:00
**En la diapositiva:** Título "Demostración en vivo" + captura de respaldo del frontend por si falla la demo.

**Qué decir — P2:** "Los resultados los mostramos en vivo. Vamos a recorrer el frontend completo en tres minutos: desde crear una empresa y un usuario, hasta registrar un medidor y ver sus datos reales."

> **Aquí corren la demo del frontend.** Sigan el guion bilingüe de `DEMO_DIALOGO_FRONTEND.md` (Login → empresa → usuario → medidor → detalle y consumo). El diálogo está en inglés con su traducción. Duración: ~3:10 según la hoja de tiempos de ese archivo.

**Plan B (si la demo falla):** tener capturas o un video corto grabado del mismo flujo.

---

## Diapositiva 9 — Resultados (Logros medibles) · ⏱ 1:15
**En la diapositiva:** 4–5 métricas/logros en tarjetas:
- Plataforma funcional con 9 microservicios + adaptador LoRaWAN desplegados.
- Registro e integración de medidores LoRaWAN de distintos fabricantes (BOVE, YOUNIO).
- Ingesta y decodificación de mensajes en tiempo real.
- Consumos agregados (hora/día/mes/año) y alarmas (fuga, batería, etc.).
- `[ajustar: nº de medidores probados, nº de mensajes procesados, tiempo de respuesta]`.

**Qué decir — P1:** "Como resultados concretos: logramos una plataforma funcional con nueve microservicios y el adaptador LoRaWAN desplegados en producción; el registro e integración de medidores LoRaWAN de distintos fabricantes; y la ingesta y decodificación de mensajes en tiempo real, como acaban de ver."

**Qué decir — P2:** "Además, la plataforma agrega el consumo por hora, día, mes y año, y detecta alarmas como fugas o batería baja. En nuestras pruebas procesamos `[ajustar]` mensajes provenientes de `[ajustar]` medidores, con un tiempo de respuesta de `[ajustar]`."

---

## Diapositiva 10 — Discusión · ⏱ 1:00
**En la diapositiva:** 3 bullets de análisis crítico: ventajas (escalabilidad de microservicios, independencia de protocolo), limitaciones (`[ajustar]`, p.ej. cobertura LoRaWAN, dependencia de la nube Loriot), comparación con soluciones comerciales.

**Qué decir — P1:** "En la discusión: la arquitectura de microservicios nos dio escalabilidad e independencia — cada protocolo se integra sin tocar el resto del sistema. Frente a soluciones comerciales, la nuestra es propia, abierta y adaptable al negocio."

**Qué decir — P2:** "Como limitaciones honestas identificamos `[ajustar]`: por ejemplo, la cobertura depende de la red LoRaWAN disponible y de la nube del operador. Son puntos que dejamos planteados para trabajo futuro."

---

## Diapositiva 11 — Conclusiones · ⏱ 1:00
**En la diapositiva:** 3–4 conclusiones alineadas 1:1 con los objetivos + 1 línea de trabajo futuro.

**Qué decir — P2:** "Concluimos que cumplimos los cuatro objetivos: diseñamos e implementamos una plataforma de microservicios que integra medidores LoRaWAN y entrega su información de forma útil, con consumo y alarmas en tiempo real."

**Qué decir — P1:** "Como trabajo futuro proponemos `[ajustar]`: por ejemplo, analítica predictiva de fugas, app móvil y soporte de más fabricantes. Con esto demostramos que una solución propia, escalable y de bajo costo es viable. Muchas gracias."

---

## Diapositiva 12 — Agradecimientos / Preguntas · ⏱ 0:20
**En la diapositiva:** "Gracias" + datos de contacto + "¿Preguntas?".

**Qué decir — P1/P2 (juntos o alternando):** "Gracias por su atención. Quedamos atentos a sus preguntas."

---

## Tabla de tiempos (15:05)

| # | Diapositiva | Voz principal | Tiempo |
|---|-------------|---------------|--------|
| 1 | Portada | P1 / P2 | 0:40 |
| 2 | Antecedentes | P1 / P2 | 1:15 |
| 3 | Problemática | P2 / P1 | 1:15 |
| 4 | Objetivos | P1 / P2 | 1:15 |
| 5 | Metodología | P1 / P2 | 1:15 |
| 6 | Arquitectura | P1 / P2 | 1:45 |
| 7 | Flujo de un mensaje | P1 / P2 | 1:05 |
| 8 | Demo en vivo | P2 (+ guion demo) | 3:00 |
| 9 | Logros medibles | P1 / P2 | 1:15 |
| 10 | Discusión | P1 / P2 | 1:00 |
| 11 | Conclusiones | P2 / P1 | 1:00 |
| 12 | Preguntas | P1 / P2 | 0:20 |
| | **Total exposición** | | **~15:05** |

> Q&A va **aparte** del cronómetro de 15 min. Si el tribunal fija un tope estricto, recorten primero los segundos "extra" de las diapositivas 6 y 9, nunca la demo.

---

### Consejos de exposición
- **Reparto:** P1 abre (portada, antecedentes, objetivos, arquitectura, flujo) y P2 refuerza (problemática, metodología, demo, logros, conclusiones) — alternen para mantener el ritmo. Ajusten según con qué parte cada uno se sienta más cómodo.
- **Tiempo:** ensayen con cronómetro apuntando a 15:00. La demo de 3 min es el corazón; no la sacrifiquen. Recorten la teoría antes que la demo.
- **Ensayen la transición** entre presentadores en voz alta — es donde más se traba una defensa a dúo.
- **Plan B de la demo:** tengan video/capturas por si el frontend no levanta.
