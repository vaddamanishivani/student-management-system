#student-management-system
import java.util.ArrayList;
import java.util.Scanner;





class Student {
    String id, name;
    Student(String id, String name) { this.id = id; this.name = name; }
    public String toString() { return id + " - " + name; }
}
public class StudentManagementSystem {
    static ArrayList<Student> students = new ArrayList<>();
    static Scanner scanner = new Scanner(System.in);
 public static void main(String[] args) {
        while (true) {
            System.out.println("1. Add 2. View 3. Delete 4. Exit");
            switch (scanner.nextInt()) {
                case 1 -> addStudent();
                case 2 -> viewStudents();
                case 3 -> deleteStudent();
                case 4 -> { return; }
                default -> System.out.println("Invalid option.");
            }
        }
    }
static void addStudent() {
        System.out.print("ID: "); String id = scanner.next();
        System.out.print("Name: "); String name = scanner.next();
        students.add(new Student(id, name));
    }
    static void viewStudents() {
        for (Student student : students) System.out.println(student);
    }
    static void deleteStudent() {
        System.out.print("ID: ");
        students.removeIf(s -> s.id.equals(scanner.next()));
    }
}
