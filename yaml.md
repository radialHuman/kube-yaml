## Source : [Yaml Tutorial | Learn YAML in 18 mins](https://youtu.be/1uFVr15xDGg)
- serialization tool : to transfer data between different languaes using a standard format
- it used to be xml and json but yaml is the most cleana nd readable one
- indentation and line seperation are important
- plus there are no comments n json, making ti difficult to read
- there ar tags in xml making it look clunky
- .yml or .yaml

### Key things
- kv pairs : string or numebr without quotes unless it has quotes or new line in it, single or double both works
```yaml
    - app : name
    - app : "name's"
    - port : 8000
```

- objects
    - any kv pair if indented inside the object name can be part of the obejct
    ```yaml
    object-name :
        k1 : v1
        k2 : v2
    ```
- comments 
    - #anywhere
- list : alignment can be under the bject name or indented
    - are activated using dash, if an object needs to have multiple sets of kv pairs
```yaml
    object-with-list:
        - k1 : v1
          k2 : v2
        - l1 : w1
          l2 : w2

    object-with-list:
        - name1
        - name 2
    object-with-list:[name1, "name2", 3]

    object-nested1:
        - class1
            - name1
    object-nested2:
    - class1
      - name1
```
- boolean
```yaml
    - deployed : true
    - deployed : yes
    - deployed : on
    - checked : false
    - checked : no
    - checked : off
```
- mutli line string : can be used to execute multi line shell script after pipe operator
```yaml
object-name: | #this here indicates that the following is multiline 
    this is a 
    multiline string
    for the obejct

object-name: > #this si to indicate that the folowing multi liens are actuall single line but for readblaility have split
    this is a 
    multiline string
    for the obejct
```
- env variable : if there are variables inside the pod which eneds to be accessed
```yaml
$VARIABLE
```

- placeholders : for templates
```yaml
name : {{ .Values.name.be.populated }}
port : {{ .Values.port.be.populated }}

```
- seperator : multi components in one file
```yaml
---
```