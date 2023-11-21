[[Deque]]

ArrayDeque (также известный как «Array Double Ended Queue», произносится как «ArrayDeck») - это особый вид растущего массива, который позволяет нам добавлять или удалять элементы с обеих сторон.

Реализация ArrayDeque может использоваться как Stack (последний пришел-первый вышел) или Queue (первый пришел-первый вышел)

Под капотом ArrayDeque поддерживается массив, который удваивает свой размер при заполнении.

Первоначально, массив инициализируется с размером 16. Он реализован как двусторонняя очередь, где он поддерживает два указателя, а именно голову и хвост.

```java
import java.util.ArrayDeque;  
import java.util.Deque;  
  
public class ArrayDequeExample {  
    public static void main(String[] args) {  

        Deque<Integer> anus = new ArrayDeque();  
        for(int i = 0; i < 5; i++){  
            anus.add(i);  
            System.out.println(anus);  
        }  
        for(int i = 0; i < 5; i++){  
            anus.push(i);  
            System.out.println(anus);  
        }  
        System.out.println(anus);  
    }  
}
```