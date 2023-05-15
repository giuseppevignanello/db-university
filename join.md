1.  Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia
    SELECT `students`.\*
    FROM `students`
    JOIN `degrees` ON `degrees`.`id` = `students`.`degree_id`
    WHERE `degrees`.`name` = "Corso di Laurea in Economia";
