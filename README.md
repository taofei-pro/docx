# docx
![GitHub release (latest SemVer)](https://img.shields.io/github/v/release/taofei-pro/docx?sort=semver)
[![Go Report Card](https://goreportcard.com/badge/github.com/taofei-pro/docx)](https://goreportcard.com/report/github.com/taofei-pro/docx)
[![GoDoc](https://pkg.go.dev/badge/github.com/taofei-pro/docx?status.svg)](https://pkg.go.dev/github.com/taofei-pro/docx?tab=doc)
## Introduction
docx is a simple library to creating DOCX file in Go.

## Getting Started
### Install
Go modules supported
```sh
go get github.com/taofei-pro/docx
```
Import:
```sh
import "github.com/taofei-pro/docx"
```

### Usage
**Example:**
```go
package main

import (
	"github.com/taofei-pro/docx"
)

func main() {
	f := docx.NewFile()
	// add new paragraph
	para := f.AddParagraph()
	// add text
	para.AddText("test")

	run := para.AddText("test font size")
	run.Size(22)

	para.AddText("test color").Color("808080")
	para.AddText("test font size and color").Size(22).Color("121212")

	nextPara := f.AddParagraph()
	nextPara.AddLink("google", `http://google.com`)

	f.Save("./test.docx")
}

```
