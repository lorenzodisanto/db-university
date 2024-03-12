# EX - QUERY con JOIN

### Traccia 1

- Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

```sql
SELECT
  `students`.`id` AS `id_student`,
  `students`.`name`,
  `students`.`surname`

FROM `students`

INNER JOIN `degrees`
ON `degrees`.`id` = `students`.`degree_id`

WHERE `degrees`.`name`= "Corso di Laurea in Economia";
```

### Traccia 2

- Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di
  Neuroscienze

```sql
SELECT *

FROM `degrees`
INNER JOIN `departments`
ON `departments`.`id` = `degrees`.`department_id`

WHERE `departments`.`name` = "Dipartimento di Neuroscienze"
AND `degrees`.`level` = "magistrale";
```

### Traccia 3

- Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)

```sql
SELECT
  `courses`.`name` AS `name_course`

FROM `courses`

INNER JOIN `course_teacher`
ON `course_teacher`.`course_id` = `courses`.`id`

INNER JOIN `teachers`
ON `teachers`.`id` = `course_teacher`.`teacher_id`

WHERE `teachers`.`id` = 44;
```

### Traccia 4

- Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome

```sql
SELECT
 `students`.`surname` AS `surname_student`,
 `students`.`name` AS `name_student`,
 `degrees`.`name` AS `name_degree`,
 `departments`.`name` AS `name_departement`

FROM `students`

INNER JOIN `degrees`
ON `degrees`.`id` = `students`.`degree_id`

INNER JOIN `departments`
ON `departments`.`id` = `degrees`.`department_id`

ORDER BY `surname_student` ASC, `name_student` ASC;
```

### Traccia 5

- Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti

```sql
SELECT
 `degrees`.`name` AS `name_degree`,
 `courses`.`name` AS `name_course`,
 `teachers`.`name` AS `name_teacher`,
 `teachers`.`surname` AS `surname_teacher`

FROM `degrees`

INNER JOIN `courses`
ON `courses`.`degree_id` = `degrees`.`id`

INNER JOIN `course_teacher`
ON `course_teacher`.`course_id` = `courses`.`id`

INNER JOIN `teachers`
ON `teachers`.`id` = `course_teacher`.`teacher_id`;
```

### Traccia 6

- Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)

```sql
SELECT
  DISTINCT `teachers`.*

FROM `teachers`

INNER JOIN `course_teacher`
ON `course_teacher`.`teacher_id` = `teachers`.`id`

INNER JOIN `courses`
ON `courses`.`id` = `course_teacher`.`course_id`

INNER JOIN `degrees`
ON `degrees`.`id` = `courses`.`degree_id`

INNER JOIN `departments`
ON `departments`.`id` = `degrees`.`department_id`

WHERE `departments`.`name` = "Dipartimento di Matematica";
```

### Traccia 7

- BONUS: Selezionare per ogni studente il numero di tentativi sostenuti per ogni esame, stampando anche il voto massimo. Successivamente, filtrare i tentativi con voto minimo 18.

```sql

```
