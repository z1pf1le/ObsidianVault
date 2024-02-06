[[Поток]]
Нестатический метод класса _Thread_ _join()_ приостановит выполнение текущего потока до тех пор, пока другой поток не закончит свое выполнение.

Sure, here is an example of using the join method to make the main thread wait for the completion of the two other threads:

```java
public class Main {
    public static void main(String[] args) {
        Thread thread1 = new Thread(new MyRunnable("Thread 1"));
        Thread thread2 = new Thread(new MyRunnable("Thread 2"));

        thread1.start();
        try {
            thread1.join(); // Main thread will wait for thread1 to finish
        } catch (InterruptedException e) {
            e.printStackTrace();
        }

        thread2.start();
        try {
            thread2.join(); // Main thread will wait for thread2 to finish
        } catch (InterruptedException e) {
            e.printStackTrace();
        }

        System.out.println("Both threads have finished, main thread exiting.");
    }
}

class MyRunnable implements Runnable {
    private String name;

    public MyRunnable(String name) {
        this.name = name;
    }

    @Override
    public void run() {
        for (int i = 0; i < 5; i++) {
            System.out.println(name + " is running");
            try {
                Thread.sleep(1000);
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
        }
    }
}
```

In this example, the main thread starts `thread1` and then uses the `join` method to wait for `thread1` to finish before starting `thread2`. After `thread2` finishes, the main thread prints a message and exits.