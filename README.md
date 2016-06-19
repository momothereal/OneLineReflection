# OneLineReflection

Simple reflection utility for string->value.

Example
---

See the [code example](https://github.com/momothereal/OneLineReflection/blob/master/src/ca/momoperes/onelinereflection/example/Main.java) for a ready-to-run sample.

Usage
---

In this scenario, you have an initialized object, we'll call it the context.

In the context's class, Human, you have a method, `public String getName()`, which returns the value of the field you initialized with the object.

Getting the value from `getName()` using the utility would be:

```java

Human human = new Human("Bob");
String name = (String) new ReflectionProcessor("$.getName()", human).process(); // Returns "Bob"

```

Note that `$` represents the context. You can also use `this` to access it.

_____________________

In another scenario, you want to execute a static method. No context is needed here.

In our `com.example.foo.MyClass` class, we have a static method, `public static void doSomething()`.

Invoking the method using the utility would be:

```java

new ReflectionProcessor("com.example.foo.MyClass.doSomething()").process();

```

Features
---

 - Object-oriented calls
 - Static calls
 - Fields, methods (with parameters), classes (with package), literals (String, Boolean, Integer, Long)

Disclaimer
---

This is for demonstration purposes, some features you could expect might or might not be present.

*Features not included*:

- Decimal literals (Double, Float)
- Short, Byte literals
- Constructors
