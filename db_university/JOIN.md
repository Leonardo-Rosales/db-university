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

SELECT  `departments`.`name` AS `department_name`, `degrees`.*
FROM `degrees`
JOIN `departments`
ON `departments`.`id` = `degrees`.`department_id`
WHERE `degrees`.`name` LIKE 'Corso di Laurea Magistrale%' AND `departments`.`name` = 'Dipartimento di Neuroscienze'

```

### 3. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)

```SQL

SELECT `courses`.*, `teachers`.`name` AS `teacher_name`, `teachers`.`surname` AS `teacher_surname`, `teachers`.`id` AS `teacher_id`
FROM `courses`
JOIN `course_teacher`
ON `courses`.`id` = `course_id`
JOIN `teachers`
ON `teacher_id` = `teachers`.`id`
WHERE `teachers`.`id` = 44

```

### 4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome

```SQL

SELECT `students`.`name` AS `student_name`, `students`.`surname` AS `student_surname`, `departments`.`name` AS `department_name`, `degrees`.*
FROM `students`
JOIN `degrees`
ON `students`.`degree_id` = `degrees`.`id`
JOIN `departments`
ON `degrees`.`department_id` = `departments`.`id`
ORDER BY `students`.`name` ASC, `students`.`surname` ASC

```

### 5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti

```SQL

SELECT `degrees`.`name` AS `degree_name`, `courses`.`name` AS `course_name`, `teachers`.`name` AS `teacher_name`, `teachers`.`surname` AS `teacher_surname`
FROM `degrees`
JOIN `courses`
ON `degrees`.`id` = `courses`.`degree_id`
JOIN `course_teacher`
ON `course_teacher`.`course_id` = `courses`.`id`
JOIN `teachers`
ON `course_teacher`.`teacher_id` = `teachers`.`id`

```

### 6. Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)

```SQL

```

### 7. BONUS: Selezionare per ogni studente il numero di tentativi sostenuti per ogni esame, stampando anche il voto massimo. Successivamente, filtrare i tentativi con voto minimo 18

```SQL

```