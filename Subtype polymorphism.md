---
tags:
  - CS202
---
Subtype polymorphism is a class of [[Polymorphism]] that enables a program to use a subclass where a superclass is expected. This creates a dynamic method binding between two classes.

```cpp
Ex.

#ifndef EMPLOYEE_H
#define EMPLOYEE_H
class Employee: public Person
{
	private:
		int ID;
	public:
		Employee();
		Employee(int);
		Employee(const Employee&);
		int getID() const;
		void setID(const int);
}
#endif

#include "Employee.h"
Employee::Employee()
{
	employee_id = 0;
}

Employee::Employee(int ID, std::string first, std::string last) : Person(first, last)
{
	this->ID = ID;
}

Employee::Employee(const Employee& c) : Person(c)
{
	ID = c.ID;
}

int Employee::getID() const
{
	return ID;
}
	
void Employee::setID(int ID){
	
	this->ID = ID;
}
```
