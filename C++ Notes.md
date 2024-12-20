# C++ Programing Language

## About

> ### Year 
>
> Fall 2022
>

> # BY 
>
> ### A. S.  Eldesouky

## Table of Content

[TOC]

## Diving In 



### Data Input and Output



#### Input / Output Manipulators



|                         std::Keyword                         | Manipulators                                                 | Library |
| :----------------------------------------------------------: | :----------------------------------------------------------- | :-----: |
|                  boolalpha and  noboolalpha                  | switches between textual and numeric representation of booleans (function) |         |
|                   showbase and  noshowbase                   | controls whether prefix is used to indicate numeric base (function) |         |
|                  showpoint and noshowpoint                   | controls whether decimal point is always included in floating-point representation (function) |         |
|                    showpos and noshowpos                     | controls whether the `+` sign used with non-negative numbers (function) |         |
|                     skipws and noskipws                      | controls whether leading whitespace is skipped on input (function) |         |
|                  uppercase and nouppercase                   | controls whether uppercase characters are used with some output formats (function) |         |
|                    unitbuf and nounitbuf                     | controls whether output is flushed after each operation (function) |         |
|                 internal and left and right                  | sets the placement of fill characters (function)             |         |
|                     dec and hex and oct                      | changes the base used for integer I/O (function)             |         |
| fixed and scientific and hexfloat (C++11)  and defaultfloat (C++11) | changes formatting used for floating-point I/O (function)    |         |
|                              ws                              | consumes whitespace (function template)                      |         |
|                             ends                             | outputs '**\0**' (function template)                         |         |
|                            flush                             | flushes the output stream (function template)                |         |
|                             endl                             | outputs '**\n**' and flushes the output stream (function template) |         |
|          emit_on_flush and noemit_on_flush (C++20)           | controls whether a stream's basic_syncbuf emits on flush (function template) |         |
|                      flush_emit (C++20)                      | flushes a stream and emits the content if it is using a basic_syncbuf (function template) |         |
|                        resetiosflags]                        | clears the specified ios_base flags (function)               |         |
|                         setiosflags                          | sets the specified ios_base flags (function)                 |         |
|                           setbase                            | changes the base used for integer I/O (function)             |         |
|                           setfill                            | changes the fill character (function template)               |         |
|                         setprecision                         | changes floating-point precision (function)                  |         |
|                             setw                             | changes the width of the next input/output field (function)  |         |
|                      get_money (C++11)                       | parses a monetary value (function template)                  |         |
|                      put_money (C++11)                       | formats and outputs a monetary value (function template)     |         |
|                       get_time (C++11)                       | parses a date/time value of specified format (function template) |         |
|                       put_time (C++11)                       | formats and outputs a date/time value according to the specified format (function template) |         |
|                        quoted (C++14)                        | inserts and extracts quo                                     |         |



## Variables and Data Type 

- **Variables :** A named piece of memory that use to store specific types of data.
- **Data Type :** A particular kind of data item, as defined by the values it can take.

 ### Number Systems 

- There is different number systems other than decimal system (Binary, Octal, Hexadecimal, etc.)

- All data is represented by a bench of grouped cells of **0**'s and **1**'s in memory 
- Bigger numbers needs bigger memory to represent 
- Hexadecimal makes us deals with the streams of data with **0**'s and **1**'s more easier 
- Octal like hexadecimal but it's no longer used in modern times 

|   System    | Base |            Represent            |     Example      | Symbol |
| :---------: | :--: | :-----------------------------: | :--------------: | :----: |
|   Decimal   |  10  |         **0** to **9**          |       5924       |  non   |
|   Binary    |  2   |          **0** , **1**          | 0001011100100100 |   0b   |
|    Octal    |  8   |         **0** to **7**          |      13444       |   0    |
| Hexadecimal |  16  | **0** to **9** , **A** to **F** |       1724       |   0x   |

```c++
#include <iostream>
int main()
{
    // Representation in C++
    int decimal = 15 ; 
    int binary = 0b1111 ; 
    int octal = 017 ; 
    int hexa = 0xF ; 

    // Print Numbers 
    std::cout << "decimal is " << decimal << std::endl ; 
    std::cout << "binary is " << binary << std::endl ; 
    std::cout << "octal is " << octal << std::endl ; 
    std::cout << "hexa is " << hexa << std::endl ; 
}

/*	Output 
* 
*	decimal is 15
*	binary is 15 
*	octal is 15
*	hexa is 15
*/
```

### Declaration and Initialization  

```c++
// Variable braced initialization
Data_Type Variable_Name {Value} ; // 

// Function variable initialization
Data_Type Variable_Name (Value) ; 

// Assignment initialization
Data_Type Variable_Name = Value ;
```

> - Size of data type in memory 
>
> ```c++
> std::cout << sizeof(data_type) ; 
> ```

> The whole point of initialization with `{}` is to prevent or warn against potential data losses in this case. 

### Integer 

- Stores decimal 
- Typically occupies 4 bytes or more in memory (depend on system)

#### Initialization

1. Variable braced initialization

   ```c++
   #include <iostream>
   int main()
   {
       /********************************** Variable braced initialization ***************************/
       // declaration and initialization
       int variable_X {} ;							  // Initializes with zero 
       int variable_Y {10} ; 						// Initializes with 10 
       int variable_Z {15} ; 						// Initializes with 15
       int variable_F {variable_Y} ;		 // Initializes with different exist variable
       
       // Error and Warning 
       //int variable_H {variable_W} ; 	// Initializes with different not exist variable -> compiler error 
       //int variable_V {2.9} ;				 // Initializes with different data type ->  error or warning 
   
       std::cout << "variable_X: " << variable_X << std::endl ; 
       std::cout << "variable_Y: " << variable_Y << std::endl ; 
       std::cout << "variable_Z: " << variable_Z << std::endl ; 
       std::cout << "variable_F: " << variable_F << std::endl ; 
   }
   
   /*	Output 
   * 
   *	variable_X: 0
   *	variable_Y: 10
   *	variable_Z: 15
   *	variable_F: 10
   */
   ```

2. Function variable initialization

   ```c++
   #include <iostream>
   int main()
   {
       /********************************** Function variable initialization ***************************/
       // declaration and initialization
       int variable_Y (10) ; 						// Initializes with 10 
       int variable_Z (15) ; 						// Initializes with 15
       int variable_F (variable_Y) ;		 // Initializes with different exist variable 
   
       
       // Error and Warning 
       //int variable_H {variable_W} ; 	// Initializes with different not exist variable -> compiler error 
       int variable_V (2.9) ;				 // Initializes with different data type ->  information lost 
   
     
       std::cout << "variable_Y: " << variable_Y << std::endl ; 
       std::cout << "variable_Z: " << variable_Z << std::endl ; 
       std::cout << "variable_F: " << variable_F << std::endl ; 
       std::cout << "variable_V: " << variable_V << std::endl ;
   }
   
   /*	Output 
   * 
   *	variable_Y: 10
   *	variable_Z: 15
   *	variable_F: 10
   *	variable_V: 2
   */
   ```

3. Assignment initialization

   ```c++
   #include <iostream>
   int main()
   {
       /********************************** Assignment initialization ***************************/
       // declaration integer 
       int variable_name ; 
       // initialization integer with 20
       variable_name = 20 ; 
       // declaration and initialization
       int variable_X = 0 ;						// Initializes with zero 
       int variable_Y = 10 ; 						// Initializes with 10 
       int variable_Z = 15 ; 						// Initializes with 15
       int variable_F = variable_Y ;		        // Initializes with different exist variable  
   
       int variable_V = 2.9  ;				        // Initializes with different data type
   
    
       std::cout << "variable_name: " << variable_name << std::endl ; 
       std::cout << "variable_X: " << variable_X << std::endl ; 
       std::cout << "variable_Y: " << variable_Y << std::endl ; 
       std::cout << "variable_Z: " << variable_Z << std::endl ; 
       std::cout << "variable_F: " << variable_F << std::endl ; 
       std::cout << "variable_V: " << variable_V << std::endl ;
   }
   
   /*	Output 
   * 
   *	variable_name: 20
   *	variable_X: 0
   *	variable_Y: 10
   *	variable_Z: 15
   *	variable_F: 10
   *	variable_V: 2
   */
   ```

#### Modifiers

1. Singed and unsigned

   ```c++
   signed int variable_X {10} ; 		// Initializes with 10 
   signed int variable_Y {-10} ; 		// Initializes with -10 
   
   unsigned int variable_Z {10} ; 		// Initializes with 10 
   unsigned int variable_F {-10} ; 	// compiler error
   ```

   | Type with Modifiers | Bytes in memory |                  Range                  |
   | :-----------------: | :-------------: | :-------------------------------------: |
   |    unsigned int     |        4        |       **0** to **4,294,967,295**        |
   |     signed int      |        4        | **-2,147,483,648** to **2,147,483,647** |

2. long and short 

   |                     Type with Modifiers                      | Bytes in memory | Example |
   | :----------------------------------------------------------: | :-------------: | :-----: |
   |       short, short int, signed short, signed short int       |        2        | -32768  |
   |                      unsigned short int                      |        2        |   455   |
   |         long, long int, signed long, signed long int         |     4 or 8      |  -1588  |
   |                      unsigned long int                       |     4 or 8      |   33    |
   | long long, long long int, signed long long, signed long long int |        8        | -459874 |
   |                    unsigned long long int                    |        8        |  44658  |

   ```c++
   #include <iostream>
   int main()
   {
       //short and long
       short short_var {-32768} ; //  2 Bytes 
       short int short_int {455} ; // 
       signed short signed_short {122}; //
       signed short int signed_short_int {-456}; // 
       unsigned short int unsigned_short_int {456};
       
       int int_var {55} ; // 4 bytes
       signed signed_var {66};//
       signed int signed_int {77};//
       unsigned int unsigned_int{77};
       
       long long_var {88}; // 4 OR 8 Bytes
       long int long_int {33};
       signed long signed_long {44};
       signed long int signed_long_int {44};
       unsigned long int unsigned_long_int{44};
   
       long long long_long {888};// 8 Bytes
       long long int long_long_int {999};
       signed long long signed_long_long {444};
       signed long long int signed_long_long_int{1234};
       unsigned long long int unsigned_long_long_int{1234};
   
       std::cout << "Short variable, size : " << sizeof (short) << " bytes" << std::endl;
       std::cout << "Short Int, size : " << sizeof (short int) << " bytes" << std::endl;
       std::cout << "Signed short, size : " << sizeof (signed short) << " bytes" << std::endl;
       std::cout << "Signed short int, size : " << sizeof (signed short int) << " bytes" << std::endl;   
       std::cout << "unsigned short int, size : " << sizeof (unsigned short int) << " bytes" << std::endl;   
       std::cout << "---------------------" << std::endl;
   
       std::cout << "Int variable, size : " << sizeof (int) << " bytes" << std::endl;
       std::cout << "Signed variable, size : " << sizeof (signed) << " bytes" << std::endl;
       std::cout << "Signed int, size : " << sizeof (signed int) << " bytes" << std::endl;       
       std::cout << "unsigned int, size : " << sizeof (unsigned int) << " bytes" << std::endl;        
       std::cout << "---------------------" << std::endl;
   
       std::cout << "Long variable, size : " << sizeof (long) << " bytes" <<std::endl;
       std::cout << "Long int, size : " << sizeof (long int) << " bytes" << std::endl;
       std::cout << "Signed long, size : " << sizeof (signed long) << " bytes" << std::endl;
       std::cout << "Signed long int, size : " << sizeof (signed long int) << " bytes" << std::endl;  
       std::cout << "unsigned long int, size : " << sizeof (unsigned long int) << " bytes" << std::endl;  
       std::cout << "---------------------" << std::endl;
       
       std::cout << "Long long, size : " << sizeof (long long) << " bytes" << std::endl;
       std::cout << "Long long int, size : " << sizeof (long long int) << " bytes" << std::endl;
       std::cout << "Signed long long, size : " << sizeof (signed long long) << " bytes" <<std::endl;   
       std::cout << "Signed long long int, size : " << sizeof (signed long long int) << " bytes" << std::endl;       
       std::cout << "unsigned long long int, size : " << sizeof (unsigned long long int) << " bytes" << std::endl;  
       std::cout << "---------------------" << std::endl;
      
       return 0;
   }
   
   /* Output
           Short variable, size : 2 bytes
           Short Int, size : 2 bytes
           Signed short, size : 2 bytes
           Signed short int, size : 2 bytes
           unsigned short int, size : 2 bytes
           ---------------------
           Int variable, size : 4 bytes
           Signed variable, size : 4 bytes
           Signed int, size : 4 bytes
           unsigned int, size : 4 bytes
           ---------------------
           Long variable, size : 4 bytes
           Long int, size : 4 bytes
           Signed long, size : 4 bytes
           Signed long int, size : 4 bytes
           unsigned long int, size : 4 bytes
           ---------------------
           Long long, size : 8 bytes
           Long long int, size : 8 bytes
           Signed long long, size : 8 bytes
           Signed long long int, size : 8 bytes
           unsigned long long int, size : 8 bytes
           ---------------------
   */
   ```

### Fraction

