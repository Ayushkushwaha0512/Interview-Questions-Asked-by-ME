## APPINVENTIVE TECHNOLOGIES

# DATE OF INTERVIEW :- 31 Jan 2025

# -> Technical Interview 2

## Q1. What is Interface ans its uses in programming?
 Answer
    An interface in Java is a Reference type, similar to a class, that can contain only constants, method signature, deafult methods, static method, and default methods, and nested types.
    Interfacecannot contain instance fields or constructors.
    Interfaces are used to specify a set of methods that a class must implement. They provide a way to achieve abstraction and multiple inheritance in java.

    USES
        -> abstraction: Interfaces allow you to define methods that mist be implemented by derived classes, without providing the implementation details.
        -> multiple inheritance: Java does not support multiple inheritance with classes, but a class can implement multiple interfaces, allowing for a form of multiple inheritance.
        -> Loose Coupling: Interface help in reducing the dependency of a class on the implementation details of another class, promoting loose Coupling.
        -> Polymorphism: Interface enables Polymorphism behavior. A single interface Reference can point to objects of different implementing classes, allowing for dynamic method invocation.


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