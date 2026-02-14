# Dokumentacija Projekta - Mountain Tours System

## Osnovne Informacije

**Predmet:** Informacioni sistemi 2024/2025
**Tema:** Planinarske ture
**Članovi tima:** Uroš Dimitrijević, Pavle Vlajković

---

## Pregled Projekta

Projekat predstavlja sveobuhvatan informacioni sistem za organizovanje, rezervaciju i upravljanje planinarskim turama. Sistem omogućava korisnicima da pretražuju i rezervišu ture, vodičima da upravljaju svojom dostupnošću i vode ture, a turističkim operaterima da kreiraju i upravljaju ponudama tura.

---

## Sadržaj Projekta

### Use Case Dijagrami
Kreirani UML dijagrami slučajeva korišćenja koji pokrivaju sve glavne funkcionalnosti sistema:

#### Discovery (Pretraga)
- Pretraga tura po lokaciji, datumu, težini, ceni
- Pregled detalja ture
- Pregled profila vodiča i turističkih operatera
- Čitanje recenzija i ocena

#### Account & Registration (Nalozi i Registracija)
- Registracija korisnika
- Autentifikacija
- Odobravanje registracije vodiča (Admin)
- Odobravanje registracije turističkih operatera (Admin)
- Upravljanje profilom
- Čuvanje omiljenih tura/vodiča

#### Booking (Rezervacije)
- Zahtev za privatnu turu
- Rezervacija grupne ture
- Pregled mojih rezervacija
- Prekazivanje rezervacije
- Otkazivanje rezervacije
- Odgovor na zahtev za turu (Vodič)
- Upravljanje listom učesnika (Vodič)

#### Management (Upravljanje Turama)
- Pregled svih tura (Vodič)
- Otkazivanje ture
- Upravljanje kalendarom dostupnosti
- Odgovor na dodelu ture
- Kreiranje grupne ture (Operater)
- Dodela vodiča turi
- Postavljanje rasporeda i kapaciteta ture

#### Pre-Tour (Pre-ture Aktivnosti)
- Praćenje lokacije u realnom vremenu
- Komunikacija sa klijentima
- Pregled kontrolne liste za turu
- Deljenje lokacije uživo (Vodič)
- Ažuriranje statusa ture
- Upload fotografija sa ture

#### Post-Tour (Post-ture Aktivnosti)
- Prijavljivanje problema
- Ocenjivanje i recenzija vodiča
- Ocenjivanje i recenzija ture
- Objavljivanje ažuriranja ture (Operater)
- Verifikacija akreditacija vodiča
- Pregled prihoda i statistike
- Nadgledanje bezbednosti (Admin)
- Rešavanje sporova (Admin)

### Class Dijagram
- Kreiran detaljni dijagram klasa koji modelira domenske entitete sistema
- Definisane klase, atributi, metode i relacije između entiteta

### Sequence Dijagrami
Kreirani sekvencijalni dijagrami za ključne procese:

1. **Registration Approval** - Proces odobravanja registracije vodiča/operatera
2. **Tour Booking** - Proces rezervacije ture
3. **Tour Management and Guide Assignment** - Upravljanje turama i dodela vodiča
4. **Post-Tour** - Post-ture aktivnosti (recenzije, izveštaji)

### DFD Dijagrami
- **DFD Level 0** - Kontekstni dijagram sistema
- **DFD Level 1** - Detaljniji prikaz tokova podataka između procesa

### BPMN Dijagrami
Kreirani BPMN dijagrami poslovnih procesa:

1. **User Registration** - Proces registracije korisnika
2. **Tour Discovery** - Proces pretrage i otkrivanja tura
3. **Tour Creation** - Proces kreiranja nove ture

### C4 Arhitektura
Implementirana C4 arhitektura korišćenjem LikeC4 alata:

#### Akteri Sistema
- **User** - Registrovani korisnik koji pretražuje i rezerviše ture
- **Guide** - Sertifikovani vodič koji vodi ture
- **Tour Operator** - Poslovni entitet koji kreira i upravlja turama
- **Administrator** - Sistemski administrator

#### Eksterni Sistemi
- **Stripe** - Procesiranje plaćanja
- **Email Provider** (SendGrid/Mailgun) - Slanje emailova
- **Maps API** - Geolokacijske usluge

#### Mikroservisna Arhitektura
Sistem je dizajniran kao mikroservisna arhitektura sa sledećim servisima:

1. **Web Application** (React/TypeScript)
   - SPA aplikacija za sve tipove korisnika

2. **API Gateway** (YARP/.NET)
   - Jedinstvena tačka ulaza
   - Rutiranje zahteva
   - Rate limiting

