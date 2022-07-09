import java.util.Scanner;

public class Urok7 {
    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        System.out.println("Imput sum 1");
        int a = scan.nextInt();
        System.out.println("Imput sum 2");
        int b = scan.nextInt();
        System.out.println("Imput sum 3");
        int c = scan.nextInt();
        int result = sum(a,b,c);
        System.out.println("summa vashyh chisel =" + result);
    }
    static int sum(int a, int b, int c) {
        return a+b+c;
    }
}
