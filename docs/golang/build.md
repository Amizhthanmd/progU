---
sidebar_position: 21
---

# Go build

Building Go applications is an essential part of Go development. Below is a comprehensive guide covering Go builds from basic to advanced.

## 1. Basic Build Commands

### a. Simple Build

The most basic way to build a Go application:

- Builds the package in the current directory.
- Produces an executable binary in the same directory.

```bash
go build
```

### b. Naming the Output

Specify the output binary name using the -o flag:

```bash
go build -o myapp
```

### c. Building Specific Files

To build a specific file (useful for multi-file projects):

```bash
go build main.go
```

## 2. Cross-Compilation

Build for different platforms and architectures using GOOS and GOARCH.

### a. List of Platforms

Check supported platforms:

```bash
go tool dist list
```

### b. Example Commands

1. `Linux` (64-bit):

```bash
GOOS=linux GOARCH=amd64 go build -o myapp
```

2. `Windows` (64-bit):

```bash
GOOS=windows GOARCH=amd64 go build -o myapp.exe
```

3. `macOS` (ARM):

```bash
GOOS=darwin GOARCH=arm64 go build -o myapp
```

## 3. Build with metadata

Build the application and pass metadata using ldflags:

```bash
go build -ldflags "-X main.version=1.0.0 -X main.buildDate=$(date +%Y-%m-%d) -X main.commit=$(git rev-parse --short HEAD)" -o app
```

[Checkout](https://github.com/Amizhthanmd/go-build-flag) this github

