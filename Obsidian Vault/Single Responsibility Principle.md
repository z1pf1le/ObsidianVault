[[Solid]]

Принцип единственной ответственности


```java
public class Main {  
    public static void main (String[] args) {  
        Computer anus = new Computer("sfinkter", 1488);  
        SaveComputer saver = new SaveComputer();  
        saver.saveToFile("out.dat", anus);  
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
class SaveComputer {  
    void saveToFile(String path, Computer cmp) {  
        System.out.println("saving to file" + path +" " + cmp);  
    }  
    void saveToDB(String path, Computer cmp) {  
        System.out.println("saving to BD" + path +" " + cmp);  
    }  
}
```