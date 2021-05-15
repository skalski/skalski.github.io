---
title: "Why Is Go the Language for the Next Decade"
date: 2021-05-15T13:01:28+02:00
tldr: "Go is Love - FULLSTOP"
draft: false
tags: [go,golang]
---
RUST is currently traded as the new replacement for C, C++ and Java. But there are better alternatives. Go (Golang) has turned out to be the better choice for me.
<!--more-->
### Why is that?
Go is actually comparable to RUST. Both offer a variety of features that at first glance seem very equivalent. However, Golang is a better choice, as RUST's syntax is too similar to C and thus takes over its inherent complexity.
Go is different in this respect. It offers the deep level of possibilities, but does not have the "pointer dramaturgy" promoted by RUST. Thus one is fast on the C-Level on the way has however a better entrance.

I myself started with Go only a few months ago. Nevertheless I was able to migrate a lot of projects completely. Partly in record time.
The advantages are obvious.

The code base is much smaller than for example JAVA or even C#. Also the distribution of binaries is much easier.
On the other hand you can work quite close to the system without having to worry about the architecture. A binary that works on Windows will also work on an IOT device from the same code base without changes.
Including file handling, memory handling and error handling.

### Let's make an example.
In java you have to do certain thinks to create an Object.
We habe to add a POJO, with getter, setter and a lot of stuff. Or you rather add Lombok.
At last you have 
* a Controller
* an Object, with Getter, Setter and Builder
* and if everything getting "out of hand" a fabric...

Well done! Not!

In Go you have just your go File where you use your stuff and an `struct`.
A `struct` represent the whole object.

```go
package main

import{
	"fmt"
}

type User struct {
	Name		string
	Addresses	[]Addresses
}

type Addresses struct {
	Street	string
	Number	int16
	ZIP	string
	City	string
}

func main(){
	//here we can use the struct
}
```

As you can see, it is complete low-level code, but come powerful with all features you would miss.
One of the major points at Go is, that the most needed things are already there. Netherless if you want to write an API, or a Website, complex Image manipulations or an OS at last.

Another point is that the second-system effect is established with Go even with new projects. This is due to the simplicity of the language. The effect describes that one writes an already running software faster and more efficiently in the second attempt. As soon as one works with C or Go, one pays attention by default to sparseness of the code base.
 
If I think of my software DocDog, it shows very well that this project would have considerably more complexity in Java or C#. But just the features, which seem to be missing at the beginning (OOP, classes) quickly move into the background. You write software that does a task as efficiently as possible.

And I think thats beautiful :-)

