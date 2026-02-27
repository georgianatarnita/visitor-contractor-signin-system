Sistem de Înregistrare Vizitatori – SSATR IA 2025

Student: Tarniță Georgiana-Beatroce
Scenariu: Visitor / Access & Role Management System (Tennis Tournament Facility)

Prezentarea Proiectului

Sistemul de Înregistrare Vizitatori este o aplicație web demonstrativă care permite gestionarea accesului utilizatorilor (Admin, Player, Referee) într-un sistem de tip „controlled access environment”.

Aplicația simulează procesul de înregistrare, autentificare și acces controlat într-o infrastructură digitală (în acest caz – o platformă pentru gestionarea unui turneu de tenis).

Scopul proiectului este de a demonstra:

fluxul de autentificare și autorizare

gestionarea utilizatorilor pe roluri

protejarea accesului la anumite secțiuni

organizarea aplicației pe layere (MVC)

Funcționalități Implementate
Înregistrare utilizator

Crearea unui cont nou cu validare a datelor (username, email, parolă).

Autentificare (Sign-In)

Login securizat pe bază de token JWT.

Control acces pe roluri

Acces diferențiat în funcție de tipul utilizatorului:

Admin

Player

Referee

Gestionare utilizatori (Admin)

Vizualizare listă utilizatori

Editare date

Ștergere utilizatori

Filtrare și căutare

Profil utilizator

Actualizarea informațiilor personale și schimbarea parolei.

Comunicare în timp real (WebSocket)

Pregătire pentru actualizări live (meciuri / notificări).

Tehnologii Utilizate
Backend

Java 17
Spring Boot
Spring Security
Spring MVC
JWT Authentication
WebSocket (STOMP)
Maven

Frontend

React
Material UI
Axios
SockJS + STOMP

Arhitectura Sistemului

Aplicația este organizată pe o arhitectură separată frontend–backend, folosind modelul MVC pe partea de backend și arhitectură component-based pe frontend.

Componente Principale
Backend

Controller
Gestionează cererile HTTP și rutele API.

Service
Conține logica de business (gestionare utilizatori, autentificare, validări).

Repository
Acces la date (persistență).

Model
Entitățile sistemului (User).

Security Layer
Gestionare autentificare JWT și autorizare pe roluri.

WebSocket Configuration
Configurarea comunicării în timp real.

Frontend

AuthContext
Gestionează starea de autentificare.

ProtectedRoute
Controlează accesul la pagini în funcție de rol.

Dashboard-uri separate

Admin Dashboard

Player Dashboard

Referee Dashboard

User Management Components
UserList, UserDetails, Profile.

Structura Proiectului

Backend:

controller

service

repository

model

security

config

Frontend:

components

context

services

styles

Fluxul Aplicației
Flux Înregistrare Utilizator

Utilizatorul accesează pagina de înregistrare

Introduce datele personale

Sistemul validează datele

Se creează contul

Utilizatorul este autentificat automat

Flux Autentificare

Utilizatorul introduce username și parolă

Backend validează datele

Se generează un token JWT

Token-ul este stocat în frontend

Utilizatorul este redirecționat către dashboard-ul corespunzător rolului

Flux Control Acces

La accesarea unei rute protejate

ProtectedRoute verifică autentificarea

Verifică rolul utilizatorului

Permite sau restricționează accesul

Simulări și Simplificări

Nu este implementată infrastructură hardware reală (badge fizic / scanner QR)

Sistemul este orientat educațional

Nu sunt implementate mecanisme avansate de securitate (rate limiting, 2FA etc.)

Dashboard-urile pentru turnee și meciuri sunt structuri pregătite pentru extindere

Capturi de Ecran

Pagina Login

Pagina Register

Admin Dashboard

User Management

Profile

Rularea Aplicației
Cerințe Prealabile

Java 17
Node.js
Maven
Browser web

Pași de Rulare

Backend:

mvn clean install
mvn spring-boot:run

Frontend:

npm install
npm start
Acces Aplicație

Backend:
http://localhost:8080

Frontend:
http://localhost:3000

Limitări Cunoscute

Nu există integrare hardware reală

Nu este implementată infrastructură distribuită

Sistemul este prototip educațional

Funcționalitățile legate de turnee/meciuri sunt extensibile

Posibile Îmbunătățiri Viitoare

Integrare completă gestionare turnee și meciuri

Notificări în timp real

Dashboard statistic

Integrare bază de date avansată

2FA

Deploy în cloud

Concluzie

Aplicația demonstrează un sistem funcțional de autentificare și control acces bazat pe roluri, folosind arhitectură modernă (Spring Boot + React).

Proiectul reprezintă un prototip educațional de sistem digital de gestionare acces utilizatori, care poate fi extins într-o platformă completă de management pentru infrastructuri sportive sau organizaționale.
