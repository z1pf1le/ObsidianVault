[[Промежуточные методы]]

Метод создает на основании каждого элемента данных текущего потока новый поток, при это укладывая созданные потоки в единый.

```java

import java.util.Arrays;  
import java.util.List;  
import java.util.stream.Collectors;  
  
public class Main{  
    public static void main(String[] args) {  
       Singer singer1 = new Singer("Hoi", new String[]{"Lirika", "SElsky keif"});  
       Singer singer2 = new Singer("Tsoi", new String[]{"Kukushka", "Peremen", "Prohojy"});  
       Singer singer3 = new Singer("KiSH", new String[]{"Ohotnik", "Motorcycle>"});  
  
       Singer[] rockStars = new Singer[]{singer1,singer2,singer3};  
  
        List<String> song = Arrays.stream(rockStars)  
                .flatMap(n-> Arrays.stream(n.getSongs()))  
                .collect(Collectors.toList());  
  
        System.out.println(song);  
    }  
}

public class Singer{  
    private String name;  
    private String[] songs;  
  
    public Singer(String name, String[] songs) {  
        this.name = name;  
        this.songs = songs;  
    }  
  
    public String getName() {  
        return name;  
    }  
  
    public String[] getSongs() {  
        return songs;  
    }  
  
    @Override  
    public String toString() {  
        return "Singer{" +  
                "name='" + name + '\'' +  
                ", songs=" + Arrays.toString(songs) +  
                '}';  
    }  
}
```



```java
import java.util.stream.Stream;  
  
public class flatMapEx{  
    public static void main(String[] args) {  
        Stream<Phone> phoneStream = Stream.of(new Phone("iPhone 6 S", 54000), new Phone("Lumia 950", 45000),new Phone("Samsung Galaxy S 6", 40000));  
  
        phoneStream  
  
                .flatMap(p->Stream.of(String.format("название: %s  цена без скидки: %d", p.getName(), p.getPrice()), String.format("название: %s  цена со скидкой: %d", p.getName(),  
                        p.getPrice()-(int)(p.getPrice()*0.1))))  
  
                .forEach(s->System.out.println(s));  
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