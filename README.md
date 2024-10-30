# govalid

`govalid` is a code generator that implements a `func (t T) Validate() error` method on a given type that returns an error when called if the current value is not one of the constants declared in a given file in code generation. Example:

```go
func (p Planet) Validate() error {
  switch p {
  case Earth:
    return nil
  case Mars:
    return nil
  }
  return fmt.Errorf("invalid value")
}
```

Usage:

```sh
govalid -in filename.go -type Planet
```

Install:

```sh
go install github.com/ufukty/govalid@latest
```
