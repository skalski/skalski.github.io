---
title: "Exception Handling With Go"
date: 2021-04-27T07:16:55+02:00
tldr: "You can add defer RecoverPanic() to catch wild exceptions"
draft: false
tags: [go]
---
Go is somewhat different in terms of exception handling than Java or Python, for example.
This can sometimes be a bit special, if you also want to find errors that are not caught by the method.
<!--more-->

So there is no try/catch statement in Go.
But with a little trick, you can catch such errors with `defer`.

The command `defer` tells a method what to do at the end of its runtime.

Example:
```go

func main() {
	defer fmt.Println("World!")
	fmt.Print("Hello, ")
}

```
This will output: `Hello, World!`

From the first glance, when you get in touch with, you mostly got no idea, what to do with it?
Why should such a feature exists?

But in the end, this feature can save your ass. Because, when a method fails, it will fail at the line, where it was writen.
Everything else below it, will not executed.
But `defer` is special. From the moment the line was touched by the excecution, it will run in the end of the method. It does no matter, what the outcome
of the whole Method was.

You can make use of this behavior for our exception handling:

```go
func main() {
	defer RecoverPanic("parse panic") // or whatever you want to catch
	// do whatever to do now...
}

func RecoverPanic(msg string) {
	if r := recover(); r != nil {
		if msg != "parse panic" {
			fmt.Println("There was a error while parsing!")
		} else {
			//everthing else what can happen
			fmt.Println("An unexpected Error was catched!")
		}
	}
}

```

Now the program will no longer say goodbye with a huge stacktrace, but will output a factual error handling.
This little Trick can help if you do something that will run on otherones Computer.
Also you can rerun Methods from there to fix the Error or whatever.

Enjoy


