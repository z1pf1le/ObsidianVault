[[List]]
[[Deque]]


Двусвязонный список

В LinkedList элементы фактически представляют собой звенья одной цепи. У каждого элемента помимо тех данных, которые он хранит, имеется ссылка на предыдущий и следующий элемент. По этим ссылкам можно переходить от одного элемента к другому.

```java
import java.util.LinkedList;
public class Main {

   public static void main(String[] args) {

       String str1 = new String("Hello World!");
       String str2 = new String("My name is Earl");
       String str3 = new String("I love Java");
       String str4 = new String("I live in Moscow");

       LinkedList<String> earlBio = new LinkedList<>();
       earlBio.add(str1);
       earlBio.add(str2);
       earlBio.add(str3);
       earlBio.add(str4);

       System.out.println(earlBio);

   }
}
```