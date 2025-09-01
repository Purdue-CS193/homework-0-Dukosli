# Aydan's First CS193 Homework
- Yeah so you see 
- All the things I like
- I love that all my friends (like 6 people) are all in 193 together
```
import java.io.BufferedWriter;
import java.io.File;
import java.io.FileWriter;

public class It {
    public static void main(String[] args) {
        try {
            File n = new File("./src/If.java");
            FileWriter f = new FileWriter(n);
            BufferedWriter bw = new BufferedWriter(f);

            if (n.createNewFile()) {
                System.out.println("Yeah");
            }

            bw.write(String.format("""
                    import java.util.Scanner;

                    public class If {
                        public static void main(String[] args) {
                            Scanner sc = new Scanner(System.in);
                            int c = sc.nextInt();

                            System.out.println(isEven(c));
                            sc.close();
                        }

                        static boolean isEven(int n) {
                    """));

            for (int i = -42; i <= 67; i++) {
                bw.write(String.format("\t\tif (n == %d) {\n\t\t", i));
                if (i%2 == 0) {
                    bw.write("\treturn true;");
                } else {
                    bw.write("\treturn false;");
                }
                bw.write(String.format("\n\t\t}\n"));
            }

            bw.write(String.format("""
                        return false;
                        }
                    }
                    """));


            bw.close();
            f.close();
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}

```