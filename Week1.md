# Code

```java
import java.util.Scanner;
class Student {
    String USN, name;
    void accept() {
        Scanner s = new Scanner(System.in);
        System.out.print("Enter USN: ");
        USN = s.nextLine();
        System.out.print("Enter name: ");
        name = s.nextLine();
    }
    void display() {
        System.out.println("USN and Name: " + USN + " " + name);
    }
}
class StudentRun {
    public static void main(String args[]) {
        Scanner s = new Scanner(System.in);
        System.out.print("Enter no of students: ");
        int n = s.nextInt();
        s.nextLine();
        Student st[] = new Student[n];
        for (int i = 0; i < n; i++) {
            st[i] = new Student();
            st[i].accept();
        }
        for (int i = 0; i < n; i++) {
            st[i].display();
        }
    }
}
```

# Output

```
Enter no of students: 2
Enter USN: 159
Enter name: Mrudhul
Enter USN: 157
Enter name: Monish
USN and Name: 159 Mrudhul
USN and Name: 157 Monish
```
