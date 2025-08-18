## **Assignment No : 03**

## **Assignment Name : Friend Function, Friend Class, Constructors & Inheritance**

## **Program 01: How Friend function work**

---

## **Code:**
```C
#include <bits/stdc++.h>
using namespace std;

class Rectangle {
    int height;
protected:
    int width;
public:
    Rectangle(int h, int w);
    friend int area(Rectangle &r);
};

int main() {
    int h, w;
    cout << "Enter height and width of the rectangle: ";
    cin >> h >> w;
    Rectangle obj(h, w);
    cout << "Area of the rectangle: " << area(obj);
    return 0;
}

Rectangle :: Rectangle(int h, int w) {
    height = h;
    width = w;
}

int area(Rectangle &r) {
    return r.height * r.width;
}

```



## **Output:** 
<p align="center">
<img width="439" height="86" alt="image" src="https://github.com/user-attachments/assets/828db1c0-130a-4a2f-ab82-31ddb419c49b" />



## **Discussion:**
The area() function is a friend function of the Rectangle class. So it can use private and protected parts of the class. That’s why it can use length (private) and width (protected). The function is defined outside the class, but it is declaired inside the class. It is not a member of the class. So we don’t call it with an object like other functions. We send the object to it as a parameter, and then it can read the data inside.


## **Program 02: How friend classs work**

---

## **Code:**
```C
#include <bits/stdc++.h>
using namespace std;

class Rectangle {
    int height;
protected:
    int width;
public:
    Rectangle(int h, int w);
    friend class Area;
};

class Area {
    int circumference;
protected:
    int center;
public:
    int calArea(Rectangle &r);
};

int main()
{
    int h, w;
    cout << "Enter height and width of the rectangle: ";
    cin >> h >> w;
    Rectangle obj1(h, w);
    Area obj2;
    cout << "Area of the rectangle: " << obj2.calArea(obj1);
    return 0;
}

Rectangle :: Rectangle(int h, int w) {
    height = h;
    width = w;
}

int Area :: calArea(Rectangle &r) {
    return r.height*r.width;
}

```



## **Output:** 
<p align="center">
<img width="412" height="60" alt="image" src="https://github.com/user-attachments/assets/ef671933-d6a1-44f2-b341-5b5e80c38457" />




## **Discussion:**
Area class is friend of Rectangle class. That means Area can access private (height) and protected (width) members of Rectangle. Normally other class can't see those data, but friend class can. So inside calArea() function, it can use r.height and r.width without any problem. But Rectangle class is not a friend of Area class. So Rectangle can not access the private and protected members of Area class.



## **Program 03: How default constructor in derived class work**

---

## **Code:**

```C
#include <bits/stdc++.h>
using namespace std;

class Student{
protected:
    string name;
public:
    Student();
};

class RUET_ECE : public Student{
    int roll;
public:
    void setRoll();
    void print();
};

int main() {
    RUET_ECE stu1;
    stu1.setRoll();
    stu1.print();
    return 0;
}

Student :: Student() {
    cout << "Enter student name: ";
    getline(cin, name); 
}

void RUET_ECE :: setRoll() {
    cout << "Enter student roll: ";
    cin >> roll;
}

void RUET_ECE :: print() {
    cout << "Student name: " << name << endl;
    cout << "Student roll: " << roll << endl;
}

```



## **Output:** 
<p align="center">
<img width="325" height="104" alt="image" src="https://github.com/user-attachments/assets/2c7f410c-599e-4763-ae07-7b04bde407f3" />



## **Discussion:**
RUET_ECE is the derived class of Student. Hence, when an object of RUET_ECE is created, at first the default constructor of Student is called to initialize the protected data name. Then setRoll() method is used to initialize student roll. The print() mrthod is used to print out the data on screen. Default constructor of class RUET_ECE can also be used to initialize student roll. In that case when an object is created of RUET_ECE, at first the default constructor of class Student then the default constructor of class RUET_ECE would get called automatically. 



## **Program 04: How parameterized constructor in derived class work**

---

## **Code:**
```C
#include <bits/stdc++.h>
using namespace std;

class Student{
protected:
    string name;
public:
    Student(string name) : name(name) {};
};

class RUET_ECE : public Student{
    int roll;
public:
    RUET_ECE(string name, int roll) : Student(name), roll(roll) {};
    void print();
};

int main() {
    string name;
    int roll;
    cout << "Enter student name and roll: " << endl;
    getline(cin, name);
    cin >> roll;
    RUET_ECE stu1(name, roll);
    stu1.print();
    return 0;
}

void RUET_ECE :: print() {
    cout << "Student name: " << name << endl;
    cout << "Student roll: " << roll << endl;
}


```



## **Output:** 
<p align="center">
<img width="315" height="127" alt="image" src="https://github.com/user-attachments/assets/02c43d36-824b-444e-8c5d-be1a6f0a8de0" />



## **Discussion:**
RUET_ECE is the derived class of Student. As Student has constructor with arguments, class RUET_ECE's constructor need to pass arguments to class Student's constructor when an object of class RUET_ECE is created. In case of parameterized constructor the constructor of base class (Student) does not get called automatically with its required arguments when an object is created of derived class (RUET_ECE). Hence, during the definition of parameterized constructor of derived class we need to explicitly call base class parameterized constructor & pass the required arguments.



## **Program 05: How constructor in multiple inheritance work**

---

