### Contare quanti iscritti ci sono stati ogni anno

```SQL
SELECT YEAR(`enrolment_date`) AS anno, COUNT(*) AS numero_iscritti
FROM `students`
GROUP BY YEAR(`enrolment_date`)
```


### Contare gli insegnanti che hanno l'ufficio nello stesso edificio

```SQL
SELECT `office_address`, COUNT(*) AS numero_insegnanti
FROM `teachers`
GROUP BY `office_address`;
```