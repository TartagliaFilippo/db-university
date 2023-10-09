# EX QUERY SELECT

### QUERYES:

1. Selezionare tutti gli studenti nati nel 1990 (160)

```sql
SELECT * FROM `students` WHERE `date_of_birth` LIKE '1990-%'
```

2. Selezionare tutti i corsi che valgono più di 10 crediti (479)

```sql
SELECT * FROM `courses` WHERE `cfu` > 10
```

3. Selezionare tutti gli studenti che hanno più di 30 anni

```sql
SELECT * FROM `students` WHERE `date_of_birth` <= '1993-10-06'
```

4. Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di
   laurea (286)

```sql
SELECT * FROM `courses` WHERE `year` = '1' AND `period` = 'I semestre'
```

5.  Selezionare tutti gli appelli d esame che avvengono nel pomeriggio (dopo le 14) del
    20/06/2020 (21)

```sql
 SELECT * FROM `exams` WHERE `date` = '2020-06-20' AND `hour` > '14:00:00'
```

6. Selezionare tutti i corsi di laurea magistrale (38)

```sql

SELECT * FROM `degrees` WHERE `name` LIKE 'corso di laurea magistrale%'
```

7. Da quanti dipartimenti è composta l università? (12)

```sql
SELECT COUNT(*) FROM `departments`
```

8. Quanti sono gli insegnanti che non hanno un numero di telefono? (50)

```sql
SELECT COUNT(*) FROM `teachers` WHERE `phone` IS NULL
```

### QUERIES GROUP BY

1. Contare quanti iscritti ci sono stati ogni anno

```sql
SELECT YEAR(`enrolment_date`) "anno_iscrizione", COUNT(*) "numero_studenti" FROM `students` GROUP BY YEAR(`enrolment_date`);
```

2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio

```sql
SELECT `office_address` "indirizzo_ufficio", COUNT(*) "numero_insegnanti" FROM `teachers` GROUP BY `office_address`;
```

3. Calcolare la media dei voti di ogni appello d'esame

```sql
SELECT `exam_id` "esame", AVG(`vote`) "media_voti" FROM `exam_student` GROUP BY `exam_id`;
```

4. Contare quanti corsi di laurea ci sono per ogni dipartimento

```sql
SELECT `department_id` "dipartimenti", COUNT(*) "numero_corsi_laurea" FROM `degrees` GROUP BY `department_id`;
```

### QUERIES JOIN

1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

```sql
SELECT `students`.`name` "nome_studente", `students`.`surname` "cognome_studente", `degrees`.`name` "nome_corso" FROM `students` JOIN `degrees` ON `degrees`.`id`= `students`.`degree_id` WHERE `degrees`.`name` = "Corso di Laurea in Economia";
```

2. Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze

```sql

```

3. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)

```sql

```

4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome

```sql

```

5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti

```sql

```

6. Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)

```sql

```

7. BONUS: Selezionare per ogni studente il numero di tentativi sostenuti
   per ogni esame, stampando anche il voto massimo. Successivamente,
   filtrare i tentativi con voto minimo 18.

```sql

```
