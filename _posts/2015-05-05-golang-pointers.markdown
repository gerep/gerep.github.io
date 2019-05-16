---
layout: post
title: "golang pointers"
date: 2015-05-05
categories:
---

When you send a parameter to a function you are sending a copy of that variable, doesn't matter what happen inside the funcion, the original variable won't change.

In a variable declaration there is a memory space used to store information. The first byte is the address. Using & before a variable will return its memory address.

```golang
package main

import "fmt"

var name string = "Gerep"
var age int = 31
var pi float32 = 3.14

func main() {
    fmt.Println("name address: ", &name)
    fmt.Println("age address: ", &age)
    fmt.Println("pi address: ", &pi)
}
```

Return:

```
name address:  0x54aab0
age address:  0x546060
pi address:  0x546014
```
Declaring a pointer is also simple:

```golang
package main

import "fmt"

var name string
var age int  

var stringPointer *string
var integerPointer *int

func main() {
    stringPointer = &name
    fmt.Println(stringPointer)
    integerPointer = &age
    fmt.Println(integerPointer)
}
```

Return:

```
0x54b440
0x552930
```

Remember:

**&** is used to return the variable memory address. <strong>*</strong> is used to return the value of the variable that is being pointed (dereferencing).

```golang
package main

import "fmt"

func main() {
    name := "Gerep"
    stringPointer := &name

    age := 31
    integerPointer := &age

    fmt.Println("Name: ", name)
    fmt.Println("stringPointer points to a variable with value: ", *stringPointer)
    fmt.Println("Age: ", age)
    fmt.Println("integerPointer points to a variable with value: ", *integerPointer)
}
```

Return:

```
Name: Gerep
stringPointer points to a variable with value: Gerep
Age:  31
integerPointer points to a variable with value: 31
```