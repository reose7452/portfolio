+++
title = "Week 4 Concurrency og AI Coach"
date = 2026-09-12
draft = false
+++

I uge 4 var emnet concurrency og hvordan Java kan håndtere flere opgaver samtidig. Vi byggede også videre på vores AI Coach og arbejdede med at gøre svarene fra Gemini kortere og mere relevante for vores Training App.

Concurrency kan være nyttigt når flere opgaver kan udføres uafhængigt af hinanden. Hvis flere threads arbejder med de samme data, skal man samtidig være opmærksom på race conditions.

## Det har vi arbejdet med

1. Gennemgået threads og hvordan opgaver kan beskrives med Runnable og Callable
2. Arbejdet med ExecutorService til at håndtere opgaver og Future til at hente resultater fra dem
3. Gennemgået race conditions og problemer som kan opstå når threads bruger fælles data
4. Overvejet hvor concurrency kunne bruges i vores Training App
5. Tilpasset prompten så Gemini svarer som en AI fitness coach med et simpelt og venligt sprog
6. Tilføjet en instruktion om at svare med mellem 2 og 4 korte sætninger og højst 80 ord
7. Bedt Gemini om at undgå titler og unødvendige introduktioner
8. Tilføjet en instruktion om at henvise til en sundhedsfaglig person ved spørgsmål som kræver en medicinsk diagnose
9. Brugt DTOer til at håndtere candidates, content og parts i Gemini svaret
10. Tilpasset testen af vores AiCoachService til den forbedrede AI Coach

## Resultat

Vi valgte ikke at implementere concurrency i projektet i denne uge, fordi vi ikke fandt et sted hvor det gav mening i de nuværende funktioner. Concurrency kunne blive relevant senere hvis appen skal håndtere flere uafhængige AI opgaver samtidig. Vi har forbedret instruktionerne til vores AI Coach og strukturen til at læse svaret fra Gemini.
