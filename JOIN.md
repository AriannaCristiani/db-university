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



### Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti

```SQL
SELECT deg.`name` AS corso_laurea, c.`name` AS nome_corso, t.`name` AS nome_insegnante, t.`surname` AS cognome_insegnante
FROM `degrees` deg
JOIN `course_teacher` ct 
ON deg.`id` = ct.`course_id`
JOIN `courses` c 
ON ct.`course_id` = c.`id`
JOIN `teachers` t 
ON ct.`teacher_id` = t.`id`
ORDER BY deg.`name`, c.`name`, t.`name`, t.`surname`;
```



### Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)

```SQL
SELECT DISTINCT t.* 
FROM `teachers` t
JOIN `course_teacher` ct 
ON t.`id` = ct.`teacher_id`
JOIN `courses` c 
ON ct.`course_id` = c.`id`
JOIN `degrees` deg 
ON c.`degree_id` = deg.`id`
WHERE deg.`department_id` = (SELECT `id` FROM `departments` WHERE `name` = 'Dipartimento di Matematica');
```