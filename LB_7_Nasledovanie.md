public class Student {
    String firstName;
    String lastName;
    String group;
    double averageMark;
public Student (String firstName, String lastName, String group, double averageMark) {
    this.firstName = firstName;
    this.lastName = lastName;
    this.group = group;
    this.averageMark = averageMark;
}
int getScholarship () {
    if(this.averageMark==5)
        return 100;
    else
        return 80;
}
}



public class Aspirant extends Student {
    String scientific;


    public Aspirant(String firstName, String lastName, String group, double averageMark, String scientific) {
        super(firstName, lastName, group, averageMark);
        this.scientific = scientific;

    }

    int getScholarship () {
        if(this.averageMark==5)
            return 200;
        else
            return 180;
    }
}





public class Main {
    public static void main (String[] args) {
    Student Ivanov = new Student("Ivanov", "Ivan", "new", 4);
        System.out.println(Ivanov.getScholarship());
    Student Petrov = new Aspirant("Petrov", "Petr", "old", 5, "Sun");
        System.out.println(Petrov.getScholarship());
        System.out.println (Ivanov.firstName + " , "+ Ivanov.averageMark + " , " + Ivanov.getScholarship());


        }


            }



