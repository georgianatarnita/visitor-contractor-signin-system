Sistem de Înregistrare Vizitatori/Contractori - SSATR IA 2025

Student: [Tarniță Georgiana-Beatroce]
Scenariu: [Visitors/Contractors sign in system]

Prezentarea Proiectului

Sistemul de Înregistrare Vizitatori/Contractori oferă gestionarea accesului în clădiri într-un mod sigur și eficient. Permite pre-înregistrarea vizitatorilor, monitorizarea în timp real a prezenței acestora și notificări automate către gazde, îmbunătățind atât securitatea, cât și experiența vizitatorilor.

Funcționalități Cheie

Pre-înregistrare: Vizitatorii pot fi înregistrați anticipat și primesc coduri QR valabile temporar.

Acces prin cod QR: Scanare securizată pentru intrare și ieșire.

Monitorizare în timp real: Urmărirea vizitatorilor activi și a numărului de persoane din clădire.

Notificări și alerte: Gazdele primesc notificări la sosirea/plecarea vizitatorilor; sistemul suportă apeluri de urgență.

Tehnologii Utilizate
Backend

Java 17, Spring Boot 3.2

RabbitMQ pentru mesagerie

Baza de date PostgreSQL

Frontend

Thymeleaf, HTML/CSS/JavaScript

Bootstrap 5 pentru design responsive

Infrastructură

Docker, Docker Compose

Maven pentru build și gestionarea dependențelor

Alte Biblioteci/Instrumente

Lombok pentru reducerea codului repetitiv

Spring Security pentru autentificare și autorizare

JUnit & Mockito pentru testare

Arhitectura Sistemului
Arhitectura Generală

Sistemul utilizează o arhitectură modulară ce combină frontend, backend, mesagerie și baza de date. Scanările codurilor QR de către vizitatori sunt procesate în timp real, iar notificările sunt trimise gazdelor și dashboard-urilor administrative.

Componente Principale:

Interfață Web: Afișează dashboard-uri, formulare de înregistrare și informații despre vizitatori.

Backend API: Gestionează logica de business, generarea codurilor QR și mesageria.

Broker de Mesaje (RabbitMQ): Asigură actualizări și notificări în timp real către serviciile relevante.

Baza de Date: Stochează profilele vizitatorilor, logurile de acces și informațiile gazdelor.

Diagramă Arhitectură:
(Se introduce o imagine a diagramei care arată fluxul între frontend, backend, RabbitMQ și baza de date)

Fluxuri de Date
Flux Intrare Vizitator

Gazda pre-înregistrează vizitatorul → sistemul generează cod QR

Vizitatorul primește codul QR prin email/SMS

Vizitatorul scanează codul QR la poarta de acces → cererea ajunge la backend

Backend publică evenimentul în RabbitMQ

Consumatorul actualizează baza de date și trimite notificarea gazdei

Flux Ieșire Vizitator

Vizitatorul scanează codul QR la ieșire

Backend validează și actualizează ora de ieșire

Dashboard-ul și baza de date sunt actualizate în timp real

Simulări și Simplificări

Scanarea codului QR simulată prin introducerea manuală a codului în interfața web

Datele despre locație ale vizitatorilor sunt considerate doar punctele de intrare/ieșire

Aplicația mobilă înlocuită cu interfață web responsive

Capturi de Ecran
Dashboard Principal



Înregistrare Vizitator



Monitorizare Vizitatori Activi



Schema Bazei de Date

Tabele principale:

Visitor: Stochează informații personale ale vizitatorilor, codul QR și perioada de valabilitate

Host: Stochează informații despre gazde și detalii de contact

AccessLog: Urmărește orele de intrare și ieșire ale vizitatorilor

Notifications: Stochează evenimentele trimise gazdelor

Relații:

Visitor → Host (mulți-la-unul)

Visitor → AccessLog (unu-la-mulți)

(Includeți o diagramă a schemei bazei de date dacă este disponibilă)

Rularea Aplicației
Cerințe Prealabile

Java 17 sau versiune superioară

Docker și Docker Compose

Maven 3.8+

Browser web

Instrucțiuni de Configurare

Clonare repository

git clone [repository-url]
cd [project-directory]

Pornire servicii infrastructură

docker-compose up -d

Configurare aplicație

cp src/main/resources/application.properties.example src/main/resources/application.properties
# Editați configurația dacă este necesar

Build aplicație

mvn clean install

Rulare aplicație

mvn spring-boot:run

Acces aplicație

Interfață Web: http://localhost:8080

Provocări și Soluții

Provocare 1: Gestionarea actualizărilor vizitatorilor în timp real fără pierderi de notificări
Soluție: Integrare RabbitMQ pentru procesare asincronă a evenimentelor

Provocare 2: Asigurarea securității și expirării codurilor QR
Soluție: Implementare coduri QR cu valabilitate limitată și validare în backend

Provocare 3: Numărare exactă a persoanelor în caz de evacuare de urgență
Soluție: Dashboard în timp real sincronizat cu check-in/check-out

Îmbunătățiri Viitoare

Aplicație mobilă pentru check-in/check-out vizitatori

Control acces bazat pe geofencing

Autentificare multi-factor pentru zone cu securitate ridicată

Dashboard analitic pentru tendințe vizitatori

Integrare cu sistemele de calendar ale companiei pentru pre-înregistrare automată
