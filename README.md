# Go Notes
## Basics
- `go mod init hello_world` marks the directory as a Go module

**Sample**
```go
package main

import "fmt"

func main() {
	fmt.Println("Hello, world!")
}
```
- First line is a package declaration
- The `main` package in a Go module contains the code that starts a Go program
- Next is an `import` declaration
- Lists packages referenced in the file
- Go only imports whole packages
- All Go programs start from the `main` function
