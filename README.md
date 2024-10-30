# govalid

`govalid` is a code generator that implements a Validate method on a given type. The method returns an error when it is called; if the current value is not one of those constants declared in a given file in code generation.

## Example

Input (you provide):

```go
type Planet string

const (
  Earth = Planet("earth")
  Mars  = Planet("mars")
)
```

Command:

```sh
govalid -in filename.go -type Planet
```

Output:

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

## Install

```sh
go install github.com/ufukty/govalid@latest
```
