### Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

```SQL
SELECT s.*
FROM `students` s
JOIN `degrees` d 
ON s.`degree_id` = d.`id`
WHERE d.`name` = 'Corso di Laurea in Economia';
```