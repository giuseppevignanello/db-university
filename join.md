1.  Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia
    SELECT `students`.\*
    FROM `students`
    JOIN `degrees` ON `students`.`degree_id` = `degrees`.`id`  
    WHERE `degrees`.`name` = "Corso di Laurea in Economia";

2.  Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze
    SELECT `degrees`.\*
    FROM `degrees`
    JOIN `departments` ON `degrees`.`department_id` = `departments`.`id`
    WHERE `degrees`.`level` = "magistrale" AND `departments`.`name` = "Dipartimento di Neuroscienze";

3.  Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)
    SELECT `courses`.\*
    FROM `courses`
    JOIN `course_teacher` ON `courses`.`id` = `course_teacher`.`course_id`
    JOIN `teachers` ON `course_teacher`.`teacher_id` = `teachers`.`id`
    WHERE `teachers`.`name` = "Fulvio" AND `teachers`.`surname` = "Amato";

4.  Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il
    relativo dipartimento, in ordine alfabetico per cognome e nome

    SELECT `students`.`name`, `students`.`surname`, `degrees`.`name` AS `Degree Name`, `degrees`.`level` AS `level`, `degrees`.`address` AS `degree address`, `degrees`.`email` AS `degree email`, `degrees`.`website` AS `degree website`, `departments`.`name` AS `Department Name`, `departments`.`phone`, `departments`.`address` AS `department address`, `departments`.`email` AS `department email`, `departments`.`website` AS `departments website`, `departments`.`head_of_department`
    FROM `students`
    JOIN `degrees` ON `degrees`.`id` = `students`.`degree_id`
    JOIN `departments` ON `departments`.`id` = `degrees`.`department_id`
    ORDER BY `students`.`surname`, `students`.`name`;

    5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti
       SELECT `degrees`.\*, `courses`.`name` AS `Course Name`, `courses`.`period`, `courses`.`year`,`courses`.`cfu`, `courses`.`website` AS `Course Website`,`teachers`.`name` AS `Teacher Name`,`teachers`.`surname`AS `teacherssurname`,`teachers`.`phone`, `teachers`.`email` AS `Teacher Email`,`teachers`.`office_address`, `teachers`.`office_number`
       FROM `degrees`
       JOIN `courses` ON `degrees`.`id` = `courses`.`degree_id`
       JOIN `course_teacher` ON `courses`.`id` = `course_teacher`.`course_id`
       JOIN `teachers` ON `course_teacher`.`teacher_id` = `teachers`.`id`;

5.  Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)
    SELECT `teachers`.\*
    FROM `teachers`
    JOIN `course_teacher` ON `teachers`.id = `course_teacher`.`teacher_id`
    JOIN `courses` ON `course_teacher`.`course_id` = `courses`.`id`
    JOIN `degrees` ON `courses`.`degree_id` = `degrees`.`id`
    JOIN `departments` ON `degrees`.`department_id` = `departments`.`id`
    WHERE `departments`.`name` = "Dipartimento di Matematica";
