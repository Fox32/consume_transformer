# consume_transformer
A Barback transformer that removes files from the output of pub build and serve.

The transformer can be used to stop emitting output files that satisfy a filter 
from getting outputted by pub build or pub serve. This allows to emit a 
deployable version of your application, without source or sensitive files.


### Configuration

The next step is the configuration the transformer for your package. Add it to 
the `dependencies` and `transformers` sections of your `pubspec.yaml` 
and add the desired filters. A filter is a regular expression that is matched
against the full name of the assets. The following example removes all files 
that end with the file exentsion `.psd`.

```
dependencies:
- consume_transformer

transformers:
- consume_transformer:
    patterns: ["\\.psd$"]
```

You need to add the transformer to you `pubspec.yaml` file as the last 
transformer to catch all files created during all build stages.


### License

```
The MIT License (MIT)

Copyright (c) 2015 Oliver Sand

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```