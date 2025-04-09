# Traccia

Modellizzare la struttura di un database per memorizzare tutti i dati riguardanti una università:
sono presenti diversi Dipartimenti (es.: Lettere e Filosofia, Matematica, Ingegneria ecc.);
ogni Dipartimento offre più Corsi di Laurea (es.: Civiltà e Letterature Classiche, Informatica, Ingegneria Elettronica ecc..)
ogni Corso di Laurea prevede diversi Corsi (es.: Letteratura Latina, Sistemi Operativi 1, Analisi Matematica 2 ecc.);
ogni Corso può essere tenuto da diversi Insegnanti;
ogni Corso prevede più appelli d'Esame;
ogni Studente è iscritto ad un solo Corso di Laurea;
ogni Studente può iscriversi a più appelli di Esame;
per ogni appello d'Esame a cui lo Studente ha partecipato, è necessario memorizzare il voto ottenuto, anche se non sufficiente. Pensiamo a quali entità (tabelle) creare per il nostro database e cerchiamo poi di stabilirne le relazioni. Infine, andiamo a definire le colonne e i tipi di dato di ogni tabella.

## tables: macro_areas, degree_courses, courses, teachers, exam_calls, students, votes


## Table: `macro_areas`

**columns**
- id: (BIGINT) - primary_key - auto_increment - NOTNULL
- name: VARCHAR(200) - NOTNULL



## Table: `degree_courses`

**columns**
- id: (BIGINT) - primary_key - auto_increment - NOTNULL
- macro_areas_id: (BIGINT) - foreign_key - NOTNULL
- name: VARCHAR(200) - NOTNULL



## Table: `courses` //many to many with teachers

**columns**
- id: (BIGINT) - primary_key - auto_increment - NOTNULL
- students_id: (BIGINT) - foreign_key - NOTNULL
- degree_courses_id: (BIGINT) - foreign_key - NOTNULL
- name: VARCHAR(100) - NOTNULL




## Table: `teachers` //many to many with courses

**columns**
- id: (BIGINT) - primary_key - auto_increment - NOTNULL
- full_name:
- email:


## Table: `course_teacher` //pivot table 

**columns**
- teachers_id: (BIGINT) - foreign_key - NOTNULL
- courses_id: (BIGINT) - foreign_key - NOTNULL




## Table: `exam_calls` //many to many with students

**columns**
- id: (BIGINT) - primary_key - auto_increment - NOTNULL
- courses_id: (BIGINT) - foreign_key - NOTNULL



## Table: `exam_call_student` //pivot table 

**columns**
- exam_calls_id: (BIGINT) - foreign_key - NOTNULL
- students_id: (BIGINT) - foreign_key - NOTNULL



## Table: `students`

**columns**
- id: (BIGINT) - primary_key - auto_increment - NOTNULL
- name:
- email: 
- freshman: 




## Table: `votes`

**columns**
- id: (BIGINT) - primary_key - auto_increment - NOTNULL
- studens_id: (BIGINT) - foreign_key - NOTNULL
- vote: TINYINT(30) - NULL