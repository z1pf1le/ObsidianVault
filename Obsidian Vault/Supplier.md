
[[Статические методы]]

Данный метод применяется для создания бесконечного потока данных на основании данных генерируемых с помощью реализации Supplier.
Внимание: созданный поток бусконечен, поэтому в случае необходимости собрать данные потока в структуру данных его необходимо ограничить(например при помощи метода limit).

https://www.youtube.com/watch?v=P_MZQhMsiDA&list=PLtNPgSbW9TX5IQAKzgrJnaayjaDoCjkio&index=25

остановился на 13:20

```java
import java.util.List;  
import java.util.function.Supplier;  
import java.util.stream.Collectors;  
import java.util.stream.Stream;  
  
public class Main{  
    public static void main(String[] args) {  
        Stream<Integer> stream = Stream.generate(getRandomNumber(1,20)); //создание бесконечного потока  
        List<Integer> list =stream.limit(20).collect(Collectors.toList()); //остановка потока  
  
        System.out.println(list);  
  
    }  
  
    public static Supplier<Integer> getRandomNumber(int start, int end){ //реализация интерфейса для дальнейшего использования  
        class RandGen implements Supplier<Integer>{  
            @Override  
            public Integer get() {  
                return (int) ( start + Math.random() * ( end - start ) + 1 );  
            }  
        }  
        return new RandGen();  
    }  
}
```