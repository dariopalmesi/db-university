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