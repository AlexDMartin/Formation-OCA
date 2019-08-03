# Oracle Certified Associate
## Java Building Blocks
### Fields and methods
* Methods (procedures)
* Fields (variables)
### Comments

``` java
// single line
```

``` java
/* Multiple
 * Line Comment
 */
``` 

``` java
/**
  * Javadoc Multiple Line Comment
  *
  */
```

### Classes vs Files
* At most one of the classes in the file is allowed to be public
* If you have a public class, it needs to match the filename

### Compilation
<Will Require an image later>

### Package declarations
Package are logical grouping for classes

Import Statements tell Java which packages to look in for classes

Java classes are groupes into packages

### Wildcards
The * is a wildcard that matches all classes in the package

It doesn't import child packages, fields or methods

It imports only classes

### Redundant imports
The java.lang package is automatically imported

Java automatically looks in the current package for other classes

#### Naming conflicts
When the class is found in multiple packages, Java gives you the compiler error: 
``` 
The type XXXXX is ambiguous
``` 

If you explicitly import a class name, it takes precedence over any wildcard present

If there is a tie, we get a compiler error:
``` 
The import XXXXX collides with another import statement
``` 

You can pick one to use in import and use the others fully qualified class name\
Or have both fully qualified class names

### Packages
Default Package :
* Special Unnamed package
* Only for throwaway code
* In real life, always name your packages to avoid naming conflicts and to allow others to reuse your code

The directory structure on your computer is related to the package name
``` bash
javac packageA/classA.java packageB/classB.java
``` 
then
``` bash
java packageB.classB
``` 

### Classpath
``` bash
java -cp "[path to jar]" MyPackage.MyClass
``` 

### Creating Objects
An object is an instance of a class
#### Constructor
To create an instance you have to write ```new```  before it

The constructor is a special type of method that creates a new object

The name of the constructor must match the name of the class

:warning: There is no return type

The purpose of a constructor is to initialize fields\
Or you can do it on the line on which they are declared

You don't have to code a constructor

#### Read / write
* Reading: "getting" a variable
* Writing: "setting" a variable

#### Instance initializers
The code between braces (```{}```) is called a "code block"

Instance initializers: when a code block appears outside a method

:warning: If there is an odd number of braces or there isn't the same amount of opening and closing braces, the code will not compile

#### Order of initialization
Fields and instance initializer blocks are run in the order they appear in the file

The constructor runs after all fields and instance initializers have run

:warning: You can't refer to a variable before it has been initialized

### Primitive types
There is height built-in datat types called "Java Primitive Types"

All Java objects are just a complex collection of these primitive data types

### Reference types
A reference type refers to an object (an instance of a class)

:warning: References do not hold the value they refer to

A reference can be assigned to another object of the same type

A reference can be assigned to a new object using the ```new``` keyword

### Difference between primitives and reference
Reference types can be assigned to null

Primitive types will give you a compiler error if you attempt to assign them to null

Primitives do not have methods

All the primitive types have a lowercase type name

### Declaring and initializing variables
You need to state the variable type along with giving it a name

To initialize a variable: 
```
variableName = [desired value]
```

### Multiple initialization
You can declare many variables in the same declaration as long as they are all of the same type\
Separated by a comma
``` java
    [Type1] name1 = [value1], name2 = [value2]; // "= [valueX]" are optional
```

### Identifiers
* The name must begin with a letter or the symbol $ or _
* Subsequent characters may also be a number
* You cnnot use the same name as java reserved words

### Local variables
Local variables must be initialized before use

The compiler will not let you read an uninitialized variable

### Instance and class variables
Instance variables / class variables : variables that are not local

Instance variables are called fields

Class variables are shared across multiple objects

Class variables have  the keyword ```static``` before it

### Variable scope
Local variables can never have a scope larger than the method they are defined in\
However, they can have a smaller scope\

|   |   |
|---|---|
|Local variables|In scope from declaration to end of block|
|Instance variables|In scope from declaration until garbage collected|
|Class variables|In scope from declaration until the program ends|

### Destroying objects
Java provides a garbage collector to automatically look for objects that aren't needed anymore

Heap (free store) represents a large pool og unused memory allocated to your Java application

### Garbage Collection
Garbage Collection is the process of automatically freeing memory on the heap by deleting objects that are no longer reachable in your program

Java provides a method called ```System.gc()``` that suggests that now might be a good time to kick off a garbage collection run\
Java is free to ignore the request

An object is no longer reachable when: 
* The object no longer has any references pointing to it
* All references to the object have gone out of scope

:warning It is the object that gets garbage collected, not its references

#### Finalize()
```finalize()``` fet called if the garbage collector tries to collect the object

```finalize()``` call could run zero or one time

### Benefits of Java
* Object oriented
* Encapsulation
* Platform independent
* Robust
* Simple
* Secure