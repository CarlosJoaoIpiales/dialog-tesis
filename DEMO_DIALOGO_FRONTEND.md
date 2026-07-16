# Athenea — Frontend Demo Script (3 minutes)

**Live demo of the Angular frontend only.** Two presenters: **P1** and **P2**.
Flow: Login → Company → User → Meter → Detail & Consumption.

Each block shows the **on-screen action**, the **English line** to say, and the **Spanish translation** (what you are saying).

---

## 0 · Intro — P1 (~20s)
*On screen: Athenea landing / login page.*

**EN:** "Good morning. Athenea is a web platform for managing IoT water meters. In the next three minutes we'll walk through the complete frontend flow — from creating a company and a user, to registering a meter and viewing its data in real time."

**ES (traducción):** *"Buenos días. Athenea es una plataforma web para gestionar medidores de agua IoT. En los próximos tres minutos recorreremos el flujo completo del frontend — desde crear una empresa y un usuario, hasta registrar un medidor y ver sus datos en tiempo real."*

---

## 1 · Login — P1 (~15s)
*On screen: type email + password, sign in, dashboard loads.*

**EN:** "First we sign in as administrators. Authentication is handled with JSON Web Tokens, so every request to the backend is secured."

**ES:** *"Primero iniciamos sesión como administradores. La autenticación usa JSON Web Tokens, así que cada petición al backend viaja segura."*

---

## 2 · Register a company — P2 (~30s)
*On screen: Accounts → Companies → Register. Fill name, RUC, nickname. Save.*

**EN:** "Athenea is multi-tenant. Under Accounts and Companies, we register a new company with its name, tax ID and nickname. This company will own the users and meters we create next."

**ES:** *"Athenea es multi-empresa. En Cuentas y Empresas, registramos una nueva empresa con su nombre, RUC y alias. Esta empresa será dueña de los usuarios y medidores que creemos a continuación."*

---

## 3 · Register a user — P1 (~30s)
*On screen: Accounts → Users → Register. Fill name, email, phone, role; assign the company. Save.*

**EN:** "Now we create a user. We enter their name, email, phone and role, and link them to the company we just created. From now on, that user can log in and manage only that company's devices."

**ES:** *"Ahora creamos un usuario. Ingresamos su nombre, correo, teléfono y rol, y lo vinculamos a la empresa que acabamos de crear. Desde ahora, ese usuario puede iniciar sesión y gestionar solo los dispositivos de esa empresa."*

---

## 4 · Register a meter — P2 (~45s)
*On screen: Devices → Meters → Register. Select communication type = LoRaWAN. Form reveals LoRaWAN fields. Enter Dev EUI, region, class. Place marker on the map. Assign company. Save.*

**EN:** "This is the core feature: registering a meter. We choose the communication type — LoRaWAN — and the form adapts, asking for the LoRaWAN identifiers: the Dev EUI, the region and the class. We locate the meter on the map, assign it to our company, and save. The Dev EUI is the unique key the platform uses to match every incoming message to this meter."

**ES:** *"Esta es la funcionalidad central: registrar un medidor. Elegimos el tipo de comunicación — LoRaWAN — y el formulario se adapta, pidiendo los identificadores LoRaWAN: el Dev EUI, la región y la clase. Ubicamos el medidor en el mapa, lo asignamos a nuestra empresa y guardamos. El Dev EUI es la clave única que la plataforma usa para asociar cada mensaje entrante a este medidor."*

---

## 5 · Meter detail & consumption — P1 (~40s)
*On screen: open the meter's detail. Show communication tab (Dev EUI, region). Switch to the consumption report tab: messages table + hourly/daily/monthly/yearly charts.*

**EN:** "Finally, we open the meter's detail. Here we see its communication settings — the Dev EUI we just registered — the decoded messages arriving from the device, and the consumption report: hourly, daily, monthly and yearly charts. Everything is retrieved by the meter's unique key."

**ES:** *"Por último, abrimos el detalle del medidor. Aquí vemos su configuración de comunicación — el Dev EUI que acabamos de registrar — los mensajes decodificados que llegan del dispositivo, y el informe de consumo: gráficas por hora, día, mes y año. Todo se obtiene por la clave única del medidor."*

---

## 6 · Close — P2 (~10s)
*On screen: consumption chart with data.*

**EN:** "In three minutes we went from an empty platform to a fully registered meter reporting real data. Thank you."

**ES:** *"En tres minutos pasamos de una plataforma vacía a un medidor completamente registrado reportando datos reales. Gracias."*

---

### Timing cheat-sheet
| Block | Speaker | Time |
|-------|---------|------|
| Intro | P1 | 0:20 |
| Login | P1 | 0:15 |
| Company | P2 | 0:30 |
| User | P1 | 0:30 |
| Meter | P2 | 0:45 |
| Detail & consumption | P1 | 0:40 |
| Close | P2 | 0:10 |
| **Total** | | **~3:10** |

**Tip:** rehearse once with a timer. If you run long, trim the Login and Close lines first.
