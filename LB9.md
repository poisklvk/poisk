import java.io.*;
public class Main {
    public static void main(String[] args) throws IOException {
        File dir = new File("C://Filess", "222.txt");
        boolean result = dir.createNewFile();
        File dir1 = new File("C://Filess", "333.txt");
        boolean result1 = dir1.createNewFile();

        String str = "Hello ";
        String str2 = "World!";
        FileOutputStream fos = new FileOutputStream("C://Filess/222.txt");
        byte[] buffer = str.getBytes();
        fos.write(buffer);
        buffer = str2.getBytes();
        fos.write(buffer);

        String str3 = "Good ";
        String str4 = "day!!!!";
        FileOutputStream fos1 = new FileOutputStream("C://Filess/333.txt");
        byte[] buffer1 = str3.getBytes();
        fos1.write(buffer1);
        buffer1 = str4.getBytes();
        fos1.write(buffer1);

        FileInputStream fin = new FileInputStream("C://Filess/333.txt");
        int i = -1;
        String strMove = "";
        while ((i = fin.read()) != -1)
            strMove += (char) i;
        String[] strMoveArray = strMove.split("\n");

        PrintStream ps2 = new PrintStream(fos);
        for (i = 0; i < strMoveArray.length; i++) {
            ps2.println(strMoveArray[i]
                    + strMoveArray[i].length());


        }
    }
}
