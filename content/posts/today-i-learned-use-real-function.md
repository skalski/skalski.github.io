---
title: "Today I Learned Use .thenCallRealMethod()"
date: 2021-04-26T13:49:33+02:00
tldr: "Mockito got a killerfeature: .thenCallRealMethod();"
draft: false
tags: [java]
---

I was dying to got some stuff working.
I was mocking a method, but then there was one Method, where i needed the real output so hard.
<!--more-->


But, when a method is a mock, everything is a mock.
Example of the problem:

```java
@GetterSetter
class SomeObject(){

	public int a;
	public int b;

	public int function sum(){

		return a + b;
	}
}
```

Now you can use it and mock it. But, what happens, when you just want to mock the Setter but will assert that `sum()` does everything as it should?

```java
	when(SomeObject).getA().thenReturn(1);
	when(SomeObject).getB().thenReturn(2);

	assertEqual(someObject.sum(), 3);
```

This will die in a NPE at least.
Now I learned something cool...


```java
	when(SomeObject).getA().thenReturn(1);
	when(SomeObject).getB().thenReturn(2);
	when(SomeObject).sum().thenCallRealMethod();
	assertEqual(someObject.sum(), 3);
```
This will do the Trick... and it saves hours on Google.


