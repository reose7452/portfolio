+++
title = "Week 5 REST API, Javalin og dokumentation"
date = 2026-09-19
draft = false
+++

I uge 5 arbejdede vi med at gøre funktionerne i vores Training App tilgængelige gennem et REST API. Vi brugte Javalin til at oprette endpoints og koblede dem sammen med vores DAO lag og AI Coach.

## Det har vi arbejdet med

1. Tilføjet Javalin og oprettet Application som startpunkt for vores REST API
2. Oprettet controllers og route klasser til brugere, øvelser, AI Coach og træningsprogrammer
3. Implementeret GET, POST, PUT og DELETE endpoints til øvelser
4. Tilføjet endpoints til at oprette og hente brugere
5. Oprettet et endpoint hvor brugeren kan stille spørgsmål til vores AI Coach
6. Tilføjet generering af et træningsprogram ud fra brugerens oplysninger
7. Brugt request og response DTOer til at håndtere JSON uden at sende vores entities direkte
8. Tilføjet validering af blandt andet navne, ids, antal sæt og træningsdage
9. Brugt HTTP statuskoder som 200, 201, 204, 400, 404 og 405
10. Tilføjet logging af requests og samlet fejl i et JSON format med status og msg
11. Oprettet en requests.http fil til manuelle requests i IntelliJ
12. Dokumenteret endpoints, JSON formater og statuskoder i README

## Resultat

Ved slutningen af uge 5 har Training App fået et REST API som forbinder HTTP requests med vores eksisterende backend. Routes og controllers er opdelt efter funktion, og DTOerne bestemmer hvilke data APIet modtager og returnerer. API dokumentationen beskriver hvordan endpoints kan bruges, og fejl returneres i samme JSON format. Det er grundlaget for de automatiserede endpoint tests i uge 6.
