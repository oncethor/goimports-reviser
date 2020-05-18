# goimports-reviser [![Tweet](https://img.shields.io/twitter/url/http/shields.io.svg?style=social)](https://twitter.com/intent/tweet?text=Right%20golang%20imports%20sorting%20and%20code%20formatting%20tool%20(goimports%20alternative)&url=https://github.com/incu6us/goimports-reviser&hashtags=golang,code,goimports-reviser,goimports,gofmt,developers)
!['Status Badge'](https://github.com/incu6us/goimports-reviser/workflows/build/badge.svg)
!['Release Badge'](https://github.com/incu6us/goimports-reviser/workflows/release/badge.svg)
!['Quality Badge'](https://goreportcard.com/badge/github.com/incu6us/goimports-reviser)
[![codecov](https://codecov.io/gh/incu6us/goimports-reviser/branch/master/graph/badge.svg)](https://codecov.io/gh/incu6us/goimports-reviser)
![GitHub All Releases](https://img.shields.io/github/downloads/incu6us/goimports-reviser/total?color=green)
![GitHub release (latest by date)](https://img.shields.io/github/v/release/incu6us/goimports-reviser?color=green)
![license](https://img.shields.io/github/license/incu6us/goimports-reviser)

!['logo'](./images/reviser-muscot_200.png)

Tool for Golang to sort goimports by 3 groups: std, general and project dependencies.
Also, formatting for your code will be prepared(so, you don't need to use `gofmt` or `goimports` separately). 
Use additional option `-rm-unused` to remove unused imports.

## Install
```bash
$ brew tap incu6us/homebrew-tap
$ brew install incu6us/homebrew-tap/goimports-reviser
```

## How To Use
!['How To'](./images/howto.gif)

Before usage:
```go
package testdata

import (
	"log"

	"github.com/incu6us/goimports-reviser/testdata/innderpkg"

	"bytes"

	"github.com/pkg/errors"
)
``` 

After usage:
```go
package testdata

import (
	"bytes"
	"log"
	
	"github.com/pkg/errors"
	
	"github.com/incu6us/goimports-reviser/testdata/innderpkg"
)
```

Comments(not Docs) for imports is acceptable. Example:
```go
package testdata

import (
    "fmt" // comments to the package here
)
```  

### Options:
```text
  -file-path string
    	File path to fix imports(ex.: ./reviser/reviser.go). Required parameter.
  -project-name string
    	Your project name(ex.: github.com/incu6us/goimports-reviser). Required parameter.
  -rm-unused
    	Remove unused imports. Optional parameter.
  -version
    	Show version.
```

## Examples:
### Bash
```bash
goimports-reviser -project-name github.com/incu6us/goimports-reviser -file-path ./reviser/reviser.go 
```

### Example, to configure it with JetBrains IDEs (via file watcher plugin):
![example](./images/image.png)
