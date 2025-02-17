# APPINVENTIVE TECHNOLOGIES

# Date Interview:- 25 Jan 2025

# ->Technical Interview

## Q1. what is OOPs?
ans- OOPs stands for Object-Oriented Programming System. It is a programming paradigm based on the concept of 
     "objects", which can contain data and code to manipulate that data.

## Q2. what are the key principles of OOPs?
ans- The key principles of OOPs are:

    **Encapsulation:** Bundling the data and methods that operate on the data within one unit, e.g., a class.
    **Abstraction:** Hiding the complex implementation details and showing only the necessary features of an object.
    **Inheritance:** Creating new classes from existing ones, allowing for code reuse and the creation of a hierarchical
                    relationship between classes.
    **Polymorphism:** Allowing objects to be treated as instances of their parent class rather than their actual class,
                    enabling one interface to be used for a general class of actions.

## Q3.what are types of Inheritance?
ans- The types of inheritance in OOPs are:

    1. **Single Inheritance**: A class inherits from one superclass.
    2. **Multiple Inheritance**: A class inherits from more than one superclass.
    3. **Multilevel Inheritance**: A class inherits from a superclass, which in turn inherits from another superclass.
    4. **Hierarchical Inheritance**: Multiple classes inherit from a single superclass.
    5. **Hybrid Inheritance**: A combination of two or more types of inheritance.

## Q4. Why Multiple inheritance not support in java?
ans- Multiple inheritance is not supported in Java to avoid complexity and simplify the design. The main reason is
     to prevent the "Diamond Problem," where a class can inherit from two classes that have a common superclass, leading
     to ambiguity in method resolution. Instead, Java supports multiple inheritance of type through interfaces, allowing 
     a class to implement multiple interfaces.

## Q5. what is interface? write their example.
ans- An interface in Java is a reference type, similar to a class, that can contain only constants, method signatures, 
     default methods, static methods, and nested types. Interfaces cannot contain instance fields or constructors. They 
     are used to specify a set of methods that a class must implement.

Example:
    ```java
    // Define an interface
    interface Animal {
        void eat();
        void sleep();
    }

    // Implement the interface in a class
    class Dog implements Animal {
        public void eat() {
            System.out.println("Dog is eating");
        }

        public void sleep() {
            System.out.println("Dog is sleeping");
        }
    }

    // Main class to test the implementation
    public class Main {
        public static void main(String[] args) {
            Dog dog = new Dog();
            dog.eat();
            dog.sleep();
        }
    }


## Q6. How we determine which interface method is called when a class inherits from two interfaces with the same method?
ans- When a class inherits from two interfaces that have the same method, the class must provide an implementation for
     that method. The implementation will be the same for both interfaces. If you need to differentiate between the two,
     you can use default methods in interfaces or create separate methods in the implementing class.

    Example:
    ```java
    interface InterfaceA {
        default void show() {
            System.out.println("InterfaceA show method");
        }
    }

    interface InterfaceB {
        default void show() {
            System.out.println("InterfaceB show method");
        }
    }

    class MyClass implements InterfaceA, InterfaceB {
        // Overriding the show method to resolve the conflict
        public void show() {
            InterfaceA.super.show(); // Call InterfaceA's show method
            InterfaceB.super.show(); // Call InterfaceB's show method
        }
    }

    public class Main {
        public static void main(String[] args) {
            MyClass obj = new MyClass();
            obj.show();
        }
    }


## Q7. what is the use of super keyword in java?
ans- In Java, the super keyword is a reference variable used to access the immediate parent class's methods, variables, or
     constructors. It is commonly used in inheritance to interact with the parent class. Below are its specific uses:
      
      -> Access Parent class variables: When a subclass has a field with the same name as a field in its parent class, the
         super keyword can be used to distinguish between the parent class's field and the current class's field.

      -> Access Parent class methods: If a subclass overrides a method from the parent class, the super keyword can be used
         to call the overridden method in the parent class.

      -> Call Parent class constructor: The super keyword can be used to explicitly call the parent class's constructor.
         This is particularly useful when the parent class constructor has parameters or specific initialization logic.

      -> Invoke Parent class constructor with arguments: You can use super to call a specific constructor in the parent class,
         even if it takes arguments.

      -> prevent Shadowing of Parent class members: When a parent class and a subclass have members (variables or methods) with
         the same name, super ensures that the parent class's member is accessed instead of the subclass's member.


