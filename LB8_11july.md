import javax.xml.namespace.QName;

public class Polzovateli {
    String name;
    int old;

    public Polzovateli (String name, int old) {
     this.name = name;
     this.old = old;

 }
}


public interface Taker {
public void found();
public void take ();
public void report();

}

public interface deliver {
    public void order();
    
}


public interface Order {
    public void order ();
}


public interface Takeandreturn {
    public void take();
    public void returns();
}

public class Reader extends Polzovateli implements Takeandreturn{

    public Reader(String name, int old) {
        super(name, old);
    }

    @Override
    public void take() {
        System.out.println("I take this book");
    }

    @Override
    public void returns() {
        System.out.println("I return this book");
    }

}


public class Librarian extends Polzovateli implements Order {
    public Librarian (String name, int old) {
        super(name,old);
    }

    @Override
    public void order() {
        System.out.println("five books, please");

    }
}


public class DeliveryBooks extends Polzovateli implements Order{

    public DeliveryBooks(String name, int old) {
        super(name, old);
    }
    @Override
    public void order() {
        System.out.println("You need this books!");

    }
}


public class Administrator extends Polzovateli implements Taker {


    public Administrator(String name, int old) {
        super(name, old);
    }

    @Override
    public void found() {
      System.out.println("Nadya! Found me red book!");
    }

    @Override
    public void take() {
        System.out.println("take this book, please");

    }

    @Override
    public void report() {
        System.out.println("Attention! You have to book for 3 days already! You are a criminal!");

    }
}


public class Main {
    public static void main(String[] args) {
        Librarian librarian = new Librarian("Anna", 70);
        Reader reader = new Reader("Vanyusha", 10);
        DeliveryBooks deliveryBooks = new DeliveryBooks("Fyodor", 40);
        Administrator administrator = new Administrator("Agafya Tyhonovna", 90);
        reader.take();
        administrator.found();
        administrator.take();
        librarian.order();
        deliveryBooks.order();
        administrator.report();
        reader.returns();
    }
}




