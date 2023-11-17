[[Collection]]

интерфейс

**List (список)** представляет собой коллекцию, в которой допустимы дублирующие значения. Элементы такой коллекции пронумерованы, начиная от нуля, к ним можно обратиться по индексу.

```java
import java.util.ArrayList;
import java.util.List;

public class ListExample {
    public static void main(String[] args) {
        // Создаем объект типа List
        List<String> fruits = new ArrayList<>();

        // Добавляем элементы в список
        fruits.add("Apple");
        fruits.add("Banana");
        fruits.add("Orange");

        // Получаем размер списка
        int size = fruits.size();
        System.out.println("Размер списка: " + size);

        // Получаем элементы списка по индексу
        String firstFruit = fruits.get(0);
        String lastFruit = fruits.get(size - 1);
        System.out.println("Первый фрукт: " + firstFruit);
        System.out.println("Последний фрукт: " + lastFruit);

        // Проверяем наличие элемента в списке
        boolean hasMango = fruits.contains("Mango");
        System.out.println("Есть ли манго в списке? " + hasMango);

        // Удаляем элемент из списка
        fruits.remove("Banana");
        System.out.println("Список после удаления банана: " + fruits);

        // Очищаем список
        fruits.clear();
        System.out.println("Список после очистки: " + fruits);
    }
}
```