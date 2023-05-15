1. Contare quanti iscritti ci sono stati ogni anno
   SELECT YEAR(`enrolment_date`) AS `YEAR`, COUNT(\*)
   FROM `students`
   GROUP BY YEAR(`enrolment_date`)
   ORDER BY YEAR(`enrolment_date`);