- A numerical quantity that is not a whole number (e.g. 1/2, 0.5).
- Floating point numbers memory representation by **[IEEE_754](https://en.wikipedia.org/wiki/IEEE_754)** 

#### Fraction Data Type

|    Type     | Bytes in memory | Precision | Symbol (Suffixes) |       Example        |
| :---------: | :-------------: | :-------: | :---------------: | :------------------: |
|    float    |        4        |     7     |         f         |      0.123456f       |
|   double    |        8        |    15     |         -         |   0.12345678912345   |
| long double |       12        | > double  |         L         | 0.12345678912345678L |

```c++
  #include <iostream>
  #include <iomanip>
  int main()
  {
      // Declare and initialize floating point 
      float X {0.123456789123456789123456789f} ; 
      double Y {0.123456789123456789123456789} ; 
      long double Z {0.123456789123456789123456789L} ; 

      // Size of data types
      std::cout << "Size of float: " << sizeof(float) << std::endl ; 
      std::cout << "Size of double: " << sizeof(double) << std::endl ; 
      std::cout << "Size of long double: " << sizeof(long double) << std::endl ; 

      // Precision of floating point
      std::cout << std::setprecision(20) ;        // control srd::cout precision length
      std::cout << "float: " << X << std::endl ; 
      std::cout << "double: " << Y << std::endl ; 
      std::cout << "long double: " << Z << std::endl ; 
  }

  /* Output
          Size of float: 4
          Size of double: 8
          Size of long double: 16

          float: 0.12345679104328155518				  #valid 7 precision 
          double: 0.1234567891234567838		  		#valid 15 precision
          long double: 0.12345678912345678912		#valid longer than 15 precision
  */
```

#### Narrowing Conversion

- Precision is a problem for a **float** data type because it's very limited.
- **double & long double** commonly used for floating point representation.

```c++
#include <iostream>
#include <iomanip>
int main()
{
    float X {123400081945.0f} ; 
    double Y {123400081945.0} ; 

    std::cout << std::setprecision(20) ;        // control srd::cout precision length
    std::cout << "float: " << X << std::endl ; 
    std::cout << "double: " << Y << std::endl ;
}

/* Output 
        float: 123400085504
        double: 123400081945
*/
```

 #### Scientific Notation

- Scientific notation is a way of expressing numbers that are too large or too small to be conveniently written in decimal form.

  ![Scientific Notation Definition](/image/scientific-notation.svg)

```c++
#include <iostream>
#include <iomanip>
int main()
{
    double X {192400023} ; 
    double Y {1.92400023e8} ; 
    double Z {1.924e8} ;

    double A {0.00000000003498} ;
    double B {3.498e-11} ;

    std::cout << std::setprecision(20) ;        // control srd::cout precision length
    std::cout << "X: " << X << std::endl ; 
    std::cout << "Y: " << Y << std::endl ;
    std::cout << "Z: " << Z << std::endl ;
    std::cout << "A: " << A << std::endl ;
    std::cout << "B: " << B << std::endl ;
}

/* Output 
        X: 192400023
        Y: 192400023
        Z: 192400000
        A: 3.4979999999999998372e-11
        B: 3.4979999999999998372e-11
*/
```

#### Infinity and NaN

- Infinity happened when we try to divide **value** over **0** 
- NaN happened when we try to divide **0.0** over **0.0**

```c++
#include <iostream>
int main()
{
    double X {5.6} ; 
    double Y {-5.6} ; 
    double Z {} ; 

    std::cout << "X / Z = " << X / Z << std::endl; 
    std::cout << "Y / Z = " << Y / Z << std::endl;
    std::cout << "Z / Z = " << Z / Z << std::endl;
}

/* Output
        X / Z = inf
        Y / Z = -inf
        Z / Z = nan
*/
```

### Booleans 

- A binary variable that can have one of two possible values, **0** (false) or **1** (true).
- Use in decision statement or function return 
- Take one byte in memory

```c++
#include <iostream>
int main()
{
    bool red {false};
    bool green {true};
    
    //size of boolean
    std::cout << "Size of bool : " << sizeof(bool) << std::endl;

    if (red == true)
    {
        std::cout << "Stop!" << std::endl;
    }
    else
    {
        std::cout << "Go through!" << std::endl;
    }

    if (green)
    {
        std::cout << "The light is green!" << std::endl;
    }
    else
    {
        std::cout << "The light is NOT green!" << std::endl;
    }

    //1 -->> true
    //0 -->> false
    std::cout << "red : " << red << std::endl;
    std::cout << "green : " << green << std::endl;

    std::cout << std::boolalpha;                // control std::cout output for booleans data
    std::cout << "red : " << red << std::endl;
    std::cout << "green : " << green << std::endl;
}

/* Output
        Size of bool : 1   
        Go through!        
        The light is green!
        red : 0
        green : 1
        red : false        
        green : true
*/
```

### Characters

- A data type that holds one character (letter, number, etc.)

- Take one byte in memory (2^8 = 256 different values **0~255**)

- Use **ASCII** code for representation

   ![ASCII Code](/image/ASCII-Table.png)

  > - It's possible to assign a valid ASCII code to a char variable, and the corresponding character will be stored in.
  > - ASCII was the first encoding representation text in a computer.
  > - It doesn't represent all characters (e.g. Arabic, east Asian language).
  > - There's better way to represent character in C++ like **Unicode**

```c++
#include <iostream>
int main()
{
	char character1 {'a'};
    char character2 {'r'};
    char character3 {'r'};
    char character4 {'o'};
    char character5 {'w'};
    
    std::cout << character1 << std::endl;
    std::cout << character2 << std::endl;
    std::cout << character3 << std::endl;
    std::cout << character4 << std::endl;
    std::cout << character5 << std::endl;
    
    char value = 65 ;                               				// ASCII character code for 'A'
    std::cout << "value : " << value << std::endl;  // A
    std::cout << "value as intager : " << static_cast<int>(value) << std::endl; 
}

/* Output
        a
        r        
        r        
        o        
        w        
        value : A
        value as intager : 65
*/
```

### Auto 

Let the compiler deduce the type 

```c++
#include <iostream>
int main()
{
	auto A {12};        // int
    auto B {13.0};      // double
    auto C {14.0f};     // float
    auto D {15.0l};     // long double
    auto E {'e'};       // char
    auto F { 123u};     // unsigned int
    auto G { 123ul};    //unsigned long int
    auto H { 123ll};    // long long int

    std::cout << "A occupies : " << sizeof(A) << " bytes" << std::endl;
    std::cout << "B occupies : " << sizeof(B) << " bytes" << std::endl;
    std::cout << "C occupies : " << sizeof(C) << " bytes" << std::endl;
    std::cout << "D occupies : " << sizeof(D) << " bytes" << std::endl;
    std::cout << "E occupies : " << sizeof(E) << " bytes" << std::endl;
    std::cout << "F occupies : " << sizeof(F) << " bytes" << std::endl;
    std::cout << "G occupies : " << sizeof(G) << " bytes" << std::endl;
    std::cout << "H occupies : " << sizeof(H) << " bytes" << std::endl;
}

/* Output 
        A occupies : 4 bytes 
        B occupies : 8 bytes 
        C occupies : 4 bytes 
        D occupies : 16 bytes
        E occupies : 1 bytes 
        F occupies : 4 bytes 
        G occupies : 4 bytes
        H occupies : 8 bytes
*/
```

### Assignment 

- Change the data after declare it with another value 
- Don't change the value of **auto** data type with another to avoid garbage value

```c++
#include <iostream>
int main()
{
	int A{123}; // Declare and initialize
    std::cout << "A : "  << A << std::endl;
    
    A = 55; // Assign
    std::cout << "A : "  << A << std::endl;

    std::cout << "----------------" << std::endl;

    double B {44.55}; // Declare and initialize
    std::cout << "B : " << B << std::endl;
    
    B = 99.99; // Assign
    std::cout << "B : " << B << std::endl;

    std::cout << "----------------" << std::endl;

    bool state{false}; // Declare and initialize
    std::cout << std::boolalpha;
    std::cout << "state : " << state << std::endl;
    
    state = true; // Assign
    std::cout << "state : " << state << std::endl;

    std::cout << "----------------" << std::endl;
    
    auto C {333u}; // Declare and initialize with type deduction
    std::cout << "C : " << C << std::endl;
    
    C = -22; // Assign negative number. DANGER!
    std::cout << "C : " << C << std::endl;
}

/* Output
        A : 123
        A : 55
        ----------------
        B : 44.55       
        B : 99.99       
        ----------------
        state : false
        state : true
        ----------------
        C : 333
        C : 4294967274
*/
```

### Enumeration

An enumeration is a user-defined data type that consists of integral constants. To define an enumeration, keyword `enum` is used. Each enumeration is represented by an integral value under the hood.

```c++
// Declaration 
enum Enumeration_Name {variable_0, variable_1, variable_2, ...., variable_n}; 

// Initilization
Enumeration_Name Variable_Name {variable_x} ; 
```

By default, variable_0 is 0, variable_1 is 1 and so on. You can change the default value of an `enum` element during declaration (if necessary).

```c++
enum Enumeration_Name 
{
    variable_0 = 5, 
    variable_1 = 3,
    variable_2 = 79
}; 
```

When you create an enumerated type, only blueprint for the variable is created. Here's how you can create variables of `enum` type. 

```c++
enum boolean { false, true };

// inside function
enum boolean check;

/************************************ using different syntax ************************************/
enum boolean 
{ 
   false, true
} check;
```

![enum](/image/enum.webp)

#### enum class

C++11 has introduced `enum` classes (also called scoped enumerations), that makes enumerations both strongly typed and strongly scoped. Class `enum` doesn’t allow implicit conversion to int, and also doesn’t compare enumerators from different enumerations. We can now specify the underlying type of the enumeration (as long as it’s an integer type). The default is integer; as with C++98. 

![enum_cast](/image/enum_cast.webp)

```c++
// Declaration 
enum class Enumeration_Name {variable_0, variable_1, variable_2, ...., variable_n}; 

// Initilization
Enumeration_Name Variable_Name {Enumeration_Name::variable_x} ; 
```

![enum_class](/image/enum_class.webp)

#### using enum C++20

A `using-enum-declaration` introduces the enumerator names of the named enumeration as if by a `using-declaration` for each enumerator. When in class scope, a `using-enum-declaration` adds the enumerators of the named enumeration as members to the scope, making them accessible for member lookup. 

```c++
enum class Month 
{
    jan, feb, mar, apr,
    may, jun, jul, aug, 
    sep, oct, nov, dec
};

// without using enum

std::string_view month_to_string (Month month)
{
    switch (month)
    {
        case Month::jan : return "january" ; 
        case Month::feb : return "february" ;
        .
        .
        .    
    }
}

// with using enum

std::string_view month_to_string (Month month)
{
    switch (month)
    {
        using enum Month
        case jan : return "january" ; 
        case feb : return "february" ;
        .
        .
        .    
    }
}
```

### Structures

Structure is a collection of variables of different data types under a single name. It is similar to a classes in that, both holds a collection of data of different data types. 

#### Declaration 

```c++
struct structName 
{
    // variables declaration  
};
```

#### Initialization  

```c++
structName objectName ; 
objectName.variableName = variableData ; 
```

> A structure variable can be passed to a function in similar way as normal argument.

#### Structured Binding

Structured binding is one of the newest features of C++17 that binds the specified names to sub-objects or elements of initializer. In simple words, Structured Bindings give us the ability to declare multiple variables initialized from a tuple or struct. The main purpose of Structured Bindings in C++ 17 is to make the code clean and easy to understand. Like a reference, a structured binding is an ***alias to an existing object***. Unlike a reference, the type of a structured binding ***does not have to be a reference type***.

```c++
auto [identifier-list] = expression ;
```

Example 

```c++
#include <bits/stdc++.h>

struct Point
{
	int x;
	int y;
};

int main( )
{
	Point p = { 1,2 };
	
	// Structure binding
	auto[ x_coord, y_coord ] = p;
	
	std::cout << "X Coordinate : " << x_coord << std::endl;
	std::cout << "Y Coordinate : " << y_coord << std::endl;
	
	return 0;
}
```

#### Designated Initializers C++20



### Aggregate Initialization



### Type Aliases 

Type alias is a name that refers to a previously defined type, similar to `typedef`.

```c++
using Identifier_Name = Data_Type ; 
Identifier_Name Variable_Name = Value ; 
```

> Recommended in modern C++

### Variable Lifetime

The period of time in which a variable is alive in memory. It becomes alive when you declare it and it is killed (wiped out) from memory at some point.

1. Local Duration: dies at the end of the block
2. Static Duration: dies at the end of the program 
3. Dynamic Duration: you decide when it dies

### Variable Scope

A region in your code where a variable name can be mentioned. You may be reading from it, writing into it, basically using it in any conceivable way.

> Trying to use a variable out of it’s scope will result in a compiler error.     

1. Global Variable: it's a variable with global scope, meaning that it is visible throughout the program.
2. Local Variable:  it's a variable that is given local scope. Local variable references in the function or block in which it is declared override the same variable name in the larger scope.

![Difference-Between-Local-and-Global-Variable-Comparison-Summary (1)](/image/Difference-Between-Local-and-Global-Variable-Comparison-Summary (1).jpg)

## Operations on Data

### Basic Operations

|  Operation  | Symbol | Operands |   Example   |
| :---------: | :----: | :------: | :---------: |
|  Addition   |   +    |    2     | 5 + 26 = 31 |
| Subtraction |   -    |    2     | 36 - 5 = 31 |
|  Multiply   |   *    |    2     | 6 * 5 = 30  |
|  Division   |   /    |    2     | 31 / 10 = 3 |
|   Modulus   |   %    |    2     | 31 % 10 = 1 |

### Increment and Decrement

| Operation | Symbol | Operands |  Example   |
| :-------: | :----: | :------: | :--------: |
| Increment |   ++   |    1     | X++ or ++X |
| Decrement |   --   |    1     | Y-- or --Y |

> Prefix vs. Postfix.
>
> ![Difference between postfix and prefix](/image/Difference-Between-Prefix-and-Postfix-Comparison-Summary.jpg)
>
> ![value of  postfix and prefix](/image/postfix-and-prefix-operators.jpg)

### Assignment Operators 

|   Operation    | Symbol | Operands | Example |
| :------------: | :----: | :------: | :-----: |
|   sum equal    |   +=   |    2     | A  += 5 |
| subtract equal |   -=   |    2     | B -= 5  |
| multiply equal |   *=   |    2     | C *= 5  |
|  divide equal  |   /=   |    2     | D /= 5  |
| modulus equal  |   %=   |    2     | E %= 5  |

### Relational Operators 

|      Operation       | Symbol | Operands | Example |
| :------------------: | :----: | :------: | :-----: |
|      less than       |   <    |    2     |  X < Y  |
|  less than or equal  |   <=   |    2     | X <= Y  |
|     bigger than      |   >    |    2     |  X > Y  |
| bigger than or equal |   >=   |    2     | X >= Y  |
|        equal         |   ==   |    2     | X == Y  |
|      not equal       |   !=   |    2     | X != Y  |

> return Booleans value (**true** or **false**).

### Logical Operator

| Operation | Symbol | Operands | Example  |
| :-------: | :----: | :------: | :------: |
|    AND    |   &&   |    2     |  X && Y  |
|    OR     |  \|\|  |    2     | X \|\| Y |
|    NOT    |   !    |    1     | !X or !Y |

### Ternary Operators

The conditional operator is kind of similar to the if-else statement as it does follow the same algorithm as of if-else statement but the conditional operator takes less space and helps to write the if-else statements in the shortest way possible.

```c++
variable = (Expression1) ? Expression2 : Expression3
```

![Ternary operator-in-c](/image/Ternary-operator-in-c.png)

> all Expressions must be can compared (same data type).

### Comma Operator

- The comma operator (represented by the token `,`) is a binary operator that evaluates its first operand and discards the result, it then evaluates the second operand and returns this value (and type). The comma operator has the lowest precedence of any C operator, and acts as a sequence point. 
- Comma acts as a separator when used with function calls and definitions, function like macros, variable declarations, enum declarations, and similar constructs.
-  We know that in C and C++, every statement is terminated with a semicolon but comma operator also used to terminate the statement after satisfying the following rules. 
  1. The variable declaration statements must be terminated with semicolon.
  2. The statements after declaration statement can be terminated by comma operator.
  3. The last statement of the program must be terminated by semicolon.

### Precedence and Associativity

![precedence](/image/precedence.png)

## Control Flow

Control flow is the order in which individual statements, instructions or function calls of an imperative program are executed or evaluated.

### if Statement

```c++
// use for testing one condition 
if (condition)
{
    // Code if the condition is true 
}
else 
{
    // Code if the condition is false
}
```

> - Condition return true or false only
> - True conditions: is any number different than 0, or expression evaluating to something other than 0 
> - False conditions: is any number equal to 0, or expression evaluating to 0

### else if Statement

```c++
// use for testing multiple conditions 
if (condition 1)
{
    // Code if the condition 1 is true 
}
else if (condition 2)
{
    // Code if the condition 2 is true 
}
else if (condition 3)
{
    // Code if the condition 3 is true 
}
else 
{
    // Code if the three conditions is false
}
```

 ### switch Statement 

```c++
// use for testing several different conditions
switch (condition)
{
    case A:
        // code if the variable match with case A
    break ; 
    case B:
        // code if the variable match with case B
    break ;  
    case C:
        // code if the variable match with case C
    break ; 
    default:
        // code if the variable not matching with any case
    break ;
}
```

> if the **break** isn't existed after the **case** is finished, the program will continue to the next **case** until finding a **break** or end of the **switch** statement  

### Short Circuit Evaluation 

Short-circuiting is a programming concept by which the compiler skips the execution or evaluation of some sub-expressions in a logical expression. The compiler stops evaluating the further sub-expressions as soon as the value of the expression is determined.

```c++
int main()
{
    int a = 10;
    int b = -1;
  
    // Here b == -1 is not evaluated as
    // a != 10 is false
    if (a != 10 && b == -1) {
        printf("I won't be printed!\n");
    }
    else {
        printf("Hello, else block is printed");
    }
    
    a = 0;
    // myfunc(b) will not be called
    if (a != 0 && myfunc(b)) {
        // do_something();
    }
    
    a = 15;
    // Here since a is 10, calculate_sqrt
    // function will be called
    if (a >= 10 && calculate_sqrt(a)) {
        printf("I will be printed!\n");
    }
  
    return 0;
}
```

### if constexpr

a C++17 feature which allows conditionally compiling code based on template parameters in a clear and minimal fashion.

 ```c++
 constexpr bool condition {false} ; 
 if constexpr (condition)
 {
     // Code if the condition is true 
 }
 else 
 {
     // Code if the condition is false
 }
 ```

> condition must be constexpr or exist before compile time 

### if with Initializer 

a C++17 has extended existing if statement’s syntax. Now it is possible to provide initial condition within if statement itself. This new syntax is called "if statement with initializer". This enhancement simplifies common code patterns and helps users keep scopes tight. Which in turn avoids variable leaking outside the scope.

```c++
if (init; condition) 
{
   // Code if the condition is true 
} else 
{
   // Code if the condition is false
}
```

### switch with Initializer 

```c++
switch (init; condition)
{
    case A:
        // code if the variable match with case A
    break ; 
    case B:
        // code if the variable match with case B
    break ;  
    case C:
        // code if the variable match with case C
    break ; 
    default:
        // code if the variable not matching with any case
    break ;
}
```

## Loops 

- A loop is used for executing a block of statements repeatedly until a particular condition is satisfied.
- the main components of a loop are
  1. Iterator
  2. Starting Point
  3. Test( controls when the loop stops)
  4. Increment(Decrement)
  5. Loop body

### for Loop

```c++
for (initialization; condition; update) 
{
    // body of-loop 
}
```

or we can initialize the iterator outside the loop scope 

```c++
Data_Type initialization ;  
for ( ; condition; update) 
{
    // body of-loop 
}
```

- `initialization` - initializes variables and is executed only once
- `condition` - if `true`, the body of `for` loop is executed, if `false`, the for loop is terminated
- `update` - updates the value of initialized variables and again checks the condition
	 `Iterator` must be integral data type, we can use `size_t` instead of `unsigned int` 	

<img src="/image/cpp-for-loop-flowchart.webp" alt="cpp-for-loop-flowchart" style="zoom:50%;" />

We can use multiple declarations and updates in for loop 

```c++
for (initialization1, initialization2, ...; condition; update1, update2, ...) 
{
    // body of-loop 
}
```

 ### Rang Based for Loop

In C++11, a new range-based `for` loop was introduced to work with collections such as **arrays** and **vectors**. 

```c++
for (variable : collection) 
{
    // body of loop
}
```

Example 

```c++
#include <iostream>

int main() 
{
    int num_array[] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
  
    for (int n : num_array) 
    {
        cout << n << " ";
    }
    return 0;
}

/* 
* Output:1 2 3 4 5 6 7 8 9 10
*/
```

> Range based for loop with initializer, helper variable in loop scope (C++20)
>
> ```c++
> for (initialization; variable : collection) 
> {
>     // body of loop
> }
> ```

### while Loop

```c++
while (condition) 
{
    // body of the loop
}
```

- A `while` loop evaluates the `condition`
- If the `condition` evaluates to `true`, the code inside the `while` loop is executed.
- The `condition` is evaluated again.
- This process continues until the `condition` is `false`. 
- When the `condition` evaluates to `false`, the loop terminates.

<img src="/image/cpp-while-loop-flowchart.webp" alt="cpp-while-loop-flowchart" style="zoom:50%;" />

### do while Loop

The `do...while` loop is a variant of the `while` loop with one important difference: the body of `do...while` loop is executed once before the `condition` is checked.

```c++
do 
{
   // body of loop;
}
while (condition);
```

- The body of the loop is executed at first. Then the `condition` is evaluated.
- If the `condition` evaluates to `true`, the body of the loop inside the `do` statement is executed again.
- The `condition` is evaluated once again.
- If the `condition` evaluates to `true`, the body of the loop inside the `do` statement is executed again.
- This process continues until the `condition` evaluates to `false`. Then the loop stops.

<img src="/image/cpp-do-while-loop-flowchart.webp" alt="cpp-do-while-loop-flowchart" style="zoom:50%;" />

### Infinite Loops

If the `condition` in a loops are always `true`, it runs forever (until memory is full).

```c++
for( ; ; ) 
{
      // body of loop;
}
```

```c++
while () 
{
    // body of the loop
}
/********************************/
while (true) 
{
    // body of the loop
}
```

```c++
do 
{
   // body of loop;
}
while ();
/********************************/
do 
{
   // body of loop;
}
while (true);
```

### Nested Loops

A loop within another loop is called a nested loop.

```c++
for (initialization; condition; update) 
{
    // body of-loop 
    for (initialization; condition; update) 
    {
        // body of-loop
        for (initialization; condition; update) 
        {
            // body of-loop
            // we can do this as we need 
        } 
    } 
}
```

```c++
while (condition) 
{
    // body of the loop
    while (condition) 
    {
        // body of the loop
        while (condition) 
        {
            // body of the loop
            // we can do this as we need 
        }
    }
}
```

```c++
do 
{
   // body of loop;
    do 
    {
       // body of loop;
       // we can do this as we need 
    }
    while (condition);
}
while (condition);
```

### break 

the `break` statement terminates the loop when it is encountered.

```c++
break ;
```

> `break` statement is usually used with decision-making statements.

<img src="/image/cpp-break-statement.webp" alt="cpp-break-statement" style="zoom:50%;" />

### continue 

In computer programming, the `continue` statement is used to skip the current iteration of the loop and the control of the program goes to the next iteration.

```c++
continue ;
```

> `continue` statement is almost always used with decision-making statements.

<img src="/image/cpp-continue-statement.webp" alt="cpp-continue-statement" style="zoom:50%;" />

## Arrays

An array is a collection of elements of the same type placed in contiguous memory locations that can be individually referenced by using an index to a unique identifier.

### Declaration and Initialization

```c++
// Declaration 
Data_Type arr_name [arr_size] ; 

// Declaration and Initialization
Data_Type arr_name [arr_size] {item1, item2, item3, ..., item(arr_size-1)} ; 
```

 ```c++
 // declare and initialize and array
 int x[6] {19, 10, 8, 17, 9, 15};
 
 /**************************** or ****************************/
 
 // declare and initialize an array
 int x[] {19, 10, 8, 17, 9, 15};
 ```

<img src="/image/cpp-array-initialization.webp" alt="cpp-array-initialization" style="zoom:50%;" />

If an array has a size `n`, we can store up to n number of elements in the array. In such cases, the compiler assigns random values to the remaining places. Oftentimes, this random value is simply `0`.

```c++
// store only 3 elements in the array
int x[6] {19, 10, 8};
```

<img src="/image/cpp-array-empty-members.webp" alt="cpp-array-empty-members" style="zoom:50%;" />

### Array Access

In C++, each element in an array is associated with a number. The number is known as an array index. We can access elements of an array by using those indices.

```c++
// syntax to access array elements
arr[index];
```

<img src="/image/cpp-array-declaration.webp" alt="cpp-array-declaration" style="zoom:50%;" />

- The array indices start with `0`. Meaning x[0] is the first element stored at index `0`.
- If the size of an array is `n`, the last element is stored at index `(n-1)`. 
- Elements of an array have consecutive addresses. For example, suppose the starting address of `x[0]` is 2120d. Then, the address of the next element `x[1]` will be 2124d, the address of `x[2]` will be 2128d and so on.
- If we declare an array of size 10, then the array will contain elements from index 0 to 9, if we try to access the element at index 10 or more than 10, it will result in Undefined Behavior.

 ### Size of Arrays

Before C++ 17 there's only way to find size of an array.

```c++
size = sizeof(arr_name) / sizeof(arr_name[0]) ; 
```

After C++ 17 we got a new way to find the size of an array.

```c++
size = std::size(arr_name) ; 
```

> ### Omit Array Size
>
> You don't have to specify the size of the array. But if you don't, it will only be as big as the elements that are inserted into it, but it's available for only one the first dimension of the array.
>
> ```c++
> Data_Type arr_name [] ; 
> Data_Type arr_name [][2nd_D_arr_size] ;
> Data_Type arr_name [][2nd_D_arr_size][3rd_D_arr_size] ;
> ```

### Array of  Characters 

String is a collection of characters. There are two types of strings commonly used in C++ programming language:

- Strings that are objects of string class (The Standard C++ Library string class)
- C-strings (C-style Strings)

Now we'll just take C-strings. In C programming, the collection of characters is stored in the form of arrays. This is also supported in C++ programming. Hence it's called C-strings.

C-strings are arrays of type `char` terminated with null character, that is, `\0` (ASCII value of null character is 0).

```c++
char string_name[] = "string_data" ;

char string_name[] {"string_data"} ;

char string_name[5] {"Data"} ;

char string_name[] {'D', 'a', 't', 'a', '\0'} ;

char string_name[5] {'D', 'a', 't', 'a', '\0'} ;
```

> `cctype` and `cstring` are a libraries containing different functions to deal with strings.

### Multi Dimensional Array

In C++, we can create an array of an array, known as a multidimensional array.

![123D array](/image/123D-array.png)

#### 2D Array

```c++
/****************************** 2D Array ******************************/
// Declaration 
Data_Type arr_name [1st_D_arr_size][2nd_D_arr_size] ;

// Declaration and Initialization
Data_Type arr_name [1st_D_arr_size][2nd_D_arr_size] {{1st_D_Data}, {2nd_D_Data}} ;
```

![2Darray](/image/2Darray.png)

#### 3D Array

```c++
/****************************** 3D Array ******************************/
// Declaration 
Data_Type arr_name [1st_D_arr_size][2nd_D_arr_size][3rd_D_arr_size] ;

// Declaration and Initialization
Data_Type arr_name [1st_D_arr_size][2nd_D_arr_size][3rd_D_arr_size] 
{     /************** 2nd_D_Data **************/
    { {3rd_D_Data}, {3rd_D_Data},  {3rd_D_Data} }, // 1st_D_Data
    { {3rd_D_Data}, {3rd_D_Data},  {3rd_D_Data}},  // 1st_D_Data
    { {3rd_D_Data}, {3rd_D_Data},  {3rd_D_Data}},  // 1st_D_Data
} ;
```

<img src="/image/3D-array.jpg" alt="3D-array" style="zoom:67%;" />

## Pointers

Pointers are variables that store the memory addresses of other variables. If we have a variable `var` in our program, `&var` will give us its address in the memory.

![cpp-pointer-working](/image/cpp-pointer-working.webp)

### Declaration and Initialization

```c++
// Declaration 
Data_Type *ptr ; 

// Declaration and Initialization
Data_Type *ptr {Value} ; 

// Initialization
int var {} ;
ptr = &var ; 
```

> - ***** it's called the **dereference operator**. It operates on a pointer and gives the value pointed by the address stored in the pointer. That is, `*pointVar = var`.
> - `ptr` and `*ptr` is completely different. We cannot do something like `*ptr = &var;`
> - Pointer to another variable must be same data type or get compiler error. 

```c++
// wirting into uninitialized pointer is very BAD!!!
int * ptr ; // unkown address
* ptr = 5 ; // very BAB, writing in junk address
// must initilize the pointer before use it.
```

### Pointer to Array

```c++
int *ptr;
int arr[5];
ptr = arr;
```

![cpp-pointers-and-arrays](/image/cpp-pointers-and-arrays.png)

> Array names decay to pointers. In simple words, array names are converted to pointers. That's the reason why we can use pointers to access elements of arrays.

### Constant with Pointers

![PointersWithConstants-1024x535](/image/PointersWithConstants-1024x535.png)

1. Non const pointer to Non const data

   ```c++
   /*********** Non const pointer to Non const data ***********/
   int * ptr {} ; 
   int var {10} ; 
   
   ptr = &var ; 
   
   // can change the pointed value to another 
   *ptr = 5 ;
   
   // can change the pointer itself
   int x {20} ; 
   ptr = &x ; 
   ```

2. Non const pointer to const data

   ```c++
   /*********** Non const pointer to const data ***********/
   int const * ptr {} ; 
   const int var {10} ; 
   
   ptr = &var ; 
   
   // can't change the pointed value to another 
   *ptr = 5 ; // compiler error
   
   // can change the pointer itself
   int x {20} ; 
   ptr = &x ; 
   ```

3. const pointer to Non const data

   ```c++
   /*********** const pointer to Non const data ***********/
   int * const ptr {} ; 
   const int var {10} ; 
   
   ptr = &var ; 
   
   // can change the pointed value to another 
   *ptr = 5 ; 
   
   // can't change the pointer itself
   int x {20} ; 
   ptr = &x ; // compiler error
   ```

4. const pointer to const data

   ```c++
   /*********** const pointer to const data ***********/
   int const * const ptr {} ; 
   const int var {10} ; 
   
   ptr = &var ; 
   
   // can't change the pointed value to another 
   *ptr = 5 ; // compiler error
   
   // can't change the pointer itself
   int x {20} ; 
   ptr = &x ; // compiler error
   ```

> One way to remember the syntax (according to Bjarne Stroustrup) is the `spiral rule`.
> The rule says, start from the name of the variable and move clockwise to the next pointer or type. Repeat until expression ends.
>
> ![spiral-2](/image/spiral.jpg)

### Pointer Arithmetic 

A set of operations we can do on the pointer representing the array to manipulate the array. These operations can include navigating from element to element, computing the distance between elements and comparing addresses of elements.

<img src="/image/cpp_memory_pointer_arithmetic_07.svg" alt="cpp_memory_pointer_arithmetic_07" style="zoom:50%;" />

> `std::ptrdiff_t` is the signed integer type of the result of subtracting two pointers.

### Dynamic Memory Allocation 

Lot’s of programs running on our OS. We can quickly run our of memory.

A trick that fools your program into thinking it is the only program running on your OS, and all memory resources belong to it. Each program is abstracted into a process, and each process has access to the memory range 0 ~ 2𝑁, where N is 32 on 32 bit systems and 64 on 64 bit.

The entire program is not loaded in real memory by the CPU and MMU. Only parts that are about to be executed are loaded. Making effective use of real memory, a valuable and lacking resource. The memory map is a standard format defined by the OS. All programs written for that OS must conform to it. It is usually divided into some sections.

![memory-layout-in-c](/image/memory-layout-in-c.png)

So far we’ve only been using memory allocated on the stack. We are going to see how one can allocate memory from the heap, and some of the differences between these mechanisms.

![stack vs heap](/image/stack-vs-heap.png)

We can allocate and then deallocate memory dynamically using the `new` and `delete` operators respectively.

1. `new` operator returns the address of the **memory location**.

    ```c++
    Data_Type *ptr = new Data_Type ;
    
    /************************* Example *************************/
    // declare an int pointer
    int * ptr;
    
    // dynamically allocate memory
    // using the new keyword 
    ptr = new int;
    
    // assign value to allocated memory
    *ptr = 45;
    ```

 2. `delete` operator is used. It returns the memory to the operating system. This is known as **memory deallocation**.

    ```c++
    delete ptr;
    
    /************************* Example *************************/
    // declare an int pointer
    int * ptr;
    
    // dynamically allocate memory
    // using the new keyword 
    ptr = new int;
    
    // assign value to allocated memory
    *ptr = 45;
    
    // print the value stored in memory
    cout << *ptr; // Output: 45
    
    // deallocate the memory
    delete ptr;
    ```

> If the program uses a large amount of unwanted memory using `new`, the system may crash because there will be no memory available for the operating system. In this case, the `delete` operator can help the system from crash.

In some rare cases, the ‘new’ operator will fail to allocate dynamic memory from the heap. When that happens, and you have no mechanism in place to handle that failure, an exception will be thrown and your program will crash. ‘new’ fails very rarely in practice and you’ll see many programs that assume that it always works and don’t check for memory allocation failure in any way. Depending on your application, failed memory allocations can be very bad and you need to check and handle them.

```c++
int * data = new int[10000000000000000]; //CRASH!
```

There's two ways to check for failed memory allocations:

1. Through the exception mechanism

   ```c++
   //exception
   for(size_t i{0} ; i < 100 ; ++i)
   {
       try
       {
           int * data = new int[1000000000];
       }
       catch(std::exception& ex)
       {
           std::cout << "  Something went wrong : " << ex.what() << std::endl;
       }
   }
   ```

2. `std::notthrow` setting

   ```c++
   //std::nothrow
   for(size_t i{0} ; i < 100 ; ++i)
   {
       int * data = new(std::nothrow) int[1000000000];
       if(data!=nullptr)
       {
           std::cout << "Data allocated" << std::endl;
       }
       else
       {
           std::cout << "Data allocation failed" << std::endl;
       }  
   }
   ```

### Dynamic Array

A dynamic array is quite similar to a regular array, but its size is modifiable during program runtime. Dynamic Array elements occupy a contiguous block of memory. Once an array has been created, its size cannot be changed. However, a dynamic array is different. A dynamic array can expand its size even after it has been filled. During the creation of an array, it is allocated a predetermined amount of memory. This is not the case with a dynamic array as it grows its memory size by a certain factor when there is a need.

```c++
DataType * ptr_array { new DataType[size]{} } ; 
```

- Regular arrays have a fixed size. You cannot modify their size once declared.
- With these types of arrays, the memory size is determined during compile time.
- Dynamic arrays are different. Their sizes can be changed during runtime.
- In dynamic arrays, the size is determined during runtime.
- Dynamic arrays in C++ are declared using the `new` keyword.
- We use `square brackets` to specify the number of items to be stored in the dynamic array.
- Once done with the array, we can free up the memory using the delete operator.
- Use the `delete` operator with `[]` to free the memory of all array elements.
- A `delete` without `[]` frees the memory of only a single element.
- There is no built-in mechanism to resize C++ arrays.
- To initialize an array using a list initializer, we don’t use the `=` operator.

### Dangling Pointer 

Dangling pointer is a pointer pointing to a memory location that has been freed (or deleted). There are different ways where Pointer acts as dangling pointer:

1. Uninitialized pointer

   ```c++
   int * p_number; // Dangling uninitialized pointer
   
   std::cout << std::endl;
   std::cout << "Case 1 : Uninitialized pointer : ." << std::endl;
   std::cout << "p_number : " << p_number << std::endl;
   std::cout << "*p_number : " << *p_number << std::endl; //CRASH!
   ```

2. Deleted pointer

   ```c++
   std::cout << std::endl;
   std::cout << "Case 2 : Deleted pointer" << std::endl;
   int * p_number1 {new int{67}};
   
   std::cout << "*p_number1 (before delete) : " << *p_number1 << std::endl;
   
   delete p_number1;
   //undefined behaviour : Crash/ garbage or whatever
   std::cout << "*p_number1(after delete) : " << *p_number1 << std::endl; 
   ```

3. Multiple pointers pointing to same memory

   ```c++
   std::cout << std::endl;
   std::cout << "Case 3 : Multiple pointers pointing to same address : " << std::endl;
   
   int *p_number3 {new int{83}};
   int *p_number4 {p_number3};
   
   std::cout << "p_number3 - " << p_number3 << " - " << *p_number3 << std::endl;
   std::cout << "p_number4 - " << p_number4 << " - " << *p_number4 << std::endl;
   
   //Deleting p_number3
   delete p_number3;
   
   //p_number4 points to deleted memory. Dereferncing it will lead to
   //undefined behaviour : Crash/ garbage or whatever
   std::cout<< "p_number4(after deleting p_number3) - " << p_number4 << " - " << *p_number4 ;
   ```

## Reference

 When a variable is declared as a reference, it becomes an alternative name for an existing variable. A variable can be declared as a reference by putting ‘&’ in the declaration. 

### Declaration and Initialization

```c++
DataType & ref_name = ref_variable ; 
```

Example 

```c++
#include <iostream>
int main()
{
  int x = 10;
  // ref is a reference to x.
  int& ref = x;
  // Value of x is now changed to 20
  ref = 20;
  std::cout << "x = " << x << '\n';
  // Value of x is now changed to 30
  x = 30;
  std::cout << "ref = " << ref << '\n';
  return 0;
}

/* Output
* x = 20
* ref = 30
*/
```

### Applications 

1. **Modify the passed parameters in a function**: If a function receives a reference to a variable, it can modify the value of the variable. For example, the following program variables are swapped using references. 
2. **Avoiding a** **copy of large structures**: Imagine a function that has to receive a large object. If we pass it without reference, a new copy of it is created which causes wastage of CPU time and memory. We can use references to avoid this. 
3. **In For Each Loops to modify all objects** : We can use references in for each loops to modify all elements. 
4. **For Each Loop to avoid the** **copy of objects**: We can use references in each loop to avoid a copy of individual objects when objects are large.  

### Reference vs. Pointer

<img src="/image/ref-vs-ptr.jpg" alt="ref vs ptr" style="zoom:67%;" />

### const Reference

A `const` reference that isn’t `const`. We can change the variable only from the original one, not from the reference variable .

```c++
const DataType & ref_name = ref_variable ; 
```

 ```c++
 #include <iostream>
 int main()
 {
 	int age {27};
 	const int& ref_age{age};
 	
 	std::cout << "age : " << age << std::endl;
 	std::cout << "ref_age : " << ref_age << std::endl;
 	
 	//Mofify through reference -> compiler error
 	//ref_age++;  
 	
 	//Mofify through original variable
 	age++;
 	
 	std::cout << "age : " << age << std::endl;
 	std::cout << "ref_age : " << ref_age << std::endl;
 }
 
 /* Output 
 * age : 27
 * ref_age : 27
 * age : 28
 * ref_age : 28
 */
 ```

## String 

Previously we said. String is a collection of characters. There are two types of strings commonly used in C++ programming language:

- Strings that are objects of string class (The Standard C++ Library string class)
- C-strings (C-style Strings)

And we spoke about C-strings in Arrays chapter, now we'll just take the standard C++ library string class. C++ has in its definition a way to represent a sequence of characters as an object of the class. This class is called `std::string`. String class stores the characters as a sequence of bytes with the functionality of allowing access to the single-byte character. 

> must include `<string>` for string class.

### Declaration and Initialization

```c++
// Declaration 
std::string str ; 

// Declaration and Initialization
std::string str {"str Data"} ; 

// Initialization
std::string str ; 
str = "str Data" ; 
```



### C-style vs. C++ Class String 

1. A character array is simply an array of characters that can be terminated by a null character. A string is a class that defines objects that be represented as a stream of characters.
2. The size of the character array has to be allocated statically, more memory cannot be allocated at run time if required. Unused allocated memory is wasted in the case of the character array. In the case of strings, memory is allocated dynamically. More memory can be allocated at run time on demand. As no memory is preallocated, no memory is wasted.
3. There is a threat of array decay in the case of the character array. As strings are represented as objects, no array decay occurs.
4. Implementation of character array is faster than `std::string`. Strings are slower when compared to implementation than character array.
5. Character arrays do not offer many inbuilt functions to manipulate strings. String class defines a number of functionalities that allow manifold operations on strings.

### Operation on string

1. Iterator Functions

   ![string Iterators](/image/string-Iterators.png)

2. Capacity Functions

   ![string capacity](/image/string-capacity.PNG)

   > by default capacity of string is `15`.

3. Access Functions

   ![string access](/image/string-access.png)

4. Manipulating Functions

   ![string manipulating](/image/string-manipulating.png)

5. Search Functions 

   ![string search](/image/string-search.png)

6. Constant 

   ![string constant](/image/string-constant.png)

7. Numeric Function 

   ![string to numeric](/image/string-to-numeric.png)

### Escape Sequence 

| Escape sequence | Description          | Representation                |
| --------------- | -------------------- | ----------------------------- |
| `\'`            | single quote         | byte `0x27` in ASCII encoding |
| `\"`            | double quote         | byte `0x22` in ASCII encoding |
| `\?`            | question mark        | byte `0x3f` in ASCII encoding |
| `\\`            | backslash            | byte `0x5c` in ASCII encoding |
| `\a`            | audible bell         | byte `0x07` in ASCII encoding |
| `\b`            | backspace            | byte `0x08` in ASCII encoding |
| `\f`            | form feed - new page | byte `0x0c` in ASCII encoding |
| `\n`            | line feed - new line | byte `0x0a` in ASCII encoding |
| `\r`            | carriage return      | byte `0x0d` in ASCII encoding |
| `\t`            | horizontal tab       | byte `0x09` in ASCII encoding |
| `\v`            | vertical tab         | byte `0x0b` in ASCII encoding |

### Raw String Literals

A raw string literal is a string in which the escape characters like **\n**, **\t** or **\”**  of C++ are not processed. Hence, this was introduced in C++11, a raw string literal which starts with `R( and ends in )`. These raw string literals allow a series of characters by writing precisely its contents like raw character sequence. 

```c++
std::string str {R "delimiter( raw_characters )delimiter"} ; 

// Ordinary String Literal 
std::string str {"\\\\n"} ; 
    
// Raw String Literal 
std::string str {R"(\\n)"} ; 
```

### string_view C++17

The std::string has some demerits, one of the most common situations is constant strings. Below is the program that demonstrates the problem that occurs in dealing with constant strings with std::string: 

```c++
// C++ program to demonstrate the
// problem occurred in string
#include <iostream>
#include <string>
  
// Driver Code
int main()
{
    char str_1[]{ "Hello !!, GeeksforGeeks" };
  
    string str_2{ str_1 };
    string str_3{ str_2 };
  
    // Print the string
    std::cout << str_1 << '\n'
         << str_2 << '\n'
         << str_3 << '\n';
  
    return 0;
}

/* Output
* Hello !!, GeeksforGeeks
* Hello !!, GeeksforGeeks
* Hello !!, GeeksforGeeks
*/

/* 
The output is the same as expected. But, in order to view “Hello !!, 
GeeksforGeeks” twice the std::string performs overheads on the memory twice. 
But here the task was to read the string (“Hello !!, GeeksforGeeks”), 
and no write operation is required on it. So just to display a string why assign memory multiple times.
In order to deal with the strings more efficiently, C++17 proposed 
std::string_view() which provides the view of pre-defined char str[] without creating a new object to the memory. 
*/ 
```

**Benefits of `std::string_view`:**

- **Light and Cheaper:** The `std::string_view` is a very light, cheaper and is mainly used to provide the view of the string. Whenever the `std::string_view` is created there is no need to copy the string in the manner as done in the above example that was inefficient and was causing overhead on the memory. It makes the copying process of the string quite efficient and never creates any copy of the string when the modification is being made in the viewed string the made changes have appeared in the `std::string_view`.
- **Better Performance:** The `std::string_view` is better than the const `std::string&` because it removes the constraint of having a `std::string` object at the very beginning of the string as `std::string_view` is composed of two elements first one is `const char*` that points to the starting position of the array and the second is size.
- **Supports crucial function:** The `std::string_view` supports mostly all crucial function that is applied over the `std::string` like `substr`, `compare`, `find`, overloaded comparison operators `(e.g., ==, <, >, !=)`. So in most of the cases, it removes the constraint of having a `std::string` object declaration when our preference is read-only.

> `std::string_view` C++17 library has proposed a standard type of string (`std::string_view`) which is different from the usual `std::string`.  

- The `std::string_view` provides a lightweight object that offers read-only access to a string or a part of a string using an interface similar to the interface of `std::_string` and merely refers to the contiguous char sequence. Unlike `std::string`, which keeps its own copy of the string, It also provides a view of a string that is defined elsewhere in the source code.
- it is composed of two members: a `const char*` that points to the start of the char array, and the _size. It is a non-owning reference to a string in itself.

![string_view_indirection](/image/string_view_indirection.svg)

## Function

A function is a block A reusable piece of code that can take a number of optional inputs and produce some desirable output that performs a specific task. 

There are two types of function:

1. Standard Library Functions: Predefined in C++
2. User-defined Function: Created by users

### Prototype and Definition 

C++ allows the programmer to define their own function. A user-defined function groups code to perform a specific task and that group of code is given a name (identifier). When the function is invoked from any part of the program, it all executes the codes defined in the body of the function.

The prototype needs to come BEFORE the function call in your file. Otherwise the compilation will fail. The full function definition coming in front of main() also doubles as a prototype(declaration).

```c++
// prototype with defination 
returnType functionName (parameter1, parameter2,...) 
{
    // function body   
    
    return returnData
}

// prototype separate from the defination 
returnType functionName (parameter1, parameter2,...); // prototype

int main ()
{
    // main body
}

returnType functionName (parameter1, parameter2,...) // definaion
{
    // function body   
    
    return returnData
}
```

### Call Functions 

To use the function, we need to call it. 

```c++
returnType functionName (parameter1, parameter2,...) 
{
    // function body   
    
    return returnData
}

int main()
{
    // calling the function 
    returnVariable = functionName (parameter1, parameter2,...) ;	// if has return value
    functionName (parameter1, parameter2,...) ;					  // if has no return value
}
```

![cpp-function-call](/image/cpp-function-call.webp)

### Multiple Source Files

Small programs are typically written in a single `.cpp` file. However, as programs get larger, it's necessary to split the source into several files in order to make the project manageable. Because C++ needs to know the declarations of functions before they are called, function prototypes (declarations) are typically written at the top of a single-file, multiple-function program. This ensures that the call and the definition are both consistent. the compiler compiles each file individually. It does not know about the contents of other code files, or remember anything it has seen from previously compiled code files. So even though the compiler may have seen the definition of function *add* previously (if it compiled *add.cpp* first), it doesn’t remember. 

> One Definition Rule : The same function implementation can’t show up in the global namespace more than once.

The linker searches for definitions in all translation units (.cpp ) files in the project. Doesn’t have to live in a . cpp file with the same name as the header.

![Multiple files](/image/Multiple_files.png)

### Function Parameters 

 a function can be declared with parameters (arguments). A parameter is a value that is passed when declaring a function. called parameters. A legal C++ function can have 0 or more parameters.

Output parameters should be passed in such a way that you can modify the arguments from inside the function. Options are passing by reference or by pointer. References are preferred in C++.

Input parameters shouldn’t be modifiable from inside a function. The function really need to get input (read) from the arguments. You enforce modification restrictions with the `const`. Options are passing by `const` reference, passing by `pointer` to `const`, or even passing by `const pointer` to `const`

> The `void` keyword, used in the previous examples, indicates that the function should not return a value. If you want the function to return a value, you can use a data type (such as `int`, `string`, etc.) instead of `void`, and use the `return` keyword inside the function.

![cpp-function-parameters](/image/cpp-function-parameters.webp)

#### Default Parameter 

You can also use a default parameter value, by using the equals sign (`=`). If we call the function without an argument, it uses the default value.

```c++
#include <iostream>

void myFunction(string country = "Egypt") 
{
  std::cout << country << "\n";
}

int main()
{
  myFunction("Sweden");
  myFunction("India");
  myFunction();
  myFunction("USA");
  return 0;
}

/* Output
* Sweden
* India
* Egypt
* USA
*/
```

#### Call by Value 

When a function is called in the call by value, the **value of the actual parameters is copied into formal parameters.** Both the actual and formal parameters have their own copies of values, therefore any change in one of the types of parameters will not be reflected by the other. This is because both actual and formal parameters point to different locations in memory (i.e. they both have different memory addresses).

![call-by-value-in-C-min](/image/call-by-value-in-C-min.png)

> - If we call by `const value`, we can't change the copy it's cause a compiler error.
> - If the passed parameters doesn't exact data type, the compiler will implement **implicit conversion**.

#### Call by Address 

In the call by address method, **both actual and formal parameters indirectly share the same variable.** In this type of call mechanism, pointer variables are used as formal parameters. The formal pointer variable holds the address of the actual parameter, hence the changes done by the formal parameter is also reflected in the actual parameter, both parameters point to different locations in memory, but since the formal parameter stores the address of the actual parameter, they share the same value. 

![call-by-Address-in-C-min](/image/call-by-Address-in-C-min.png)

```c++
// prototype with defination 
returnType functionName (*parameter) 
{
    // function body   
    
    return returnData
}
```

> - If we call by `Address to const value`, we can't change the value it's cause a compiler error.
> - If we call by `const Address to const value`, we can't change the value and the pointer point it's cause a compiler error.
> - If the passed parameters doesn't exact data type, we'll got a complier error. 

#### Call by Reference 

In the call by reference, **both formal and actual parameters share the same value.** Both the actual and formal parameter points to the same address in the memory. That means any change on one type of parameter will also be reflected by other. Calls by reference are preferred in cases where we do not want to make copies of objects or variables, but rather we want all operations to be performed on the same copy.

![call-by-reference-in-C-min](/image/call-by-reference-in-C-min.png)

```c++
// prototype with defination 
returnType functionName (&parameter) 
{
    // function body   
    
    return returnData
}
/
```

> - If we call by `Reference to const value`, we can't change the value it's cause a compiler error.
> - If the passed parameters doesn't exact data type, we'll got a complier error. 

![call by address vs call by reference](/image/Difference-Between-Call-By-Address-and-Call-By-Reference-Comparison-Summary-1.jpg)

#### Passing Array

  We can pass arrays as an argument to a function. And, also we can return arrays from a function. 

```c++
returnType functionName(dataType arrayName[arraySize, dataType arraySize) 
{
    // function body
}
```

> - It is not mandatory to specify the number of rows in the array. However, the number of columns should always be specified. This is why we have used `int n[][2]`, also we can pass arrays with more than 2 dimensions as a function argument. 
> - We can also return an array from the function. However, the actual array is not returned. Instead the address of the first element of the array is returned with the help of pointers.
> - If we pass array by reference we must pass the true array size to avoid the compiler error.
> - when an array name is passed as a function parameter, the parameter name inside the body of the function is no longer a "real array" name, and it has lost all size information it had. It becomes just a pointer to the first element of the array. `sizeof(array)` isn't going to give us the size of the entire array, it's just going to be the size of a pointer on your system. 
> - 

![Passing-Array-To-Function-In-C](/image/Passing-Array-To-Function-In-C.png)

#### Passing String

![pass string](/image/pass-string.PNG)

1. Copy Value 

   ![string pass by value](/image/string-pass-by-value.png)

   ![pass literals string](/image/pass-literals-string.png)

2. Read-Only

   ![pass string_view](/image/pass-string_view.png)

![general rule for passing parameters](/image/general-rule-for-passing-parameters.png)

### Function return

The `void` keyword, used in the previous examples, indicates that the function should not return a value. If you want the function to return a value, you can use a data type (such as `int`, `string`, etc.) instead of `void`, and use the `return` keyword inside the function.

#### return by value

In modern compilers, return by value is commonly optimized out by the compiler when possible and the function is modified behind your back to return by reference, avoiding unnecessary copies!

```c++
// program to add two numbers using a function
#include <iostream>

// declaring a function
int add(int a, int b)
{
    return (a + b);
}

int main() 
{
    int sum;
    // calling the function and storing
    // the returned value in sum
    sum = add(100, 78);
    std::cout << "100 + 78 = " << sum << std::endl;
    return 0;
}
```

![cpp-function-return-statement](/image/cpp-function-return-statement.webp)

#### return by refinance

In C++ Programming, not only can you pass values by reference to a [function](https://www.programiz.com/cpp-programming/function) but you can also return a value by reference. 

```c++
#include <iostream>
// global variable
int num;
// function declaration
int& test();

int main() 
{
  // assign 5 to num variable
  // equivalent to num = 5;
  test() = 5;
  cout << num;
  return 0;
}
// function definition
// returns the address of num variable
int& test() 
{
  return num;
}
```

#### return by pointer 

C++ allows you to return a pointer from a function. To do so, you would have to declare a function returning a pointer.

```c++
int * myFunction() 
{
   .
   .
   .
}
```

### constexpr Functions

- The `constexpr` specifier declares that it is possible to evaluate the value of a function or variable at compile time.

- Such variables and functions can then be used where only compile-time constant expressions are allowed.

- These functions are used to improve the performance of the program by doing computations at compile time instead of run time.

- These functions can really be helpful, where executing a program multiple times as the constant expressions will only be evaluated once during the compile time.

- The `constexpr` specifies that the value of a variable or function can appear in constant expressions.

-  the `constexpr` function it doesn’t have to be at compile time. 

  ![constexpr function](/image/constexpr-function.webp)

### constvel Functions

- `consteva` function, every call to the function must directly or indirectly produce a compile-time constant expression.
- The `consteval` function is the same as `constexpr` function except that if the call to a `consteval` function doesn’t evaluate to a compile-time constant expression, then the program gives an error while it is not so in the case of a `constexpr` function.
- Function can appear in constant expressions, it doesn’t say that the function has to be, while a `consteval` specifies that a function is an immediate function, that is, every call to the function must produce a compile-time constant.

![function compile-runtime](/image/function-compile-runtime.png)

### Arguments to main Function 

We can also give command-line arguments in C and C++. Command-line arguments are given after the name of the program in command-line shell of Operating Systems. To pass command line arguments, we typically define main() with two arguments : first argument is the number of command line arguments and second is list of command-line arguments. 

```c++
int main(int argc, char *argv[]) 
{ 
    /* ... */ 
}

/********* or *********/
int main(int argc, char **argv) 
{ 
    /* ... */ 
}
```

- `argc` (ARGument Count) is int and stores number of command-line arguments passed by the user including the name of the program. So if we pass a value to a program, value of argc would be 2 (one for argument and one for program name)
- The value of argc should be non negative.
- `argv` (ARGument Vector) is array of character pointers listing all the arguments.
- If argc is greater than zero,the array elements from argv[0] to argv[argc-1] will contain pointers to strings.
- Argv[0] is the name of the program , After that till argv[argc-1] every element is command -line arguments.

Example 

```c++
// Name of program mainreturn.cpp
#include <iostream>
using namespace std;
  
int main(int argc, char** argv)
{
    cout << "You have entered " << argc
         << " arguments:" << "\n";
  
    for (int i = 0; i < argc; ++i)
        cout << argv[i] << "\n";
  
    return 0;
}

/* input 
* $ g++ mainreturn.cpp -o main 
* $ ./main Abdelrahman Saad Eldesouky
*/

/* Output 
* You have entered 4 arguments:
* ./main
* Abdelrahman
* Saad
* Eldesouky
*/
```

Properties of Command Line Arguments:

1. They are passed to main() function.
2. They are parameters/arguments supplied to the program when it is invoked.
3. They are used to control program from outside instead of hard coding those values inside the code.
4. `argv[argc]` is a NULL pointer.
5. `argv[0]` holds the name of the program.
6. `argv[1]` points to the first command line argument and `argv[n]` points last argument.

### std::optional

`std:optional` - a new helper type added in C++17. It’s a wrapper for your type and a flag that indicates if the value is initialized or not. `std::optional` was added in C++17 and brings a lot of experience from `boost::optional` that was available for many years. Since C++17 you can just `#include <optional>` and use the type. 

```c++
//Declare and Initialization
std::optional<Data_Type> Variable_Name{Value} ;
```



Usually, you can use an optional wrapper in the following scenarios:

- If you want to represent a nullable type nicely.

  - Rather than using unique values (like -1, nullptr, NO_VALUE or something)
  - For example, a user’s middle name is optional. You could assume that an empty string would work here, but knowing if a user entered something or not might be important. With std::optional<std::string> you get more information.

- Return a result of some computation (processing) that fails to produce a value and is not an error.

  For example, finding an element in a dictionary: if there’s no element under a key it’s not an error, but we need to handle the situation.

- To perform lazy-loading of resources.

  For example, a resource type has no default constructor, and the construction is substantial. So you can define it as std::optional<Resource> (and you can pass it around the system), and then load only if needed later.

- To pass optional parameters into functions.

```c++
std::optional<std::string> UI::FindUserNick()
{
    if (nick_available)
    {
        return { mStrNickName };
    }
    return std::nullopt; // same as return { };
}

// use:
std::optional<std::string> UserNick = UI->FindUserNick();
if (UserNick)
{
    Show(*UserNick);
}
```

### Function Overloading

Function overloading is a feature of object oriented programming where two or more functions can have the same name but different parameters. When a function name is overloaded with different jobs it is called Function Overloading. In Function Overloading “Function” name should be the same and the arguments should be different.

Parameter Differences:

1. Order 
2. Number
3. Types

```c++

#include <iostream>
 
void print(int i) {
  std::cout << " Here is int " << i << std::endl;
}
void print(double  f) {
  std::cout << " Here is float " << f << std::endl;
}
void print(char const *c) {
  std::cout << " Here is char* " << c << std::endl;
}
 
int main() {
  print(10);
  print(10.10);
  print("ten");
  return 0;
}

/* Output
* Here is int 10 
* Here is float 10.1 
* Here is char* ten
*/
```

How  Function Overloading works?

- Exact match

   (Function name and Parameter)

- If a not exact match is found

  1. Char, Unsigned char, and short are promoted to an int.
  2. Float is promoted to double

- If no match found:

  C++ tries to find a match through the standard conversion.

- ELSE ERROR 

### Lambda Function

A mechanism to set up anonymous functions (without names). Once we have them set up, we can either give them names and call them , or we can even get them to do things directly.

```c++
// Declaring
[ capture clause ] (parameters) -> return-type  
{   
   definition of method   
};

// Assigning
auto Call_Name = [ capture clause ] (parameters) -> return-type  
{   
   definition of method   
};

// Calling
Call_Name(parameters) ; 

// Calling Directly After Definition
[ capture clause ] (parameters) -> return-type  
{   
   definition of method   
}();
```

#### Capture List 

A lambda can introduce new variables in its body (in **C++14**), and it can also access, or *capture*, variables from the surrounding scope. A lambda begins with the capture clause. It specifies which variables are captured, and whether the capture is by value or by reference. Variables that have the ampersand (`&`) prefix are accessed by reference and variables that don't have it are accessed by value. An empty capture clause, `[ ]`, indicates that the body of the lambda expression accesses no variables in the enclosing scope. You can use a capture-default mode to indicate how to capture any outside variables referenced in the lambda body: `[&]` means all variables that you refer to are captured by reference, and `[=]` means they're captured by value. You can use a default capture mode, and then specify the opposite mode explicitly for specific variables. For example, if a lambda body accesses the external variable `total` by reference and the external variable `factor` by value, then the following capture clauses are equivalent:

```c++
[&total, factor]
[factor, &total]
[&, factor]
[=, &total]
[variable] 	// capture by vallue 
[&variable]	// capture by reference 
[=]		   //  capture all by value 
[&]		   //  capture all by reference 
```

Only variables that are mentioned in the lambda body are captured when a capture-default is used. If a capture clause includes a capture-default `&`, then no identifier in a capture of that capture clause can have the form `&identifier`. Likewise, if the capture clause includes a capture-default `=`, then no capture of that capture clause can have the form `=identifier`. An identifier or **this** can't appear more than once in a capture clause. 

> Values captured by value can't be modified in the body of the lambda function by default. There are ways around this and we'll learn about them later. 

![lambda_function](/image/lambda_function.png)

### Static Variables in Function 

When a variable is declared as static, space for **it gets allocated for the lifetime of the program**. Even if the function is called multiple times, space for the static variable is allocated only once and the value of variable in the previous call gets carried through the next function call. 

**Global variable vs Static variable**

- Both global and static variables have static storage duration. They live throughout the entire lifetime of the program.
- Static variables are scoped to the function in which they are declared and used. If you try to access them outside that function, you’ll get a compiler error.
- Global variables are scoped to the global scope of the file where they are declared. They are accessible and usable through out the entire file.

### Inline Function 

When the program executes the function call instruction the CPU stores the memory address of the instruction following the function call, copies the arguments of the function on the stack and finally transfers control to the specified function. The CPU then executes the function code, stores the function return value in a predefined memory location/register and returns control to the calling function. This can become overhead if the execution time of function is less than the switching time from the caller function to called function (callee). For functions that are large and/or perform complex tasks, the overhead of the function call is usually insignificant compared to the amount of time the function takes to run. However, for small, commonly-used functions, the time needed to make the function call is often a lot more than the time needed to actually execute the function’s code. This overhead occurs for small functions because execution time of small function is less than the switching time.

C++ provides an inline functions to reduce the function call overhead. Inline function is a function that is expanded in line when it is called. When the inline function is called whole code of the inline function gets inserted or substituted at the point of inline function call. This substitution is performed by the C++ compiler at compile time. Inline function may increase efficiency if it is small.

```c++
inline returnType functionName (parameter1, parameter2,...) 
{
    // function body   
    
    return returnData
}
```

- Inline functions can increase the size of your application binary.
- It is recommended to use them for short, frequently used functions.
- The programmer (You), should weigh in the benefits against the downsides of inlining your functions.
- Usually only functions of a few lines of code and simple logic, like our max function should be inlined.
- Marking your function as inline is just a suggestion to the compiler. The compiler might agree and inline your function or just ignore you.

### Recursion Function 

A function that calls itself is known as a recursive function. And, this technique is known as recursion. The recursion continues until some condition is met. To prevent infinite recursion, `if...else statement` (or similar approach) can be used where one branch makes the recursive call and the other doesn't.

![cpp-function-recursion-working](/image/cpp-function-recursion-working.webp)

Example: Factorial of a Number Using Recursion

```c++
// Factorial of n = 1*2*3*...*n

#include <iostream>

int factorial(int);

int main() 
{
    int n, result;

    std::cout << "Enter a non-negative number: ";
    std::cin >> n;

    result = factorial(n);
    std::cout << "Factorial of " << n << " = " << result;
    return 0;
}

int factorial(int n) 
{
    if (n > 1) 
    {
        return n * factorial(n - 1);
    } 
    else 
    {
        return 1;
    }
}
```

![cpp-function-recursion-example](/image/cpp-function-recursion-example.webp)

**Advantages of Recursion:**

1. It makes our code shorter and cleaner.
2. Recursion is required in problems concerning data structures and advanced algorithms, such as Graph and Tree Traversal.

**Disadvantages of Recursion:**

1. It takes a lot of stack space compared to an iterative program.
2. It uses more processor time.
3. It can be more difficult to debug compared to an equivalent iterative program.

### Function Templates

Templates are powerful features of C++ which allows us to write generic programs. We can create a single function to work with different data types by using a template, Instead of function overload.

```c++
// Definition by value
template <typename T>
T Function_Name(T parameter1, T parameter2, ...) 
{
    // code
}

// Definition by reference 
template <typename T>
T& Function_Name(T& parameter1, T& parameter2, ...) 
{
    // code
}

// Definition by pointer  
template <typename T>
T* Function_Name(T* parameter1, T* parameter2, ...) 
{
    // code
}

// Calling with deduction
Function_Name(parameter1, parameter2,...);

// Calling with explicitly
Function_Name<dataType>(parameter1, parameter2,...);

```

- Function templates are just blueprints. They’re not real C++ code consumed by the compiler. The compiler generates real C++ code by looking at the arguments you call your function template with.

- The real C++ function generated by the compiler is called a template instance.

- A template instance will be reused when a similar function call (argument types) is issued. No duplicates are generated by the compiler.

- Real function declarations and definitions, aka template instances are created when you call the function with arguments. 

- If the template parameters are of the same type (T,T), then the arguments you call the function with must also match, otherwise you get a compiler error.

- The arguments passed to a function template must support the operations that are done in the body of the function.

- [cppinsights.io](cppinsights.io) that can show you template instantiations. You can even use the debugger to infer that information from the activation record of a template function

  ![function_tempelet](/image/function_tempelet.png)

- For the template arguments must be of the same type.

> Template instances won’t always do what you want. A good example is when you call our maximum function with pointers. DISASTER!

#### Template Specialization

Function Templates aren't real C++ code, they're blueprints the compiler uses to generate actual C++ code in template instances. Template specializations however are real C++ code. If multiple function template specialization definitions show up in multiple files, you'll get redefinition errors.

```c++
// Definition with template specialization 
template <> 
return_Type Function_Name<Data_Type> (Data_Type parameter1, Data_Type parameter2, ...) 
{
    // code
}
```

#### Template Overloading 

![Template_Overloading](/image/Template_Overloading.png)

C++ treats specialization and overloads very differently. This is best explained with an example. 

```c++
template <typename T> void foo(T);
template <typename T> void foo(T*); // overload of foo(T)
template <>           void foo<int>(int*); // specialisation of foo(T*)

foo(new int); // calls foo<int>(int*);
```

The compiler does overload resolution before it even looks at specializations. So, in both cases, overload resolution chooses `foo(T*)`. However, only in the first case does it find `foo<int*>(int*)` because in the second case the `int*` specialization is a specialization of `foo(T)`, not `foo(T*)`. 

> overload when you can, specialize when you need to. 

#### Template with Multiple Parameters 

 ```c++
template <typename return_Type, typename T, typename P> 
return_Type Function_Name (T parameter1, P parameter2, ...) 
{
    // code
}
 ```

![multiple_template](/image/multiple_template.png)

> We can use `auto` to deduced the `return` type, and the function definition must be before the `main` function.

#### Decltype with auto 

The `decltype` type specifier yields the type of a specified expression. The `decltype` type specifier, together with the `auto` keyword, is useful primarily to developers who write template libraries. Use `auto` and `decltype` to declare a template function whose return type depends on the types of its template arguments. Or, use `auto` and `decltype` to declare a template function that wraps a call to another function, and then returns the return type of the wrapped function. 

```c++
decltype( expression ) // its return the type of the expression parameter 
```

In C++14, you can use `decltype(auto)` with no trailing return type to declare a template function whose return type depends on the types of its template arguments.

In C++11, you can use the `decltype` type specifier on a trailing return type, together with the `auto` keyword, to declare a template function whose return type depends on the types of its template arguments. For example, consider the following code example in which the return type of the template function depends on the types of the template arguments. In the code example, the *UNKNOWN* placeholder indicates that the return type cannot be specified.

The introduction of the `decltype` type specifier enables a developer to obtain the type of the expression that the template function returns. Use the *alternative function declaration syntax* that is shown later, the `auto` keyword, and the `decltype` type specifier to declare a *late-specified* return type. The late-specified return type is determined when the declaration is compiled, instead of when it is coded. 

```c++
// C++11
template<typename T, typename P>
auto Function_Name (T a, P b) -> decltype(expression)
{
   // code
}

// C++14
template<typename T, typename P>
decltype(auto) Function_Name (T a, P b) 
{
   // code
}
```

![auto_decltype](/image/auto_decltype.png)

#### Non Type Template Parameter 

A template non-type parameter is a template parameter where the type of the parameter is predefined and is substituted for a constexpr value passed in as an argument. 

```c++
template<Data_Type T, typename P>
Return_Type Function_Name (T a) 
{
   // code
}
```

A non-type parameter can be any of the following types:

- An integral type
- An enumeration type
- A pointer or reference to a class object
- A pointer or reference to a function
- A pointer or reference to a class member function
- std::nullptr_t
- A floating point type (since C++20)

> In c++17 and below, only `int` like types could be used as non type template parameter.

#### auto Function Template

 ```c++
auto Function_Name (auto parameter1, auto parameter2, ..)
{
    // code 
    // its return the largest type 
}
 ```

#### Template Parameter for Lambda 

```c++
auto Function_Name = [] <typename T> (T parameter1, T parameter2, ..)
{
    // code 
    // pervent passing different parameter 
}
```

#### C++20 Standard Concepts

The concepts library provides definitions of fundamental library concepts that can be used to perform compile-time validation of template arguments and perform function dispatch based on properties of types. These concepts provide a foundation for equational reasoning in programs.

Most concepts in the standard library impose both syntactic and semantic requirements. It is said that a standard concept is *satisfied* if its syntactic requirements are met, and is *modeled* if it is satisfied and its semantic requirements (if any) are also met.

![C++20_Concepts](/image/C++20_Concepts.png)

```c++
// Syntax 1
template <typename T>
requires std::C++_Concept <T>
T Function_Name (T a, T b)
{
    // code
}

// Syntax 1 by using a type trait 
template <typename T>
requires std::Type_Trait <T> 
T Function_Name (T a, T b)
{
    // code
}

// Syntax 2
template <std::C++_Concept T>
T Function_Name (T a, T b)
{
    // code
}

// Syntax 3
auto Function_Name (std::C++_Concept auto a, std::C++_Concept auto b)
{
    // code
}

template <typename T>
T Function_Name (T a, T b) requires std::C++_Concept <T>
{
    // code
}
```

#### C++20 Custom Concepts 

We can build our concepts for custom usage. It can use like the **C++20 Standard Concepts**.

The requires clause can take in four kinds of requirements :

1. Simple Requirements

   ```c++
   // Simple requirements
   template <typename T> 
   concept Concept_Name = requires (T a, ..)
   {
        expression // check for valid condition 
    };
   ```

2. Nested Requirements

   ```c++
   // Nested Requirements
   template <typename T> 
   concept Concept_Name = requires (T a, ..)
   {
       expression // check for valid condition 
       requires expression // check if the expression is true
    };
   ```

3. Compound Requirements

   ```c++
   // Compound Requirements
   template <typename T> 
   concept Concept_Name = requires (T a, ..)
   {
       // check for valid condition and the result is valid for second condition 
       expression -> std::C++_Concept 
    };
   ```

   We can use `||` and `&&` to compound the concept 

   ```c++
   // Example 
   #include <iostream>
   #include <concepts>
   
   template <typename T>
   concept TinyType = requires ( T t)
   {
   	sizeof(T) <=4; // Simple requirement
   	requires sizeof(T) <= 4; // Nested requirement
   };
   
   template <typename T>
   //requires std::integral<T> || std::floating_point<T> -> OR operator
   //requires std::integral<T> && TinyType<T>			 -> AND operator
   requires std::integral<T> && requires ( T t)
   {
   	sizeof(T) <=4; // Simple requirement
   	requires sizeof(T) <= 4; // Nested requirement
   }
   T add(T a, T b)
   {
       return a + b;
   }
   
   int main()
   {
       long long int x{7};
       long long int y{5};
   
       add(x,y);
       return 0;
   }
   ```

4. Type Requirements

   This's out of scope for now. 

> We can use Concepts with `auto` keyword.
>
> ```c++
> std::integral auto add (std::integral auto a,std::integral auto b)
> {
> 	return a + b;
> } 
> // or 
> std::floating_point auto x = add(5,8);
> ```

 ## Classes 

A class is a blueprint for the object. It's used to create new data types like a person, this person has some information like name (string), age (int), Wight (double), and address (string). Therefore we use classes in C++ to create objects from persons. 

### Class Creation

```c++
class className 
{
    // class variables 
    // class functions 
};
```

Example 

```c++
class Cylinder 
{
  public: 
    double raduis{1.5}; 
    double hight{2.75}; 
    
    double volume ()
    {
        return PI * raduis * hight ; 
    }
};
```

> - The variables declared inside the class are known as **data members**.
> - The functions are known as **member functions** of a class.

> - `public` keyword used to make the class member accessible outside the class scope.
> - Class member are private by default, they can't be access unless we use the `public` keyword.  

> - **data members** in most cases, we'll keep them private from the outside because users of our class don't really care about the member variables. They just want to do things with your class. So we usually flag our member variables as private, and we can do that using the `private` keyword.

> - Class member variables can either be raw stack variables or pointers.
> - Members can’t be references.
> - Class methods have access to the member variables, regardless of whether they are `public` or `private`.

### Objects 

When a class is created, only the specification for the object is created; no memory or storage is allocated. So to use the data and access functions defined in the class, we need to create objects. Also we can use pointer to object, and create heap object through `new` operator. 

```c++
className objectName ; 
className * p_class = &objectName;
className * p_class = new objectName;
```

If we need to access the class member we use the `.` operator, if we use a pointer class we use ``->`` operator 

```c++ 
objectName.classMember ;
objectName->classMember ;
```

### Constructors 

A constructor is a special type of member function that is called automatically when an object is created. In C++, a constructor has the same name as that of the class and it does not have a return type. A constructor is primarily used to initialize objects. They are also used to run a default code when an object is created.

```c++
class  className 
{
  public:
    // create a constructor
    className() 
    {
      // code
    }
};
```

> - Same name as the class.
> - No return type.
> - Can have parameters. Can also have an empty parameter list.
> - Usually used to initialize member variables of a class.

> If we have not defined a constructor in our class, then the C++ compiler will automatically create a **default constructor** with an empty code and no parameters.

#### Constructors Types

1. A constructor with no parameters is known as a **default constructor**.

   ```c++
   // C++ program to demonstrate the use of default constructor
   #include <iostream>
   
   // declare a class
   class  Wall 
   {
     private:
       double length;
     public:
       // default constructor to initialize variable
       Wall()
       {
         length = 5.5;
         std::cout << "Creating a wall." << std::endl;
         std::cout << "Length = " << length << std::endl;
       }
   };
   
   int main() 
   {
     Wall wall1;
     return 0;
   }
   ```

   If we need to initialize an empty constructor we can use the following: 

   ```c++
   class  Wall 
   {
     private:
       double length;
     public:
       // default constructor to initialize variable
       Wall() = default ; 
   };
   ```

2. A constructor with parameters is known as a **parameterized constructor**. This is the preferred method to initialize member data.

   ```c++
   // C++ program to calculate the area of a wall
   #include <iostream>
   
   // declare a class
   class Wall 
   {
     private:
       double length;
       double height;
     public:
       // parameterized constructor to initialize variables
       Wall(double len, double hgt) 
       {
         length = len;
         height = hgt;
       }
   
       double calculateArea() 
       {
         return length * height;
       }
   };
   
   int main() 
   {
     // create object and initialize data members
     Wall wall1(10.5, 8.6);
     Wall wall2(8.5, 6.3);
   
     std::cout << "Area of Wall 1: " << wall1.calculateArea() << std::endl;
     std::cout << "Area of Wall 2: " << wall2.calculateArea();
   
     return 0;
   }
   ```

3. The **copy constructor** in C++ is used to copy data of one object to another.

   ```c++
   #include <iostream>
   
   // declare a class
   class Wall 
   {
     private:
       double length;
       double height;
     public:
       // initialize variables with parameterized constructor
       Wall(double len, double hgt)
       {
         length = len;
         height = hgt;
       }
       // copy constructor with a Wall object as parameter
       // copies data of the obj parameter
       Wall(Wall &obj) 
       {
         length = obj.length;
         height = obj.height;
       }
   
       double calculateArea() 
       {
         return length * height;
       }
   };
   
   int main() 
   {
     // create an object of Wall class
     Wall wall1(10.5, 8.6);
   
     // copy contents of wall1 to wall2
     Wall wall2 = wall1;
   
     // print areas of wall1 and wall2
     std::cout << "Area of Wall 1: " << wall1.calculateArea() << std::endl;
     std::cout << "Area of Wall 2: " << wall2.calculateArea();
   
     return 0;
   }
   ```
   
   > - If you're trying to set up a copy constructor that passes parameter by value, this is going to cause a chain of endless copy constructor calls because the copy constructor is going to want to call a copy constructor to set up a copy. This is going to be a bad C++ design and cause a compiler error because of the potential for an endless chain of copy constructor calls.
   >
   >   ![copy-constructor-attemp1](/image/copy-constructor-attemp1.png)
   >
   > - To fix this we pass the object by reference, but if there's any pointer to the member variable we blindly copied the memory address and the edge pointer and pasted that into our copied object. So this's will lead us to a problem. If we change the edge from the original class, the changes will be seen in copied class and this is not what we want.
   >
   >   ![copy-constructor-attemp2](/image/copy-constructor-attemp2.png)
   >
   > - To fix this we need to avoid blindly copying the pointer for the member variable. We need to set up a new memory location and use that to store the information in our copy object.
   >
   >   ![copy-constructor-attemp3](/image/copy-constructor-attemp3.png)
   >
   > - Finally, we can reuse the parameterized constructor of the class to copy our data and avoid setting up a copy constructor that is doing all the heavy job.
   >
   >   ![copy-constructor-delegation](/image/copy-constructor-delegation.png)

#### Default Parameters for constructors

 We can use default values to set our variables same as function. 

```c++
// Declaration 
class  className 
{
  public:
    className() = default ; 
    className(parm1, parm2 = preSet_value)
    {
        // code
    } 
};

// calling 
className objectName(parm1) ; 
// or 
className objectName(parm1, parm2) ; 
```

> - If we set all parameters with default value the compiler will be confused as to which constructor to call.
>
> - If we split our constructor into declaration and definition, the declaration is in the header file and the definition is in the implementation file. We don't have to specify the default parameter again in the implementation. If you do that, you will get a computer error because this is not valid C++ syntax.
>
> - We can't set the first parameter only with default value this will generate a compiler error. 
>
>   ```c++
>   class  className 
>   {
>     public:
>       className() = default ; 
>       className(parm1 = preSet_value, parm2)
>       {
>           // code
>       } 
>   };
>   ```

#### Initializer List for Constructor

 Initializer list is another way to assign the parameter with the member variables in a class. 

```c++
class Cylinder 
{
  public: 
    Cylinder() = default ; 
    // Declare initializer list for constructor
    Cylinder (double raduis_parm, double hight_parm) : raduis(raduis_parm), hight(hight_parm)
    {
        
    }
    /* Also we can declare it like that 
    Cylinder (double raduis_parm, double hight_parm) 
    		: raduis(raduis_parm), 
    		hight(hight_parm)
    {
        
    }
    */
    double volume ()
    {
        return PI * raduis * hight ; 
    }
  private: 
    double raduis{1.5}; 
    double hight{2.75}; 
};
```

![initilizer-list-vs-member-wise-copy](/image/initilizer-list-vs-member-wise-copy.png)

#### Explicit Constructor 

`Explicit` Keyword in C++ is used to mark constructors to not implicitly convert types in C++. It is optional for constructors that take exactly one argument and work on constructors(with a single argument) since those are the only constructors that can be used in typecasting.

Example 

```c++
// constructor without 'explicit'
#include <iostream>

class Square 
{
    public:
        Square (double side_parm) : side(side_parm)
        {
        }
    	double surface ()
        {
            return side * side ; 
        }
    private:
        double side;
};

bool compare (Square S1, Square S2)
{
    return ((S1.surface() > S2.surface())? true : false) ; 
}

int main()
{
	Square S1(3);
    Square S2(1);
    std::cout << std::boolalpha << compare(S1, S2) ; // Output: true
    std::cout << std::boolalpha << compare(S1, 5.0) ; // Output: false
	return 0;
}
```

If a class has a constructor which can be called with a single argument, then this constructor becomes a conversion constructor because such a constructor allows conversion of the single argument to the class being constructed. In this case, when `com1 == 3.0` is called, `3.0` is implicitly converted to Complex type because the default constructor can be called with only one argument because both parameters are default arguments and we can choose not to provide them.
We can avoid such implicit conversions as these may lead to unexpected results. We can make the constructor explicit with the help of an `explicit` keyword.

Example 

```c++
// constructor with 'explicit'
#include <iostream>

class Square 
{
    public:
        explicit Square (double side_parm) : side(side_parm)
        {
        }
    	double surface ()
        {
            return side * side ; 
        }
    private:
        double side;
};

bool compare (Square S1, Square S2)
{
    return ((S1.surface() > S2.surface())? true : false) ; 
}

int main()
{
	Square S1(3);
    Square S2(1);
    std::cout << std::boolalpha << compare(S1, S2) ; // Output: true
    std::cout << std::boolalpha << compare(S1, 5.0) ; // Compiler Error: could not convert '5.0e+0' from 'double' to 'Square'
}
```

We receive an error here because to avoid any unexpected errors we have made our constructor an explicit constructor and `3.0` won’t be converted to Complex by our constructor on its own.

#### Constructor Delegation

Many classes have multiple constructors that do similar things. 

Example 

```c++
class Delegation 
{
    public:
        Delegation() = default ;
        Delegation(int my_max) 
        {
            max = my_max > 0 ? my_max : 10;
        }
        Delegation(int my_max, int my_min) 
        {
            max = my_max > 0 ? my_max : 10;
            min = my_min > 0 && my_min < max ? my_min : 1;
        }
        Delegation(int my_max, int my_min, int my_middle) 
        {
            max = my_max > 0 ? my_max : 10;
            min = my_min > 0 && my_min < max ? my_min : 1;
            middle = my_middle < max && my_middle > min ? my_middle : 5;
        }
    private: 
    	int max;
    	int min;
    	int middle;
    	int end; 
};
```

We could reduce the repetitive code by adding a function that does all of the validation, but the code for class would be easier to understand and maintain if one constructor could delegate some of the work to another one. To add delegating constructors, use the following syntax by using the constructor as initializer list: 

```c++
constructor (. . .) : constructor (. . .)
```

```c++
class Delegation 
{
    public:
        int max;
        int min;
        int middle;

        Delegation(int my_max) 
        {
            max = my_max > 0 ? my_max : 10;
        }
        Delegation(int my_max, int my_min) : Delegation(my_max) 
        {
            min = my_min > 0 && my_min < max ? my_min : 1;
        }
        Delegation(int my_max, int my_min, int my_middle) : Delegation (my_max, my_min)
        {
            middle = my_middle < max && my_middle > min ? my_middle : 5;
        }
    private: 
    	int max;
    	int min;
    	int middle;
    	int end; 
};
int main() 
{
    Delegation c1{ 1, 3, 2 };
}
```

Event sequence: 

1. The constructor `Delegation(int, int, int)` is called.
2. Then first calls the constructor `Delegation(int, int)`.
3. Then in turn calls `Delegation(int)`. 
4. Body of the `Delegation(int)` will be executed first. 
5. Then the Body of the `Delegation(int, int)`. 
6. Then the Body of the `Delegation(int, int, int)`. 
7. Finally it returns to the main function to complete the code sequence.

> No further initializations before/after delegation call.
>
> ```c++
> class Delegation 
> {
>     public:
>         int max;
>         int min;
>         int middle;
> 
>         Delegation(int my_max) 
>         {
>             max = my_max > 0 ? my_max : 10;
>         }
>         Delegation::Delegation(int my_max, int my_min) : end(max), Delegation(my_max) // compiler error
>         {
>             min = my_min > 0 && my_min < max ? my_min : 1;
>         }
>         Delegation::Delegation(int my_max, int my_min, int my_middle) : Delegation (my_max, my_min), end(min) // compiler error
>         {
>             middle = my_middle < max && my_middle > min ? my_middle : 5;
>         }
>     private: 
>     	int max;
>     	int min;
>     	int middle;
>     	int end; 
> };
> int main() 
> {
>     Delegation c1{ 1, 3, 2 };
> }
> ```

#### Deleted Constructors 

Deleted constructor's is a feature we have in C++ to disassemble some code structures and prevent them from being used to build objects. Any time somebody tries to use a syntax that is going to call this constructor, they are going to get a compiler error saying that they can't use this constructor because it was deleted.

```c++
class className 
{
  public: 
    className() = delete; 
    className(parm1, parm2); 
    returnType functionMember(); 
  private: 
    // code
};
```

#### Move Constructors

 

#### Initializer list constructors



### Class Across Multiple files

We can divide our class into multiple files as source and header files as shown: 

```cpp
// class header file

class className 
{
  public: 
    className() = default; 
    className(parm1, parm2); 
    returnType functionMember(); 
  private: 
    // code
};
```

```c++
// class source file 

#include "className.h"

className::className(parm1, parm2)
{
    // code
}

returnType className::functionMember()
{
    // code
}
```

> `::` called scope resolution operator. 

### Destructors 

Special methods that are called when an object dies. They are needed when the object needs to release some dynamic memory, or for some other kind of clean up.

![destructors](/image/destructors.png)

![destructorsCall](/image/destructorsCall.png) 

> It's not possible to pass parameters to your destructor, if you do that, you're going to get a computer error, distractors where always have no parameters in C++.

### The `this` Pointer 

Each class member function contains a hidden pointer called `this`. That pointer contains the address of the current object, for which the method is being executed. This also applies to constructors and destructors. It can be used for different usage as shown: 

1. **Printing out object addresses**

   We use that this keyword to get the address of the current object for which a specific method or function is being called.

   ```c++
   className::className(parm1, parm2)
   {
       // code
       std::cout << "constructor address is:" << this << std::endl; 
   }
   ```

2. **Conflicting names**

   It may be used to resolve conflicts when you have a parameter and a member variable that are named the same way.

   ```c++
   className::className(parm)
   {
       // code
       this->parm = parm ; // this->parm is the class member variable and parm is passing parm
   }
   ```

3. **Chained calls using pointers**

   If we want to set up a change by using pointers.

   ![Chained-calls-using-pointers-1](/image/Chained-calls-using-pointers-1.png)

   ![Chained-calls-using-pointers-2](/image/Chained-calls-using-pointers-2.png)

4. **Chained calls using reference**

   We can do the same thing using references as pointers with little difference.

   ![Chained-calls-using-referance-1](/image/Chained-calls-using-referance-1.png)

   ![Chained-calls-using-referance-2](/image/Chained-calls-using-referance-2.png)

### Class vs Struct 

|          |       Class        |      Struct       |
| :------: | :----------------: | :---------------: |
|  Member  | Private by default | Public by default |
| Override |  Change to public  | Change to private |

### Class Size 

*The size of the object is going to be the sum of the sizes of its member variables. The functions are not going to be counted then the functions are just helper functions that live somewhere in memory, but they're not going to be accounted for in the size of our object. And as a result, we might think functions are not accounted for in the size of the object. Functions are not affiliated with class objects. It's going to be the blueprint from which we're going to generate thousands of objects if we want. But the functions or the methods are going to be associated with the blueprint itself. So it really wouldn't make sense to associate the size of those functions in memory with class objects.*

### Getter and Setter Function 

We can use two types of functions to access the class member for reading or editing: 

1. **Setter** 

   ```c++
   returnType className::set_variableName(dataType variableName)
   {
       this->variableName = variableName ;
   }
   ```

2. **Getter** 

   ```c++
   returnType className::get_variableName()
   {
       return variableName ;
   }
   ```

We can use the same function to do the both functionality by using reference: 

```c++
returnType& functionMember()
{
    return variableName;
}

// for read 
objectName.functionMember() ; 

// for edit 
objectName.functionMember() = variableData ; 
```

### The `const` Object 

We can’t modify `const` objects. That’s fine and it’s what we want. But we can’t read from them either, which makes them kind of useless.

```c++
const className objectName ; 
```

When we need to pass an `const` object to function we have 5 cases: 

1. **Passing by value**

   It'll work as expected because it's a copy of the original object. 

   ```c++
   const className objectName ; 
   returnType functionMember(objectName parm) ; 
   ```

2. **Passing by non `const` reference**

   It'll generate a compiler error because it can modify the object member and the compiler doesn't allow passing `const` object as function arguments.

    ```c++
    const className objectName ; 
    returnType functionMember(objectName& parm) ; 
    ```

3. **Passing by `const` reference**

   It'll generate a compiler error because it can modify the object member unless it'll be useless. 

    ```c++
   const className objectName ; 
   returnType functionMember(const objectName& parm) ; 
    ```

4. **Passing by non `const` pointer**

   It'll generate a compiler error because it can modify the object member and the compiler doesn't allow passing `const` object as function arguments.

    ```c++
   const className objectName ; 
   returnType functionMember(objectName* parm) ; 
    ```

5. **Passing by `const` pointer**

   It'll generate a compiler error because it can modify the object member unless it'll be useless. 

    ```c++
   const className objectName ; 
   returnType functionMember(const objectName* parm) ; 
    ```

We can't read from any class member of an `const` class unless we mark our member function with `const` keyword to read from an object. It'll not generate any error for reading any object member flagged with `const`.

```cpp
// class header file

class className 
{
  public: 
    className() = default; 
    className(parm1, parm2); 
    returnType functionMember() const ; 
  private: 
    // code
};
```

```c++
// class source file 

#include "className.h"

className::className(parm1, parm2)
{
    // code
}

returnType className::functionMember() const 
{
    // code
}
```

The Entire concept of protecting the constant source of `cost` object is named **`const` correctness**, and it is summarized in this few points here:

- For `const` objects you can only call `const` member functions.
- `const` objects are completely non modifiable( immutable), the compiler won't allow calling a member function that modifies the `const` object in any way.
- We are not allowed to modify the object in any way inside `const` member functions.
- We're not allowed to call a method that modifies the object indirectly either.
- Any attempt to modify an object’s member variable (direct or indirect) from within a `const` member functions will result in a compiler error. 
- You can't call any non `const` member functions from within a `const` member function.

### The `mutable` Keyword

Sometimes there is requirement to modify one or more data members of class through `const` function even though you don’t want the function to update other members of class. This task can be easily performed by using `mutable` keyword.  

```c++
class className 
{
  public: 
    className() = default; 
    className(parm1, parm2); 
    returnType functionMember() const ; 
  private: 
    // code
    mutable dataType memberVariable ; 
};
```

### Friends

The friends are external functions or classes with access to private members of a class. 

```c++
class className 
{
  public: 
    className() = default; 
    // declare external function as friends function 
    friend returnType externalFunction() ; 
    // declare external class as friends class
    friend class externalClass ; 
    
  private: 
    // code
};
```

> - The friend function is first declared and alive somewhere.
> - The implementation can live in any translation unit. Just be sure that it will be found at link stage.
> - The declaration has to show up before you call the function.
> - The class determines who is its friend ( through friend declaration).
> - The friend declaration can appear in public or private section of the class, either works the same.
> - We can have multiple friend functions in the same class.
> - Friend functions can be overloaded.
> - We have to use the `objectName.memberVariable_name` syntax in the friend function.
> - Friend functions are not member functions.
> - Friend functions don’t have access to the this pointer.

### Arrays  of Classes 

The Array of Objects stores objects. An array of a class type is also known as an array of objects, array elements are copies.

```c++
className arrayName[number_of_objects] = {objectName1, objectName2, ...}; 
```

> - Range-based loops regenerate copies.
>
>   ```c++
>   for(className objectName : arrayName)
>   {
>       // code
>   }
>   ```
>
> - Use reference to avoid this copies.
>
>   ```c++
>   for(className & objectName : arrayName)
>   {
>       // code
>   }
>   ```
>
> - Regular loops don’t make copies.
>
>   ```c++
>   for(size_t i{}; i < std::size(arrayName); ++i)
>   {
>       // code
>   }
>   ```
>
> - `built-in place` doesn't generate copies, because most modern compilers will realize that the last point we use to initialize our shape array is `built-in place`. If we did regular copies, we would throw away the `built-in-place point`, after we finish initializing the array. Modern compilers are smart to realize that and will insert a bunch of optimizations to make it so that what ends up in the array is the original `built-in-place` one. No need to copy it. 
>
>   ```c++
>   className arrayName[number_of_objects] = {objectName1, objectName2, className(parm)}; 
>   ```

### Shallow vs Deep Copy

- Shallow copy: Member wise copy of member variables, even for pointers.
- Deep Copy: When pointer member variables are involved, allocating new memory and copying in data from the source pointer. 

![Shallow-copy](/image/Shallow-copy.png)![deep-copy](/image/deep-copy.png)

### Static Members

 Regular member variables are associated with objects, they belong to class objects. What if we need member variables that are not tied to any object, but the class blueprint itself. 

#### Static Member Variables 

Static member variables are not tied to any object of the class. They live in the context of object blueprints. They are created even before a single class object has been created.

We can define class members static using `static` keyword. When we declare a member of a class as static it means no matter how many objects of the class are created, there is only one copy of the static member. A static member is shared by all objects of the class. All static data is initialized to zero when the first object is created, if no other initialization is present. We can't put it in the class definition but it can be initialized outside the class as done in the following example by redeclaring the static variable, using the scope resolution operator `::` to identify which class it belongs to.

```c++
// class header file

class className 
{
  public: 
    // static variable decleration
    static dataType variableName ; 
    
    className() = default; 
    className(parm1, parm2); 
    returnType functionMember(); 
  private: 
    // code
};
```

```c++
// class source file 

#include "className.h"

// static variable initialization  
dataType className::variableName {} ; 

className::className(parm1, parm2)
{
    // code
}

returnType className::functionMember()
{
    // code
}
```

> - Non integral static member variables, be it `const` or `non const` can't be in-class initialized. That's forbidden by the C++ standard.
> -  If the floating point static member variable is marked `const`, it can be in-class initialized.
> - We can't in-class initialize static `char *` member variables.
> - We can't declare a `non const` static member variable and in-class initialize it.
> - Sometimes we get things to be in-class initializable by making them `constexpr`.
> - Static initialization order is not guaranteed. If have static variables that depend on other static variables, we may get crashes for our app if the initialization order doesn’t work in your favor.

> If we mark the member variable as in line, we are telling the compiler to allow the initialization of the static member variable in the class definition.
>
> ```c++
> // class definition
> 
> class className 
> {
>   public: 
>     // inline static variable decleration
>     inline static dataType variableName {}; 
>     
>     className() = default; 
>     className(parm1, parm2); 
>     returnType functionMember(); 
>   private: 
>     // code
> };
> ```

Before C++ 17, we couldn't really do much in terms of initializing our member variables in the class declaration if they are static, only integral types `int` and `enum` are initializable from the class declaration, and others have to be initialized in some CPP file and be initialized from there.

![static-member1](/image/static-member1.png)

![static-member2](/image/static-member2.png)

> We have to go through an initializer list if our member variable happens to be a constant, if we don't go through an initializer list and try to do something like this in the body of the constructor, we'll get a compiler error.

#### Static Member Functions 

A static member function can be called even if no objects of the class exist and the **static** functions are accessed using only the class name and the scope resolution operator `::`. A static member function can only access static data member, other static member functions and any other functions from outside the class. Static member functions have a class scope and they do not have access to the `this` pointer of the class. We could use a static member function to determine whether some objects of the class have been created or not.

```c++
className::functionName (parm1, parm2);  
```

> - We can't use `const` keyword with `static` keyword.
> - Static member functions are allowed to access only the static data members or other static member functions, they can not access the non-static data members or member functions of the class. `const` member functions pledge to never modify the members of a class, but static member functions don't have access to object member variables, so marking them `const` doesn't make any sense. The compiler forbids that and if we do that you'll get a compiler error.
> - Static member functions have no business accessing member variables. They then have no business accessing the `this` pointer, whose purpose is to allow us to manipulate members of the current object. The compiler forbids that and if we try to use the this pointer in a static method, you'll get a hard compiler error.

### Nested Class

A nested class is a class which is declared in another enclosing class. A nested class is a member and as such has the same access rights as any other member. The members of an enclosing class have no special access to members of a nested class; the usual access rules shall be obeyed.

```c++
#include<iostream>

/* start of Enclosing class declaration */
class Enclosing 
{	
    private:
        int x;

        /* start of Nested class declaration */
        class Nested 
        {
            int y;
            void NestedFun(Enclosing *e) 
            {
                cout<<e->x; // works fine: nested class can access
                            // private members of Enclosing class
            }	
        }; // declaration Nested class ends here
}; // declaration Enclosing class ends here

int main()
{	

}
```

> - When Inner is private, its objects can’t be created from the outside, like in `main()`.
> - Outer doesn’t have access to private section of Inner.
> - Inner has access to private section of Outer.
> - Inner can directly access static members of Outer, but can’t access member variables without going through an object.

## Namespaces

A facility in the C++ programming language to avoid name conflicts: 

- Namespace provide the space where we can define or declare identifier i.e. variable,  method, classes.
- Using namespace, you can define the space or context in which identifiers are defined i.e. variable, method, classes. In essence, a namespace defines a scope.

> **Advantage of Namespace to avoid name collision:**
>
> - Example, you might be writing some code that has a function called `xyz()` and there is another library available which is also having same function `xyz()`. Now the compiler has no way of knowing which version of `xyz()` function you are referring to within your code.
> - A namespace is designed to overcome this difficulty and is used as additional information to differentiate similar functions, classes, variables etc. with the same name available in different libraries. 
> - The best example of namespace scope is the C++ standard library (`std`) where all the classes, methods and templates are declared. Hence while writing a C++ program we usually include the directive using namespace `std`. 

### Declaration

```c++
namespace  namespaceName 
{
    // code declarations i.e. variable  (int a;)
    returnType functionName();
    classes ( class className{};)
}
```

To call the namespace-enabled version of either function or variable, prepend the namespace name as follows:

```c++
namespaceName::code ;  // code could be variable , function or class.
```

> We can use a **Default Global Namespace** by flag it with `::` resolution operator. 
>
> ```c++
> // Global Scope
> returnType functionName();
> // Namespace Scope
> namespace  namespaceName 
> {
>     // code declarations i.e. variable  (int a;)
>     returnType functionName();
>     classes ( class className{};)
> }
> 
> int main()
> {
>     namespaceName::functionName() ; // namespace scope
>     ::functionName() ; // global scope
> }
> ```

### Nested Namespaces

Namespaces can be nested where you can define one namespace inside another name space as follows:

```c++
namespace namespaceName 
{
    // code declarations
    namespace namespaceNameNested 
    {
        // code declarations
    }
}
```

We can access members of nested namespace by using `::` operator as follows:

```c++
// to access members of namespaceNameNested
using namespace namespaceName::namespaceNameNested;
// to access members of namespaceName
using namespace namespaceName;
```

### Namespaces Across Multiple Files

We can split our `namespace` across multiple files as follows: 

```c++
// namespace header file

namespace namespaceName
{
    class className 
    {
      public: 
        className() = default; 
        className(parm1, parm2); 
        returnType functionMember(); 
      private: 
        // code
    };
}
```

```c++
// namespace source file
#include "className.h"

namespace namespaceName
{
    className::className(parm1, parm2)
    {
        // code
    }

    returnType className::functionMember()
    {
        // code
    }
}
```

### `using` Namespaces 

We can also avoid prepending of namespaces with the `using` namespace directive. This directive tells the compiler that the subsequent code is making use of names in the specified namespace. Names introduced in a using directive obey normal scope rules. The name is visible from the point of the using directive to the end of the scope in which the directive is found. Entities with the same name defined in an outer scope are hidden.

```c++
using namespace namespaceName ; 

// or 
using namespace namespaceName::memberName ; 

// using Namespace alias
namespace anotherName = namespaceName ; 
```

### Anonymous Namespaces 

- When the compiler sees an anonymous namespace declaration it will generate an internal name for the namespace.
- The generated unique namespace name is not accessible to the developer.
- There can only be one anonymous namespace for a single translation unit. If we set up multiple anonymous namespace blocks, they’ll just be extensions to the first one.
- Anonymous namespaces in different translation units are completely separate though, the compiler generates different unique namespace names for them behind the scenes.
- Because we don’t have access to the compiler generated namespace name for anonymous namespaces, names declared inside anonymous namespaces are only reachable/usable in the TU where they were declared.

> Names in an anonymous namespace are only reachable/usable from the TU where they were declared/defined.

## Smart Pointers 

As we’ve known not deallocating a pointer causes a memory leak that may lead to crash of the program. A Smart Pointer is a wrapper class over a pointer with an operator like`*` and `->` overloaded. The objects of the smart pointer class look like normal pointers. But, unlike Normal Pointers it can deallocate and free destroyed object memory. 

> - The idea is to take a class with a pointer, destructor, and overloaded operators like `*` and `->`. Since the destructor is automatically called when an object goes out of scope, the dynamically allocated memory would automatically be deleted.
> - `<memory>` library used to handle smart pointer. 

There's three types of smart pointers: 

1. Unique Pointer
2. Shared Pointer
3. Weak Pointer

### Unique Pointer

`unique_ptr` stores one pointer only. We can assign a different object by removing the current object from the pointer.

![uniquePtr](image/uniquePtr.png)

```c++
// Create new unique ptr
std::unique_ptr<Data_Type> ptr_Name {new Data_Type(Value)};

//  Manage a previously allocated ptr
Data_Type * ptr_Name1 = new Data_Type(Value);
std::unique_ptr<Data_Type> ptr_Name2{ptr_Name1};

// Initialize with nullptr
std::unique_ptr<Data_Type> ptr_Name {nullptr};

// using make_unique syntax. Calls new internally for us, we don't have to do it ourselves
std::unique_ptr<Data_Type> ptr_Name = std::make_unique<Data_Type>(Value) ;

// Copies and Assignments are not allowed with unique ptr
std::unique_ptr<Data_Type> ptr_Name1 = ptr_Name2 ; // Error.This does some kind of copy

//Can move the pointer ownership. 
std::unique_ptr<Data_Type> ptr_Name1 = std::make_unique<Data_Type>(ptr_Name2);
std::unique_ptr<Data_Type> ptr_Name2 = std::move(ptr_Name1); 

//Can reset unique ptr : releases memory and sets the pointer to nullptr
std::unique_ptr<Data_Type> ptr_Name = std::make_unique<Data_Type>(Value) ;
ptr_Name.reset() ;

/******* Passing and Returning unique ptr to functions *******/
// 1. Pass unique_ptr by value
fun(unique_ptr_Name) ; // Error.This does some kind of copy

// 2. Pass by move the pointer ownership
std::unique_ptr<Data_Type> ptr_Name = std::make_unique<Data_Type>(Value) ;
fun(std::move(ptr_Name)) ; // Ownership will move to the body of the function and memory will be released when function returns.

// 3. Pass unique_ptr by reference
void fun(const std::unique_ptr<Data_Type> & ptr_Name)
{
    ptr_Name->do_somthing() ; 
    ptr_Name.reset() ; // Compiler error
}
std::unique_ptr<Data_Type> ptr_Name = std::make_unique<Data_Type>(Value) ;
fun(ptr_Name) ; // Ownership won't move to the body of the function and memory won't be released when function returns.

// 4. Returning unique ptr from function by value
std::unique_ptr<Data_Type> get_unique_ptr()
{
    std::unique_ptr<Data_Type> ptr_Name = std::make_unique<Data_Type>(Value) ;
	ptr_Name->do_somthing() ; 
    return ptr_Name;  // The compiler does some optimizations and doesn't return a copy here
					// it's returning something like a reference to the local object.
					// We can prove this by looking at the address of objects in memory.
					// This is not standard behavior, some compilers may actually return 
					// by value by making a copy. The compilers have some freedom to choose
					// their own way to do things.
}
std::unique_ptr<Data_Type> ptr_Name = get_unique_ptr() ;

/******* Smart Pointers and Arrays *******/
// 1. using unique_ptr
std::unique_ptr<Data_Type[]> arr_ptr = std::unique_ptr<Data_Type[]> (new Data_Type[arrr_size]{value1, value2 , value3});
// or 
auto arr_ptr = std::unique_ptr<Data_Type[]> (new Data_Type[arrr_size]{value1, value2 , value3});

// 2. using make_unique
std::unique_ptr<Data_Type[]> arr_ptr = std::make_unique<Data_Type[]> (3);
// or 
auto arr_ptr = std::make_unique<Data_Type[]> (3); // Works but can't initialize individual elements
auto arr_ptr = std::make_unique<Data_Type[]> (3) {value1, value2 , value3} //Compiler error
auto arr_ptr = std::make_unique<Data_Type[]> {value1, value2 , value3} //Compiler error
```

### Shared Pointer

`shared_ptr` more than one pointer can point to this one object at a time and it’ll maintain a Reference Counter using `use_count()` method.

![sharedptr](image/sharedptr.png)

```c++
// Create new shared ptr
std::shared_ptr<Data_Type> ptr_Name {new Data_Type(Value)};

//  Manage a previously allocated ptr
Data_Type * ptr_Name1 = new Data_Type(Value);
std::shared_ptr<Data_Type> ptr_Name2{ptr_Name1};

// Initialize with nullptr
std::shared_ptr<Data_Type> ptr_Name {nullptr};

// using make_shared syntax. Calls new internally for us, we don't have to do it ourselves
std::shared_ptr<Data_Type> ptr_Name = std::make_shared<Data_Type>(Value) ;

// Copies and Assignments are allowed with shared ptr
std::shared_ptr<Data_Type> ptr_Name1 = ptr_Name2 ; // use_count = 2

// Copying
std::shared_ptr<Data_Type> ptr_Name1 ;
ptr_Name3 = ptr_Name1 ; // use_count = 3
// or 
std::shared_ptr<Data_Type> ptr_Name4 {nullptr};
ptr_Name4 = ptr_Name1 ; // use_count = 4
// or 
std::shared_ptr<Data_Type> ptr_Name5 {ptr_Name1};

// Can reset shared ptr : decrement use_count
std::shared_ptr<Data_Type> ptr_Name = std::make_shared<Data_Type>(Value) ;
ptr_Name.reset() ; // use_count-- 

// Create shared pointers from unique_ptrs : // Ownership moves from unique_ptrs to shared_ptrs from now on
std::unique_ptr<Data_Type> unique_ptr_Name = std::make_unique<Data_Type>(Value) ;
std::shared_ptr<Data_Type> shared_ptr_Name = std::move(unique_ptr_Name); 
std::shared_ptr<Data_Type> shared_ptr_Name = unique_ptr_Name; // Error: Direct assignment 
													     // Doesn't work, must do an explicit std::move to move ownership

// Can't transform from std::shared_ptr to std::unique_ptr
std::unique_ptr<Data_Type> unique_ptr_Name {shared_ptr_Name} ; // Compiler error
/* 	The reason this transformation is disabled isn't hard to think of.
	At any given moment, there may be any number of shared pointers 
	spread through your entire application working on the same object, 
	If you were to instantly make one of those a unique ptr. 
	What do you do with the remaining copies?. 
	Unique ptr can't have copies anyway. So the compiler prevents you from doing this.
*/

// Returning unique_ptr to shared_ptr
std::shared_ptr<Data_Type> shared_ptr_Name = get_unique_ptr(); // This implicitly moves and use_count++

/******* Passing and Returning unique ptr to functions *******/
// 1. Pass shared_ptr by value
			// use_count = 1
void fun1 (std::shared_ptr<Data_Type> shared_ptr_Name)
{
    shared_ptr_Name->do_somthing() ; // use_count = 2
}
			// use_count = 1

// 2. Pass shared_ptr by non const ref
			// use_count = 1
void fun2 (std::shared_ptr<Data_Type> & shared_ptr_Name)
{
    shared_ptr_Name->do_somthing() ; // use_count = 1
    shared_ptr_Name.reset() ; // non protected pointer because of non const ref
}
			// use_count = 1

// 3. Pass shared_ptr by const ref
			// use_count = 1
void fun2 (const std::shared_ptr<Data_Type> & shared_ptr_Name)
{
    shared_ptr_Name->do_somthing() ; // use_count = 1
    shared_ptr_Name.reset() ;  // Compiler error because of const ref
}
			// use_count = 1

// 4. Returning shared_ptr from function by value
std::shared_ptr<Data_Type> get_shared_ptr()
{
    std::shared_ptr<Data_Type> ptr_Name = std::make_shared<Data_Type>(Value) ;
	ptr_Name->do_somthing() ; 
    return ptr_Name;  // The compiler does some optimizations and doesn't return a copy here
					// it's returning something like a reference to the local object.
}
std::shared_ptr<Data_Type> ptr_Name = get_shared_ptr() ; // use_count = 1

// 5. Returning shared_ptr from function by ref (const or non const)
////RETURNING SHARED_PTR BY REF( CONST OR NON CONST) IS A RECIPE FOR DISASTER. DON'T DO IT.
//returning std::shared_ptr by reference doesn't properly increment the reference count,
// which opens up the risk of deleting something at the wrong time. We'll get a crash
std::shared_ptr<Data_Type> get_shared_ptr()
{
    std::shared_ptr<Data_Type> ptr_Name = std::make_shared<Data_Type>(Value) ;
	ptr_Name->do_somthing() ; 
    return ptr_Name;  // The compiler does some optimizations and doesn't return a copy here
					// it's returning something like a reference to the local object.
}
std::shared_ptr<Data_Type> ptr_Name = get_shared_ptr() ; // use_count = 0

/******* Smart Pointers and Arrays *******/
// 1. using shared_ptr
std::shared_ptr<Data_Type[]> arr_ptr (new Data_Type[arrr_size]{value1, value2 , value3});

// 2. using make_shared: make_shared syntax isn't supported yet for raw arrays. Some compilers do offer

// 3. Read from array
std::cout << arr_ptr[index] << std::endl;

// 4. Setting elements
arr_ptr[index] = value ;
```

### Weak Pointer

It’s much more similar to `shared_ptr` except it’ll not maintain a Reference Counter. In this case, a pointer will not have a stronghold on the object. The reason is if suppose pointers are holding the object and requesting for other objects then they may form a Deadlock. 

![weakPtr](image/weakPtr.png)

A `weak_ptr` is created as a copy of `shared_ptr`. It provides access to an object that is owned by one or more `shared_ptr` instances but does not participate in reference counting. The existence or destruction of `weak_ptr` has no effect on the `shared_ptr` or its other copies. It is required in some cases to break circular references between `shared_ptr` instances.

**Cyclic Dependency (Problems with shared_ptr):** Let’s consider a scenario where we have two classes A and B, both have pointers to other classes. So, it’s always like A is pointing to B and B is pointing to A. Hence, use_count will never reach zero and they never get deleted.

![weakPtrex1](image/weakPtrex1.png)

This is the reason we use `weak_ptr` as they are not reference counted. So, the class in which `weak_ptr` is declared doesn’t have a stronghold of it. the ownership isn’t shared, but they can have access to these objects.

![weakPtrex2](image/weakPtrex2.png)

So, in case of `shared_ptr`because of cyclic dependency use_count never reaches zero which is prevented using `weak_ptr`, which removes this problem by declaring `A_ptr` as `weak_ptr`, thus class A does not own it, only have access to it and we also need to check the validity of object as it may go out of scope. In general, it is a design issue.

>**When to use `weak_ptr`?**
>When you do want to refer to your object from multiple places – for those references for which it’s ok to ignore and deallocate (so they’ll just note the object is gone when you try to dereference).

## Operator Overloading 

In C++, we can make operators work for user-defined classes. This means C++ has the ability to provide the operators with a special meaning for a data type, this ability is known as operator overloading. For example, we can overload an operator ‘+’ in a class like String so that we can concatenate two strings by just using +. Other example classes where arithmetic operators may be overloaded are Complex Numbers, Fractional Numbers, Big Integer, etc.

Operator overloading is a compile-time polymorphism. It is an idea of giving special meaning to an existing operator in C++ without changing its original meaning.

![operatorOverloading](image/operatorOverloading.png)

### Addition Operator 

#### As Member

```c#
// Point.h 
class Point
{
    public:
        Point() = default;
        Point(double x, double y) : 
            m_x(x), m_y(y){
        }
        ~Point() = default;

        //Member
        Point operator+(const Point& right_operand)
        {
            return Point(this->m_x + right_operand.m_x , this->m_y + right_operand.m_y);
        }

       void print_info()
       {
            std::cout << "Point [ x : " << m_x << ", y : " << m_y << "]" << std::endl;
        }

    private : 
        double m_x{};
        double m_y{};
};
```

```c++
// main.cpp
#include "point.h"

int main()
{
    Point p1(10,10);
    Point p2(20,20);
    Point p3{p1 + p2}; // p1.operator+(p2)

    Point p4{p2 + Point(5,5)}; // p2.operator+(Point(5,5))
    
    p3.print_info();
    p4.print_info();

    (Point(20,20) + Point(10,10)).print_info(); //(Point(20,20)).operator+(Point(10,10))
    
    return 0;
}
```

#### As Non-Member

```c#
// Point.h 
class Point
{
    public:
        Point() = default;
        Point(double x, double y) : 
            m_x(x), m_y(y){
        }
        ~Point() = default;
    
       friend Point operator+(const Point& left_operand, const Point& right_operand); 
       void print_info()
       {
            std::cout << "Point [ x : " << m_x << ", y : " << m_y << "]" << std::endl;
        }

    private : 
        double m_x{};
        double m_y{};
};

//Non Member
inline Point operator+(const Point& left_operand, const Point& right_operand)
{
    return Point(left_operand.m_x + right_operand.m_x ,left_operand.m_y + right_operand.m_y);
}
```

```c++
// main.cpp
#include "point.h"

int main()
{
    Point p1(10,10);
    Point p2(20,20);
    //Point p3{p1 + p2}; // opearator+(p1,p2);
    Point p3{operator+ (p1,p2)};

    Point p4{p2 + Point(5,5)};
    
    p3.print_info();
    p4.print_info();

    (Point(20,20) + Point(10,10)).print_info();
    
    return 0;
}
```

### Subscript Operator 

#### For Reading

```c#
// Point.h 
#include <cassert> // for using assert() to chech the input data in run time
class Point
{
    public:
        Point() = default;
        Point(double x, double y) : 
            m_x(x), m_y(y){
        }
        ~Point() = default;
    
       double operator[](size_t index) const
       {
           	assert( (index == 0) || (index == 1));
            if(index == 0)
            {
                return m_x;
            }
           else
           {
                return m_y;
            }
       }
    
       void print_info()
       {
            std::cout << "Point [ x : " << m_x << ", y : " << m_y << "]" << std::endl;
        }

    private : 
        double m_x{};
        double m_y{};
};
```

```c++
// main.cpp
#include <iostream>
#include "point.h"

int main()
{
    Point p1(10,20);
    std::cout << "p1.x : " << p1[0] << std::endl; // x coordinate : 10
    std::cout << "p1.x : " << p1.operator[](0) << std::endl; // x coordinate : 10
    std::cout << "p1.y : " << p1[1] << std::endl; // y coordinate : 20
    return 0;
}
return 0;
}
```

#### For Reading and Writing

> To use the Subscript Operator for Reading and Writing, we just change the operator function to return as reference `&` 

```c#
// Point.h 
#include <cassert> // for using assert() to chech the input data in run time
class Point
{
    public:
        Point() = default;
        Point(double x, double y) : 
            m_x(x), m_y(y){
        }
        ~Point() = default;
    
       double& operator[](size_t index)
       {
           	assert( (index == 0) || (index == 1));
            if(index == 0)
            {
                return m_x;
            }
           else
           {
                return m_y;
            }
       }
    
       void print_info()
       {
            std::cout << "Point [ x : " << m_x << ", y : " << m_y << "]" << std::endl;
        }

    private : 
        double m_x{};
        double m_y{};
};
```

```c++
// main.cpp
#include <iostream>
#include "point.h"

int main(){

    Point p1(10,20);

    p1.print_info();

    //Changing the data
    p1[0] = 35.6;
    p1[1] = 23.9;

    p1.print_info();
    return 0;
}
```

### Stream Insertion Operation Operator

```c#
// Point.h 
#include <iostream>
class Point
{
    public:
        Point() = default;
        Point(double x, double y) : 
            m_x(x), m_y(y){
        }
        ~Point() = default;

        void print_info(){
            std::cout << "Point [ x : " << m_x << ", y : " << m_y << "]" << std::endl;
        }
    
        friend std::ostream& operator<<(std::ostream& os, const Point& p);

        /* we usually don't use this because the first operand is the member itself
        std::ostream& operator<< (std::ostream& os)
        {
            os << "Point [ x : " << m_x << ", y : " << m_y << "]";
            return os;			
        }
        */

    private : 
        double m_x{}; 
        double m_y{}; 
};

inline std::ostream& operator<<(std::ostream& os, const Point& p)
{
	os << "Point [ x : " << p.m_x << ", y : " << p.m_y << "]";	
	return os;
}
```

```c++
// main.cpp
#include <iostream>
#include "point.h"

int main()
{
    Point p1(10,20);
    Point p2(3,4);
    
    // p1 << std::cout (operator as member function)
    
    std::cout << p1 << p2 << std::endl; // as print_info()
   
    return 0;
}
```

### Stream Extraction Operator

```c#
// Point.h 
#include <iostream>
class Point
{
    public:
        Point() = default;
        Point(double x, double y) : 
            m_x(x), m_y(y){
        }
        ~Point() = default;

        void print_info(){
            std::cout << "Point [ x : " << m_x << ", y : " << m_y << "]" << std::endl;
        }
    
        friend std::ostream& operator<<(std::ostream& os, const Point& p);

        /* we usually don't use this because the first operand is the member itself
        std::istream& operator<<(std::istream& is)
        {
            double x , y ; 
            is >> x >> y ; 
            m_x = x ; 
            m_y = y ; 
            return is;
        }
        */

    private : 
        double m_x{}; 
        double m_y{}; 
};

inline std::istream& operator<<(std::istream& is, const Point& p)
{
	double x , y ; 
    is >> x >> y ; 
    p.m_x = x ; 
    p.m_y = y ; 
	return is;
}
```

```c++
// main.cpp
#include <iostream>
#include "point.h"

int main()
{
    Point p2;
    std::cin >> p2;//
    std::cout << "p2 : " << p2 << std::endl;
}
```

### Compound Operators 

```c#
// Point.h 
inline Point operator+= (const Point& left_operand, const Point& right_operand)
{
    left_operand.m_x += right_operand.m_x ;
    left_operand.m_y += right_operand.m_y ;
    return left_operand ;
}

inline Point operator-= (const Point& left_operand, const Point& right_operand)
{
    left_operand.m_x += right_operand.m_x ;
    left_operand.m_y += right_operand.m_y ;
    return left_operand ;
}

inline Point operator+ (const Point& left_operand, const Point& right_operand) // another way to implement + using +=
{
    Point p(left_operand.m_x , left_operand.m_y)
    return p += right_operand ;
}

inline Point operator- (const Point& left_operand, const Point& right_operand) // another way to implement - using -=
{
    Point p(left_operand.m_x , left_operand.m_y)
    return p -= right_operand ;
}
```

### Conversions Operators 

> - Overloaded conversion operators must be a member method.
> - We can use the `explicit ` keyword to avoid implicit cast by the compiler, then explicitly cast every data type to be used. 
> - When a binary operator is implemented as a member function, the left operand is never implicitly converted.

```c++
#include <iostream>
class Number
{
   public:
	Number() = default;
	Number(int value );
     ~Number();

    explicit operator double() const
    {
        return (static_cast <double> (m_wrapped_int));
    }
    
    //getter
    int get_wrapped_int() const{
        return m_wrapped_int;
    }
    
    private : 
        int m_wrapped_int{0};
};

double sum(double a, double b)
{
    return a + b;
}

int main() 
{
    Number n1(22);
    Number n2(10);
    
    double result = sum(static_cast<double>(n1),static_cast<double>(n2));
    std::cout << "result : " << result <<  std::endl;
}
```

### Unary Prefix Increment Operator 

#### As Member

```c++
#include <iostream>
class Point
{
    public:
        Point() = default;
        Point(double x, double y) : 
            m_x(x), m_y(y)
        {
        }

        void operator++() 
        {
            ++m_x;
            ++m_y;
        }

        ~Point() = default;

    private : 
        double m_x{}; 
        double m_y{}; 
};

int main() 
{
    Point p1(10,10);
    p1.operator++();
    std::cout << "p1 : " << p1 << std::endl; // p1: (11,11)
}
```

#### As Non-Member

```c++
#include <iostream>
class Point
{
    public:
        Point() = default;
        Point(double x, double y) : 
            m_x(x), m_y(y)
        {
        }

        friend void operator++(Point& operand);

        ~Point() = default;

    private : 
        double m_x{}; 
        double m_y{}; 
};

inline void operator++(Point& operand)
{
	++(operand.m_x);
	++(operand.m_y);
}

int main() 
{
    Point p1(10,10);
    ++p1; //operator++(p1);
    std::cout << "p1 : " << p1 << std::endl; // p1: (11,11)
}
```

### Unary Postfix Increment Operator

#### As Member

```c++
#include <iostream>
class Point
{
    public:
        Point() = default;
        Point(double x, double y) : 
            m_x(x), m_y(y)
        {
        }

        void operator++() 
        {
            ++m_x;
            ++m_y;
        }
    
    	Point operator++(int) // dummy int
        {
            Point local_point(*this);
            ++(*this);
            return local_point;
        }

        ~Point() = default;

    private : 
        double m_x{}; 
        double m_y{}; 
};

int main() 
{
    Point p1(10,10);
    std::cout << "p1 : " << p1++ << std::endl; // (10,10);
    std::cout << "p1 : " << p1 << std::endl; // (11,11)
}
```

#### As Non-Member

```c++
#include <iostream>
class Point
{
    public:
        Point() = default;
        Point(double x, double y) : 
            m_x(x), m_y(y){
        }

        friend void operator++(Point& operand);
   	    friend Point operator++(Point& operand,int);

        ~Point() = default;

    private : 
        double m_x{}; 
        double m_y{}; 
};

inline void operator++(Point& operand)
{
	++(operand.m_x);
	++(operand.m_y);
}

inline Point operator++(Point& operand,int)
{
	Point local_point(operand);
	++operand;
	return local_point;
}

int main() 
{
    Point p1(10,10);
    std::cout << "p1 : " << p1++ << std::endl; // (10,10);
    std::cout << "p1 : " << p1 << std::endl; // (11,11)
}
```

### Copy Assignment Operator

Copy constructor and Assignment operator are similar as they are both used to initialize one object using another object. But, there are some basic differences between them:

|                     **Copy constructor**                     |                   **Assignment operator**                    |
| :----------------------------------------------------------: | :----------------------------------------------------------: |
| It is called when a new object is created from an existing object, as a copy of the existing object | This operator is called when an already initialized object is assigned a new value from another existing object. |
|    It creates a separate memory block for the new object.    | It does not create a separate memory block or new memory space. |
|               It is an overloaded constructor.               |                  It is a bitwise operator.                   |
| C++ compiler implicitly provides a copy constructor, if no copy constructor is defined in the class. | A bitwise copy gets created, if the Assignment operator is not overloaded. |

> - If you have no custom copy assignment operator in place, the compiler is going to generate one for you The compiler generated one is going to do member wise copy
> - The copy assignment operator can only be done as a member function. So C++ does it supports doing this as a non-member.
> - ![CopyAssignment](image/CopyAssignment.png)
> - We can use `Copy Assignment` for custom assignments with two objects with different data.

```c++
#include <iostream>
class Point
{
    public:
        Point() = default;
        Point(double x, double y) : 
            m_x(x), m_y(y)
        {
        }

        Point& operator= (const Point& right_operand)
        {
            if(this != & right_operand) // check for self assignment 
            {
                delete p_data;
                p_data = new int(*(right_operand.p_data));
                m_x =  right_operand.m_x;
                m_y = right_operand.m_y;
            }
            return *this;
		}

        ~Point() = default;

    private : 
        double m_x{}; 
		double m_y{}; 
		int * p_data; 
};

int main() 
{
    Point p1(10,10);
    Point p1(20,20);
    std::cout << "p1 : " << p1++ << std::endl; // (10,10)
    std::cout << "p1 : " << p1 << std::endl; // (20,20)
    
    p1 = p2 ;
    std::cout << "p1 : " << p1++ << std::endl; // (20,20)
    std::cout << "p1 : " << p1 << std::endl; // (20,20)
}
```

### Functors

Objects of a class that overloads the () operator The C++.

```c++
#include <iostream>
#include <string>

class Print
{
    public : 
        void operator()(const std::string& name) const
        {
            std::cout << "The name is : " << name << std::endl;
        }

        std::string operator()(const std::string& last_name, const std::string& first_name) const 
        {
            return (last_name + " " + first_name);
        }
};

void do_something(const Print& printer)
{
    printer("Snow");
}


int main()
{
    Print print;
    print("John");
    do_something(print);
    std::cout << print("Daniel","Gray") << std::endl;
   
    return 0;
}
```

## Inheritance

The capability of a `class` to derive properties and characteristics from another class is called `Inheritance`. 

- Inheritance is one of the most important features of Object-Oriented Programming. 
- Inheritance is a feature or a process in which, new classes are created from the existing classes. 
- The new class created is called “derived class” or “child class” and the existing class is known as the “base class” or “parent class”. 
- The derived class now is said to be inherited from the base class.
- Building types on top of other types.
- Inheritance hierarchies can be set up to suit your needs.
- Code reuse is improved.

![Inheritance](image/Inheritance.png)

When we say derived class inherits the base class, it means, the derived class inherits all the properties of the base class, without changing the properties of base class and may add new features to its own. These new features in the derived class will not affect the base class. The derived class is the specialized class for the base class.

- **Sub Class:** The class that inherits properties from another class is called Subclass or Derived Class. 
- **Super Class:** The class whose properties are inherited by a subclass is called Base Class or Superclass. 

### Why and When to Use Inheritance 

Consider a group of vehicles. You need to create classes for Bus, Car, and Truck. The methods `fuelAmount()`, `capacity()`, `applyBrakes()` will be the same for all three classes. If we create these classes avoiding inheritance then we have to write all of these functions in each of the three classes.

![inheritanceExample](image/inheritanceExample.png)

This increases the chances of error and data redundancy. To avoid this type of situation, inheritance is used. If we create a class Vehicle and write these three functions in it and inherit the rest of the classes from the vehicle class, then we can simply avoid the duplication of data and increase re-usability. Using inheritance, we have to write the functions only one time instead of three times as we have inherited the rest of the three classes from the base class (Vehicle).

![inheritanceExample2](image/inheritanceExample2.png)

### Inheritance Implementation 

```c++
class  <derived_class_name> : <access-specifier> <base_class_name>
{
        //body
}
/*
* class					— keyword to create a new class
* derived_class_name	 — name of the new class, which will inherit the base class
* access-specifier  	 — either of private, public or protected. If neither is specified, PRIVATE is taken as default
* base-class-name  		 — name of the base class
*/
```

> - A derived class doesn’t inherit ***access*** to private data members. However, it does inherit a full parent object, which contains any private members which that class declares.
> - When a base class is privately inherited by the derived class, public members of the base class becomes the private members of the derived class and therefore, the public members of the base class can only be accessed by the member functions of the derived class. They are inaccessible to the objects of the derived class.
> - When the base class is publicly inherited by the derived class, public members of the base class also become the public members of the derived class. Therefore, the public members of the base class are accessible by the objects of the derived class as well as by the member functions of the derived class.
> - You can restrict the private member to a more relaxed access level, by using the `using` keyword. If we put them in a public section, they are going to be resurrected with a public access level and they are going to be accessible from inheriting classes, you should know is that you can't resurrect something that is already private. **This not good design** 

### Class  Access Specifier

Access modifiers are used to implement an important aspect of Object-Oriented Programming known as Data Hiding. Access Modifiers or Access Specifiers in a class are used to assign the accessibility to the class members, i.e., they set some restrictions on the class members so that they can’t be directly accessed by the outside functions. There are 3 types of access modifiers available in C++: 

1. **Public**: All the class members declared under the public specifier will be available to everyone. The data members and member functions declared as public can be accessed by other classes and functions too. The public members of a class can be accessed from anywhere in the program using the direct member access operator (.) with the object of that class. 
2. **Private**: The class members declared as private can be accessed only by the member functions inside the class. They are not allowed to be accessed directly by any object or function outside the class. Only the member functions or the friend functions are allowed to access the private data members of the class. 
3. **Protected**: The protected access modifier is similar to the private access modifier in the sense that it can’t be accessed outside of its class unless with the help of a friend class. The difference is that the class members declared as Protected can be accessed by any subclass (derived class) of that class as well. 

### Modes of Inheritance

 There are 3 modes of inheritance:

1. **Public Mode**: If we derive a subclass from a public base class. Then the public member of the base class will become public in the derived class and protected members of the base class will become protected in the derived class.
2. **Protected Mode**: If we derive a subclass from a Protected base class. Then both public members and protected members of the base class will become protected in the derived class.
3. **Private Mode**: If we derive a subclass from a Private base class. Then both public members and protected members of the base class will become Private in the derived class.

![ModesOfInheritance](image/ModesOfInheritance.png)

> ​    The private members in the base class cannot be directly accessed in the derived class, while protected members can be directly accessed.

```c++
class A 
{
    public:
        int x;
    protected:
        int y;
    private:
        int z;
};
  
class B : public A 
{
    // x is public
    // y is protected
    // z is not accessible from B
};
  
class C : protected A 
{
    // x is protected
    // y is protected
    // z is not accessible from C
};
  
class D : private A // 'private' is default for classes
{
    // x is private
    // y is private
    // z is not accessible from D
};
```

### Constructors with Inheritance

#### Default Constructors with Inheritance

Always provide a default constructor for your classes, especially if they will be part of an inheritance hierarchy. Constructors are going to be called in your inheritance hierarchy, starting from the most basic going down to the most specialized one.

![DefaultConstructorsInheritance](image/DefaultConstructorsInheritance.png)

#### Custom Constructors With Inheritance

![CustomConstructorsInheritance](image/CustomConstructorsInheritance.png)

We have three ways to do this: 

```c++
/******************* 1. Set the values in the body *******************/
// BAD : Compiler error - m_address is private to person
CivilEngineer::CivilEngineer(std::string_view fullname,int age,
    std::string_view address,int contract_count, std::string_view speciality)
{
    m_full_name = fullname;
    m_age = age;
    //m_address = address;
    m_speciality = speciality;
    std::cout << "Custom constructor called for CivilEnginner ... " << std::endl;
}

/******************* 2. Set the values with Initializer lists : Doing it wrong *******************/
// BAD : Compiler error - You can't initialize a member variable that doesn't belong to the class that you are trying to build an object for.
CivilEngineer::CivilEngineer(std::string_view fullname,int age,
    std::string_view address,int contract_count, std::string_view speciality)
    :m_full_name(fullname),m_age(age),m_address(address),m_speciality(speciality)
{
    std::cout << "Custom constructor called for CivilEnginner ... " << std::endl;
}

/******************* 3. Set the values with Initializer lists *******************/
// We can still use initializer lists, but we are going to use constructors whose job is going to be to initialize these member variables.
CivilEngineer::CivilEngineer(std::string_view fullname,int age,
    std::string_view address,int contract_count, std::string_view speciality)
     : Engineer(fullname,age,address,contract_count), m_speciality(speciality)
{
    std::cout << "Custom constructor called for CivilEnginner ... " << std::endl;
}
```

#### Copy Constructors With Inheritance

![CopyConstructorsInheritance](image/CopyConstructorsInheritance.png)

```c++
// Base class copy constructors 
Person::Person(const Person& source) : m_full_name(source.m_full_name) , m_age(source.m_age), m_address(source.m_address)
{
    std::cout << "Custom copy constructor for Person called..." << std::endl;
}

// Derived class copy constructors 
// 1. BAD
Engineer::Engineer(const Engineer& source) : contract_count(source.contract_count)
{
    std::cout << "Custom copy constructor for Engineer called..." << std::endl;
}

// 2. BAD
Engineer::Engineer(const Engineer& source)
     : Person(source.m_full_name,source.m_age,source.get_address()) , contract_count(source.contract_count)
{
    std::cout << "Custom copy constructor for Engineer called..." << std::endl;
}
/* 
* Not reusing the copy constructor we have in Person
* m_address is private to Person, can’t be directly accessed from Engineer object
* We could set up a public method to return the address but that could go against your design guidelines
*/ 

// 3. GOOD
Engineer::Engineer(const Engineer& source)
     : Person(source) , contract_count(source.contract_count)
{
    std::cout << "Custom copy constructor for Engineer called..." << std::endl;
}
/*
* The compiler is smart enough to see that we aren't passing an `engineer` object to initialize a person object and what are the * * * * * computers going to do is really smart. Suppose our engineer object is made up of two layers: 
* - The inner layer is going to be containing the information about the `person`.
* - The outer layer is going to be containing the `engineer`.
* So the compiler is going to see that we are passing the `engineer` object to initialize a `person` object and what it is going to do is * really smart. It is going to strip off all of this `engineer` part that we have in our `engineer` object, and we will be just left * * * whether the `person` apart that we pass then to initialize a `person` object.
*/
```

#### Inheriting Base Constructors

![InheritingBaseConstructors](image/InheritingBaseConstructors.png)

```c++
// Using statement : Inherit the constructors
class Engineer : public Person
{
    using Person::Person; // Inheriting constructors
    // body ...
}
// Compiler generated constructor as result of inheritance
Engineer::Engineer(std::string_view fullname,int age, std::string_view address) : Person(fullname,age,address)
{
    std::cout << "generated constructor for Engineer called..." << std::endl;
}
```

> - Copy constructors are not inherited. But you won’t usually notice this as the compiler will insert an automatic copy constructor
> - Inherited constructors are base constructors. They have no knowledge of the derived class. Any member from the derived class will just contain junk or whatever default value it’s initialized with
> - Constructors are inherited with whatever access specifier they had in base class
> - On top of derived constructors, you can add your own that possibly properly initialize derived member variables
> - Inheriting constructors adds a level of confusion to your code, it’s not clear which constructor is building your object. It is recommended to avoid them and only use this feature if no other option is available.

#### Inheritance and Destructors

Base class part of derived object constructed first and destructed last.

![Constructors-and-Destructors-in-Inheritance-in-C](image/Constructors-and-Destructors-in-Inheritance-in-C.webp)

### Types Of Inheritance

There's 5 types of inheritance: 

1. Single inheritance.
2. Multilevel inheritance.
3. Multiple inheritance.
4. Hierarchical inheritance.
5. Hybrid inheritance.

#### Single inheritance

In single inheritance, a class is allowed to inherit from only one class. i.e. one subclass is inherited by one base class only.

![single-inheritance](image/single-inheritance.png)

```c++
class subclass_name : access_mode base_class
{
  // body of subclass
};

// OR

class A
{ 
	//... .. ... 
};

class B: public A
{
	//... .. ...
};
```

#### Multiple Inheritance

Multiple Inheritance is a feature of C++ where a class can inherit from more than one class. i.e one **subclass** is inherited from more than one **base class**.



```c++
// The number of base classes will be separated by a comma (,) and the access mode for every base class must be specified. 
class subclass_name : access_mode base_class1, access_mode base_class2, ....
{
  // body of subclass
};

// OR

class B
{ 
	//... .. ... 
};
class C
{
	//... .. ...
};
class A: public B, public C
{
	//... ... ...
};
```

> **The diamond problem** The diamond problem occurs when two super classes of a class have a common base class. The solution to this problem is `virtual` keyword to avoid two copies. When we use `virtual` keyword, the default constructor of grandparent class is called by default even if the parent classes explicitly call parameterized constructor. In general, it is not allowed to call the grandparent’s constructor directly, it has to be called through parent class. It is allowed only when `virtual` keyword is used.

####  Multilevel Inheritance

In Multilevel Inheritance, a derived class is created from another derived class.

![multilevel-inheritance](image/multilevel-inheritance.png)

```c++
class C
{ 
	//... .. ... 
};
class B:public C
{
	//... .. ...
};
class A: public B
{
	//... ... ...
};
```

#### Hierarchical Inheritance

In Hierarchical Inheritance, more than one subclass is inherited from a single base class. i.e. more than one derived class is created from a single base class.

![hierarchical-inheritance](image/hierarchical-inheritance.png)

```c++
class A  
{  
    // body of the class A.  
}    
class B : public A   
{  
    // body of class B.  
}  
class C : public A  
{  
    // body of class C.  
}   
class D : public A  
{  
    // body of class D.  
}   
```

#### Hybrid Inheritance 

Hybrid Inheritance is implemented by combining more than one type of inheritance. Like combining **Hierarchical inheritance** and **Multiple Inheritance**. 

![Hybrid-Inheritance](image/Hybrid-Inheritance.png)

## Exception Handling 

Exceptions are runtime anomalies or abnormal conditions that a program encounters during its execution. There are two types of exceptions:

1. Synchronous
2. Asynchronous 

C++ provides the following specialized keywords for this purpose:

1. `try`: Represents a block of code that can throw an exception.
2. `catch`: Represents a block of code that is executed when a particular exception is thrown.
3. `throw`: Used to throw an exception. Also used to list the exceptions that a function throws but doesn’t handle itself.

### Exception Handling Features
The following are the main advantages of exception handling over traditional error handling:

1) Separation of Error Handling code from Normal Code: In traditional error handling codes, there are always if-else conditions to handle errors. These conditions and the code to handle errors get mixed up with the normal flow. This makes the code less readable and maintainable. With try/catch blocks, the code for error handling becomes separate from the normal flow.

2) Functions/Methods can handle only the exceptions they choose: A function can throw many exceptions, but may choose to handle some of them. The other exceptions, which are thrown but not caught, can be handled by the caller. If the caller chooses not to catch them, then the exceptions are handled by the caller of the caller. In C++, a function can specify the exceptions that it throws using the throw keyword. The caller of this function must handle the exception in some way (either by specifying it again or catching it).