## Q8. what is Polymorphism?
ans- Polymorphism is one of the core concepts of object-oriented programming (OOP) that allows objects of different classes to
     be treated as objects of a common superclass. It enables a single interface to represent different underlying forms (data types).
     There are two types of polymorphism in Java:

    1. **Compile-time Polymorphism (Method Overloading)**: This occurs when multiple methods in the same class have the same name
         but different parameters (different type, number, or both). The method to be called is determined at compile time.

         Example:
        ```java
        class MathOperations {
            // Method overloading
            int add(int a, int b) {
                return a + b;
            }

            double add(double a, double b) {
                return a + b;
            }
        }

        public class Main {
            public static void main(String[] args) {
                MathOperations math = new MathOperations();
                System.out.println(math.add(5, 10)); // Calls add(int, int)
                System.out.println(math.add(5.5, 10.5)); // Calls add(double, double)
            }
        }
        ```

    2. **Runtime Polymorphism (Method Overriding)**: This occurs when a subclass provides a specific implementation of a method that
         is already defined in its superclass. The method to be called is determined at runtime.

        Example:
        ```java
        class Animal {
            void sound() {
                System.out.println("Animal makes a sound");
            }
        }

        class Dog extends Animal {
            @Override
            void sound() {
                System.out.println("Dog barks");
            }
        }   

        public class Main {
            public static void main(String[] args) {
                Animal myDog = new Dog();
                myDog.sound(); // Calls Dog's sound method
            }
        }
        ```

    Polymorphism enhances flexibility and maintainability in code by allowing the same interface to be used for different underlying forms.



## Q9. Difference between LinkedList and arraylist.
ans- a-> Underlying Data Structure:
            ArrayList: Uses a dynamic array to store elements.
            LinkedList: Uses a doubly linked list to store elements.

     b-> Performance:
            ArrayList: Provides constant time for get and set operations (O(1)), but adding or removing elements from the middle of the
             list is slow (O(n)).
            LinkedList: Provides constant time for adding or removing elements from the beginning or end of the list (O(1)), but get and
             set operations are slow (O(n)).

     c-> Memory Usage:
            ArrayList: Requires less memory overhead as it stores only the object references.
            LinkedList: Requires more memory overhead as it stores two references (next and previous) for each element.

     d-> Iteration:
            ArrayList: Better for iterating over the list as it has better cache locality.
            LinkedList: Slower iteration due to poor cache locality.
     e-> Use Case:
            ArrayList: Preferred when there are more get and set operations.
            LinkedList: Preferred when there are more insertions and deletions in the middle of the list.

## Q10. what is map in java?
ans- A Map in Java is an object that maps keys to values. It cannot contain duplicate keys, and each key can map to at most one value.

        Key Characteristics:
            Unique Keys: Each key is unique.
            Key-Value Pairs: Each key maps to exactly one value.
        
        Common Implementations:
            HashMap:
                -> Uses a hash table.
                -> Allows null values and null keys.
                -> Not synchronized.

            TreeMap:
                -> Uses a Red-Black tree.
                -> Orders keys based on their natural ordering or by a specified comparator.
                -> Not synchronized.
            LinkedHashMap:
                -> Maintains a doubly-linked list running through all its entries.
                -> Orders keys based on the order of insertion.
                -> Not synchronized.

    Example:-
    import java.util.HashMap;
    import java.util.Map;

    public class MapExample {
        public static void main(String[] args) {
            Map<String, Integer> map = new HashMap<>();
            map.put("One", 1);
            map.put("Two", 2);
            map.put("Three", 3);

            // Accessing values
            System.out.println("Value for key 'One': " + map.get("One"));

            // Iterating over keys
            for (String key : map.keySet()) {
                System.out.println("Key: " + key + ", Value: " + map.get(key));
            }
        }
    }


## Q11. which data structure use for a find a word in a book?
ans- To find a word in a book, the most commonly used data structure is a Trie (also known as a prefix tree).

    Trie (Prefix Tree):

        Definition: A Trie is a tree-like data structure that stores a dynamic set of strings, where the keys are usually strings.
        Use Case: Efficiently stores and searches for words in a dictionary or book.
        Operations:
            Insert: Adds a word to the Trie.
            Search: Checks if a word exists in the Trie.
            Prefix Search: Finds all words with a given prefix.

    Example:-
    class TrieNode {
        Map<Character, TrieNode> children = new HashMap<>();
        boolean isEndOfWord = false;
    }

    class Trie {
        private TrieNode root;

        public Trie() {
            root = new TrieNode();
        }

        public void insert(String word) {
            TrieNode node = root;
            for (char c : word.toCharArray()) {
                node = node.children.computeIfAbsent(c, k -> new TrieNode());
            }
            node.isEndOfWord = true;
        }

        public boolean search(String word) {
            TrieNode node = root;
            for (char c : word.toCharArray()) {
                node = node.children.get(c);
                if (node == null) {
                    return false;
                }
            }
            return node.isEndOfWord;
        }
    }


