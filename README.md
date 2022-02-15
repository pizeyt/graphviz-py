# WIP: graphviz-py
Allows Python code execution inside of [graphviz](https://graphviz.org/) diagrams

## Example
```dot
graph python_graph {
{{
import math

value = 0.5
sin = math.sin(value)
cos = math.cos(value)
}}

    A [label="{{= value }}"];
    B [label="{{= sin }}"];
    C [label="{{= cos }}"];

    A -- B;
    A -- C;
}
```

### Output
![output](assets/output.svg)

## Install
Coming soon!
```bash
pip install graphviz-py
```

## Usage
### Using files
```bash
graphviz-py -Tsvg example/example.py.dot -o output.svg
graphviz-py -Tpng example/example.py.dot -o output.png
```

### Using stdin / pipes
```bash
echo 'digraph { A -> B [label="{{= 38 * 73 }}"] }' | graphviz-py -Tsvg > output.svg
```

graphviz-py passes all unknown arguments to graphviz. So you can use all [graphviz arguments](https://graphviz.org/doc/info/command.html).

## Coming soon
- Requested the graphviz-py Pypi name
- Compartibility with asciidoctor-diagram
