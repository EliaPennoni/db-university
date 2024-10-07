# db-university

1. Selezionare tutti gli studenti nati nel 1990 (160)

SELECT \*
FROM `students`
WHERE YEAR(date_of_birth) = 1990;

2. Selezionare tutti i corsi che valgono più di 10 crediti (479)

SELECT \*
FROM `courses`
WHERE (cfu) > 10;

3. Selezionare tutti gli studenti che hanno più di 30 anni

SELECT \*
FROM `students`
WHERE YEAR(CURDATE()) - YEAR(date_of_birth) > 30

4. Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di
   laurea (286)

SELECT `period`, `year`
FROM `courses`
WHERE `period` = 'I semestre' AND `year` = 1;

5. Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del
   20/06/2020 (21)
   SELECT `date`, `hour`
   FROM `exams`
   WHERE (`date` = '2020-06-20' AND `hour` > '14:00:00');

6. Selezionare tutti i corsi di laurea magistrale (38)

SELECT `level`
FROM `degrees`
WHERE `level` = 'magistrale';

7. Da quanti dipartimenti è composta l'università? (12)

SELECT count(`name`)
FROM `departments`

8. Quanti sono gli insegnanti che non hanno un numero di telefono? (50)

SELECT COUNT(\*)
FROM `teachers`
WHERE `phone` IS NULL;

9. Inserire nella tabella degli studenti un nuovo record con i propri dati (per il campo
   degree_id, inserire un valore casuale)

INSERT INTO `students` (`id`, `degree_id`, `name`, `surname`, `date_of_birth`, `fiscal_code`, `enrolment_date`, `registration_number`, `email`) VALUES ('777007', '11', 'Elia', 'Pennoni', '1991/07/17', 'PNLMN91G32F', '2024-10-09', '1234567890', 'CIAOGIANNI@MUCHACHA.ORG');

10. Cambiare il numero dell’ufficio del professor Pietro Rizzo in 126

UPDATE `teachers` SET `office_address` = 'Contrada Penelope 126', `office_number` = '126' WHERE `teachers`.`id` = 1;