## **Code:**
```C
#include <bits/stdc++.h>
using namespace std;

class Parent1{
protected:
    int x;
public:
    Parent1();
};

class Parent2{
protected:
    int y;
public:
    Parent2();
};

class Child : public Parent1, public Parent2 {
protected:
    int z;
public:
    Child();
    void print();
};

int main() {
    Child c1;
    c1.print();
    return 0;
}

Parent1 :: Parent1() {
    cout << "Enter the value of x: ";
    cin >> x;
}

Parent2 :: Parent2() {
    cout << "Enter the value of y: ";
    cin >> y;
}

Child :: Child() {
    cout << "Enter the value of z: ";
    cin >> z;
}

void Child :: print() {
    cout << "The value of x, y, z are: " << x << " " << y << " " << z;
}


```



## **Output:** 
<p align="center">
<img width="382" height="115" alt="image" src="https://github.com/user-attachments/assets/e8b50717-83c9-4b9f-8dad-5b0da0a89967" />



## **Discussion:**
class Child is derived class of Parent1 & Parent2. When an object of class Child is created, at first constructor of class Parent1 then constructor of class Parent2 & at last constructor of class Child will be called as Parent1 & Parent2 are parent classes of class Child. Parent1's constructor will be called at first as Parent1 is listed first in the definition of class Child. After that Parent2's constructor will be called as Parent2 is listed second. In the definition of constructor of class Child


## **Program 06: How constructor in multi-level inheritance work**

---

## **Code:**
```C
#include <bits/stdc++.h>
using namespace std;

class Parent{
    int a;
public:
    int b;
    void Print();
    Parent(int a, int b, int c) : a(a), b(b), c(c) {}
protected:
    int c;
};

class Child : protected Parent{
    int d = 4;
public:
    int e = 5;
    void Display();
    Child(int a, int b, int c, int d, int e, int f) : Parent(a, b, c), d(d), e(e), f(f) {}
protected:
    int f = 6;
};

class GrandChild : public Child {
    int g = 7;
public:
    int h = 8;
    void Show();
    GrandChild(int a, int b, int c, int d, int e, int f, int g, int h, int i) : Child(a, b, c, d, e, f), g(g), h(h), i(i) {}
protected:
    int i = 9;
};

int main() {
    Parent p1(1, 2, 3);
    Child c1(4, 5, 6, 7, 8, 9);
    GrandChild g1(10, 11, 12, 13, 14, 15, 16, 17, 18);
    p1.Print();
    c1.Display();
    g1.Show();
    return 0;
}

void Parent :: Print() {
    cout << "Accessible by Parent class: ";
    cout << a << ' ' << b << ' ' << c << endl;
}

void Child :: Display() {
    cout << "Accessiable by Child class: ";
    cout << b << ' ' << c << ' ' << d << ' ' << e << ' ' << f << endl;
}

void GrandChild :: Show() {
    cout << "Accessiable by GrandChild class: ";
    cout << b << ' ' << c  << ' ' << e << ' ' << f << ' ' << g << ' ' << h << ' ' << i << endl;
}

```



## **Output:** 
<p align="center">
<img width="517" height="93" alt="image" src="https://github.com/user-attachments/assets/2d96e47e-988a-488e-8c4e-7029c7333cbb" />



## **Discussion:**
Here GrandChild class is derived from Child class, and Child class is derived from Parent class. When GrandChild object is made, first Parent class constructor called, then Child class constructor is called, and at last GrandChild class constructor is called. All constructors use initializer list to pass values. Here, Parent class has private variable 'a' which can be accessed only by Parent class, public variable 'b' which is accessible by everyone, and protected variable 'c' which is accessible by Child and GrandChild classes. Child class has private variable 'd' which can be accessed only by Child class, public variable 'e' which is accessible by everyone, and protected variable 'f' which is accessible by GrandChild class. GrandChild class has private variable 'g' which can be accessed only by GrandChild class, public variable 'h' which is accessible by everyone, and protected variable 'i' which is accessible only by GrandChild class.

## **Program 07: How parameterized constructor in multiple inheritance work**

---

## **Code:**
```C
#include <bits/stdc++.h>
using namespace std;

class Parent1{
protected:
    int x;
public:
    Parent1(int x) : x(x) {};
};

class Parent2{
protected:
    int y;
public:
    Parent2(int y) : y(y) {};
};

class Child : public Parent1, public Parent2 {
protected:
    int z;
public:
    Child(int x, int y, int z) : Parent1(x), Parent2(y), z(z) {};
    void print();
};

int main() {
    int x, y, z;
    cout << "Enter the value of x, y, z: ";
    cin >> x >> y >> z;
    Child c1(x, y, z);
    c1.print();
    return 0;
}

void Child :: print() {
    cout << "The value of x, y, z are: " << x << " " << y << " " << z;
}



```



## **Output:** 
<p align="center">
<img width="327" height="108" alt="image" src="https://github.com/user-attachments/assets/03a98e04-27ed-45fe-8621-f5c48ad41f81" />



## **Discussion:**
Child is derived class of class Parent1 & Parent2. When Child's object is created, base class (Parent1 & Parent2) constructors are called according to the sequence of base class listing in the derived class's (Child) inheritance declaration. Here, at first Parent1's parameterized constructor and then Parent2's parameterized constructor will be called when an object of Child (c1) is created. At last, the derived class Child's constructor will be called. As Child is derived class of Parent1 & Parent2, in the parameterized constructor of Child, the required arguments for base class constructors are passed using the special syntax; then additional initialization is performed for class Child's attributes.

