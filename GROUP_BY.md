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


### Calcolare la media dei voti di ogni appello d'esame

```SQL
SELECT e.`date` AS data_esame , AVG(es.`vote`) AS media_voti
FROM `exams` e
JOIN `exam_student` es 
ON e.`id` = es.`exam_id`
GROUP BY e.`date`
```



### Contare quanti corsi di laurea ci sono per ogni dipartimento

```SQL
SELECT d.`name` AS nome_dipartimento, COUNT(deg.`id`) AS numero_corsi
FROM `departments` d
JOIN `degrees` deg 
ON d.`id` = deg.`department_id`
GROUP BY d.`id`
```