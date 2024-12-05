-- Contare quanti iscritti ci sono stati ogni anno

SELECT COUNT(id), enrolment_date
FROM students
GROUP BY enrolment_date

-- Contare gli insegnanti che hanno l'ufficio nello stesso edificio
SELECT COUNT(id) `teachers`, `office_address`
FROM  `teachers`
GROUP BY `office_address`

-- Calcolare la media dei voti di ogni appello d'esame
SELECT AVG(vote) AS `media_vote`, `exam_id` , `student_id`
FROM `exam_student`
GROUP BY `exam_id`, `student_id`

-- Contare quanti corsi di laurea ci sono per ogni dipartimento
SELECT COUNT(`degrees`.`id`) AS `count_degrees`,
`departments`.`name` 
FROM `departments`
JOIN `degrees`
ON   `departments`.`id` = `degrees`.`department_id`
GROUP BY `departments`.`id`, `departments`.`name`

-- Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia
SELECT DISTINCT `students`.`name`, `degrees`.`name`
FROM `students`
JOIN `degrees` 
ON `degree_id` = `degrees`.`id`
WHERE `degrees`.`name` = 'Corso di Laurea in Economia'

-- Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze
SELECT `degrees`.*
FROM `degrees`
JOIN `departments`
ON `department_id` = `departments`.`id`
WHERE `departments`.`name` = 'Dipartimento di Neuroscienze'
AND `level` = 'magistrale'

-- Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)
SELECT `courses`.*
FROM `courses`
JOIN `course_teacher` ON `course_teacher`.`course_id` = `courses`.`id`
JOIN `teachers` ON `course_teacher`.`teacher_id` = `teachers`.`id`
WHERE `teachers`.`id` = 44

-- Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome
SELECT `students`.*
FROM `students`
JOIN `degrees` ON `students`.`degree_id` = `degrees`.`id`
JOIN `departments` ON `degrees`.`department_id` = `departments`.`id`
ORDER BY `students`.`surname` ASC, `students`.`name` ASC;