3) Grouping of Error Types: In C++, both basic types and objects can be thrown as exceptions. We can create a hierarchy of exception objects, group exceptions in namespaces or classes and categorize them according to their types.

### C++ try and catch

Exception handling in C++ consists of three keywords: try, throw and catch:

- The `try` statement allows you to define a block of code to be tested for errors while it is being executed.
- The `throw` keyword throws an exception when a problem is detected, which lets us create a custom error.
- The `catch` statement allows you to define a block of code to be executed if an error occurs in the try block.
- The `try` and `catch` keywords come in pairs:
  - We use the `try` block to test some code. 
  - In the `catch` block, we catch the error if it occurs and do something about it. 
  - The `catch` statement takes a single parameter. 

- If no error occurs the `catch` block is skipped. 

### Syntax

```c++
int main()
{
   try 
   {
      if (/* Condition */)
      {
         throw x;
      }
   }
   catch (int x ) {
      cout << "Exception Caught \n";
   }
}
```

There's special catch block called the ‘catch all’ block

```c++
int main()
{
   try 
   {
      if (/* Condition */)
      {
         throw x;
      }
   }
   catch (...) {
      cout << "Exception Caught \n";
   }
}
```

### Exception Cases

#### The automatic local

Variables are destroyed when we are thrown out of a try block

