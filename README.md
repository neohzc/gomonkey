# gomonkey

个人使用 针对gomonkey 在macOS13 m1 环境下无法同时申请分页读写和执行权限导致的mock失败问题进行修改 仅供个人使用 斟酌使用
fork https://github.com/agiledragon/gomonkey
## 拉取
```go
$ go get github.com/neohzc/gomonkey
```

## Features

+ support a patch for a function
+ support a patch for a public member method
+ support a patch for a private member method
+ support a patch for a interface
+ support a patch for a function variable
+ support a patch for a global variable
+ support patches of a specified sequence for a function
+ support patches of a specified sequence for a member method
+ support patches of a specified sequence for a interface
+ support patches of a specified sequence for a function variable

## Notes
+ gomonkey fails to patch a function or a member method if inlining is enabled, please running your tests with inlining disabled by adding the command line argument that is `-gcflags=-l`(below go1.10) or `-gcflags=all=-l`(go1.10 and above).
+ A panic may happen when a goroutine is patching a function or a member method that is visited by another goroutine at the same time. That is to say, gomonkey is not threadsafe.

## Supported Platform:

- ARCH
  - amd64
  - arm64
  - 386

- OS
  - Linux
  - MAC OS X
  - Windows

## Installation
- below v2.1.0, for example v2.0.2
```go
$ go get github.com/agiledragon/gomonkey@v2.0.2
```
- v2.1.0 and above, for example v2.2.0
```go
$ go get github.com/agiledragon/gomonkey/v2@v2.2.0
```

## Test Method
```go
$ cd test 
$ go test -gcflags=all=-l
```

## Using gomonkey

Please refer to the test cases as idioms, very complete and detailed.

