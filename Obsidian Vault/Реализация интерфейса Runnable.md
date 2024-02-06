[[Способы создания потока]]
```java
public class App {

    public static void main(String[] args) {
        var ferrari = new Car("Ferrari");
        var bmw = new Car("BMW");
        var ferrariThread = new Thread(ferrari, "Ferrari-Thread");
        var bmwThread = new Thread(bmw, "BMW-Thread");
        ferrariThread.start();
        bmwThread.start();
        System.out.println("Method continues execution... Main method is executed by thread " + Thread.currentThread().getName());
    }

}

class Car implements Runnable {

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