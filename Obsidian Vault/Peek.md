[[Статические методы]]

Конечно! Метод `peek()` в Java используется для просмотра (но не извлечения) элемента на вершине стека или на первой позиции очереди. Вот пример использования `peek()`:

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        // Создание стека
        Stack<Integer> stack = new Stack<>();

        // Добавление элементов в стек
        stack.push(3);
        stack.push(5);
        stack.push(7);

        // Просмотр элемента на вершине стека с помощью метода peek()
        int peekedElement = stack.peek();
        System.out.println("Элемент на вершине стека: " + peekedElement);

        // Вывод содержимого стека
        System.out.println("Содержимое стека: " + stack);
    }
}
```

Этот код создает стек, добавляет в него несколько элементов, затем использует `peek()` для просмотра элемента на вершине стека без его извлечения.