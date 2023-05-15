1. Contare quanti iscritti ci sono stati ogni anno
   SELECT YEAR(`enrolment_date`) AS `YEAR`,
   COUNT(\*)
   FROM `students`
   GROUP BY YEAR(`enrolment_date`)
   ORDER BY YEAR(`enrolment_date`);

2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio
   I tried to delete "Piano" and "Appartamento" with SUBSTRING_INDEX. But is useless.

SELECT `office_address` AS `buildings`,
COUNT(\*)
FROM `teachers`
GROUP BY `buildings`;

3. Calcolare la media dei voti di ogni appello d'esame
   SELECT AVG(`exam_student`.`vote`) AS `Average Vote`, `exam_id`
   FROM `exam_student`
   GROUP BY `exam_id`
   ORDER BY `exam_id`;
