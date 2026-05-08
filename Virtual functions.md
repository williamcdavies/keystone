---
tags:
  - CS202
aliases:
  - Virtual function
---
Virtual functions are superclass member functions expected to be overridden by subclass member functions of the same name. Virtual functions are declared with the keyword $\text{ virtual }$.

```cpp
Ex.

#ifndef SHAPE_H
#define SHAPE_H
class Shape
{
	protected:
		float perimeter;
		float area;
	public:
		Shape();
		Shape(float, float);
		Shape(const Shape&);
		getPerimeter() const;
		virtual void calculatePerimeter();
		get_area() const;
		virtual void calculateArea();
};
#endif
```