# Go 
Source: [A Tour of Go](https://go.dev/tour/list)

## Table of Contents :clipboard:
* [Basics](#basics)
    1. [Packages, variables, and functions.](#packages-variables-and-functions)
	2. [Flow control structures: for, if, else, switch and defer.](#flow-control-structures-for-if-else-switch-and-defer)
	3. [More types: structs, slices, and maps.](#more-types-structs-slices-and-maps)


## Basics
### Packages, variables, and functions.
- `Packages`: Every Go program is made up of packages. Programs start running in package `main`.

- `Imports`: The code in the next example groups the imports into a parenthesized, "factored" import statement. You can also write multiple import statements, like:
```go
import "fmt"
import "math"
```

- `Exported names`: In Go, a name is exported if it begins with a capital letter. For example, `Pi` is an exported name, as is `Pi` which is exported from the `math` package.

```go
package main

import (
	"fmt"
	"math"
	"math/rand"
)

func main() {
	fmt.Println("My favorite number is", rand.Intn(10))
	fmt.Println(math.Pi)
	// fmt.Println(math.pi) // Error: cannot refer to unexported name math.pi
}
```

- `Functions`:
```go
package main

import "fmt"

func add(x int, y int) int {
	return x + y
}

func main() {
	fmt.Println(add(4, 5))
}
```
> `Note`: the type comes after the variable name. 

> `Note`: When two or more consecutive named function parameters share a type, you can omit the type from all but the last.

```go
package main

import "fmt"

func add(a, b, c, d int) int {
	return a + b + c + d
}

func main() {
	fmt.Println(add(4, 5, 6, 7))
}
```

- `Multiple results`: A function can return any number of results.

```go
package main

import "fmt"

func swap(x, y string) (string, string) {
	return y, x
}

func main() {
	a, b := swap("hello", "world")
	fmt.Println(a, b)
}
```

- `Named return values`: Go's return values may be named. If so, they are treated as variables defined at the top of the function.

```go
package main

import "fmt"

func split(sum int) (x, y int) {
	x = sum * 4 / 9
	y = sum - x
	return
}

func main() {
	fmt.Println(split(10))
}
```

- `var`: The `var` statement declares a list of variables; as in function argument lists, the type is last.

```go
var a, b int // a and b are of type int
var c, d int = 1, 2 
var c, d = 1, 2 
var e, f = 123, "hello"
var (
	g int
	h string
	i = 1.4
	j int = 1
)
```

- `Short variable declarations`: Inside a function, the `:=` short assignment statement can be used in place of a `var` declaration with implicit type.

```go
a := 1
b := "hello"
c, d := 1, "hello"
```

- `Basic types`: Go's basic types are
	- `bool`
	- `string`
	- `int`, `int8`, `int16`, `int32`, `int64`
	- `uint`, `uint8`, `uint16`, `uint32`, `uint64`, `uintptr`
	- `byte` (alias for `uint8`)
	- `rune` (alias for `int32`)
	- `float32`, `float64`
	- `complex64`, `complex128`

- `Zero values`: Variables declared without an explicit initial value are given their zero value.
	- `0` for numeric types,
	- `false` for the boolean type, and
	- `""` (the empty string) for strings.

- `Type conversions`: The expression `T(v)` converts the value `v` to the type `T`.

```go
var i int = 42
var f float64 = float64(i)
var u uint = uint(f)
```

- `Constants`: Constants are declared like variables, but with the `const` keyword. Constants cannot be declared using the `:=` syntax.

```go
const PI = 3.14
const PI float64 = 3.14
```

- `Numeric Constants`: Numeric constants are high-precision values.

```go
const (
	Big = 1 << 100
	Small = Big >> 99
)
```

### Flow control structures: for, if, else, switch and defer.

- `For`: Go has only one looping construct, the `for` loop.

```go
package main

import "fmt"

func main() {
	sum := 0
	for i := 0; i < 10; i++ {
		sum += i
	}
	fmt.Println(sum)
}
```

> `Note`: Unlike other languages like C, Java, or JavaScript there are no parentheses surrounding the three components of the `for` statement and the braces `{ }` are always required.

- `For continued`: The init and post statements are optional.

```go
for ; sum < 1000; {
	sum += sum
}
// is equivalent to
for sum < 1000 {
	sum += sum
}
```
last example is equivalent to a `while` loop in other languages.

- `Forever`
```go
for {
	// code inside the infinite loop
}
```

- `If`: Go's `if` statements are like its `for` loops; the expression need not be surrounded by parentheses `( )` but the braces `{ }` are required.

```go
sum := 1
if sum < 10 {
	fmt.Println("sum is less than 10")
}
```

- `If with a short statement`: Like `for`, the `if` statement can start with a short statement to execute before the condition.

```go
func pow(x, n, lim float64) float64 {
	if v := math.Pow(x, n); v < lim {
		return v
	} else {
		fmt.Printf("%g >= %g\n", v, lim)
	}
	return lim
}
```

> `Note`: Variables declared inside an `if` short statement are also available inside any of the `else` blocks.

- `Switch`: Go only runs the selected case, not all the cases that follow. In effect, the `break` statement that is needed at the end of each case in those languages is provided automatically in Go.
```go
var i int = 2
switch i {
case 1:
	fmt.Println("one")
	fmt.Println("one")
case 2:
	fmt.Println("two")
	fmt.Println("two")
default:
	fmt.Println("default")
}
/// Output:
// two
// two
```

- `Switch evaluation order`: Switch cases evaluate cases from top to bottom, stopping when a case succeeds.

```go
var a = 0

func f() int {
	println("There is f()")
	a++
	return a
}

func main() {
	var i int = 2
	switch i {
	case f():
		fmt.Println("First case")
	case f():
		fmt.Println("Second case")
	case f():
		fmt.Println("Third case")
	default:
		fmt.Println("Default")
	}
}
// Output:
// There is f()
// There is f()
// Second case
```

- `Switch with no condition`: Switch without a condition is the same as `switch true`.

```go
var a = 1
switch {
case a < 0:
	fmt.Println("Neg")
case a == 0:
	fmt.Println("Zero")
case a > 0:
	fmt.Println("Pos")
}
```

- `Defer`: A `defer` statement defers the execution of a function until the surrounding function returns.  
The deferred call's arguments are evaluated immediately, but the function call is not executed until the surrounding function returns.

```go
func main() {
	fmt.Println("counting")

	for i := 0; i < 4; i++ {
		defer fmt.Println(i)
	}

	fmt.Println("done")
}
// Output:
// counting
// done
// 3
// 2
// 1
// 0
```

### More types: structs, slices, and maps.

- `Pointers`: A pointer holds the memory address of a value. Unlike C, Go has no pointer arithmetic.

```go
i := 42
p := &i
fmt.Println(*p)
*p = 21
fmt.Println(i)
```

- `Structs`: A `struct` is a collection of fields.

```go
type Vertex struct {
	x int
	y int
}

func main() {
	var v Vertex = Vertex{1, 2}
	println(v.x) // 1
	println(v.y) // 2

	v.x = 4
	println(v.x) // 4
}
```

- `Pointer to struct`: Struct fields can be accessed through a struct pointer.

```go
type Vertex struct {
	x int
	y int
}

func main() {
	v := Vertex{1, 2}
	p := &v
	p.x = 1e3
	fmt.Println(v) // {1000 2}

	(*p).x = 1e2
	fmt.Println(v) // {100 2}
}
```
> `Note`: To access the field `x` of a struct when we have the struct pointer `p` we could write `(*p).x`. However, that notation is cumbersome, so the language permits us instead to write just `p.x`, without the explicit dereference.

