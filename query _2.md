-- Contare quanti iscritti ci sono stati ogni anno

SELECT COUNT(id), enrolment_date
FROM students
GROUP BY enrolment_date

