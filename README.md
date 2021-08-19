# Ambiguity-in-Inheritance

#include <iostream>
using namespace std;

class base1{
     public:
     void greet(){
         cout<<"How are you?"<<endl;
     }

};
class base2{
     public:
     void greet(){
         cout<<"kia hal hai?"<<endl;
     }

};
class derived : public base1, public base2 {
int a;
public:
      void greet(){
          base1::greet();
      }

};
// Ambuity here is that if we call greet() function from derived class (which has the 2 identical greet() function berived from base1 and base2) then what will be invoked
// This can solved wen we declare which greet() is to be called from derived.
class B{
public:
 void say(){
     cout<<"Hello World"<<endl;
 }
};
class D: public B
{
    int a;
//     public:
//    void say(){
//        cout<<"Hello Beautifull world"<<endl;
//    }
};

int main(){
    /* Ambiguity1 
    base1 obj1;
    base2 obj2;
    obj1.greet();
    obj2.greet();
    derived obj3;
    obj3.greet();  */

    //   Ambiguity 2  When we call function(same name in base and derived) from derived class and there is no as function in derived it will call the function from it's class
        B obj3;
        obj3.say();
        D obj4;
        obj4.say();
   
    return 0;
}
