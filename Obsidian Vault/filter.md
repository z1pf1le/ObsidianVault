[[Промежуточные методы]]

Метод filter() является промежуточной операцией принимающей предикат, который фильтрует все элементы, возвращая только те, что соответствуют условию.


```java
import java.util.stream.Stream;  
  
public class filterEx{  
    public static void main(String[] args) {  
        Stream<String> citiesStream = Stream.of("Париж", "Лондон", "Мадрид","Берлин", "Брюссель");

citiesStream.filter(s->s.length()==6).forEach(s->System.out.println(s));
    }  
}  

```