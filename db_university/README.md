### Query con GROUP BY

### 1. Contare quanti iscritti ci sono stati ogni anno

```SQL

SELECT YEAR(`enrolment_date`), COUNT(`id`) AS `members`
FROM `students`
GROUP BY YEAR(`enrolment_date`)

```

### 2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio

```SQL

SELECT `office_address`, COUNT(*) AS `number_teachers`
FROM `teachers`
GROUP BY `office_address`

```

### 3. Calcolare la media dei voti di ogni appello d'esame

```SQL

SELECT `exam_id`, AVG(`vote`) 
FROM `exam_student`
GROUP BY `exam_id`

```

### 4. Contare quanti corsi di laurea ci sono per ogni dipartimento

```SQL

SELECT `department_id`, COUNT(*) AS `degrees_number`
FROM `degrees`
GROUP BY `department_id`

```

### Query con GROUP JOIN

### 1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

```SQL

SELECT  `degrees`.`name` AS `degree_name`, `students`.*
FROM `students`
JOIN `degrees`
ON `degrees`.`id` = `students`.`degree_id`
WHERE `degrees`.`name` = 'Corso di Laurea in Economia'

```

### 2. Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze

```SQL

```

### 3. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)

```SQL

```

### 4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome

```SQL

```

### 5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti

```SQL

```

### 6. Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)

```SQL

```

### 7. BONUS: Selezionare per ogni studente il numero di tentativi sostenuti per ogni esame, stampando anche il voto massimo. Successivamente, filtrare i tentativi con voto minimo 18

```SQL

```

