### Selezionare tutti gli studenti che si sono iscritti nel 1990 (160)

```SQL
SELECT *
FROM `students`
WHERE YEAR(`date_of_birth`) = 1990
```




### Selezionare tutti i corsi che valgono più di 10 crediti (479)

```SQL
SELECT * 
FROM `courses`
WHERE `cfu` > 10;
```



### Selezionare tutti gli studenti che hanno più di 30 anni

```SQL
SELECT *
FROM `students`
WHERE TIMESTAMPDIFF (YEAR ,`date_of_birth`, CURDATE()) > 30;
```



 ### Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di laurea (286)

```SQL
SELECT * 
FROM `courses`
WHERE `year` = 1  
AND `period` = 'I semestre';
 ```



 ### Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del 20/06/2020 (21)

```SQL
SELECT * 
FROM `exams`
WHERE DATE(`date`) = '2020-06-20' 
AND TIME(`hour`) >= '14:00:00';
```



### Selezionare tutti i corsi di laurea magistrale (38)

```SQL
SELECT * 
FROM `degrees`
WHERE `level` = 'magistrale';
```



### Da quanti dipartimenti è composta l'università? (12)

```SQL
SELECT COUNT(*) AS departments_count
FROM `departments`;
```



### Quanti sono gli insegnanti che non hanno un numero di telefono? (50)

```SQL
SELECT COUNT(*) AS teachers_without_phone_number
FROM `teachers`
WHERE `phone` IS NULL;
```



### Inserire nella tabella degli studenti un nuovo record con i propri dati (per il campo degree_id, inserire un valore casuale)

```SQL
INSERT INTO `students` (`degree_id`,`name`, `surname`, `date_of_birth`, `fiscal_code`, `enrolment_date`, `registration_number`, `email` )
VALUES (FLOOR(1 + (RAND() * 80)) ,'Lola', 'Glicine', '1997-12-06', 'CRSTSN96H53N219C','2019-04-19','468397','glicine@gmail.it');
```