[[IOException]]

Конструкция _try with resources_, также известная как try-with-resources, представляет собой механизм обработки исключений в Java, который может автоматически закрывать такие ресурсы, как Java InputStream или JDBC Connection, после завершения работы с ними.

```java
import java.io.File;  
import java.io.FileNotFoundException;  
import java.io.FileOutputStream;  
import java.util.Scanner;  
  
public class Main{  
    public static void main(String[] args)  {  
        try (Scanner scanner = new Scanner(new File("/home/andrei/Desktop/test"))) {  
            while (scanner.hasNext()) {  
                System.out.println(scanner.nextLine());  
            }  
        } catch (FileNotFoundException fnfe) {  
            fnfe.printStackTrace();  
        }  
    }  
}
```