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
WHERE `year` = 1  AND `period` = 'I semestre';
 ```