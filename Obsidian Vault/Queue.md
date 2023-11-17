[[Collection]]

Интерфейс _Queue_ расширяет _Collection_ и объявляет поведение очередей, которые представляют собой список с дисциплиной "первый вошел, первый вышел" (_FIFO_). Существуют разные типы очередей, в которых порядок основан на некотором критерии. Очереди не могут хранить значения _null_.

https://www.examclouds.com/ru/java/java-core-russian/interface-queue



```java
import java.util.LinkedList;
import java.util.Queue;

public class QueueExample {
    public static void main(String[] args) {
        Queue<String> queue = new LinkedList<>();
        queue.offer("Харьков");
        queue.offer("Киев");
        queue.offer("Кременчуг");
        queue.offer("Львов");

        String town;
        while ((town = queue.poll()) != null) {
            System.out.println(town);
        }
    }
}
```