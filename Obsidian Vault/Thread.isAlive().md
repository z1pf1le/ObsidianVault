[[Поток]]

Метод _isAlive()_ позволяет выяснить, используется поток или нет.

Если поток создан, но не запущен, метод вернет _false_.

Как только метод _start()_ вызван для потока, он считается _alive_ и метод _isAlive()_ вернет _true_.

Если поток закончил свое выполнение, метод вернет _false_.

```java
public class IsAliveExample {
    public static void main(String[] args) {
        Thread thread1 = new Thread(new MyRunnable("Thread 1"));
        Thread thread2 = new Thread(new MyRunnable("Thread 2"));

        System.out.println("Thread 1 is alive: " + thread1.isAlive());
        System.out.println("Thread 2 is alive: " + thread2.isAlive());

        thread1.start();
        System.out.println("Thread 1 started");

        System.out.println("Thread 1 is alive: " + thread1.isAlive());
        System.out.println("Thread 2 is alive: " + thread2.isAlive());

        try {
            thread1.join();
            System.out.println("Thread 1 joined");
        } catch (InterruptedException e) {
            e.printStackTrace();
        }

        System.out.println("Thread 1 is alive: " + thread1.isAlive());
        System.out.println("Thread 2 is alive: " + thread2.isAlive());

        thread2.start();
        System.out.println("Thread 2 started");

        System.out.println("Thread 1 is alive: " + thread1.isAlive());
        System.out.println("Thread 2 is alive: " + thread2.isAlive());
    }
}

class MyRunnable implements Runnable {
    private String name;

    public MyRunnable(String name) {
        this.name = name;
    }

    @Override
    public void run() {
        System.out.println(name + " is running");
        try {
            Thread.sleep(2000);
        } catch (InterruptedException e) {
            e.printStackTrace();
        }
    }
}
```