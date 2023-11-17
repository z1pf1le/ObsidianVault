
[[Collection]]
```java

  
class Easy 
  
{ 
  
    public static void main(String[] args) 
  
    { 
  
        // array declaration 
  
        int ar[] = { 10, 50, 60, 80, 90 }; 
  
        for (int element : ar) 
  
            System.out.print(element + " "); 
    } 
}
```

эквивалентен:

```java
class Easy 
  
{ 
  
    public static void main(String[] args) 
	
    { 
		int arr[] = { 10, 50, 60, 80, 90 }; 
	    for (int i=0; i<arr.length; i++) 
		{ 
		    System.out.print(arr[i] + " ");
		}
    } 
}
```