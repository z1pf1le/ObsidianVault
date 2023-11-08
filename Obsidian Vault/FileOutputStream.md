[[Сериализация]]

```java
import java.io.*;

public class Main {

   public static void main(String[] args) throws IOException {


       File file = new File("/home/andrei/FileOutputStreamtest.txt");
       FileOutputStream fileOutputStream = new FileOutputStream(file);

       String greetings = "Привет! Добро пожаловать на JavaRush - лучший сайт для тех, кто хочет стать программистом!";

       fileOutputStream.write(greetings.getBytes());

       fileOutputStream.close();
   }
}
```

Главное назначение класса FileOutputStream — запись байтов в файл.