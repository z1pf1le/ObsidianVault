[[Queue]]

https://www.examclouds.com/ru/java/java-core-russian/interface-queue

Интерфейс _Deque_ появился в Java 6. Он расширяет _Queue_ и описывает поведение двунаправленной очереди. Двунаправленная очередь может функционировать как стандартная очередь _FIFO_ либо как стек _LIFO_.

```java
import java.util.ArrayDeque;
import java.util.Deque;

public class ArrayDequeExample {
    public static void main(String[] args) {
        Deque<String> stack = new ArrayDeque<>();
        Deque<String> queue = new ArrayDeque<>(2);
        stack.push("A");
        stack.push("B");
        stack.push("C");
        stack.push("D");
        while (!stack.isEmpty()) {
            System.out.print(stack.pop() + " ");
        }
        System.out.println();

        queue.add("A");
        queue.add("B");
        queue.add("C");
        queue.add("D");
        while (!queue.isEmpty()) {
            System.out.print(queue.remove() + " ");
        }
    }
}
```