[[Solid]]

Принцип подстановки Барбары Лисков

объекты в программе можно заменить их наследниками без изменения свойств программы

дочерний класс должен полностью повторять функционал родительского класса

> Substitutability is a principle in object-oriented programming stating that, in a computer program, if S is a subtype of T, then objects of type T may be replaced with objects of type S

Let's do a simple example in Java:

## Bad example

```
public class Bird{
    public void fly(){}
}
public class Duck extends Bird{}
```

The duck can fly because it is a bird, but what about this:

```
public class Ostrich extends Bird{}
```

Ostrich is a bird, but it can't fly, Ostrich class is a subtype of class Bird, but it shouldn't be able to use the fly method, that means we are breaking the LSP principle.

## Good example

```
public class Bird{}
public class FlyingBirds extends Bird{
    public void fly(){}
}
public class Duck extends FlyingBirds{}
public class Ostrich extends Bird{} 
```

Подкласс не должен требать от базового кода больше, чем вызывающий класс и не должен предоставлять вызывающему коду меньше, чем базовый класс.

Сущность никогда не должна реализовывать интерфейс, содержащий элементы, которые она никогда не будет использовать.