3. **IAM Service** (.NET)
   - Autentifikacija i autorizacija
   - Registracija korisnika
   - Upravljanje profilima
   - Komponente: Auth Controller, User Controller, Role Manager

4. **Tours Service** (.NET/CQRS/MediatR)
   - Kreiranje i upravljanje turama
   - Pretraga tura
   - Dodela vodiča
   - Komponente: Tour Commands, Tour Queries, Guide Assignment, Availability Manager

5. **Booking Service** (.NET)
   - Rezervacije tura
   - Upravljanje dostupnošću
   - Integracija sa Stripe
   - Komponente: Booking Commands, Booking Queries, Availability Checker, Payment Processor

6. **Review Service** (.NET)
   - Recenzije i ocene
   - Verifikacija učešća na turi
   - Komponente: Review Commands, Review Queries, Completion Verifier

7. **Notification Service** (.NET/SignalR)
   - Real-time notifikacije
   - Event-driven komunikacija
   - Praćenje lokacije uživo
   - Komponente: SignalR Hub, Event Consumer, Event Store, Email Sender, Location Broadcaster

#### Baze Podataka (PostgreSQL)
- IAM Database - Korisnici, role, kredencijali
- Tours Database - Ture, lokacije, rasporedi
- Booking Database - Rezervacije, statusi
- Review Database - Recenzije, ocene
- Notification Database - Istorija događaja, logovi

#### Message Broker
- **RabbitMQ** - Asinhrona komunikacija između servisa

### UI Prototip

Kreirani vizuelni prototipovi korisničkog interfejsa:

1. **Landing Page** - Početna stranica aplikacije
2. **Login Screen** - Stranica za prijavu
3. **Register Screen** - Stranica za registraciju
4. **Profile Page** - Korisnički profil
5. **Tours Page** - Pregled tura
6. **Selected Tour** - Detalji odabrane ture
7. **Create Tour Dialog** - Dijalog za kreiranje ture

### Demo Snimci

Kreirani demo video snimci aplikacije:

1. **Register-Login-demo.mp4** - Demonstracija procesa registracije i prijave
2. **In-app-demo.mp4** - Demonstracija funkcionalnosti unutar aplikacije

---

## Struktura Projekta

```
IS_projekat/
├── README.md
├── DOKUMENTACIJA_PROJEKTA.md
├── demo/
│   ├── In-app-demo.mp4
│   └── Register-Login-demo.mp4
├── ui-prototype/
│   ├── landing-page/
│   ├── login-page/
│   ├── profile-page/
│   └── tours-page/
└── diagrams/
    ├── uml/
    │   ├── case-diagrams/
    │   │   ├── account_registration/
    │   │   ├── booking/
    │   │   ├── discovery/
    │   │   ├── management/
    │   │   ├── post-tour/
    │   │   └── pre-tour/
    │   ├── class-diagrams/
    │   └── sequence-diagrams/
    ├── dfd/
    ├── bpmn/
    │   ├── user-registration/
    │   ├── tour-discovery/
    │   └── create-tour/
    └── c4-architecture/
```

---

## Korišćene Tehnologije i Alati

### Modelovanje
- **Visual Paradigm** - UML dijagrami, BPMN dijagrami
- **LikeC4** - C4 arhitekturni dijagrami

### Planirane Tehnologije za Implementaciju
- **Frontend:** React, TypeScript
- **Backend:** .NET, CQRS, MediatR
- **API Gateway:** YARP
- **Real-time:** SignalR
- **Baza podataka:** PostgreSQL
- **Message Broker:** RabbitMQ
- **Plaćanja:** Stripe
- **Email:** SendGrid/Mailgun
- **Mape:** Google Maps API

---

## Doprinosi po Članovima Tima

Bazirano na git istoriji:

**Pavle Vlajković:**
- UI prototip dizajn
- Demo video snimci
- BPMN dijagrami

**Uroš Dimitrijević:**
- Use Case dijagrami i dokumentacija
- Sequence dijagrami
- Class dijagram
- DFD dijagrami
- C4 arhitektura

---

## Zaključak

Projekat Mountain Tours System predstavlja kompletan informacioni sistem za organizovanje planinarskih tura. Kroz sistematičan pristup modelovanju, definisani su svi aspekti sistema - od korisničkih slučajeva, preko strukture podataka, do tehničke arhitekture. Mikroservisna arhitektura omogućava skalabilnost i održivost sistema, dok je event-driven pristup obezbeđuje efikasnu komunikaciju između komponenti i podršku za real-time funkcionalnosti poput praćenja lokacije vodiča.
