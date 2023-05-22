# C++ Interview Questions And Answers

Most targeted up-to-date C++ interview questions and answers list

# Table of Contents

1. [What is the difference between `struct` and `class` in C++?](#1-what-is-the-difference-between-struct-and-class-in-c)
2. [What is the difference between pass by value and pass by reference?](#2-what-is-the-difference-between-pass-by-value-and-pass-by-reference)
3. [What is a constructor?](#3-what-is-a-constructor)
4. [What is the difference between `new` and `malloc`?](#4-what-is-the-difference-between-new-and-malloc)
5. [What is function overloading?](#5-what-is-function-overloading)
6. [What is the difference between `delete` and `delete[]`?](#6-what-is-the-difference-between-delete-and-delete)
7. [What are virtual functions?](#7-what-are-virtual-functions)
8. [What is the difference between function overloading and function overriding?](#8-what-is-the-difference-between-function-overloading-and-function-overriding)
9. [What is a template in C++?](#9-what-is-a-template-in-c)
10. [What is a destructor?](#10-what-is-a-destructor)
11. [What is the difference between a shallow copy and a deep copy?](#11-what-is-the-difference-between-a-shallow-copy-and-a-deep-copy)
12. [What is the `const` keyword in C++?](#12-what-is-the-const-keyword-in-c)


## 1. What is the difference between struct and class in C++?

In C++, the only difference between a struct and a class is that members and base classes are public by default in a struct, while they are private by default in a class.

Example:

```cpp
struct MyStruct {
    int publicVar;
};

class MyClass {
    int privateVar;
};
```

## 2. What is the difference between pass by value and pass by reference?

Passing by value creates a copy of the argument, while passing by reference allows the function to directly modify the original argument.
Example of pass by value:

```cpp
void setValue(int value) {
    value = 10;
}

int main() {
    int num = 5;
    setValue(num);
    // num is still 5
    return 0;
}
```

Example of pass by reference:

```cpp
void setValue(int& value) {
    value = 10;
}

int main() {
    int num = 5;
    setValue(num);
    // num is now 10
    return 0;
}
```

## 3. What is a constructor?

A constructor is a special member function of a class that is automatically called when an object of the class is created. It is used to initialize the object's data members.

Example:

```cpp
class MyClass {
public:
    int value;
    
    MyClass() {
        value = 0; // Initialization
    }
};

int main() {
    MyClass obj;
    // obj.value is initialized to 0
    return 0;
}
```

## 4. What is the difference between new and malloc?

new is an operator in C++ used for dynamic memory allocation, while malloc is a function in C used for the same purpose. The major difference is that new calls the constructor of the object being allocated memory, while malloc does not.

Example of new:

```cpp
int* num = new int;
```

Example of malloc:

```cpp
int* num = (int*)malloc(sizeof(int));
```

## 5. What is function overloading?

Function overloading is a feature in C++ that allows multiple functions with the same name but different parameter lists. The compiler determines which function to call based on the arguments provided.

Example:

```cpp
void print(int num) {
    cout << "Integer: " << num << endl;
}

void print(float num) {
    cout << "Float: " << num << endl;
}

int main() {
    print(10);
    print(3.14);
    return 0;
}
```

## 6. What is the difference between delete and delete[]?

delete is used to deallocate memory allocated using new, while delete[] is used to deallocate memory allocated using new[]. It is important to match the allocation and deallocation methods correctly.

Example:

```cpp
int* num = new int;
delete num;

int* arr = new int[10];
delete[] arr;
```

## 7. What are virtual functions?

Virtual functions are functions declared in a base class and overridden in derived classes. They allow polymorphic behavior, where a function call is resolved at runtime based on the actual object type.

Example:

```cpp
class Rectangle : public Shape {
public:
    void draw() override {
        cout << "Drawing a rectangle." << endl;
    }
};

int main() {
    Shape* shape = new Circle();
    shape->draw(); // Output: "Drawing a circle."

    shape = new Rectangle();
    shape->draw(); // Output: "Drawing a rectangle."

    delete shape;
    return 0;
}
```

## 8. What is the difference between function overloading and function overriding?

Function overloading is having multiple functions with the same name but different parameter lists within the same class, whereas function overriding is providing a different implementation of a function in a derived class, which is already defined in the base class.

## 9. What is a template in C++?

Templates are used in C++ to create generic functions or classes that can work with different data types without the need for code duplication. They allow writing code that is independent of the specific data types used.

Example of a template function:

```cpp
template <typename T>
T getMax(T a, T b) {
    return (a > b) ? a : b;
}

int main() {
    int maxInt = getMax(5, 10);
    double maxDouble = getMax(3.14, 2.71);
    return 0;
}
```

## 10. What is a destructor?
  
A destructor is a special member function of a class that is called when an object is destroyed or goes out of scope. It is used to perform any necessary cleanup or deallocation of resources.
Example:

```cpp
class MyClass {
public:
    ~MyClass() {
        // Destructor code here
    }
};

int main() {
    MyClass obj;
    // Object obj will be destroyed and destructor will be called when it goes out of scope
    return 0;
}
```
## 11. What is the difference between a shallow copy and a deep copy?

A shallow copy copies the memory address of an object, resulting in two objects pointing to the same memory location. A deep copy creates a new object and copies the values of the members to the newly created object.

Example of a shallow copy:

```cpp
class MyClass {
public:
    int* data;

    MyClass(const MyClass& other) {
        data = other.data; // Shallow copy
    }
};
```

Example of a deep copy:

```cpp
class MyClass {
public:
    int* data;

    MyClass(const MyClass& other) {
        data = new int(*other.data); // Deep copy
    }
};
```

## 12. What is the const keyword in C++?

The const keyword in C++ is used to declare that a variable or a function does not modify the value it references or the object it operates on. It provides immutability and allows the compiler to perform optimizations.

Example of a const variable:

```cpp
const int MAX_VALUE = 100;
```

Example of a const function:

```cpp
int getValue() const {
    return value;
}
```

## What's more?
<a href="https://interviewplus.ai/developers-and-programmers/c-plus-plus/questions">A comprehensive list of questions and answers</a>

## Contributing
We welcome contributions from our users to help make this resource as comprehensive and useful as possible. If you have been recently interviewed and encountered a question that is not currently covered on our website, feel free to suggest it as a new question. Your contributions will be added to our platform, and we will make sure to credit you for your contributions. We appreciate your help in making our platform a valuable tool for all job seekers.

## License
MIT License
