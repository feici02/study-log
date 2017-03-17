## How ot set up a Go environment on macOS?

### 1. install
```
brew install go
```

### 2. create your workspace directory
```
mkdir $HOME/go
cd !$
```

### 3. edit and source setenv.sh

#### setenv.sh:
```
#!/bin/bash

export GOPATH=$(pwd)
export PATH=$PATH:/usr/local/opt/go/libexec/bin:$GOPATH
```
#### source it
```
source ./setenv.sh
```

### 4. check your environment
```
go version
```

### 5. edit your first go program
#### hello.go:
```
package main

import "fmt"

func main() {
    fmt.Printf("hello, world\n")
}
```
#### build & run
```
mkdir src/go
cd !$
vim hello.go
go build
./hello
```

### 6. run "A Tour of Go" locally
```
go get golang.org/x/tour/gotour
# in $GOPATH/bin
gotour
```

### reference
1. [Go doc](https://golang.org/doc)
1. [Go wiki](https://github.com/golang/go/wiki)
