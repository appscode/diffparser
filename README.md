[![CLA assistant](https://cla-assistant.io/readme/badge/appscode/diffparser)](https://cla-assistant.io/appscode/diffparser)

[Website](https://appscode.com) • [Slack](https://slack.appscode.com) • [Forum](https://discuss.appscode.com) • [Twitter](https://twitter.com/AppsCodeHQ)

DiffParser
===========

DiffParser is a Golang package for parsing git diffs. This supports diffs containing binary files. This library is forked from http://github.com/waigani/diffparser

Install
-------

```sh
go get http://github.com/appscode/diffparser
```

Usage Example
-------------

```go
package main

import (
	"fmt"
	"github.com/appscode/diffparser"
)

// error handling left out for brevity
func main() {
	byt, _ := ioutil.ReadFile("example.diff")
	diff, _ := diffparser.Parse(string(byt))

	// You now have a slice of files from the diff,
	file := diff.Files[0]

	// diff hunks in the file,
	hunk := file.Hunks[0]

	// new and old ranges in the hunk
	newRange := hunk.NewRange

	// and lines in the ranges.
	line := newRange.Lines[0]
}
```

More Examples
-------------

See diffparser_test.go for further examples.


Credits
-------
This repository started as a fork of https://github.com/waigani/diffparser .
