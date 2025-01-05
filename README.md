# Unexpected Zero Value When Accessing Non-Existent Map Key in Go

This example demonstrates a common but subtle issue in Go: accessing a non-existent key in a map.  Unlike some languages that might throw an exception, Go maps return the zero value of the map's value type. This silent failure can lead to hard-to-debug errors.

The `bug.go` file contains the problematic code.  `bugSolution.go` demonstrates how to safely handle this scenario using the comma ok idiom.

## How to reproduce

1. Save the code in `bug.go`.
2. Run using `go run bug.go`.
3. Observe the output - it will be 0, not an error.

## Solution

The recommended way to check for the existence of a key before accessing it is using the comma ok idiom.