```c++
int main()
{
    //Showing that that automatic local variables are destroyed when 
    //we are thrown out of a try block
    int a{10};
    int b{10};

    try
    {
        Item item; // When exception is thrown, control immediately exits the try block
                    // an automatic local variables are released
                    // But pointers may leak memory.
        if( b == 0 )
            throw 110;
        a++; // Just using a and b in here, could use them to do anything.
        b++;
        std::cout << "Code that executes when things are fine" << std::endl;
        
    } 
    catch(int ex)
    {
        std::cout << "Something went wrong. Exception thrown : " << ex <<  std::endl;
    }
}
```

#### Throwing a pointer

Throwing a pointer is a recipe for disaster, as by the time the catch block executes, the memory allocated and used in try block is pointing to invalid data. The program may seem to work sometimes but there are no guarantees you'll always get valid stuff if you dereference pointers allocated in the try block.

```c++
int main()
{
    int c{0};
    try
    {
        int var{55};
        int* int_ptr = &var;
        if(c == 0)
            throw int_ptr; // recipe for disaster
        std::cout << "Keeping doing some other things..." << std::endl;
    }
    catch(int* ex)
    {
        std::cout << "Something went wrong. Exception thrown : " <<*ex << std::endl;
    }
	std::cout << "END." << std::endl;
}
```

