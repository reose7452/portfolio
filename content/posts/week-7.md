+++
title = "Week 7 Security"
date = 2026-10-18
draft = false
+++

I uge 7 arbejdede vi med security i vores Training App. Formålet var at gøre det muligt for brugere at registrere sig, logge ind og få adgang til beskyttede dele af APIet.

Fokus i denne uge var password hashing, JWT tokens og beskyttelse af routes.

## Det har vi arbejdet med

1. Brugt BCrypt til at hashe passwords, før de bliver gemt i databasen
2. Oprettet en PasswordService til at hashe og kontrollere passwords
3. Udvidet AuthService med funktionalitet til registrering og login
4. Oprettet DTOer til registrering, login og svar med JWT token
5. Oprettet endpoints til registrering og login
6. Oprettet en JwtService til at generere og validere JWT tokens
7. Sat en udløbstid på en time på JWT tokens
8. Gemt JWT secret som environment variable i stedet for at hardcode den
9. Beskyttet AI Coach routen, så den kræver et gyldigt Bearer token
10. Returneret 401 Unauthorized, hvis et token mangler, er ugyldigt eller har forkert format
11. Oprettet tests til password hashing, registrering, login, JWT tokens og beskyttede routes

## Resultat

Ved slutningen af uge 7 har Training App fået et grundlæggende login og sikkerhedssystem. Passwords bliver ikke gemt som almindelig tekst, og brugere kan registrere sig og logge ind for at få et JWT token. Tokenet kan derefter bruges til at få adgang til den beskyttede AI Coach route. Vi har også testet både gyldige og ugyldige loginforsøg og tokens.
