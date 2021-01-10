## Java Collections



A  ```collection``` —sometimes called a container —is simply an object that groups multiple elements into a single unit. Collections are used to store, retrieve, manipulate, and communicate aggregate data. Typically, they represent data items that form a natural group, such as a poker hand (a collection of cards), a mail folder (a collection of letters), or a telephone directory (a mapping of names to phone numbers).

Java provides Collection Framework which defines several classes and interfaces to represent a group of objects as a single unit.



Benefits of the Java Collections framework:

- **Reduces programming effort**: By providing useful data structures and algorithms, the Collections Framework frees you to concentrate on the important parts of your program rather than on the low-level "plumbing" required to make it work. By facilitating interoperability among unrelated APIs, the Java Collections Framework frees you from writing adapter objects or conversion code to connect APIs. 
- **Increases program speed and quality**: This Collections Framework provides high-performance, high-quality implementations of useful data structures and algorithms. The various implementations of each interface are interchangeable, so programs can be easily tuned by switching collection implementations. Because you're freed from the drudgery of writing your own data structures, you'll have more time to devote to improving programs' quality and performance.



### 1. List



A List is an ordered Collection (sometimes called a sequence). Lists may contain duplicate elements. In addition to the operations inherited from Collection, the List interface includes operations for the following:

- **Positional access** —manipulates elements based on their numerical position in the list. This includes methods such as get, set, add, addAll, and remove. 

- **Search**—searches for a specified object in the list and returns its numerical position. Search methods include indexOfand lastIndexOf. 

- **Iteration**—extends Iterator semantics to take advantage of the list's sequential nature. The listIteratormethods provide this behavior. 

- **Range-view**—The sublistmethod performs arbitrary range operations on the list.



#### 1.1 ArrayList

The **ArrayList **class implements the **List **interface. ArrayListsupports dynamic arrays that can grow as needed.

``` java
import java.util.ArrayList;

public class Main {
  public static void main(String[] args) {
    ArrayList<Integer> nums = new ArrayList<>();
    nums.add(5);
    nums.add(3);
    nums.set(2, 6);
    nums.remove(0);
    for (int i : nums) {
    	// Loop Through
    }
  }
}
```



### 2. Set



A Set is a Collection that **CANNOT** contain duplicate elements. 

It models the mathematical set abstraction. The Set interface contains only methods inherited from Collection and adds the restriction that duplicate elements are prohibited. Set also adds a stronger contract on the behavior of the equals and hashCodeoperations, allowing Set instances to be compared meaningfully even if their implementation types differ. Two Set instances are equal if they contain the same elements.



#### 2.1 **HashSet**

**HashSet** implements the **Set** interface. It creates a collection that uses a hash table for storage.

``` java
import java.util.HashSet;

public class Main {
  public static void main(String[] args) {
    HashSet<String> animals = new HashSet<>();
    animals.add("dog");
    animals.add("cat");
    animals.add("bird");
    
    if (animals.contains("panda")) {
      // false
    }
    animals.remove("bird");
    
  }
}


```



### 3. Map



A Map is an object that maps keys to values. 

A map **cannot** contain duplicate keys: Each key can map to at most one value. It models the mathematical function abstraction. The Map interface includes methods for basic operations (such as put, get, remove, containsKey, containsValue, size, and empty), bulk operations (such as putAlland clear), and collection views (such as keySet, entrySet, and values).



#### 3.1 HashMap

The **HashMap** class uses a hashtableto implement the **Map** interface. This allows the execution time of basic operations, such as get( ) and put( ), to remain constant even for large sets.

``` java
import java.util.HashMap;

public class Main {
  public static void main(String[] args) {
    // Create a HashMap object called capitalCities
    HashMap<String, String> locationMap = new HashMap<>();
    // Add keys and values (Country, City)
    locationMap.put("England", "London");
    locationMap.put("Germany", "Berlin");
    locationMap.put("Norway", "Oslo");
    locationMap.put("USA", "Washington DC");
    
    String city = locationMap.get("USA"); // Washington DC
    locationMap.clear();
  }
}
```

