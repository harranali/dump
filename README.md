# dump
![Build Status](https://github.com/harranali/dump/actions/workflows/build-main.yml/badge.svg)
[![GoDoc](https://godoc.org/github.com/harranali/dump?status.svg)](https://godoc.org/github.com/harranali/dump)
[![Go Report Card](https://goreportcard.com/badge/github.com/harranali/dump)](https://goreportcard.com/report/github.com/harranali/dump)

A simple Go package to perform Dump and Die

# Install
```bash
go get github.com/harranali/dump
```

# Usage 
Dumping a Struct:
```go
package main

import (
	"github.com/harranali/dump"
)

func main() {
	type Person struct {
		Name string
		Age  int
	}

	jack := Person{
		Name: "jack",
		Age:  32,
	}
	dump.DD(jack)
}

// out put

#Type: main.Person
#Underlying Type: struct
#Value: {jack 32}
```


Dumping Strings:
```go
package main

import (
	"github.com/harranali/dump"
)

func main() {
	t := "this is a test string"
	dump.DD(t)
}

// out put

#Type: string
#Value: this is a test string
```

Dumping Numeric:
```go
package main

import (
	"github.com/harranali/dump"
)

func main() {
	t := 123.43
	dump.DD(t)
}

// out put

#Type: float64
#Value: 123.43
```

Dumping a Channel:
```go
package main

import (
	"github.com/harranali/dump"
)

func main() {
	var c chan int
	dump.DD(c)
}

// out put

#Type: chan int
#Underlying Type: chan
#Value: <nil>
```

Dumping an Interface:
```go
package main

import (
	"github.com/harranali/dump"
)

func main() {
	type Getter interface {
		get()
	}
	var g Getter
	dump.DD(g)
}

// out put

#Type: interface
```
