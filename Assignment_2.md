
## **Assignment No : 02**

## **Assignment Name : Constructor & its applications**

## **Program 01:**

---

## **Code:**
```C
#include <bits/stdc++.h>
using namespace std;

class Car {
    string name;
    string model;
    public:
        Car();
};

Car :: Car() {
    cout << "I am a default constructor";
}

int main()
{
    Car c1;
    return 0;
}

```



## **Output:** 
<p align="center">
<img width="345" height="143" alt="image" src="https://github.com/user-attachments/assets/8323e5e6-8fd4-47ee-851c-053b38e8ec98" />




## **Program 02:**

---

## **Code:**
```C
#include <bits/stdc++.h>
using namespace std;

class Car {
    string company;
    string model;
    public:
        Car();
        void setData(string c, string m);
        void display();
};

int main()
{
    Car c1;
    c1.setData("Audi", "2023");
    c1.display();
    return 0;
}

Car :: Car() {}

void Car :: setData(string c, string m) {
    company = c;
    model = m;
}

void Car :: display() {
    cout << "Company: " << company << endl;
    cout << "Model: " << model << endl;
} 

```



## **Output:** 
<p align="center">
<img width="218" height="69" alt="image" src="https://github.com/user-attachments/assets/c3eac5f5-5bde-4131-98c2-b1cc77c7b5df" />



## **Program 03:**

---

## **Code:**
```C
#include <bits/stdc++.h>
using namespace std;

class Car {
    string company;
    string model;
    public:
        Car();
        void display();
};

int main()
{
    Car c1, c2;
    c1.display();
    c2.display();
    return 0;
}

Car :: Car() {
    company = "BMW";
    model = "2025XS";
}

void Car :: display() {
    cout << "Company: " << company << endl;
    cout << "Model: " << model << endl;
} 

```



## **Output:** 
<p align="center">
<img width="232" height="118" alt="image" src="https://github.com/user-attachments/assets/41fed493-143a-4b83-87a5-2cd6a449c0f4" />




## **Program 04:**

---

## **Code:**
```C
#include <bits/stdc++.h>
using namespace std;

class Car {
    string company;
    string model;
    public:
        Car();
        Car(string s);
        void display();
};

int main()
{
    Car c1, c2("2025D");
    c1.display();
    c2.display();
    return 0;
}

Car :: Car() {
    company = "AUDI";
}

Car :: Car(string s) {
    model = s;
}

void Car :: display() {
    cout << "Company: " << company << endl;
    cout << "Model: " << model << endl;
} 
```



## **Output:** 
<p align="center">
<img width="329" height="126" alt="image" src="https://github.com/user-attachments/assets/9ed659b5-0e1b-4ede-a99b-aad8dbf6784a" />




## **Program 05:**

---

## **Code:**
```C
#include <bits/stdc++.h>
using namespace std;

class Car {
    string company;
    string model;
    public:
        Car();
        Car(string s, string s2);
        void setData(string c, string m);
        void display();
};

int main()
{
    Car c1, c2("BMW", "2025XS");
    c1.setData("Audi", "2025GS");
    c1.display();
    c2.display();
    return 0;
}

Car :: Car() {
    company = "BMW";
}

Car :: Car(string s, string s2) {
    company = s;
    model = s2;
}

void Car :: setData(string c, string m) {
    company = c;
    model = m;
}

void Car :: display() {
    cout << "Company: " << company << endl;
    cout << "Model: " << model << endl;
} 
```



## **Output:** 
<p align="center">
<img width="203" height="114" alt="image" src="https://github.com/user-attachments/assets/aeb0ea7f-c894-48b7-8aff-bd67b21ebc7e" />




## **Program 06:**

---

## **Code:**
```C
#include <bits/stdc++.h>
using namespace std;

class Animal {
    string color;
    float height;
    float weight;
    public:
        Animal(string a, float b, float c);
        Animal(const Animal &obj); 
        void display();
};

int main() {
    Animal dog1("red", 104.58, 49.69), cat("white", 36.4, 4.2);
    Animal dog2 = dog1;
    cat.display();
    dog2.display();
    return 0;
}

Animal :: Animal(string a, float b, float c) {
    cout << "parameterized constructor called" << endl;
    color = a;
    height = b;
    weight = c;
}

Animal :: Animal(const Animal &obj) {
    cout << "Copy constructor called" << endl;
    color = obj.color;
    height = obj.height;
    weight = obj.weight;
}

void Animal :: display(void) {
    cout << "Color: " << color << endl;
    cout << "Height: " << height << endl;
    cout << "Weight: " << weight << endl;
}


```



## **Output:** 
<p align="center">
<img width="323" height="208" alt="image" src="https://github.com/user-attachments/assets/73341db7-4e6e-4ce9-acb1-865edb13ed4d" />