## Q12. what is Exceptions in java?
ans- Exceptions in Java are events that disrupt the normal flow of the program's instructions. They are used to handle errors and 
     other exceptional events in a controlled manner.

    Key Characteristics:
        -> Exception Hierarchy: All exceptions are derived from the Throwable class.
                -> Checked Exceptions: Subclasses of Exception (excluding RuntimeException). Must be either caught or declared in the 
                                        method signature.
                -> Unchecked Exceptions: Subclasses of RuntimeException. Do not need to be declared or caught.
                -> Errors: Subclasses of Error. Indicate serious problems that a reasonable application should not try to catch.
    
    Common Exception Types:
        1. Checked Exceptions:
                ->  IOException
                -> SQLException
        2. Unchecked Exceptions:
                -> NullPointerException
                -> ArrayIndexOutOfBoundsException
        3. Errors:
                -> OutOfMemoryError
                -> StackOverflowError

    Handling Exceptions:
        -> Try-Catch Block: Used to catch and handle exceptions.
        -> Finally Block: Used to execute important code such as closing resources, regardless of whether an exception is thrown or not.
        -> Throwing Exceptions: Using the throw keyword to explicitly throw an exception.
        -> Declaring Exceptions: Using the throws keyword in the method signature to declare that a method might throw exceptions.

    example

    public class ExceptionExample {
        public static void main(String[] args) {
            try {
                int result = divide(10, 0);
                System.out.println("Result: " + result);
            } catch (ArithmeticException e) {
                System.out.println("Exception caught: " + e.getMessage());
            } finally {
                System.out.println("Finally block executed.");
            }
        }

        public static int divide(int a, int b) throws ArithmeticException {
            if (b == 0) {
                throw new ArithmeticException("Division by zero");
            }
            return a / b;
        }
    }


## Q13. Difference Between final and finally in Exception Handling.
ans- Final:-
        A keyword used to define constants, prevent method overriding, and prevent inheritance.
        example:
            public final class FinalClass {
                public final void finalMethod() {
                    final int finalVariable = 10;
                    // finalVariable = 20; // This will cause a compilation error
                }
            }

    Finally:-
        A block used in exception handling to ensure that a section of code is executed, regardless of whether an exception is thrown or not.
        example:
            public class FinallyExample {
                public static void main(String[] args) {
                    try {
                        int result = divide(10, 0);
                        System.out.println("Result: " + result);
                    } catch (ArithmeticException e) {
                        System.out.println("Exception caught: " + e.getMessage());
                    } finally {
                        System.out.println("Finally block executed.");
                    }
                }
            
                public static int divide(int a, int b) {
                    if (b == 0) {
                        throw new ArithmeticException("Division by zero");
                    }
                    return a / b;
                }
            }


## Q14. Difference between static and final keyword in java.
ans- Static:-
        Variable: A static variable is shared among all instances of a class. It belongs to the class, not to any specific instance.
        Method: A static method belongs to the class rather than any instance. It can be called without creating an instance of the class.
        Block: A static block is used for static initializations of a class. It runs once when the class is loaded.

        Example:- 
            public class StaticExample {
                static int staticVariable = 10;
            
                static void staticMethod() {
                    System.out.println("Static method called.");
                }
            
                static {
                    System.out.println("Static block executed.");
                }
            
                public static void main(String[] args) {
                    StaticExample.staticMethod();
                    System.out.println("Static variable: " + StaticExample.staticVariable);
                }
            }
    Final:- 
        Variable: A final variable's value cannot be changed once it is initialized. It makes the variable a constant.
        Method: A final method cannot be overridden by subclasses.
        Class: A final class cannot be subclassed.

        Example:-
            public final class FinalClass {
                public final void finalMethod() {
                    final int finalVariable = 10;
                    // finalVariable = 20; // This will cause a compilation error
                }
            }

## Q15. Difference Between Switch and if-else.
ans:- if-else:
        Used for conditional branching based on boolean expressions.
        Can handle complex conditions involving logical operators (&&, ||, !).

        Syntax:
        if (condition1) {
            // code block
        } else if (condition2) {
            // code block
        } else {
            // code block
        }

      Switch:
        Used for selecting one of many code blocks to be executed.
        Works with byte, short, char, int, String, and enum types.
        More efficient than if-else for multiple equality checks.

        Syntax:
        switch (expression) {
            case value1:
                // code block
                break;
            case value2:
                // code block
                break;
            // more cases
            default:
                // default code block
        }

    
## Q16. Why switch is Faster than if-else?
ans:- Jump Table Optimization:
        -> The switch statement can be optimized by the compiler using a jump table. This allows the program to directly jump to the case
         that matches the switch expression, making it faster than evaluating multiple if-else conditions sequentially.
        -> In contrast, if-else statements are evaluated sequentially, which means each condition is checked one by one until a match is
         found or all conditions are exhausted.

 
