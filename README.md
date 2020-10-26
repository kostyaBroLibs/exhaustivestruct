# exhaustivestruct

[![Go Report Card](https://goreportcard.com/badge/github.com/mbilski/exhaustivestruct)](https://goreportcard.com/badge/github.com/mbilski/exhaustivestruct)

exhaustivestruct is a go static analysis tool to find structs that have some, but no all, initialized fields.

> :warning: This linter is meant to be used only for special cases.
> It is not recommended to use it for all files in a project.

## Installation

```
go get -u github.com/mbilski/exhaustivestruct/cmd/exhaustivestruct
```

## Usage

```
exhaustivestruct files/packages
```

## Example

``` go
type User struct {
  Name string
  Age int
}

var user = User{ // fails with "Age is missing in User"
  Name: "John",
}

var user2 = User{} // ignores empty structs
```

