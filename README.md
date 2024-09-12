# list

[![Go Reference](https://pkg.go.dev/badge/github.com/Snawoot/list.svg)](https://pkg.go.dev/github.com/Snawoot/list)

Improved version of "container/list" from Go stdlib:

* Uses generics instead of interface values.
* Uses own freelist allocator for list elements.

## Benchmarks

Benchmarks versus original "container/list".

```
goos: linux
goarch: amd64
pkg: github.com/Snawoot/list
cpu: Intel(R) N100
BenchmarkContainerList/PushFront-4                     	11407059	        117.5 ns/op	      55 B/op	       1 allocs/op
BenchmarkContainerList/PushPopFront-4                  	10579866	        131.4 ns/op	      55 B/op	       1 allocs/op
BenchmarkContainerList/PushPopFrontImmediate-4         	13294423	        91.07 ns/op	      56 B/op	       1 allocs/op
BenchmarkFreelistList/PushFront-4                      	29593803	        43.41 ns/op	      49 B/op	       0 allocs/op
BenchmarkFreelistList/PushPopFront-4                   	28675177	        42.61 ns/op	      40 B/op	       0 allocs/op
BenchmarkFreelistList/PushPopFrontImmediate-4          	128021602	        9.493 ns/op	       0 B/op	       0 allocs/op
BenchmarkFreelistList/WarmedUpPushFront-4              	130466055	        9.313 ns/op	       0 B/op	       0 allocs/op
BenchmarkFreelistList/WarmedUpPushPopFront-4           	78485906	        14.48 ns/op	       0 B/op	       0 allocs/op
PASS
ok  	github.com/Snawoot/list	18.221s
```
