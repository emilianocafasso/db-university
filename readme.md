# Table_name : Departments
# Entity_name: Department
id: BIGYINT PK AUTO_INCREMENT UNSIGNED
name: VARCHAR (50) NOT_NULL

# Table_name : Degrees
# Entity_name : Degree
id: BIGYINT PK AUTO_INCREMENT UNSIGNED
department_id: BIGINT FK UNSIGNED
name: VARCHAR (50) NOT_NULL

# Table_name : Courses 
# Entity_name : Course
id: BIGYINT PK AUTO_INCREMENT UNSIGNED
degree_id: BIGINT FK UNSIGNED
name: VARCHAR (50) NOT_NULL
year: CHAR (10) NOT_NULL

# Table_name : Teachers 
# Entity_name : Teacher
id: VARCHAR(50) PK
name: VARCHAR (50) NOT_NULL

# Table_name : Exams
# Entity_name : Exam
id: BIGINT PK AUTO_INCREMENT UNSIGNED
course_id: BIGYINT FK UNSIGNED
exam_date: DATETIME
room: VARCHAR(20)

# Table_name : Students
# Entity_name : Student
id: BIGINT PK UNSIGNED 
name: VARCHAR(50) NOT_NULL
degree_id: BIGINT FK UNSIGNED

# Pivot_table: course_teacher
course_id: BIGYINT FK AUTO_INCREMENT UNSIGNED
teacher_id: VARCHAR(50) FK

# Pivot_table: exam_student
student_id: BIGINT FK UNSIGNED
exam_id: BIGINT FK UNSIGNED
vote: TINYINT NOT_NULL




Modellizzare la struttura di un database per memorizzare tutti i dati riguardanti una università:
sono presenti diversi Dipartimenti (es.: Lettere e Filosofia, Matematica, Ingegneria ecc.);
ogni Dipartimento offre più Corsi di Laurea (es.: Civiltà e Letterature Classiche, Informatica, Ingegneria Elettronica ecc..)
ogni Corso di Laurea prevede diversi Corsi (es.: Letteratura Latina, Sistemi Operativi 1, Analisi Matematica 2 ecc.);
ogni Corso può essere tenuto da diversi Insegnanti;
ogni Corso prevede più appelli d'Esame;
ogni Studente è iscritto ad un solo Corso di Laurea;
ogni Studente può iscriversi a più appelli di Esame;
per ogni appello d'Esame a cui lo Studente ha partecipato, è necessario memorizzare il voto ottenuto, anche se non sufficiente.
Pensiamo a quali entità (tabelle) creare per il nostro database e cerchiamo poi di stabilirne le relazioni. Infine, andiamo a definire le colonne e i tipi di dato di ogni tabella.