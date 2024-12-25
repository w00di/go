# Go Notes
## Basics
### First Program
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
- `go build` creates an executable called `hello_world`

### go fmt
- `go fmt` automatically fixes the whitespace in your code to match standard format
- It can't fix braces on the wrong line
- go compiler adds `;` at the end of every statement automatically

```go
go fmt ./...
```
### go vet
- detects bugs
```go
go vet ./...
```
### Makefiles
- `make` lets devs specify a set of operations that are necessary to build a program abd the order in which the steps must be performed

**Sample**
```
.DEFAULT_GOAL := build
.PHONY:fmt vet build

fmt:
	go fmt ./...
vet: fmt
	go fmt ./...
build: vet
	go build
```
- Each operation is called a `target`
- `.DEFAULT_GOAL` defines which target is run when no target is specified
- Next are target definitions
- The word before the colon is the name of the target
- Ant word after the colon are targets that must be run first
- Indentied lines are the tasks run by the targets
- `.PHONY` line keeps make from getting confused if a directory or file has the same name as one of the listed targets
- Run `make`