#### Potential memory leaks

The destructor for Item is never called when we're thrown out of the try block, and memory is leaked.

```c++
int main()
{
    int d{0};
    try
    {
        Item * item_ptr = new Item(); // Potential memory leaks
        std::shared_ptr<Item> item_ptr = std::make_shared<Item>(); // Use smart pointer insted
        if(d == 0)
            throw 0;
        std::cout << "Keeping doing some other things..." << std::endl;
    }
    catch(int ex)
    {
        std::cout << "Something went wrong. Exception thrown : "<< ex << std::endl;
    }
	std::cout << "END." << std::endl;

}
```

#### Thrown Exception

If you throw an exception and it's not handled anywhere in your code, you'll get a hard crash.

```c++
int main()
{
	throw 0;
	std::cout << "Doing something after we throw" << std::endl;
	
	std::cout << "END." << std::endl;
}
/* 
* Output: terminate called after throwing an instance of 'int'
* 		  Aborted
*/

```

![exception-termination](image/exception-termination.png)

#### Copyable Object

If copy constructor is either deleted, protected or private, the object can't be thrown as exception. You'll get a compiler error.

```c++
class MyException{
public : 
	MyException() = default;
	MyException(const MyException & ex) ; // copyable constructor  
        
     // compiler error
	/* MyException(const MyException & ex) = delete; 
	
	protected :  
	MyException(const MyException & ex)
    {
    
    }
    private :  
	MyException(const MyException & ex)
    {
    
    }*/
};
```

