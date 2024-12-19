### Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

```SQL
SELECT s.*
FROM `students` s
JOIN `degrees` d 
ON s.`degree_id` = d.`id`
WHERE d.`name` = 'Corso di Laurea in Economia';
```


### Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze

```SQL
SELECT deg.`name` AS nome_corso, deg.`level` AS livello
FROM `degrees` deg
JOIN `departments` dep ON 
deg.`department_id` = dep.`id`
WHERE dep.`name` = 'Dipartimento di Neuroscienze' AND deg.`level` = 'Magistrale';
```