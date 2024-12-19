### Contare quanti iscritti ci sono stati ogni anno

```SQL
SELECT YEAR(`enrolment_date`) AS anno, COUNT(*) AS numero_iscritti
FROM `students`
GROUP BY YEAR(`enrolment_date`)
```