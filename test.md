# Prefixbox Test

## Short questions

- What is a package? How do you define a package?
```
A package is used to separate files, thus to improve the overall structure of the application.
You can define a package with the package command and it's place at the top of the given file.
```
- What is a constructor? When is it executed?
```
A constructor is kind of a recipe, where you tell the program what to execute when an instance is created from given class.
As stated above it is executed when an instance is created from a class, with given parameters (eg. there can be no-argument constructor, and ones with many arguments at the same time).
```
- How do you implement inheritance in Java?
```
when you define the class, you must state that it extends given parent class.
Also you have to have a super call in the child class' contructor, because the parent class' constructor must be implemented.
```
- How do you prevent someone to inherit from a class?
```
By making the class private.
```
- What is a final variable? Where you can assign value to final variables?
```
It is a constant, that means it can recieve a value only once, when you define it.
```
- Specify the available access modifiers in Java and briefly explain them
```
Public - can be reached in given package, or be imported and used.
Private - can only be reached in given file, nowhere else.
Protected - can only be reached for given file and also for children classes, it is used in parent classes.
```
- Briefly explain the mechanism of exception handling.
```
Try - catch is the must used exception handling, it is kind of an if - else statement.
You can specify what to do (for example import a file) and also what to do if the first thing didn't work out for some reasons.
When you catch given error you cannot show a stack trace to the user, there must an error code, message or maybe the program shold exit in he worst case.
```
- What is the difference between an abstract class and an interface?
```
An abstract class is a class that cannot have an instance, while an interface is basically an agreement with unimplemented methods.
An interface can be more widely used.
```
- What is the difference between Comparator and Comparable?
- How Iterable and Iterator interface works? What methods need to exist in a
class that implements them? What is their relation to for loops?

## Programming tasks

You can write your solutions in any language, you can even write pseudo code or
using only your own words.
The point is not to make a perfectly running application, the point is the way
you think!
Don't worry if you miss a semicolon or some parantheses.
You might use the Java stream API for your solutions but none of the exercises
require them

### Palindrom

Write a function which decides whether a text is palindrom(It's the same whether
you read it forwards or backwards). E.g.: abba, rotator, stats.
You might assume that the input string is not null, the length is greater than
1 and less than one million. **Strive for the low memory complexity!**

Example:

```java
//used one stringbuilder, so it doesn't have to make a new one every time a string concatenation is called

public boolean isPalindrom(String input) {
  Stringbuilder str = "";
  char[] chars = input.toCharArray();
  for(chars.length ... 0) {
    str.append(chars[i]);
  }
  return input.equals(str.toString);
}

isPalindrom("alma"); //false
isPalindrom("görög"); //true
```

### Find The Duplicate

You have an array that contains strings. Every item in the array is
unique except one which is present in the array exactly twice.
Write a function which finds the string that is present twice in the array.
You might assume that the input array is not null, the length is greater
or equal to 2 and less than one million. **Strive for the low time complexity!**

Example:

```java
O(nm) if  ArrayList.find() method is O(m).

public String findTheDuplicate(String[] input) {
  ArrayList<String> uniques;
  String duplicate;

  for(0 ... input.length) {
    if(!unique.contains(input[i])) {
      simplicate.add(input[i]);
    } else {
      duplicate = input[i];
      break;
    }
  }
  return duplicate;
}

String[] fruitBasket = new String[] { "apple", "banana", "coconut", "durian",
"banana", "elderberry", "fig", "grapefruit" };
findTheDuplicate(fruitBasket); //should return banana
```

### Count The Words

You have a long string that has some meaning on a real language. For example a
whole novel in a single string.
Write a function that counts the occurence of each word inside the string and
writes them to the output in the following format: `word: number of occurences`
You might assume that the input is not null and not empty. The order of the
words on the ouput does not matter.
The solution might be case insensitive, you don't have to differentiate
bwetween capital and non-capital letters.
The punctuation marks and line endings are not part of the words!

Example:

```java
public void countTheWords(String crazyLongString) {
  HashMap<String, Long> countedWords;
  ArrayList words = Arrays.asList(crazyLongString.split(" "));

  for (0 ... words.size) {
    if (!countedWords.haveKey(words.get(i)) || words.get(i) + "," || words.get(i) + ".") {
      countedWords.add(words.get(i): 1);
    } else {
      countedWords.value += 1;
    }
  }
  return countedWords;
}

String boci = "Boci, boci tarka, se füle, se farka.";
countTheWords(boci);

//Output:
//boci:2
//tarka:1
//se:2
//füle:1
//farka:1
```

### What Is The Output

What is the output of the following Java application? Explain your solution!

```java
package com.mycompany.myproject;

public class Person {
    public String firstName;
    public String lastName;

    public Person(String firstName, String lastName) {
        this.firstName = firstName;
        this.lastName = lastName;
    }  

    @Override
    public String toString() {return this.firstName + " " + this.lastName;}
}

public class Main {
    public static void main(String[] args) {
        int i = 0;
        String s = "apple";
        Person p = new Person("Jonh", "Doe");

        doSomething(i, s, p);

        System.out.println(i);
        System.out.println(s);
        System.out.println(p);
    }

    public static void doSomething(int i, String s, Person p)
    {
        i = 5;
        s += "banana";
        p.lastName = "Rambo";
    }
}

Output:

i = 5;
s = "applebanana";
p would be "John Rambo" if toString method would have been called whwn printing out p, because Person class' fields aren't encapsulated, they can be easily changed whenever anyone wants, which is bad practice.

```

## SQL

- What is the PRIMARY KEY?
- What is the difference between CLUSTERED INDEX and NONCLUSTERED INDEX?
- There is a table called `Employees`. Let's assume that the columns exist
and they have the right data type.
What is going to happen if we execute the script and we destroy
the database connection during the execution? What are the possible problems
that might occure?

```sql
BEGIN TRANSACTION

UPDATE Employees
SET Salary = Salary * 1.1
WHERE
    Salary < 250000
    AND IsActiveEmployee = 1


```

## Web and HTTP

- Specify the existing HTTP request methods and describe their usage!
```
GET is used to get data from the server, browsers by default send this type.
POST is used to send data from the client to the server usually to save data (register), or to compare it to a database entry (login).
DELETE is used to delete data from the server.
PUT is used to send data to the server to update existing data (changing password or username).
```
- What are the groups of HTTP response status codes? Write an example for each group!
```
200 - 299 - OK response.
400 - 499 - internal server error (eg. 404 is the not found).
500 - connection error.
```
