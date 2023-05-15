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
