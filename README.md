# procfile

A go package for parsing `Procfile` entries.

## Install

```
go get github.com/chrismytton/procfile
```

## Usage

```go
package main

import (
	"fmt"
	"github.com/chrismytton/procfile"
)

func main() {
	proclist := procfile.Parse("web: bundle exec rackup\nworker: rake resque:work")
	for name, process := range proclist {
		fmt.Println(name, "command", process.Command)
		fmt.Println(name, "arguments", process.Arguments)
	}
}
```

Copyright (c) Chris Mytton
