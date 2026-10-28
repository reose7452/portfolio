+++
title = "Week 8 Deployment og DevOps"
date = 2026-10-28
draft = false
+++

I uge 8 arbejdede vi med deployment og DevOps i vores Training App. Formålet var at gøre vores REST API tilgængeligt online, så det ikke kun kunne bruges fra vores egne computere.

Fokus i denne uge var Docker, GitHub Actions, miljøvariabler og deployment til DigitalOcean.

## Det har vi arbejdet med

1. Pakket vores Java 25 applikation som en JAR med Maven
2. Oprettet en Dockerfile, som kopierer JAR filen ind i et image og starter APIet på port 7070
3. Opsat GitHub Actions til at bygge projektet og køre testene ved pull requests til master og pushes til master
4. Ladet workflowet bygge og uploade vores Docker image til Docker Hub efter en vellykket Maven build
5. Automatiseret deployment ved pushes til master, hvor workflowet forbinder til DigitalOcean gennem SSH og kører docker compose pull og docker compose up -d
6. Forbundet den deployede backend til PostgreSQL databasen på serveren
7. Brugt miljøvariabler til databaseforbindelsen, databasepassword, JWT secret og Gemini API nøglen samt GitHub secrets til workflowets adgangsoplysninger
8. Tilknyttet vores domæne trainingappexam.dk og brugt Caddy som reverse proxy til at håndtere HTTPS foran APIet
9. Kontrolleret at APIet kan tilgås udefra gennem vores health endpoint

## Deployment

APIet er tilgængeligt gennem [trainingappexam.dk](https://trainingappexam.dk/api/health). Linket åbner vores health endpoint, som returnerer et JSON svar, når APIet kører.

Vi har ikke lavet en grafisk brugerflade til backendprojektet. De andre funktioner kan afprøves med requests.http i IntelliJ. Beskyttede endpoints kræver stadig et JWT token, selvom APIet nu er tilgængeligt online.

## Overvejelser og læring

Deployment kræver, at flere dele passer sammen: Java applikationen, Docker, databaseforbindelsen, miljøvariablerne og forbindelsen gennem domænet. Et vellykket build viser derfor ikke alene, at hele applikationen virker online. Vi skal også kontrollere den deployede API og de funktioner, vi vil bruge.

Det er også vigtigt at skelne mellem den lokale database og produktionsdatabasen. Når baseUrl i requests.http peger på vores domæne, bliver forespørgslerne sendt til den deployede backend og dens database. Hvis vi vil afprøve ændringer lokalt, skal vi i stedet starte APIet lokalt og bruge localhost:7070.

En mulig forbedring af opsætningen ville være et automatisk health check efter deployment. I vores nuværende workflow bliver den kontrol udført manuelt.

## Resultat

Training App er nu deployet med et offentligt HTTPS endpoint og en produktionsdatabase. GitHub Actions automatiserer build, tests og upload af Docker imaget, mens pushes til master også starter deployment til DigitalOcean. Vi kan derfor bruge den samme backend fra forskellige computere uden at starte en lokal server først.
