Sistem de Înregistrare Vizitatori – SSATR IA 2025

Student: Tarniță Georgiana-Beatroce
Scenariu: Visitors / Contractors Sign-In System

Prezentarea Proiectului

Sistemul de Înregistrare Vizitatori este o aplicație web demonstrativă care permite înregistrarea vizitatorilor și simularea procesului de acces într-o clădire. Aplicația oferă o interfață simplă pentru introducerea datelor vizitatorilor și generarea unui cod QR simulat, utilizat pentru verificarea accesului.

Scopul proiectului este de a demonstra fluxul de bază al unui sistem de tip visitor sign-in, precum și organizarea unei aplicații web folosind arhitectura pe layere.

Funcționalități Implementate

Înregistrare vizitator
Introducerea numelui vizitatorului prin interfață web.

Generare cod QR (simulat)
La înregistrare, sistemul generează un cod unic asociat vizitatorului.

Afișare informații vizitator
După înregistrare, sunt afișate datele vizitatorului și codul QR asociat.

Simulare check-in
Scanarea codului QR este simulată prin afișarea acestuia în interfața web.

Tehnologii Utilizate
Backend

Java 17

Spring Boot

Spring MVC

Maven

Frontend

Thymeleaf

HTML

Arhitectura Sistemului

Aplicația este organizată pe o arhitectură clasică MVC (Model–View–Controller), cu separarea clară a responsabilităților:

Componente Principale

Controller
Gestionează cererile HTTP și navigarea între pagini.

Service
Conține logica de business (crearea și gestionarea vizitatorilor).

Repository
Simulează accesul la date.

Model
Reprezintă entitatea Visitor.

View (Thymeleaf)
Pagini HTML pentru interacțiunea cu utilizatorul.

Structura Proiectului

controller – gestionarea cererilor web

service – logica aplicației

repository – gestionarea datelor

model – entități

resources/templates – fișiere Thymeleaf (index.html, qr.html)

Fluxul Aplicației
Flux Înregistrare Vizitator

Utilizatorul accesează pagina principală

Introduce numele vizitatorului

Aplicația generează un cod QR simulat

Datele vizitatorului sunt afișate pe ecran

Simulări și Simplificări

Scanarea codului QR este simulată, fără integrare hardware

Persistența datelor este simplificată

Aplicația este orientată pe demonstrarea fluxului principal, nu pe securitate sau scalabilitate

Capturi de Ecran

Pagina principală – înregistrare vizitator

Pagina de afișare cod QR

Rularea Aplicației
Cerințe Prealabile

Java 17

Maven

Browser web

Pași de Rulare
mvn clean install
mvn spring-boot:run

Acces Aplicație

http://localhost:8080

Limitări Cunoscute

Nu există autentificare sau autorizare

Nu este implementată o bază de date persistentă

Codul QR este utilizat doar în scop demonstrativ

Posibile Îmbunătățiri Viitoare

Integrare bază de date pentru persistență

Scanare QR reală

Sistem de notificări

Autentificare utilizatori

Dashboard de monitorizare vizitatori

Concluzie

Aplicația demonstrează un flux funcțional de înregistrare a vizitatorilor folosind Spring Boot și Thymeleaf, fiind un prototip educațional care poate fi extins ulterior într-un sistem complet de management al accesului.
