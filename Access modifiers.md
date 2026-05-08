---
tags:
  - CS202
---
[[Access modifiers are an inherent part of object-oriented programming]]. Since they define how attributes and methods can be accessed, [[Access modifiers are critical to encapsulation and data hiding]]. There are three base-class access specifiers:

- **Private** (members cannot be accessed from outside the class):

```cpp
class A
{
	private: // all declarations after this point are private
};
```

- **Protected** (members cannot be accessed from outside the class but can be accessed from inherited classes):

```cpp
class B
{
	protected: // all declarations after this point are protected
};
```

- **Public** (members can be accessed from outside the class):

```cpp
class C
{
	public: // all declarations after this point are public
};
```