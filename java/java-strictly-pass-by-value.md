# Java is strictly pass-by-value

From [Java is Pass-by-Value, Dammit!](http://javadude.com/articles/passbyvalue.htm)
Java is strictly pass-by-value, exactly as in C.
Read the Java Language Specification (JLS). In http://java.sun.com/docs/books/jls/third_edition/html/classes.html#8.4.1

```
- Pass-by-value
  The actual parameter (or argument expression) is fully evaluated and the resulting value is copied into a location being used to hold the formal parameter's value during method/function execution. That location is typically a chunk of memory on the runtime stack for the application (which is how Java handles it), but other languages could choose parameter storage differently.
- Pass-by-reference
  The formal parameter merely acts as an alias for the actual parameter. Anytime the method/function uses the formal parameter (for reading or writing), it is actually using the actual parameter.
```

```
Java works exactly like C. You can assign a pointer, pass the pointer to a method, follow the pointer in the method and change the data that was pointed to.
However, you cannot change where that pointer points.
```
