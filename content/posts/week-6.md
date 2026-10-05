+++
title = "Week 6 REST Assured, Testcontainers og integrationstests"
date = 2026-09-26
draft = false
+++

I uge 6 arbejdede vi med automatiserede tests af vores Training App. Vi byggede videre på vores DAO tests og tilføjede tests af REST APIet med REST Assured og Hamcrest.

Fokus i denne uge var at teste med kendte data i en separat database og kontrollere både gyldige requests og almindelige fejl.

## Det har vi arbejdet med

1. Tilføjet REST Assured og brugt Hamcrest til at kontrollere statuskoder og JSON svar
2. Oprettet en separat HibernateTestConfig med PostgreSQL og Testcontainers
3. Ladet vores DAO implementations modtage en EntityManagerFactory til testdatabasen
4. Oprettet kendte brugere, øvelser og træningsprogrammer før hver test
5. Testet CRUD funktionalitet, JPQL queries og relationer i DAO laget
6. Tilpasset Application så Javalin kan startes og stoppes under endpoint tests
7. Testet vores endpoints samt eksempler på ugyldige requests og data som ikke findes
8. Brugt en testversion af AI Coach under endpoint tests og testet AiCoachService med JSON svar fra en lokal Javalin server som efterligner Gemini
9. Tilføjet WorkoutProgramService som validerer AI data og gemmer øvelser, træningsprogram og brugerens relation i én transaktion
10. Testet at en fejl under gemning ruller transaktionen tilbage og bevarer brugerens tidligere træningsprogram
11. Opdateret API dokumentationen i README med de nye fejlbeskeder og statuskoder

## Resultat

Ved slutningen af uge 6 har vi tests af DAO laget, REST APIet og håndteringen af AI svar. Hver database test starter med kendte data i en separat testdatabase. Vi har holdt testene til konkrete eksempler som oprettelse, opdatering, ugyldige træningsdage og manglende data. Den samlede testkørsel gennemførte 36 tests uden fejl. AI testene bruger lokale svar, så vi kan teste vores kode uden at være afhængige af Gemini under testkørslen.
