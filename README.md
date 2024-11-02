#include <iostream>
using namespace std;

class Person{
    public:
  string *nameptr;
  int *ageptr;
  
  Person(string name, int age){
      nameptr = new string;
      *nameptr = name;
      ageptr = new int;
      *ageptr = age;
  }
  
  void getInfo(){
      cout<<"Name : "<<*nameptr<<endl;
      cout<<"Age : "<<*ageptr<<" Years "<<endl;
      
  }
};

class Employee : public Person{
    public:
  double *salaryptr;
  
  Employee(string name, int age, double salary) : Person(name, age){
      salaryptr = new double;
      *salaryptr = salary;
  }
  
  void getInfo(){
      cout<<"Name : "<<*nameptr<<endl;
      cout<<"Age : "<<*ageptr<<" Years "<<endl;
      cout<<"Salary : Rs."<<*salaryptr<<endl;
  }
};

class Manager : public Employee{
    public:
      string *departmentptr;
      
      Manager(string name, int age, double salary, string department) : Employee(name, age, salary){
          departmentptr = new string;
          *departmentptr = department;
      }
      
      void getInfo(){
      cout<<"Name : "<<*nameptr<<endl;
      cout<<"Age : "<<*ageptr<<" Years "<<endl;
      cout<<"Salary : Rs."<<*salaryptr<<endl;
      cout<<"Department : "<<*departmentptr<<endl;
      }
};

int main()
{   
    Person p1("Shaheer Khalid",21);
    p1.getInfo();
    Employee e1("Shahher Bandar",21,500000);
    e1.getInfo();
    Manager m1("Shaheer Khalid",21,500000,"Software Engineering");
    m1.getInfo();

    return 0;
}
