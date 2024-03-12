# EX - QUERY con GROUP BY

### Traccia 1

- Contare quanti iscritti ci sono stati ogni anno

```sql
SELECT
  YEAR(`enrolment_date`) AS `enrolment_year`,
  COUNT(*) AS `number_students`
FROM `students`
GROUP BY `enrolment_year`;
```

### Traccia 2

- Contare gli insegnanti che hanno l'ufficio nello stesso edificio

```sql
SELECT
  `office_address`,
  COUNT(*) AS `number_teachers`
FROM `teachers`
GROUP BY `office_address`;
```

### Traccia 3

- Calcolare la media dei voti di ogni appello d'esame

```sql
SELECT
  `exam_id`,
  AVG(`vote`) AS `average_vote`
FROM `exam_student`
GROUP BY `exam_id`;
```

### Traccia 4

- Contare quanti corsi di laurea ci sono per ogni dipartimento

```sql
SELECT
  `department_id`,
  COUNT(*) AS `number_degrees`
FROM `degrees`
GROUP BY `department_id`;
```