#### Implicit type conversion

Implicit type conversion doesn’t happen for primitive types.

```c++
#include <iostream>
using namespace std;
 
int main()
{
    try  {
       throw 'a';
    }
    catch (int x)  {
        cout << "Caught " << x;
    }
    catch (...)  {
        cout << "Default Exception\n";
    }
}

/* 
* Output: Default Exception
*/ 
```

#### Multiple catch blocks

Multiple catch blocks it's possible to have multiple catch blocks working with a single try block. The compiler will choose one that matches the thrown type. In this case it's going to discard the double one and see the int catch block and use it. 

```c++
#include <iostream>
 
int divide_impl( int num, int den){
 
        if( den == 0 )
            throw -1;
       return num/den;     
}
 
void divide(int a, int b){
    try
    {
        auto result = divide_impl(a,b);
        std::cout << "result : " << result ;
    }
    catch(double ex)
    {
        std::cout << "handling thrown exception : " << ex ;
    }
    catch(int ex){
        std::cout << "handling thrown exception : " << ex ;
    }
}
 
 
int main()
{
    divide(100,0);
    return 0;
}
```

#### Exceptions as class objects

We can use class objects as exception with inheritance hierarchies.

```c++
#include <iostream>
#include <string>
#include "exceptions.h"

class SomethingIsWrong
{
    public : 
        SomethingIsWrong(const std::string& s) : m_message(s){}
         ~SomethingIsWrong(){}
        std::string what()const{return m_message;}
    protected : 
        std::string m_message;
};
class Warning : public SomethingIsWrong
{
    public : 
    Warning(const std::string& s) : SomethingIsWrong(s){}
	std::string what()const{return m_message + " Yellow";}
};
class SmallError : public Warning
{
    public : 
    SmallError(const std::string& s) : Warning(s){}
	std::string what()const{return m_message + " Orange";}

};
class CriticalError : public SmallError
{
    public : 
    CriticalError(const std::string& s) : SmallError(s){}
	std::string what()const{return m_message + " Red";}

};

void do_something(size_t i)
{
      if(i == 2)
      {
          throw CriticalError("i is 2");
      }
      
      if(i == 3)
      {
          throw SmallError("i is 3");
      }
	  
      if(i == 4)
      {
          throw Warning("i is 4");
      }
      std::cout << "Doing something at iteration : " << i << std::endl;
}
int main()
{
   for(size_t i{0}; i < 5 ; ++i)
   {
      try
      {
          do_something(i);
      }
      catch(CriticalError& ex)
      {
          std::cout << "CriticalError Exception cought : " << ex.what() << std::endl;
      }
      catch(SmallError& ex)
      {
          std::cout << "SmallError Exception cought : " << ex.what() << std::endl;
      }
      catch(Warning& ex)
      {
          std::cout << "Warning Exception cought : " << ex.what() << std::endl;
      }  
      catch(SomethingIsWrong& ex)
      {
          std::cout << "SomethingIsWrong Exception cought : " << ex.what() << std::endl;
      }    
    }
}
```

