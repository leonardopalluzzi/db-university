-- 1
-- degrees
-- students

-- SELECT `students`.`name`AS 'Nome studente', `students`.`surname`AS 'Cognome studente', `degrees`.`name` AS 'Nome corso', `students`.`date_of_birth`, `students`.`fiscal_code`
-- FROM `students`
-- JOIN `degrees` ON `students`.`degree_id` = `degrees`.`id`
-- WHERE `degrees`.`name` LIKE 'Corso di Laurea in Economia%'



-- 2
-- SELECT `degrees`.`name` AS  'Nome corso', `departments`.`name` AS 'Nome macro-area'
-- FROM `degrees`
-- JOIN `departments` ON `degrees`.`department_id` = `departments`.`id`
-- WHERE `degrees`.`level` = 'Magistrale'
-- AND `departments`.`name` LIKE '%Neuroscienze%'

-- 3
-- SELECT `teachers`.`name` AS 'Nome docente', `teachers`.`surname` AS 'Cognome docente', `courses`.`name` AS 'Nome corso'
-- FROM `courses`
-- JOIN `course_teacher` ON `course_teacher`.`course_id` = `courses`.`id`
-- JOIN `teachers` ON `course_teacher`.`teacher_id` = `teachers`.`id`
-- WHERE `teachers`.`name` LIKE 'Fulvio%'

-- 4
-- SELECT *
-- FROM `students`
-- JOIN `degrees` ON `students`.`degree_id` = `degrees`.`id`
-- JOIN `departments` ON `degrees`.`department_id` = `departments`.`id`

-- 5
-- SELECT `degrees`.`name` AS 'Nome corso di laurea', `teachers`.`name` AS 'Nome insegnante', `teachers`.`surname` AS 'Cognome insegnante', `courses`.`name` AS 'Nome corso'
-- FROM `degrees`
-- JOIN `courses` ON `courses`.`degree_id` = `degrees`.`id`
-- JOIN `course_teacher` ON `course_teacher`.`course_id` = `courses`.`id`
-- JOIN `teachers` ON `course_teacher`.`teacher_id` = `teachers`.`id` 

-- 6
-- SELECT DISTINCT `teachers`.`name`, `teachers`.`surname`
-- FROM `teachers`
-- JOIN `course_teacher` ON `course_teacher`.`teacher_id` = `teachers`.`id`
-- JOIN `courses` ON `course_teacher`.`course_id` = `courses`.`id`
-- JOIN `degrees` ON `courses`.`degree_id` = `degrees`.`id`
-- JOIN `departments` ON `degrees`.`department_id` = `departments`.`id`
-- WHERE `departments`.`name` LIKE 'Dipartimento di Matematica%'

-- 7
-- SELECT `students`.`name` AS 'Nome studente', `students`.`surname` AS 'Cognome studente', `courses`.`name` AS 'Nome corso', COUNT('Nome corso'), MAX(`exam_student`.`vote`) AS 'Voto massimo'
-- FROM `exam_student`
-- JOIN `students` ON `exam_student`.`student_id` = `students`.`id`
-- JOIN `exams` ON `exam_student`.`exam_id` = `exams`.`id`
-- JOIN `courses` ON `exams`.`course_id` = `courses`.`id`
-- WHERE `exam_student`.`vote` >= 18
-- GROUP BY `Nome studente`, `Cognome studente`, `Nome corso`

-- GROUP BY
-- 1
-- SELECT DISTINCT COUNT(`students`.`name`) AS 'Numero iscritti', YEAR(`students`.`enrolment_date`) AS 'Anno iscrizione'
-- FROM `students`
-- GROUP BY `Anno iscrizione`

-- 2
-- SELECT DISTINCT COUNT(`teachers`.`name`), `teachers`.`office_address` AS 'Ufficio'
-- FROM `teachers`
-- GROUP BY `Ufficio`

-- 3
-- SELECT AVG(`exam_student`.`vote`) AS 'media voti', `exam_student`.`exam_id`
-- FROM `exam_student`
-- GROUP BY `exam_student`.`exam_id`

-- 4
-- SELECT `departments`.`name` AS 'Nome dipartimento', COUNT(`degrees`.`id`)
-- FROM `degrees`
-- JOIN `departments` ON `degrees`.`department_id` = `departments`.`id`
-- GROUP BY `departments`.`name`


