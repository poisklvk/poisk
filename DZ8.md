public class Person {
    int age;
    String fullName;
    Person (int age, String fullName) {
        this.age = age;
        this.fullName = fullName;
    }
    Person () {

    }
        static void talk(String fullName)  {
        System.out.println(fullName+" talk");
    }
    static void move(String fullName) {
        System.out.println(fullName+ " moves");
    }
}


public class Main {
    public static void main (String[] args) {
        Person child = new Person(10,"Maria");
        Person man = new Person();
    }
}