> - The compiler processes catch blocks in order and it will pick the first matching one it hits. Exceptions are part of an inheritance hierarchy, the order of your catch blocks becomes important.
> - The catch blocks must organized from the most specific to the most general one.

#### Polymorphic Exceptions

We can use Polymorphic Exceptions in our inheritance hierarchies.

```c++
#include <iostream>
#include <string>
#include "exceptions.h"

class SomethingIsWrong
{
    public : 
        SomethingIsWrong(const std::string& s) : m_message(s){}
         virtual ~SomethingIsWrong(){}
        virtual std::string what()const{return m_message;}
    protected : 
        std::string m_message;
};
class Warning : public SomethingIsWrong
{
    public : 
    Warning(const std::string& s) : SomethingIsWrong(s){}
	virtual std::string what()const override{return m_message + " Yellow";}
};
class SmallError : public Warning
{
    public : 
    SmallError(const std::string& s) : Warning(s){}
	virtual std::string what()const override {return m_message + " Orange";}
};
class CriticalError : public SmallError
{
    public : 
    CriticalError(const std::string& s) : SmallError(s){}
	virtual std::string what()const override {return m_message + " Red";}
};

void do_something(size_t i)
{
      if(i == 2)
      {
          throw CriticalError("i is 2");
      }
      
      if(i == 3)
      {
          throw SmallError("i is 3");
      }
	  
      if(i == 4)
      {
          throw Warning("i is 4");
      }
      std::cout << "Doing something at iteration : " << i << std::endl;
}
int main()
{
   for(size_t i{0}; i < 5 ; ++i)
   {
      try
      {
          do_something(i);
      } 
      catch(SomethingIsWrong& ex)
      {
          std::cout << "SomethingIsWrong Exception cought : " << ex.what() << std::endl;
      }    
    }
}
```

