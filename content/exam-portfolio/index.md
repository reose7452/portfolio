+++
title = "Exam Portfolio"
description = "Udvalgte indlæg om udviklingen af TrainingAppExam til backendeksamen på 3. semester."
draft = false
showDate = false
showReadingTime = false
showPagination = false
+++

Her har jeg samlet de indlæg, jeg har valgt til min backendeksamen på 3. semester. De handler om TrainingAppExam, som jeg har udviklet sammen med Khattab Elmir.

## Projektet

TrainingAppExam er et REST API til personlig træning. Brugeren kan oprette en konto, gemme sine fitnessoplysninger, få genereret et træningsprogram og stille fitnessrelaterede spørgsmål til en AI coach. Træningsprogrammet gemmes, så brugeren kan hente det igen senere.

Backenddelen er skrevet i Java med Javalin. Vi bruger JPA og Hibernate til PostgreSQL databasen og Gemini API til AI funktionerne. Login bruger BCrypt til passwords og JWT til adgang til beskyttede endpoints.

- [Projektets GitHub repository](https://github.com/KhattabE/TrainingAppExam)
- [README med arkitektur, ERD og API dokumentation](https://github.com/KhattabE/TrainingAppExam/blob/master/README.md)
- [Den deployede applikations health endpoint](https://trainingappexam.dk/api/health)

APIet kan afprøves med projektets `requests.http` i IntelliJ. Det har ikke en grafisk brugerflade. Health endpointet kan åbnes direkte i browseren og viser, om API'et kører.

## Udvalgte indlæg

### JPA relationer og databaseadgang

[Week 2 JPA Relations, JPQL og DAO Tests]({{< relref "/posts/week-2" >}})

Indlægget beskriver relationerne mellem brugere, træningsprogrammer og øvelser. Det viser også arbejdet med DAO klasser, JPQL og tests af databasefunktionerne.

### Integration med Gemini

[Week 3 Data Integration]({{< relref "/posts/week-3" >}})

Her beskriver jeg den første integration med Gemini gennem AiCoachService. Fokus er på HTTP requests, JSON, DTO'er og Jackson samt brugen af en miljøvariabel til API nøglen.

### REST API og validering

[Week 5 REST API, Javalin og dokumentation]({{< relref "/posts/week-5" >}})

Her bliver backendfunktionerne tilgængelige gennem HTTP endpoints. Indlægget handler om routes, controllers, request og response DTO'er, statuskoder, validering og fejlbeskeder.

### Automatiske tests

[Week 6 REST Assured, Testcontainers og integrationstests]({{< relref "/posts/week-6" >}})

Indlægget beskriver tests af DAO laget og API'et. Vi bruger en separat PostgreSQL testdatabase gennem Testcontainers og lokale AI svar, så testene ikke afhænger af Gemini. Det beskriver også lagring af et træningsprogram i én transaktion og rollback ved fejl.

### Registrering login og sikkerhed

[Week 7 Security]({{< relref "/posts/week-7" >}})

Her beskriver jeg brugerregistrering, login, BCrypt og JWT. Indlægget viser, hvordan vi beskytter endpoints og tester både gyldige og ugyldige loginforsøg og tokens.

### Deployment og DevOps

[Week 8 Deployment og DevOps]({{< relref "/posts/week-8" >}})

Her beskriver jeg, hvordan vi har gjort API'et tilgængeligt online med Docker, GitHub Actions og DigitalOcean. Indlægget dækker også miljøvariabler, Caddy og HTTPS samt forskellen mellem at sende requests til den lokale og den deployede backend.

## Andre indlæg fra forløbet

- [Week 1 Project Setup, JPA og CRUD]({{< relref "/posts/week-1" >}}) beskriver projektets første entity, databaseforbindelse og DAO.
- [Week 4 Concurrency og AI Coach]({{< relref "/posts/week-4" >}}) beskriver concurrency som emne, vores overvejelser om det og forbedringer af AI coachen. Vi valgte på det tidspunkt ikke at tilføje concurrency til projektet.

Ugeindlæggene beskriver projektet, som det så ud på de enkelte tidspunkter. Den aktuelle README beskriver den endelige API kontrakt og de endpoints, der er tilgængelige nu.
