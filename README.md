### Selezionare tutti gli studenti che si sono iscritti nel 1990 (0)

```SQL
SELECT *
FROM `students`
WHERE YEAR(`enrolment_date`) = 1990
```

### Selezionare tutti i corsi che valgono più di 10 crediti (479)

```SQL
SELECT * 
FROM `courses`
WHERE `cfu` > 10;
```