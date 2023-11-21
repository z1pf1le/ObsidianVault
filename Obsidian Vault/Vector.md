[[List]]

```java
import java.util.Vector;  
public class VectorExample {  
    Vector vector=new Vector();  
    public void addCharacterandPrint(){  
        vector.add("Weasley");  
        vector.add("Potter");  
        for(int i=0;i<vector.size();i++){  
            System.out.println("The characters are\t"+vector.get(i));  
        }  
    }  
    public static void main(String args[]){  
        VectorExample example=new VectorExample();  
        example.addCharacterandPrint();  
    }  
}
```

Вышеприведенный код, является всего лишь небольшим образцом, приведенным в качестве доказательства того, что нет большой разницы между коллекциями `ArrayList` и `Vector`. Коллекцией `Vector` можно манипулировать также, как и коллекцией `ArrayList`, используя те же методы.