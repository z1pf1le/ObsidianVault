
[Статические методы]

Данный метод применяется для создания пустого потока. Создается поток, в котором отсутствуют элементы данных.

```java
import java.util.List;  
import java.util.stream.Stream;  
  
public class Main{  
  
    public static void main(String[] args) {  

  
        Stream<String> stream1 = Stream.empty();  
 
  
		stream1.forEach(n->System.out.println(n)); 
    }  
}
```