#### Rethrown exceptions

In C++, try/catch blocks can be nested. Also, an exception can be re-thrown using “throw; “. 

```c++
#include <iostream>

int main()
{
	try {
		try 
        {
			throw 20;
		}
		catch (int n) 
        {
			std::cout << "Handle Partially ";
			throw; // Re-throwing an exception
		}
	}
	catch (int n) 
    {
		std::cout << "Handle remaining ";
	}
	return 0;
}
```

#### `noexcept` Specifier

By declaring a function, a method, or a lambda function as `noexcept`, we specify that these do not throw an exception, and if they throw, we do not care and let the program crash. `throw()` is equivalent to `noexcept(true)` but was deprecated with C++11 and will be removed with C++20. In contrast, `noexcept(false)` means that the function may throw an exception. The `noexcept` specification is part of the function type but can not be used for function overloading. 

> Exceptions can't be propagated out of a `noexcept` function by any means, if you do so the program will terminate, you can also see that the compiler gives you a warning about that.

#### Exceptions in Destructors

Destructor are by default `noexcept`, we do not expect exceptions from them, std::terminate is called in case of exception going out of destructor.

<img src="image/Exception-in-Destructour-1.png" alt="Exception-in-Destructour-1" style="zoom:80%;" /><img src="image/Exception-in-Destructour-2.png" alt="Exception-in-Destructour-2" style="zoom: 80%;" />

### Standard Exceptions

The C++ Standard library provides a base class specifically designed to declare objects to be thrown as exceptions. It is called `std::exception` and is defined in the `<exception>` header. This class has a virtual member function called `what` that returns a null-terminated character sequence (of type `char *`) and that can be overwritten in derived classes to contain some sort of description of the exception.

![cpp-exceptions](image/cpp-exceptions.jpg)

*****
## Polymorphism
## Type Casting
## Class Template
## Move Semantics
## Function Like Entities
## STL
### STL Containers
### STL Iterators
### STL Algorithm
## C++20 Ranges
## C++20 Coroutines
## C++20 Modules
