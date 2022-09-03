# Array Sort

## Learning Goals

- Learn about the `Arrays` class
- Learn about sorting an array

## Introduction

Now that we have learned about arrays and what they are, let's learn how to
sort them! But first we need to talk about a utility class to help us. Let's
start by looking at the `Arrays` class!

## Arrays Class

Similar to our `Scanner` class, there is another class for arrays called
`Arrays`! It is in the same package as the `Scanner` class, the `java.util`
package. This class has a bunch of methods to help us with our arrays - such as
an `equals()` method to help us determine if two arrays are equal and a `fill()`
method to fill an array with certain values.

To make use of some of these utility methods that Java comes with, we will need
to import it:

```java
import java.util.Arrays;
```

The above import statement should look similar to how we imported the `Scanner`
class when we covered User Interaction lesson in the last module. But unlike
the `Scanner` class when we had to declare an instance to use it, the `Arrays`
class is full of static methods. So we won't need to declare an instance of the
`Arrays` class - instead we can just use the methods directly:

```java
int[] numbers = new int[10];
Arrays.fill(numbers, 18);
```

As a review, static methods are methods that can be accessed directly on the
class without needing an instance of the class to be created. Hence, why we can
call the `fill()` method to fill an array with a certain value as we did in the
code above. The code above will take the array `numbers` and fill it with the
integer value of 18. Therefore, each `int` in the array will now have a value
of 18.

But let us now focus on the method we want to talk about - the `sort()` method!

## Sorting an Array

Say we have an array that holds 10 integer values, and we want to sort them in
ascending order (minimum to maximum). We could make use of everything we have
learned thus far: use conditional statements, loops, and the `Math` class'
`min()` and `max()` methods. But luckily for us, Java has already figured out
that programmers may want to sort arrays. This is why we have the `sort()`
method!

The `sort()` method is a static method within the `Arrays` class. So to use it,
we will need to import it as we saw above. But how do we use it? Let's look at
the following example:

```java
import java.util.Arrays;

public class Example {
    public static void main(String[] args) {
        int[] numbers = {99, -10, 100123, 18, -978, 5623, 463, -9, 287, 49};
        Arrays.sort(numbers);
        System.out.print("The numbers array AFTER sort: ");
        for (int num : numbers) {
            System.out.print(num + " ");
        }
    }
}
```

As we can see from the above example, we can use the `sort()` method by calling
it directly from the `Arrays` class and passing it the array as the parameter.
It will then sort the array `numbers` for us in ascending order. When we run
this code, it will produce the following:

```plaintext
The numbers array AFTER sort: -978 -10 -9 18 49 99 287 463 5623 100123
```

The `sort()` method also works with other primitive types; such as `double`,
`float`, `long`, `byte`, and `char`:

```java
import java.util.Arrays;

public class Example {
    public static void main(String[] args) {
        double[] numbers = {9.9, -10.0, 100.123, 1.8, -97.8, 5.623, 46.3, -9.0, 2.87, 0.49};
        Arrays.sort(numbers);
        System.out.print("The numbers array AFTER sort: ");
        for (double num: numbers) {
            System.out.print(num + " ");
        }
    }
}
```

The above will produce the following output:

```plaintext
The numbers array AFTER sort: -97.8 -10.0 -9.0 0.49 1.8 2.87 5.623 9.9 46.3 100.123
```

We can also sort reference types using the `sort()` method by their natural
ordering. For example, a `String` type will sort alphabetically:

```java
import java.util.Arrays;

public class Example {
    public static void main(String[] args) {
        String[] names = {"Leslie", "Ann", "Ron", "Ben", "Tom", "April", "Andy", "Chris", "Jerry", "Donna"};
        Arrays.sort(names);
        System.out.print("The names array AFTER sort: ");
        for (String name : names) {
            System.out.print(name + " ");
        }
    }
}
```

By passing in a `String[]` to the `sort()` method, the following output of the
above example would look like this:

```plaintext
The names array AFTER sort: Andy Ann April Ben Chris Donna Jerry Leslie Ron Tom
```
