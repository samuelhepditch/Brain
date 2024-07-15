# Memory

## Heap Memory

Heap memory is a part of RAM. Heap memory is used for dynamic memory allocation and is freed in arbitrary order.

Heap memory is managed by the programmer in languages like C/C++ and by garbage collectors in modern day languages like python and java.

Used to allocate memory for data structures like linked lists, trees and custom objects.

```
public class StackExample {
    public static void main(String[] args) {
        int a = 10;  // Primitive data type stored in stack
        int b = 20;
        int result = add(a, b);  // Method call, parameters stored in stack
        System.out.println(result);
    }

    public static int add(int x, int y) {
        int sum = x + y;  // Local variable stored in stack
        return sum;
    }
}

```

Note that anytime you see the new keyword before an obect is instantiated in java that object is going to be stored on the Heap.


## Stack Memory

Stack memory is a part of RAM. Its objective is to store local variables, function parameters and return addresses. It also follows a last in first out approach or LIFO.

Stack memory is automatically managed by the programs runtime environment. It is faster then heap memory but more limited in size.

Used for function call management and control flow.

```
public class HeapExample {
    public static void main(String[] args) {
        Person person = new Person("John", 25);  // Object stored in heap
        System.out.println(person.getName());
    }
}

class Person {
    private String name;  // Reference variable stored in heap
    private int age;  // Primitive variable stored in heap

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }
}

```


## General Rules For Stack and Heap Memory In Java

- The programmer does not make the decision to allocate memory on the stack or on the heap. This is the job of the JVM.
- In general there are several general rules:
  - Stack Memory:
    - Local variables, method params, and primitive data types.
    - Reference variables are stored on the stack.
  - Heap Memory:
    - Used for all objects and arrays.
    - Anytime allocated with new keyword its on the heap.
    - Managed by the garbage collector to reclaim memory which becomes unreachable.

## Why Are Objects and Arrays Allocated On the Heap By Default As Opposed to the Stack

- 