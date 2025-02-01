## APPINVENTIVE TECHNOLOGIES

# DATE OF INTERVIEW :- 31 Jan 2025

# -> Technical Interview 2

## Q1. What is Interface ans its uses in programming?
 Answer
An interface in Java is a Reference type, similar to a class, that can contain only constants, method signature, deafult methods, static method, and default methods, and nested types.
Interfacecannot contain instance fields or constructors.
Interfaces are used to specify a set of methods that a class must implement. They provide a way to achieve abstraction and multiple inheritance in java.

USES
1. abstraction: Interfaces allow you to define methods that mist be implemented by derived classes, without providing the implementation details.
2. multiple inheritance: Java does not support multiple inheritance with classes, but a class can implement multiple interfaces, allowing for a form of multiple inheritance.
3. Loose Coupling: Interface help in reducing the dependency of a class on the implementation details of another class, promoting loose Coupling.
4. Polymorphism: Interface enables Polymorphism behavior. A single interface Reference can point to objects of different implementing classes, allowing for dynamic method invocation.


        interface Animal{
            void eat():
            void sleep();
        }

        class dog implements Animal{
            public void eat(){
                System.out.println("Dog is eating");
            }
            public void sleep(){
                System.out.println("Dog is Sleeping");
            }
        }
        public class Main{
            public static void main(String[] args){
                Animal mydog=new Dog();
                myDog.eat();
                myDog.sleep();
            }
        }

## Q2. why we need encapsulation whem we have abstraction and vice versa?
## Answer:-

Encapsulation: It ensure that the internal state of an object is protected and can only be modified through controlled methods. This prevents unintended interfarence and misuse of the data. It provide a way to enforce rules and constraints on th data, ensuring data integrity and security.

Abstraction: It allows developers to wroks with the objects at a higher level of complexity by focusing on the essential features and ignoring the implementation details. It helps in desinging systems that are easier to understand and maintain by providing clear interfaces and reducing complexity.

Basically encapsulation and abstraction are complementary concepts in object-oriented programming .Encapsulation ensures data protection and controlled access, while abstraction simplifies complex systems by focusing on essential features. Both are essential for creating robust, maintainable, and  scalable software.


## Q3. What is Exception Handling?
## Answer:-
Execption Handling in java is a mechanism to handle runtime errors, allowing the normal flow of the program to be maintained. It provides a way to handle various error conditions and exceptional events that can occur during the execution of a program.

Key Cocepts:
1. Exception: An event that disrupts the normal flow of the program. It is an object that is thrown at runtime.
2. Throwable: The superclass of all errors and exceptions in java. It has two main subclasses: Error and Execption.
3. Checked Exceptions: Exceptions that are checked at complie-time. They must be either caught or declared in the method signature using the throws keyword.
4. Unchecked Exceptions: Exceptions hat are not checked at complie-time. They are subclasses of RuntimeException and do not need to be declared or caught.
5. Error: Indicate serious problems that a resonable application should not try to catch (e.g., OutofMemoryError).

Exception Handling Mechanism:
1. try: The block of code where exceptions might occur.
2. catch: The block of code that handles the exception.
3. finally: The block of code that executes regardless of whether an exception is thrown or not. It is typically used for cleanup activities.
4. throw: Used to explicitly throw an exception.
5. throws: Used in method signatures to declare that a method might throw exceptions.

