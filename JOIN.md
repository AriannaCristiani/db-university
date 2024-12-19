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


### Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)

```SQL
SELECT c.`name` AS nome_corso
FROM `courses` c
JOIN `course_teacher` ct 
ON c.`id` = ct.`course_id`
JOIN `teachers` t 
ON ct.`teacher_id` = t.`id`
WHERE t.`id` = 44;
```


### Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome

```SQL
SELECT s.`surname`, s.`name`, d.`name` AS nome_corso, dep.`name` AS nome_dipartimento
FROM `students` s
JOIN `degrees` d 
ON s.`degree_id` = d.`id`
JOIN `departments` dep 
ON d.`department_id` = dep.`id`
ORDER BY s.`surname`, s.`name`;
```