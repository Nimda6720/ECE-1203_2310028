## **Assignment 01:**
## An assignment on C++ Implementation of Parent, Child, and Grandchild Classes Using Inheritance.

<div align="justify">

Define three classes: A, B, and C, where C is the child class of B, B is the child class of A. Each class should have private, protected, and public members. Then, create objects of class C, B, and A and observe which members are accessible through each object. Display the output. If any members are not accessible or cause errors, include a screenshot of the error message as part of your submission.

</div>

## **Code :**
```C++
#include <bits/stdc++.h>
using namespace std;

class A {
        int a_pri = 0;
    protected:
        int a_pro = 1;
    public:
        int a_pub = 2;
    };
    class B : public A {
        int b_pri = 3;
    protected:
        int b_pro = 4;
    public:
        int b_pub = 5;
    };
    class C : public B {
        int c_pri = 6;
    protected:
        int c_pro = 7;
    public:
        int c_pub = 8;
    };

int main()
{
    A objA;
    B objB;
    C objC;
    cout << "objA: " << endl;
    cout << objA.a_pub << endl;
    cout << "objB: " << endl;
    cout << objB.a_pub << " " << objB.b_pub << endl;
    cout << "objC: " << endl;
    cout << objC.a_pub << " " << objC.b_pub << " " << objC.c_pub << endl;
    return 0;
}
```

## **Output :**
<p align="center">
    <img width="175" height="147" alt="image" src="https://github.com/user-attachments/assets/cbaa2a21-b9dd-41f4-95bc-1704a82db582" />
<br>
   <img width="856" height="832" alt="image" src="https://github.com/user-attachments/assets/7f015869-bccf-4beb-ae50-d019acf165d5" />

</br>
    
</p>
