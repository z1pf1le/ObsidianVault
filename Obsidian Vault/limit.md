[[Промежуточные методы]]

limit(long n) применяется для выборки первых n элементов потоков. Этот метод также возвращает модифицированный поток, в котором не более n элементов.


```java
import java.util.stream.Stream;  
  
public class limitEx{  
    public static void main(String[] args) {  
        Stream<String> phoneStream = Stream.of("iPhone 6 S", "Lumia 950", "Samsung Galaxy S 6", "LG G 4","Nexus 7");

phoneStream.skip(1)

    .limit(2)

    .forEach(s->System.out.println(s)); // Lumia 950 Samsung Galaxy S 6
    }  
}  

class Phone{  
    String name;  
    Integer price;  
  
    public Phone(String name, Integer price) {  
        this.name = name;  
        this.price = price;  
    }  
  
    public String getName() {  
        return name;  
    }  
  
    public Integer getPrice() {  
        return price;  
    }  
}
```