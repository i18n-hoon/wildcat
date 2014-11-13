wildcat
=======

[![GoDoc](https://godoc.org/github.com/evanphx/wildcat?status.svg)](https://godoc.org/github.com/evanphx/wildcat)

A high performance golang HTTP parser.

Baseline benchmarking results:

```
zero :: evanphx/wildcat> go test -bench . -benchmem
PASS
BenchmarkParseSimple	50000000	        41.7 ns/op	       0 B/op	       0 allocs/op
BenchmarkNetHTTP	  500000	      4501 ns/op	    4627 B/op	       7 allocs/op
BenchmarkParseSimpleHeaders	20000000	       109 ns/op	       0 B/op	       0 allocs/op
BenchmarkParseSimple3Headers	10000000	       218 ns/op	       0 B/op	       0 allocs/op
BenchmarkNetHTTP3	  500000	      6585 ns/op	    5064 B/op	      11 allocs/op
ok  	github.com/evanphx/wildcat	12.524s
```

NOTE: these are a bit of lie because wildcat doesn't yet do everything that net/http.ReadRequest does.
The numbers are included here only to provide a baseline comparison for future work.
