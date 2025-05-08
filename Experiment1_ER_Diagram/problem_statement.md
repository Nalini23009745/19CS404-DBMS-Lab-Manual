# Experiment 1: Entity-Relationship (ER) Diagram

## 🎯 Objective:
To understand and apply the concepts of ER modeling by creating an ER diagram for a real-world application.

## 📚 Purpose:
The purpose of this workshop is to gain hands-on experience in designing ER diagrams that visually represent the structure of a database including entities, relationships, attributes, and constraints.

---

## 🧪 Choose One Scenario:

### 🔹 Scenario 1: University Database
Design a database to manage students, instructors, programs, courses, and student enrollments. Include prerequisites for courses.

**User Requirements:**
- Academic programs grouped under departments.
- Students have admission number, name, DOB, contact info.
- Instructors with staff number, contact info, etc.
- Courses have number, name, credits.
- Track course enrollments by students and enrollment date.
- Add support for prerequisites (some courses require others).

---

### 🔹 Scenario 2: Hospital Database
Design a database for patient management, appointments, medical records, and billing.

**User Requirements:**
- Patient details including contact and insurance.
- Doctors and their departments, contact info, specialization.
- Appointments with reason, time, patient-doctor link.
- Medical records with treatments, diagnosis, test results.
- Billing and payment details for each appointment.

---

## 📝 Tasks:
1. Identify entities, relationships, and attributes.
2. Draw the ER diagram using any tool (draw.io, dbdiagram.io, hand-drawn and scanned).
3. Include:
   - Cardinality & participation constraints
   - Prerequisites for University OR Billing for Hospital
4. Explain:
   - Why you chose the entities and relationships.
   - How you modeled prerequisites or billing.

# ER Diagram Submission - Student Name
Nalini P -212223220063
## Scenario Chosen:
University / Hospital (choose one)

## ER Diagram:
![image (5)](https://github.com/user-attachments/assets/0cde9609-3b07-4385-affb-41084e5d3898)


## Entities and Attributes:
 1.Student
Attributes:

  * StudentID (Primary Key)
  * Name
  * DOB (Date of Birth)
  * Gender
  * Address
  * Phone
  * Email

 2.Enrollment
Attributes:

  * EnrollmentID (Primary Key)
  * StudentID (Foreign Key)
  * CourseID (Foreign Key)
  * Department
  * Grade
  * EnrollDate

3.Course
Attributes:

  * CourseID (Primary Key)
  * CourseName
  * Department
  * Credits

4.Instructor
Attributes:

  * InstructorID (Primary Key)
  * Name
  * Department
  * Phone
  * Email

 5.Department
Attributes:

  * DepartmentID (Primary Key)
  * DepartmentName
  * HeadOfDepartment

6. Classroom
Attributes:

  * ClassroomID (Primary Key)
  * RoomNumber
  * Building
  * Capacity

 7.Schedule
Attributes:

  * ScheduleID (Primary Key)
  * CourseID (Foreign Key)
  * InstructorID (Foreign Key)
  * ClassroomID (Foreign Key)
  * Time
  * Day




## Relationships and Constraints:

1.Enrollment

Entities Involved:Student, Course
Cardinality: Many-to-Many (A student can enroll in many courses, a course can have many students)
Participation:
Student:Total (each enrollment must have a student)
Course:Total (each enrollment must refer to a course)

 2. Teachers

Entities Involved:Instructor, Course
Cardinality: Many-to-Many (An instructor can teach multiple courses, a course can be taught by multiple instructors)
Participation:
Instructor:Partial
Course:Partial

3.Belongs

Entities Involved:Course, Department
Cardinality:Many-to-One (Many courses belong to one department)
Participation:
Course:Total
Department: Partial

4.Schedule

Entities Involved:Course, Instructor, Classroom
Cardinality:
One course is scheduled with one instructor in one classroom at a time (assumes composite relationship)
Participation:
Course, Instructor, Classroom:** Total (each schedule must have all three)

5.HeadOfDepartment

Entities Involved:Instructor, Department
Cardinality:One-to-One (Each department has one head instructor)
Participation:
Department:Total
Instructor: Partial



## Extension (Prerequisite / Billing):

prerequisite (Extension Points)

1. Self-Relationship on Course:

   * Add a new relationship called **`Prerequisite`** between the `Course` entity and itself.

2. Roles:

   * One side represents the **main course**, the other the **prerequisite course**.

3. Cardinality:

   * A course can have zero or more prerequisites.
   * A course can be a prerequisite for multiple other courses.

4. Participation:

   * Partial on both sides (not all courses need or serve as prerequisites).

5. (Optional):

   * Add an attribute like `PrerequisiteType` or `Condition` if needed.

Billing 

1. New Entity: `Billing`

   * Attributes: `BillingID`, `StudentID`, `Amount`, `BillingDate`, `Status`, `PaymentMethod`.

2. Relationship: `Pays`

   * Connect `Student` to `Billing` through a `Pays` relationship.

3. Cardinality:

   * A student can have many billing records.
   * Each bill is tied to one student.

4. Participation:

    Partial for `Student` (some may not have bills yet).
    Total for `Billing` (each billing must be for a student).


## Design Choices:

Use of separate entities for Enrollment, Schedule, and Billing: helps normalize many-to-many relationships and maintain relational integrity between students, courses, and financial records.

Department as a central entity: provides a logical way to group students, instructors, and courses, ensuring consistent assignment and easy management.

Classroom and Schedule entities include scheduling details:effectively separating course content from its time, location, and instructor, allowing for flexible timetable management.

Self-relationship on Course for Prerequisites:enables tracking of course dependencies without redundancy, supporting academic planning.

Instructor–Department and Instructor–Course relationships:are modular, allowing one instructor to teach multiple courses and serve as head of a department, if needed.

The design is modular and extensible:supporting future additions like prerequisites, billing, attendance tracking, or grading systems without major changes to the existing schema.

## RESULT
Thus, the Entity-Relationship (ER) Diagram have been created successfully.
