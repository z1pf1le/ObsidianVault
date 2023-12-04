[[Промежуточные методы]]

**Stream flatMapToInt(Function mapper)** returns an IntStream consisting of the results of replacing each element of this stream with the contents of a mapped stream produced by applying the provided mapping function to each element. Stream flatMapToInt(Function mapper) is an _**intermediate operation**_. These operations are always lazy. Intermediate operations are invoked on a Stream instance and after they finish their processing, they give a Stream instance as output.

```java
import java.util.Arrays;  
import java.util.stream.IntStream;  
  
public class Main{  
    public static void main(String[] args) {  
        String[] arr = new String[] {"C", "Java", "Python"};  
  
        IntStream stream = Arrays.stream(arr).flatMapToInt(n -> n.codePoints());  
  
        stream.forEach(System.out::println);  
    }  
}
```

В примере на основе каждый строки порождается поток примитивных типов(интов).

