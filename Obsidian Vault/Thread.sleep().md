[[Поток]]

Метод `sleep()` класса `java.lang.Thread` используется для того, чтобы приостановить выполнение текущего потока на указанное в миллисекундах время. Значение аргумента для миллисекунд не может быть отрицательным, в противном случае будет брошен.

```java
public class Main {
    public static void main(String[] args) {
        Thread thread1 = new Thread(new MyRunnable("Thread 1"));
        Thread thread2 = new Thread(new MyRunnable("Thread 2"));

        thread1.start();
        thread2.start();
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
                Thread.sleep(1000); // Приостанавливаем выполнение потока на 1 секунду
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
        }
    }
}
```

```java
import com.sun.jdi.PathSearchingVirtualMachine;  
  
import java.util.EnumSet;  
import java.util.stream.IntStream;  
  
import static java.lang.System.out;  
import static java.lang.Thread.currentThread;  
import static java.util.EnumSet.range;  
import static java.util.stream.IntStream.rangeClosed;  
  
public class Runner{  
    private static final int FROM_NUMBER_FIRST_THREAD = 1;  
    private static final int TO_NUMBER_FIRST_THREAD = 501;  
  
    private static final int FROM_NUMBER_SECOND_THREAD = 501;  
    private static final int TO_NUMBER_SECOND_THREAD = 1000;  
  
    private static final String TEMPLATE_MESSAGE_THREAD_NAME_AND_NUMBER = "%s : %s\n";  
  
    public static void main(final String... args) throws InterruptedException {  
  
        final TaskSummingNumbers firstTask = startSubTask(FROM_NUMBER_FIRST_THREAD, TO_NUMBER_FIRST_THREAD);  
        final TaskSummingNumbers secondTask = startSubTask(FROM_NUMBER_SECOND_THREAD, TO_NUMBER_SECOND_THREAD);  
        waitForTasksFineshed();  
        final int resultNumber = firstTask.getResultnumber() + secondTask.getResultnumber();  
        printThreadNameAndNumber(resultNumber);  
    }  
  
    private static TaskSummingNumbers startSubTask(final int fromNumber, final int toNumber){  
        final TaskSummingNumbers subtask = new TaskSummingNumbers(fromNumber, toNumber);  
        final Thread thread = new Thread(subtask);  
        thread.start();  
        return subtask;  
    }  
  
    private static void  printThreadNameAndNumber(final int number){  
        out.println(currentThread().getName());  
        out.println(number);  
//        out.println(TEMPLATE_MESSAGE_THREAD_NAME_AND_NUMBER, currentThread().getName(), number);  
    }  
  
    public static void waitForTasksFineshed() throws InterruptedException {  
        Thread.sleep(1000);  
    }  
  
    private static final class TaskSummingNumbers implements Runnable{  
        private static final int INITIAL_VALUE_RESULT_NUMBER = 0;  
  
        private final int fromnumber;  
        private final int tonumber;  
        private int resultnumber;  
  
        public TaskSummingNumbers(int fromnumber, int tonumber) {  
            this.fromnumber = fromnumber;  
            this.tonumber = tonumber;  
            this.resultnumber = INITIAL_VALUE_RESULT_NUMBER;  
        }  
  
        public int getResultnumber() {  
            return this.resultnumber;  
        }  
  
        @Override  
        public void run() {  
            rangeClosed(this.fromnumber, this.tonumber).forEach(i -> this.resultnumber += i);  
            out.println(this.resultnumber);  
        }  
    }  
}
```