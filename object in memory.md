# Objects in Memory 
- When an object is created, memory is allocated to store its data.
- The amount of memory depends on the size and type of the object's field.
- some times instead of storing the entire object's data in a variable, a reference(a memory adddress) to the object's location in memory is stored in the variable. This means multiple variables can point to the same object in memory.

- All the premitive datatypes like long, double, float everything stores in stack memory because it is predefined by java creators
- Arrays, classes, objectes are stores in the heap memory

- ![Objects_in_memory](./images/objects_in_memory.png)


## Pass-by-value 

- Example 1

```java
    public class Main{
        public static void main(String[] args){
            int x = 10;
            int y = 20;

            System.out.println(x+" "+y);

            swap(x,y);

            System.out.println(x+" "+y);
        }
    }

    public static void swap(int x, int y){
        int temp = x;
        x = y;
        y = temp;
    }

    output: 
            10 20 
            10 20 

```

- here swapping doesn't work as expected, this does not change the original x and y in main because:
    - Java is pass by value even for primitives 
    - swap(x,y) swaps copies of x and y, not the actial variables in main. 

    - ![Pass_by_value](./images/pass_by_value.png)

    - so, you need to use a wrapper class or use a container like an array or a class object because arrays are passed by reference (technically, reference value is copied)

Example 2

```java
    class Pair{
        int x;
        int y;

        Pair(int v1, int v2){
            x = v1;
            y = v2;
        }
    }

    public class Main{
        public static void main(String[] args){
            Pair p1 = new Pair(10, 20);

            System.out.println(p1.x+" "+p1.y); // 10 20 
            swap(p1)
            System.out.println(p1.x+" "+p1.y); // 20 10 
        }

        public static void swap(Pair p1){
            int temp = p1.x;
            p1.x = p1.y;
            p1.y = temp;
        }
    }
```

- java is always "pass by value" even for objects 
- But when you pass an object, you are passing the value of the reference to that object
- So you can change the internal state of the object, but you cannot change the reference itself

### What happends behind the sences of above example: 

![pass_by_value_of_reference](./images/pass_by_value_of_reference.png)

- In main(), you create an object p1 with values (10, 20)
- You pass p1 to swap(p1) - java paases a copy of the reference to the object 
- Inside swap(), p1.x and p1.y refer to the same object in memory.
- So swapping x and y inside swap() modifies the origial object. 

Analogy: 
Think of the object p1 like a house. The reference is the address.
You're giving someone a copy of the address, not the house itself.
But with that address, they can go to the same house and change the furniture (internal data).
They can't change the house to a new one — just what's inside it.