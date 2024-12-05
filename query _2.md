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
