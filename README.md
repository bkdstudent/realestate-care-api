# realestate-care-api
Data for API
## Toelichting op de structuur

**`inspectors`** — de gebruikers die kunnen inloggen, inclusief hun voorkeuren (thema, meldingen).

**`reports`** — de centrale rapportages, met een `status` (`assigned` of `completed`) en een `tasks`-array die aangeeft welke onderdelen ingevuld moeten worden. Via `inspectorId` weet je welke rapportage bij welke inspecteur hoort.

**`damage`, `maintenance`, `installations`, `modifications`** — elk een aparte resource, gekoppeld aan een rapportage via `reportId`. 
Zo is het mogelijk om per rapportage alle bijbehorende gegevens ophalen met bijv.:
```
GET /damage?reportId=2
