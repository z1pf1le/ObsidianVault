[[Статические методы]]

Данный метод применяется для конкатенации потоковю То есть объединение двух потоков в один поток. Если используются потоки с сохранением порядка, то данные потока Б следуют после данных потока А.

```java
import java.util.List;  
import java.util.stream.Stream;  
  
public class Main{  
  
    public static void main(String[] args) {  
        List<String> list1 = List.of("0", "2", "4", "6");  
        List<String> list2 = List.of("a", "b", "c", "d");  
  
        Stream<String> stream1 = list1.stream();  
        Stream<String> stream2 = list2.stream();  
  
        Stream<String> concatStream = Stream.concat(stream1, stream2);  
  
        concatStream.forEach(System.out::println);  
    }  
}
```