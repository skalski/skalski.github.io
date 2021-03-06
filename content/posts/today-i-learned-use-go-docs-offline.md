---
title: "Today I Learned - Use Go Docs Offline"
date: 2021-04-29T10:20:23+02:00
tldr: "Go has the whole documentation offline by default"
draft: false
tags: [go]
---

Go has plentiful documentation online, but sometimes using a search engine to find the right thing in go can be tough. Go has docs at the command line though. On the first glance, it saves a lot of time. Also when you work sometimes without Internet Connection or don't want to use a Hotspot.
For me this sometimes happens on the Ferry or when we go by boat at the weekend.
<!--more-->
One feature, I already knew was this one: 

### Go docs at the command line ...

You can use `go doc <name-of-package>`
Which has a result, quiet similar to this one:

```
> go doc io/ioutil
package ioutil // import "io/ioutil"

Package ioutil implements some I/O utility functions.

var Discard io.Writer = devNull(0)
func NopCloser(r io.Reader) io.ReadCloser
func ReadAll(r io.Reader) ([]byte, error)
func ReadDir(dirname string) ([]os.FileInfo, error)
func ReadFile(filename string) ([]byte, error)
func TempDir(dir, prefix string) (name string, err error)
func TempFile(dir, prefix string) (f *os.File, err error)
func WriteFile(filename string, data []byte, perm os.FileMode) error
```

Or, you can use `go doc <function>` if the function is fully qualified with the package name.

```
> go doc io/ioutil.WriteFile
func WriteFile(filename string, data []byte, perm os.FileMode) error
    WriteFile writes data to a file named by filename. If the file does not
    exist, WriteFile creates it with permissions perm; otherwise WriteFile
    truncates it before writing.
```

As an example, the command `go doc ioutil.WriteFile` will also work, what is very cool.

### But wait... there is more (Oh my god, Bod!!)

The Go language has a wonderfully comprehensive standard library. There is documentation for all of it. 
You can access that documentation anytime if you have an internet connection via https://golang.org/doc/. But as I said, sometime you can't reach it.
A friend of mine gave me a cool hint.

If you are without an internet connection, you’re still in luck. Go has a built-in feature for serving the documentation locally offline. Just run the following command:

```
$ godoc -http=:6060
```

and then visit `localhost:6060`.
I allready knew, that this feature exists in RUST. But I didn't expected that in go.
For me it's a real killerfeature.
