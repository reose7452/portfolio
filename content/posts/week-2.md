+++
title = "Week 2 JPA Relations, JPQL og DAO Tests"
date = 2026-08-29
draft = false
+++

I uge 2 byggede vi videre på backend delen af vores Training App med fokus på JPA relationer, JPQL queries og tests af vores DAO lag.

## Det har vi arbejdet med

1. Oprettet de nye entities WorkoutProgram og Exercise
2. Oprettet MuscleGroup som enum til at kategorisere øvelser
3. Tilføjet relation mellem User og WorkoutProgram med ManyToOne
4. Tilføjet relation mellem WorkoutProgram og Exercise med ManyToMany
5. Holdt relationerne simple uden unødvendige cascade indstillinger
6. Oprettet DAO interfaces og implementations til WorkoutProgram og Exercise
7. Udvidet UserDAO med flere query metoder
8. Implementeret JPQL queries til blandt andet træningsprogrammer efter antal træningsdage, øvelser efter muskelgruppe, brugere efter experience level og brugere efter deres workout program
9. Oprettet JUnit tests til DAO laget
10. Testet CRUD funktionalitet, JPQL queries og relationen mellem User og WorkoutProgram

## Resultat

Ved slutningen af uge 2 har projektet fået en mere samlet databasestruktur hvor brugere kan forbindes til træningsprogrammer og hvor træningsprogrammer kan indeholde flere øvelser. Vi har også implementeret JPQL queries til at hente data på forskellige måder og testet DAO funktionaliteten med automatiserede tests.
