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
Package are logical grouping for classes\
Import Statements tell Java which packages to look in for classes\
Java classes are groupes into packages

### Wildcards
The * is a wildcard that matches all classes in the package\
It doesn't import child packages, fields or methods\
It imports only classes

### Redundant imports
The java.lang package is automatically imported\
Java automatically looks in the current package for other classes

#### Naming conflicts
When the class is found in multiple packages, Java gives you the compiler error: 
``` 
The type XXXXX is ambiguous
``` 

If you explicitly import a class name, it takes precedence over any wildcard present\
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
To create an instance you have to write ```new```  before it\
The constructor is a special type of method that creates a new object\
The name of the constructor must match the name of the class\
There is no return type\
The purpose of a constructor is to initialize fields\
Or you can do it on the line on which they are declared\
You don't have to code a constructor

#### Read / write
* Reading: "getting" a variable
* Writing: "setting" a variable

#### Instance initializers
The code between braces (```{}```) is called a "code block"\
Instance initializers: when a code block appears outside a method\
:warning: If there is an odd number of braces or there isn't the same amount of opening and closing braces, the code will not compile

#### Order of initialization
Fields and instance initializer blocks are run in the order they appear in the file\
The constructor runs after all fields and instance initializers have run\
:warning: You can't refer to a variable before it has been initialized

### Primitive types
There is height built-in datat types called "Java Primitive Types"\
All Java objects are just a complex collection of these primitive data types

### Reference types
A reference type refers to an object (an instance of a class)
