# JavaSE-8.ObjectsComparison

See the Udemy course: https://www.udemy.com/course/curso-certificacion-profesional-desarrollador-java-se-11

In Java, object comparison is a common operation, and it's important to understand how it works. 

There are two primary ways to compare objects in Java: using the equals() method and using the == operator. Let me illustrate both with some examples.

## 1. Using the equals() Method:

The equals() method is a method defined in the Object class, and it's meant to be overridden by classes that need to specify how instances of the class are equal. 

Here's an example:

In this example, the equals() method is overridden to compare the name and age fields of two Person objects.

```java
public class Person {
    private String name;
    private int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    @Override
    public boolean equals(Object obj) {
        if (this == obj) {
            return true;
        }
        if (obj == null || getClass() != obj.getClass()) {
            return false;
        }
        Person person = (Person) obj;
        return age == person.age && name.equals(person.name);
    }

    public static void main(String[] args) {
        Person person1 = new Person("John", 25);
        Person person2 = new Person("John", 25);

        System.out.println(person1.equals(person2)); // true
    }
}
```

## 2. Using the == Operator:

The == operator compares object references, not the content of objects. 

It checks if two references point to the exact same object in memory. 

Here's an example:

In this case, str1 and str2 are different objects in memory, even though their content is the same. So, str1 == str2 returns false.

```java
public class Main {
    public static void main(String[] args) {
        String str1 = new String("Hello");
        String str2 = new String("Hello");

        System.out.println(str1 == str2); // false
    }
}
```

It's essential to choose the appropriate method depending on your use case. 

If you want to compare the content of objects, override the equals() method. 

If you want to check if two references point to the same object, use the == operator.

