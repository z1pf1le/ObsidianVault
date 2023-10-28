[[Exception]]

```java
public class RuntimeExceptionExample {
    public static void main(String[] args) {
        int[] arr = new int[20];

        arr[20] = 20;
    }
}
```

_[RuntimeException](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/RuntimeException.html)_ and its subclasses are the exceptions that can be thrown while the Java Virtual Machine is running. Further, they are unchecked exceptions. Unchecked exceptions don’t need to be declared in the method signature using the _throws_ keyword if they can be thrown once the method is executed and propagate outside the method’s scope.