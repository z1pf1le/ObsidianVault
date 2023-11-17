[[Iterator]]

```java
import java.util.*;  
  
public class FailFastAndSafe{  
  
    public static void main(String[] args) {   
        failFastIterator();  
    }  
 
    public static void failFastIterator() {  
        ArrayList<String> servers = new ArrayList<String>();  
        servers.add("Tomcat");  
  
        Iterator<String> iterator = servers.iterator();  
        while (iterator.hasNext()){  
            String server = iterator.next();  
            System.out.println(server);  
            //servers.add("Jetty"); //provokes an exception
        }  
    }  
}
```