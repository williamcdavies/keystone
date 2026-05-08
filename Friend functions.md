---
tags:
  - CS202
---
Friend functions are functions of a given class defined by the keyword $\text{ friend }$ that can access private and protected data of that class. 

```cpp
Ex.

#ifndef DISTANCE_H
#define DISTANCE_H
class Distance
{
	private:
		int distance = 0;
		friend void addFive();
	public:
		Distance();
		Distance(int);
		Distance(const Distance&);
		
		// getters and setters not included for demonstration
};
#endif

#include "Distance.h"
void addFive()
{
	distance+=5;
}
```

## Overloading Insertion & Extraction Operators 
When overloading insertion or extraction operators, friend functions can be used to access members of a class that would be otherwise inaccessible.

### Extraction Overloads

```cpp
friend ostream& operator << (ostream&, const Address&);

ostream& operator << (ostream& out, const Address& address)
{
	out << address.attribute;
	
	return out;
} 
```

### Insertion Overloads

```cpp
friend istream& operator >> (istream&, const Address&);

istream& operator >> (ostream& in, const Address& address)
{
	in >> address.attribute;
	
	return in;
} 
````

```cpp
Ex.

#ifndef DATE_H
#define DATE_H
class Date
{
	private:
		int day, month, year;
		friend ostream& operator << (ostream&, const Date&);
	public:
		Date();
		Date(int, int, int);
		Date(const Date&);	
};
#endif

#include "Date.h"
ostream& operator << (ostream& out, const Date& d){
	out << d.month << "/" << d.day << "/" << d.year << endl;
	
	return out;
}

#include "Date.h"
int main()
{
	Date today(24, 4, 2023);
	std::cout << today; // this is our goal; does not work by default
}
```

```cpp
Ex.

#ifndef FRACTION_H
#define FRACTION_H
class Fraction{
	private:
		int numerator, denominator;
		friend ostream& operator << (ostream&, const Fraction&);
		friend istream& operator << (istream&, const Fraction&);
	public:
		Fraction();
		Fraction(int, int);
		Fraction(const Fraction&);
};
#endif

#include "Fraction.h"
ostream& operator << (ostream& out, const Fraction& f)
{
	out << f.numerator << "/" << f.denominator << endl;
	
	return out;
}

istream& operator >> (istream& in, const Fraction& f)
{
	int numerator, denominator;
	in >> numerator;
	in >> denominator;
	f.numerator = numerator;
	f.denominator = denominator;
	
	return in;
}
```