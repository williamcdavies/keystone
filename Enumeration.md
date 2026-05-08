---
tags:
  - CS202
---
An enumeration is a user-defined data type that consists of integral constants. To define an enumeration, keyword $\text{ enum }$ is used.

Since [[Integers take up less system memory than other data types]], enumeration is often used to limit the amount of system memory a program requires. 

 ```cpp
enum direction // implicit enumeration
{
	north, 
	south, 
	east, 
	west
}; // defualts enumeration to equal index
```

 ```cpp
enum direction // explicit enumeration
{
	north = 2, 
	south = 4, 
	east = 6, 
	west = 8
};
```
