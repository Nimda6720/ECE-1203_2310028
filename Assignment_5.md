## **Assignment 05:**

<div align="justify">

</div>

## **Problem 1 : Square a Number Using a Class and Pass-by-Value in C++**

## **Code 1 :**
```C++
#include <bits/stdc++.h>
using namespace std;

class Squre {
    int n;
public:
    Squre(int n) : n(n) {}
    int get_n() { return n; }
};

int Sq(Squre n);

int main() {
    int n;
    cout << "Enter a number: ";
    cin >> n;
    Squre s1(n);
    cout << Sq(s1) << endl;
    return 0;
}

int Sq(Squre n) {
    return n.get_n()*n.get_n();
}


```

## **Output :**
<p align="center">

  <img width="197" height="63" alt="image" src="https://github.com/user-attachments/assets/8374d24d-2d50-4107-83f6-c1b60d9f5597" />


</p>

## **Discussion:**
In this program, the function Sq() is written outside the class Squre and is not a friend of the class. So, it can’t directly use the private variable n. But the class has a public function get_n() that gives the value of n. When Sq() is called, it gets a copy of the object, not the original one. This means any changes inside the function don’t change the original object. Inside Sq(), the function uses get_n() to get the value of n and then returns its square. Since Sq() is not part of the class, it can only use the public functions to get information. This shows how private data is kept safe and only accessed through public functions.

## **Problem 2 : Demonstrating Pass-by-Value Using a Class in C++**

## **Code 2 :**
```C++
#include <bits/stdc++.h>
using namespace std;

class Squre {
    int n;
public:
    Squre(int n) : n(n) {}
    void set_n(int n) { this->n = n; }
    int get_n() { return n; }
};

void Sq(Squre n);

int main() {
    int n;
    cout << "Enter a number: ";
    cin >> n;
    Squre s1(n);
    Sq(s1);
    cout << "value of n inside the main function: " << s1.get_n() << endl;
    return 0;
}

void Sq(Squre n) {
    n.set_n(n.get_n() * n.get_n());
    cout << "value of n inside the Sq function: " << n.get_n() << endl;
}

```

## **Output :**
<p align="center">
  
<img width="409" height="97" alt="image" src="https://github.com/user-attachments/assets/956962b8-9134-457e-87bb-eccd04f944ab" />


</p>

## **Discussion:**
In main, we make object s1. Then we pass it to Sq(Squre n) by value. That means a copy of s1 is made inside the function. So when we change n inside Sq, we only change the copy, not the original. That’s why n is changed inside the function, but in main the original s1 stays same.

## **Problem 3 : Modifying Object Data Using Pointers in C++**

## **Code 3 :**
```C++
#include <bits/stdc++.h>
using namespace std;

class Squre {
    int n;
public:
    Squre(int n) : n(n) {}
    void set_n(int n) { this->n = n; }
    int get_n() { return n; }
};

void Sq(Squre &n);

int main() {
    int n;
    cout << "Enter a number: ";
    cin >> n;
    Squre s1(n);
    Sq(s1);
    cout << "value of n inside the main function: " << s1.get_n() << endl;
    return 0;
}

void Sq(Squre &n) {
    n.set_n(n.get_n() * n.get_n());
    cout << "value of n inside the Sq function: " << n.get_n() << endl;
}


```

## **Output :**
<p align="center">
  
<img width="365" height="89" alt="image" src="https://github.com/user-attachments/assets/afbf7cc4-12cf-49aa-af26-103f591a6768" />




</p>

## **Discussion:**
In main, we make object s1. Then we pass it to Sq(Squre &n) by reference. That means the original object s1 is passed inside the function. So when we change n inside Sq, we change the original value of n. That’s why n is changed inside both the function and in main.


## **Problem 4 : Creating and Using Objects with Constructor and Destructor in C++**

## **Code 4 :**
```C++
#include <bits/stdc++.h>
using namespace std;

class Squre {
    int n;
public:
    Squre(int n) {
        this->n = n;
        cout << "Constructor is called" << endl;
    }
    ~Squre() {
        cout << "Deconstructor is called" << endl;
    }
    int get_n() { return n; }
};

int Sq(Squre n);

int main() {
    int n;
    cout << "Enter a number: ";
    cin >> n;
    Squre s1(n);
    cout << Sq(s1) << endl;
    return 0;
}

int Sq(Squre n) {
    return n.get_n()*n.get_n();
}

```

## **Output :**
<p align="center">

<img width="235" height="130" alt="image" src="https://github.com/user-attachments/assets/a2c463a6-4f1d-430b-acb5-6f3696c056fb" />



</p>

## **Discussion:**
In this program, we made object s1 in main, so constructor is called 1 time. Then we sent s1 to Sq(Squre n) by value, not by reference. So it makes a copy of s1 inside that function. That mean constructor is not called again because default copy constructor is used, but when the function ended, that copied object get destroyed, so destructor is called once. Then when main function ended, original s1 also got destroyed resulting another destructor call.
