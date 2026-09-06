% Student-Teacher-Subject Code Database

student(shakthi, teacher1, eca0512).
student(pavan, teacher2, eca0521).
student(rahul, teacher1, eca0512).
student(priya, teacher3, eca0530).
student(anitha, teacher2, eca0521).

teacher(teacher1, dr_balamurugan).
teacher(teacher2, dr_shyamala).
teacher(teacher3, dr_kumar).

subject(eca0512, engineering_electromagnetics).
subject(eca0521, digital_signal_processing).
subject(eca0530, communication_systems).

% Find teacher of a student
student_teacher(Student, Teacher) :-
    student(Student, T, _),
    teacher(T, Teacher).

% Find subject code of a student
student_subject_code(Student, Code) :-
    student(Student, _, Code).

% Find subject name from subject code
subject_name(Code, Subject) :-
    subject(Code, Subject).
