# College Database Management System (CDBMS)

This project implements a comprehensive College Database Management System (CDBMS) using MySQL. It is designed to manage various aspects of a college's operations, including students, teachers, courses, departments, and many other related entities. The database schema is meticulously crafted to support a wide range of functionalities required for efficient college management.

## Features

- **Student Management**: Manage student details, enrollments, attendance, grades, hostel accommodations, transport, and fees.
- **Teacher Management**: Maintain teacher information, including personal details, departmental affiliations, and courses taught.
- **Course and Department Management**: Organize and link courses and departments with students and teachers.
- **Classroom and Scheduling Management**: Manage classrooms, course schedules, and exam schedules.
- **Library Management**: Track books and transactions within the college library.
- **Events and Clubs Management**: Organize college events and manage student clubs.
- **Scholarship Management**: Handle scholarships and student applications.
- **User Account Management**: Manage user accounts for students, teachers, and administrators.
- **Assignment and Exam Management**: Manage assignments, exams, and results.
- **Feedback System**: Collect and store feedback from students about courses and teachers.

## Database Schema

### Tables

1. **Students**
   - `StudentID` (INT, Primary Key, Auto Increment)
   - `FirstName` (VARCHAR(50))
   - `LastName` (VARCHAR(50))
   - `DOB` (DATE)
   - `Gender` (VARCHAR(10))
   - `Address` (VARCHAR(255))
   - `PhoneNumber` (VARCHAR(15))
   - `Email` (VARCHAR(100))
   - `EnrollmentDate` (DATE)
   - `DepartmentID` (INT, Foreign Key)
   - `CourseID` (INT, Foreign Key)

2. **Teachers**
   - `TeacherID` (INT, Primary Key, Auto Increment)
   - `FirstName` (VARCHAR(50))
   - `LastName` (VARCHAR(50))
   - `DOB` (DATE)
   - `Gender` (VARCHAR(10))
   - `Address` (VARCHAR(255))
   - `PhoneNumber` (VARCHAR(15))
   - `Email` (VARCHAR(100))
   - `HireDate` (DATE)
   - `DepartmentID` (INT, Foreign Key)

3. **Courses**
   - `CourseID` (INT, Primary Key, Auto Increment)
   - `CourseName` (VARCHAR(100))
   - `CourseDescription` (TEXT)
   - `Credits` (INT)
   - `DepartmentID` (INT, Foreign Key)
   - `TeacherID` (INT, Foreign Key)

4. **Departments**
   - `DepartmentID` (INT, Primary Key, Auto Increment)
   - `DepartmentName` (VARCHAR(100))
   - `DepartmentHead` (INT, Foreign Key)

5. **Enrollments**
   - `EnrollmentID` (INT, Primary Key, Auto Increment)
   - `StudentID` (INT, Foreign Key)
   - `CourseID` (INT, Foreign Key)
   - `EnrollmentDate` (DATE)

6. **Grades**
   - `GradeID` (INT, Primary Key, Auto Increment)
   - `StudentID` (INT, Foreign Key)
   - `CourseID` (INT, Foreign Key)
   - `Grade` (VARCHAR(2))
   - `GradeDate` (DATE)

7. **Classrooms**
   - `ClassroomID` (INT, Primary Key, Auto Increment)
   - `BuildingName` (VARCHAR(100))
   - `RoomNumber` (VARCHAR(10))
   - `Capacity` (INT)

8. **Schedules**
   - `ScheduleID` (INT, Primary Key, Auto Increment)
   - `CourseID` (INT, Foreign Key)
   - `ClassroomID` (INT, Foreign Key)
   - `DayOfWeek` (VARCHAR(10))
   - `StartTime` (TIME)
   - `EndTime` (TIME)

9. **Attendance**
   - `AttendanceID` (INT, Primary Key, Auto Increment)
   - `StudentID` (INT, Foreign Key)
   - `CourseID` (INT, Foreign Key)
   - `Date` (DATE)
   - `Status` (VARCHAR(10))

10. **Exams**
    - `ExamID` (INT, Primary Key, Auto Increment)
    - `CourseID` (INT, Foreign Key)
    - `ExamDate` (DATE)
    - `ExamType` (VARCHAR(50))

11. **Results**
    - `ResultID` (INT, Primary Key, Auto Increment)
    - `StudentID` (INT, Foreign Key)
    - `ExamID` (INT, Foreign Key)
    - `MarksObtained` (INT)
    - `ResultDate` (DATE)

12. **Fees**
    - `FeeID` (INT, Primary Key, Auto Increment)
    - `StudentID` (INT, Foreign Key)
    - `Amount` (DECIMAL(10, 2))
    - `DueDate` (DATE)
    - `PaymentDate` (DATE)
    - `Status` (VARCHAR(10))

