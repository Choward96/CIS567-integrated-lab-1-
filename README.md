# CIS567-integrated-lab-1-
information contenting the code on the integrated lab
HOMEWORK_MAX = 800.0;
QUIZZES_MAX = 400.0;
MIDTERM_MAX = 150.0;
FINAL_MAX = 200.0;

# Type your code here.
student_status = ['UG','G','DL']
student = (input())

if student not in student_status:
    print(f'Error: student status must be UG, G or DL') 
    sys.exit()
    
h_score, q_score, m_score, f_score = map(float, input().split())

homework = ((h_score/HOMEWORK_MAX) * 100)
quizzes = ((q_score/QUIZZES_MAX) * 100)
midterm = ((m_score/MIDTERM_MAX) * 100)
final = ((f_score/FINAL_MAX) * 100)

homework = min(homework, 100)
quizzes = min(quizzes, 100)
midterm = min(midterm, 100)
final = min(final, 100)

print(f"Homework: {homework:2.1f}%")
print(f"Quizzes: {quizzes:2.1f}%")
print(f"Midterm: {midterm:2.1f}%")
print(f"Final Exam: {final:2.1f}%")

if student == 'UG':
    course_avg = (0.2 * homework) + (0.2 * quizzes) + (0.3 * midterm) + (0.3 * final)
elif student == 'G':
    course_avg = (0.15 * homework) + (0.05 * quizzes) + (0.35 * midterm) + (0.45 * final)
elif student == 'DL':
    course_avg = (0.05 * homework) + (0.05 * quizzes) + (0.4 * midterm) + (0.5 * final)
    
print(f"{student} average: {course_avg:2.1f}%")

if course_avg >= 90:
    grade = 'A'
elif (course_avg >=80) and (course_avg < 90):
    grade = 'B'
elif (course_avg >=70) and (course_avg < 80):
    grade = 'C'
elif (course_avg >=60) and (course_avg < 70):
    grade = 'D'
elif (course_avg < 60):
    grade = 'F'
    
print(f"Course grade: {grade}")
