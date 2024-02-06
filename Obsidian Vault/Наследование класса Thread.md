```java
public class App {

    public static void main(String[] args) {
        var ferrari = new Car("Ferrari");
        var bmw = new Car("BMW");
        ferrari.start();
        bmw.start();
        System.out.println("Method continues execution... Main method is executed by thread " + Thread.currentThread().getName());
    }

}

class Car extends Thread {

    private final String model;

    public Car(String model) {
        this.model = model;
    }

    @Override
    public void run() {
        try {
            Thread.sleep(1000);
        } catch (InterruptedException exception) {
            exception.printStackTrace();
        }
        System.out.println("Car " + model + " is being driven by thread " + Thread.currentThread().getName());
    }

}
```

[[Способы создания потока]]