

# mozlz4
`import "github.com/frioux/mozlz4"`

* [Overview](#pkg-overview)
* [Index](#pkg-index)
* [Examples](#pkg-examples)

## <a name="pkg-overview">Overview</a>


#### <a name="example_">Example</a>

Code:
``` go
file, err := os.Open(os.Args[1])
if err != nil {
    fmt.Fprintf(os.Stderr, "Couldn't open: %s\n", err)
    os.Exit(1)
}

r, err := mozlz4.NewReader(file)
_, err = io.Copy(os.Stdout, r)
if err != nil {
    fmt.Fprintf(os.Stderr, "Couldn't copy: %s\n", err)
    os.Exit(1)
}
```


## <a name="pkg-index">Index</a>
* [Variables](#pkg-variables)
* [func NewReader(r io.Reader) (io.Reader, error)](#NewReader)

#### <a name="pkg-examples">Examples</a>
* [Package](#example_)

#### <a name="pkg-files">Package files</a>
[mozlz4.go](https://github.com/frioux/mozlz4/tree/master/mozlz4.go) 



## <a name="pkg-variables">Variables</a>
``` go
var (
    ErrWrongHeader = errors.New("no mozLz4 header")
    ErrWrongSize   = errors.New("header size incorrect")
)
```
Errors



## <a name="NewReader">func</a> [NewReader](https://github.com/frioux/mozlz4/tree/master/mozlz4.go?s=622:668#L29)
``` go
func NewReader(r io.Reader) (io.Reader, error)
```
NewReader returns an io.Reader that decompresses the data from r.









## Copyright 2018 Arthur Axel fREW Schmidt

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

     http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
