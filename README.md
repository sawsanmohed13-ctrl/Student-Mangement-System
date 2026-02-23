# Student-Mangement-System
1
public class Student {
    private int id;
    private String name;
    private int grade;

    private static String universityName;
    private static int studentCount = 0;

    static {
        universityName = "Global Tech University";
        System.out.println("University data has been loaded");
    }

    public Student() {
        this.id = 0;
        this.name = "Default";
        this.grade = 0;
        studentCount++;
    }

    public Student(int id, String name, int grade) {
        this.id = id;
        this.name = name;
        this.grade = grade;
        studentCount++;
    }

    public Student(Student s) {
        this.id = s.id;
        this.name = s.name;
        this.grade = s.grade;
        studentCount++;
    }

    public void displayInfo() {
        System.out.println("ID: " + id + ", Name: " + name + ", Grade: " + grade);
    }

    public void updateGrade(int newGrade) {
        this.grade = newGrade;
    }

    public static void printUniversityName() {
        System.out.println("University Name: " + universityName);
    }

    public static void printStudentCount() {
        System.out.println("Total Students: " + studentCount);
    }

    public static void printStudent(Student s) {
        s.displayInfo();
    }

    public static Student createTopStudent(Student s) {
        return new Student(s.id, s.name, s.grade + 10);
    }
}

public class Main {
    public static void main(String[] args) {
        Student s1 = new Student();
        Student s2 = new Student(101, "Sawsan", 85);
        Student s3 = new Student(s2);

        s1.displayInfo();
        s2.displayInfo();
        s3.displayInfo();

        s2.updateGrade(90);
        
        Student.printUniversityName();
        Student.printStudentCount();
        
        Student.printStudent(s2);

        Student topStudent = Student.createTopStudent(s2);
        topStudent.displayInfo();
    }
}
