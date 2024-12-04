SELECT `date_of_birth`
FROM `students`
WHERE YEAR(`date_of_birth`) = 1990

SELECT `cfu`
FROM `courses`
WHERE `cfu` >10

SELECT `date_of_birth`
FROM `students`
WHERE `date_of_birth` < '1994-01-01'

SELECT *
FROM `courses`
WHERE year = 1 
AND period = 'I semestre'

SELECT *
FROM `exams`
WHERE hour >'14:00'
AND date = '2020-06-20'

SELECT *
FROM `degrees`
WHERE level = 'Magistrale'

SELECT COUNT('id')
FROM `departments`

SELECT COUNT(*)
FROM `teachers`
WHERE phone  is null

INSERT INTO `students` (`name`, `surname`, `date_of_birth`, `degree_id`, `fiscal_code`, `enrolment_date`, `registration_number`, `email`)
VALUES ('Dario', 'Palmesi', '1988-10-28', 2, 'djdakjnkj', '2024-05-12', '2568', 'dario.pam@io.com')

UPDATE `teachers`
SET `office_number` = 126
WHERE id=58;

DELETE FROM `students`
WHERE id=5005