13. **Library**
    - `BookID` (INT, Primary Key, Auto Increment)
    - `Title` (VARCHAR(255))
    - `Author` (VARCHAR(100))
    - `ISBN` (VARCHAR(20))
    - `Publisher` (VARCHAR(100))
    - `YearPublished` (YEAR)
    - `CopiesAvailable` (INT)

14. **Staff**
    - `StaffID` (INT, Primary Key, Auto Increment)
    - `FirstName` (VARCHAR(50))
    - `LastName` (VARCHAR(50))
    - `DOB` (DATE)
    - `Gender` (VARCHAR(10))
    - `Address` (VARCHAR(255))
    - `PhoneNumber` (VARCHAR(15))
    - `Email` (VARCHAR(100))
    - `HireDate` (DATE)
    - `DepartmentID` (INT, Foreign Key)

15. **Events**
    - `EventID` (INT, Primary Key, Auto Increment)
    - `EventName` (VARCHAR(100))
    - `EventDate` (DATE)
    - `Location` (VARCHAR(255))
    - `Description` (TEXT)

16. **Alumni**
    - `AlumniID` (INT, Primary Key, Auto Increment)
    - `FirstName` (VARCHAR(50))
    - `LastName` (VARCHAR(50))
    - `GraduationYear` (YEAR)
    - `CurrentJob` (VARCHAR(100))
    - `Email` (VARCHAR(100))
    - `PhoneNumber` (VARCHAR(15))

17. **Hostel**
    - `HostelID` (INT, Primary Key, Auto Increment)
    - `StudentID` (INT, Foreign Key)
    - `RoomNumber` (VARCHAR(10))
    - `CheckInDate` (DATE)
    - `CheckOutDate` (DATE)

18. **Transport**
    - `TransportID` (INT, Primary Key, Auto Increment)
    - `StudentID` (INT, Foreign Key)
    - `Route` (VARCHAR(100))
    - `PickupPoint` (VARCHAR(100))
    - `DropPoint` (VARCHAR(100))

19. **Notices**
    - `NoticeID` (INT, Primary Key, Auto Increment)
    - `Title` (VARCHAR(100))
    - `Description` (TEXT)
    - `Date` (DATE)

20. **UserAccounts**
    - `UserID` (INT, Primary Key, Auto Increment)
    - `Username` (VARCHAR(50))
    - `Password` (VARCHAR(255))
    - `Role` (VARCHAR(20))

21. **Assignments**
    - `AssignmentID` (INT, Primary Key, Auto Increment)
    - `CourseID` (INT, Foreign Key)
    - `Title` (VARCHAR(100))
    - `Description` (TEXT)
    - `DueDate` (DATE)
    - `SubmissionDate` (DATE)

22. **Subjects**
    - `SubjectID` (INT, Primary Key, Auto Increment)
    - `SubjectName` (VARCHAR(100))
    - `CourseID` (INT, Foreign Key)

23. **Timetable**
    - `TimetableID` (INT, Primary Key, Auto Increment)
    - `CourseID` (INT, Foreign Key)
    - `SubjectID` (INT, Foreign Key)
    - `DayOfWeek` (VARCHAR(10))
    - `StartTime` (TIME)
    - `EndTime` (TIME)
    - `ClassroomID` (INT, Foreign Key)

24. **ExamSchedules**
    - `ExamScheduleID` (INT, Primary Key, Auto Increment)
    - `ExamID` (INT, Foreign Key)
    - `SubjectID` (INT, Foreign Key)
    - `ExamDate` (DATE)
    - `StartTime` (TIME)
    - `EndTime` (TIME)
    - `ClassroomID` (INT, Foreign Key)

25. **Clubs**
    - `ClubID` (INT, Primary Key, Auto Increment)
    - `ClubName` (VARCHAR(100))
    - `ClubDescription` (TEXT)
    - `PresidentID` (INT, Foreign Key)

26. **ClubMembers**
    - `ClubMemberID` (INT, Primary Key, Auto Increment)
    - `ClubID` (INT, Foreign Key)
    - `StudentID` (INT, Foreign Key)

27. **Scholarships**
    - `ScholarshipID` (INT, Primary Key, Auto Increment)
    - `ScholarshipName` (VARCHAR(100))
    - `Description` (TEXT)
    - `Amount` (DECIMAL(10, 2))
    - `EligibilityCriteria` (TEXT)

28. **Applications**
    - `ApplicationID` (INT, Primary Key, Auto Increment)
    - `ScholarshipID` (INT, Foreign Key)
    - `StudentID` (INT, Foreign Key)
    - `ApplicationDate` (DATE)
    - `Status` (VARCHAR(20))

29. **Feedback**
    - `FeedbackID` (INT, Primary Key, Auto Increment)
    - `StudentID` (INT, Foreign Key)
    - `CourseID` (INT, Foreign Key)
    - `TeacherID` (INT, Foreign Key)
    - `FeedbackText` (TEXT)
    - `Rating` (INT)
    - `Date` (DATE)

## Getting Started

### Prerequisites

- MySQL Server
- MySQL Workbench 


