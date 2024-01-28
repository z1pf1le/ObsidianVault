[[Промежуточные методы]]

Для простой сортировки по возрастанию применяется метод sorted(). Подходит только для сортировки тех объектов, которые реализуют интерфейс Comparable.

Если же у нас классы объектов не реализуют этот интерфейс или мы хотим создать какую-то свою логику сортировки, то мы можем использовать другую версию метода sorted(), которая в качестве параметра принимает компаратор.


```java
import java.util.ArrayList;  
import java.util.Collections;  
import java.util.Comparator;  
import java.util.List;  
  
public class Main{  
    public static void main(String[] args) {  
        List<User> users = new ArrayList<>();  
        users.add(new User(3, "A"));  
        users.add(new User(2, "B"));  
        users.add(new User(1, "C"));  
  
        // Создание компаратора для сравнения объектов по полю id  
        Comparator<User> idComparator = Comparator.comparingInt(User::getId);  
  
        // Сортировка объектов с использованием компаратора  
        List<User> sortedUsers = new ArrayList<>(users);  
        sortedUsers.sort(idComparator);  
  
        // Вывод отсортированных объектов  
        for (User user : sortedUsers) {  
            System.out.println(user.toString());  
        }  
    }  
}  
  
class User {  
    private int id;  
    private String name;  
  
    public User(int id, String name) {  
        this.id = id;  
        this.name = name;  
    }  
  
    public int getId() {  
        return id;  
    }  
  
    @Override  
    public String toString() {  
        return "User{" +  
                "id=" + id +  
                ", name='" + name + '\'' +  
                '}';  
    }  
}

```