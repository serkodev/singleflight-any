# singleflight-any

This repo hard forks from [golang.org/x/sync/singleflight](https://pkg.go.dev/golang.org/x/sync/singleflight) and support generics to the Group and Key type. Comparing to the original version of singleflight, you are free to use any `comparable` key type instead of `string` only.

## Install
```
go get github.com/serkodev/singleflight-any@latest
```
## Usage

`string` key, `string` value
```golang
var g Group[string, string]
v, _, _ := g.Do("foo", func() (string, error) {
    return "bar", nil
})
```

`int` key, `string` value
```golang
var g Group[int, string]
v, _, _ := g.Do(123, func() (string, error) {
    return "bar", nil
})
```

## Requirements

go 1.18 or above.
