[[Solid]]

Принцип инверсии зависимостей

Зависимости внутри системы строятся на основе абстракций. Модули верхних уровней не должны зависеть от модулей нижних уровней, а оба типа модулей должны зависеть от абстракций; сами абстракции не должны зависеть от деталей, а вот детали должны зависеть от абстракций.

Классы должны зависеть от интерфейсов или абстрактных классов, а не от конкретных классов и функций.

харам
```java
public class Main{  
    public static void main(String[] args) {  
    ModelForm f = new ModelForm(1, 30, "Sfinkter");  
    WebFramework w = new WebFramework();  
    w.save(f);  
    }  
}  
  
class ModelForm{  
    int id;  
    int old;  
    String fio;  
  
    public ModelForm(int id, int old, String fio) {  
        this.id = id;  
        this.old = old;  
        this.fio = fio;  
    }  
}  
  
class  WebFramework {  
    void save(ModelForm frm){  
        MySQL db = new MySQL();  
        db.save(frm);  
    }  
}  
  
class MySQL{  
    void save(ModelForm frm){  
        System.out.println("form to DB");  
    }  
}
```

халяль

```java
public class Main{  
    public static void main(String[] args) {  
    ModelForm f = new ModelForm(1, 30, "Sfinkter");  
    WebFramework w = new WebFramework();  
    w.save(f);  
    }  
}  
  
class ModelForm implements IForm{  
    int id;  
    int old;  
    String fio;  
  
    public ModelForm(int id, int old, String fio) {  
        this.id = id;  
        this.old = old;  
        this.fio = fio;  
    }  
}  
  
class  WebFramework {  
    void save(IForm frm){  
        ISQL db = new MySQL();  
        db.save(frm);  
    }  
}  
  
class MySQL implements ISQL{  
     public void save(IForm frm){  
        System.out.println("form to DB");  
    }  
}  
  
interface  IForm{  
}  
  
interface  ISQL{  
    public void save(IForm f);  
}
```