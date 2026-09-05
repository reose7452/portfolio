+++
title = "Week 3 Data Integration"
date = 2026-09-06T00:00:00+02:00
draft = false
+++

I uge 3 arbejdede vi med data integration og koblede Gemini API sammen med vores Training App. Her begyndte vi på en simpel AI Coach som kan sende spørgsmål til Gemini og modtage svar tilbage.

## Det har vi arbejdet med

1. Oprettet en AiCoachService til kommunikationen med Gemini API
2. Brugt HttpClient til at sende requests til APIet
3. Oprettet request data med DTOer
4. Brugt Jackson til at lave request data om til JSON
5. Sendt spørgsmål til Gemini gennem en HTTP POST request
6. Modtaget JSON svar fra APIet
7. Brugt Jackson til at læse og parse svaret
8. Hentet selve AI svaret ud af JSON strukturen
9. Gemte API keyen som environment variable i stedet for at hardcode den
10. Oprettet en test som bekræfter at integrationen virker og at vi får et gyldigt svar tilbage

## Resultat

Ved slutningen af uge 3 har projektet fået en fungerende integration til Gemini API. Training App kan nu sende et spørgsmål til AI servicen, modtage et svar fra Gemini og returnere selve teksten fra svaret. Integrationen er samtidig testet og klar til at blive bygget videre på senere.
