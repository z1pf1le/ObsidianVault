[[Solid]]

Принцип разделения интерфейса

Принцип в формулировке Роберта Мартина декларирует, что клиенты не должны зависеть от методов, которые они не используют. То есть если какой‑то метод интерфейса не используется клиентом, то изменения этого метода не должны приводить к необходимости внесения изменений в клиентский код.

Следование принципу ISP заключается в создании интерфейсов, которые достаточно специфичны и требуют только необходимый минимум реализаций методов. Избыточные интерфейсы, напротив, могут требовать от реализующего класса создание большого количества методов, причём даже таких, которые не имеют смысла в контексте класса.

В чём‑то принцип разделения интерфейса перекликается с принципом единственной ответственности — интерфейсы не должны быть избыточно «толстыми», если вдруг в приложении формируется слишком объёмный интерфейс, то есть высокая вероятность, что так происходит из‑за того, что в этом интерфейсе слишком много разных ответственностей, а значит логичнее всего провести декомпозицию сложного интерфейса на несколько простых.

клиенты не должны быть вынуждены реализовывать методы, которые они не будут использовать.

харам
```java
public class Main {  
    public static void main (String[] args) {  
    Line line = new Line();  
    line.drawLine();  
    line.drawCircle(); //порожняком идёт  
    }  
}  
class Line implements Shape{  
  
    @Override  
    public void drawLine() {  
        System.out.println("line drawing");  
    }  
  
    @Override  
    public void drawCircle() {  
  
    }  
  
    @Override  
    public void drawRect() {  
  
    }  
}  
class Circle implements Shape{  
  
    @Override  
    public void drawLine() {  
  
    }  
  
    @Override  
    public void drawCircle() {  
        System.out.println("Circle drawing");  
    }  
  
    @Override  
    public void drawRect() {  
  
    }  
}  
  
class Rect implements Shape{  
  
    @Override  
    public void drawLine() {  
  
    }  
  
    @Override  
    public void drawCircle() {  
  
    }  
  
    @Override  
    public void drawRect() {  
        System.out.println("Rect drawing");  
    }  
}  
  
interface Shape {  
    void drawLine();  
    void drawCircle();  
    void drawRect();  
}

```

халяль 

```java
public class Main {  
    public static void main (String[] args) {  
    Line line = new Line();  
    Circle circle = new Circle();  
    line.drawLine();  
    circle.drawCircle();  
    }  
}  
class Line implements Iline{  
  
    @Override  
    public void drawLine() {  
        System.out.println("line drawing");  
    }  
  
}  
class Circle implements ICircle {  
    @Override  
    public void drawCircle() {  
        System.out.println("Circle drawing");  
    }  
  
}  
  
class Rect implements IRect{  
    @Override  
    public void drawRect() {  
        System.out.println("Rect drawing");  
    }  
}  
  
interface Iline {  
    void drawLine();  
}  
  
interface ICircle {  
    void drawCircle();  
}  
  
interface IRect {  
    void drawRect();  
}
```