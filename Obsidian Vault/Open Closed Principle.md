[[Solid]]

Принцип открытости/закрытости
программные сущности (классы, модули, функции и т.п.) должны быть открыты для расширения, но закрыты для изменения. Расширение с помощью наследников (не меняя сущности родителя).

```java
public class Main {  
    public static void main (String[] args) {  
        Computer anus = new Computer("sfinkter", 1488);  
        SaveInerface saver = new SaveComputerToFile();  
        SaveInerface saver2 = new SaveComputerToDB();  
        saver.save("out.dat", anus);  
        saver2.save("out.dat", anus);  
    }  
}  
class Computer{  
    String name;  
    int memory_size;  
    Computer(String name, int memory_size) {  
        this.name = name;  
        this.memory_size = memory_size;  
    }  
}  
class SaveComputerToFile implements SaveInerface{  
    public void save(String path, Computer cmp) {  
        System.out.println("saving to file " + path +" " + cmp);  
    }  
}  
  
class SaveComputerToDB implements SaveInerface{  
    public void save(String path, Computer cmp) {  
        System.out.println("saving to DB " + path +" " + cmp);  
    }  
}  
interface SaveInerface {  
    void save(String path, Computer cmp);  
}
```

Поведение наследующих классов не должно противоречить поведению заданному базовым классом.


