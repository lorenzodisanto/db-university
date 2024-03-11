# EX - QUERY con SELECT

### Traccia 1

- Selezionare tutti gli studenti nati nel 1990 (160)

```sql
SELECT *
FROM `students`
WHERE YEAR(`date_of_birth`) = 1990;
```

### Traccia 2

- Selezionare tutti i corsi che valgono più di 10 crediti (479)

```sql
SELECT *
FROM `courses`
WHERE `cfu` > 10;
```

### Traccia 3

- Selezionare tutti gli studenti che hanno più di 30 anni

```sql
SELECT *
FROM `students`
WHERE `date_of_birth` < DATE_SUB(NOW(), INTERVAL 30 YEAR);
```

3676 studenti hanno più di 30 anni al 2024-03-11.

### Traccia 4

- Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di laurea (286)

```sql
SELECT *
FROM `courses`
WHERE `period` LIKE "I semestre" AND `year` = 1;
```

### Traccia 5

- Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del 20/06/2020 (21)

```sql
SELECT *
FROM `exams`
WHERE `date` LIKE "2020-06-20" AND TIME(`hour`) >= "14%";
```

### Traccia 6

- Selezionare tutti i corsi di laurea magistrale (38)

```sql
SELECT *
FROM `degrees`
WHERE `level` LIKE "magistrale";
```

### Traccia 7

- Da quanti dipartimenti è composta l'università? (12)

```sql
SELECT COUNT(*) AS numero_dipartimenti
FROM `departments`;
```

### Traccia 8

- Quanti sono gli insegnanti che non hanno un numero di telefono? (50)

```sql
SELECT *
FROM `teachers`
WHERE `phone` IS NULL;
```
