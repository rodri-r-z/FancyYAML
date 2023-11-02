# SnakeYAMLDataParser

Parse YAML files with SnakeYAML the easy way.

## Dependencies

- SnakeYAML

## `new Parser(java.nio.file.Path.Pah)`

```java
final Parser YParser = new Parser(java.nio.file.Paths.get("path/to/mny/yaml/file"));
System.out.println(YParser.AsDouble("parent1"));
```

## Modifiers

```java
Parser.RETURN_NULL_ON_EXCEPTION // Returns null when an exception is encountered
Parser.RETURN_0_ON_EXCEPTION // Returns null when an exception is encountered
```

## `Parser.RETURN_NULL_ON_EXCEPTION`
Works for `Parser.AsString`, `Parser.AsArrayList`, `Parser.AsStringList`, `Parser.AsIntegerList`, `Parser.AsDoubleList`, `Parser.AsLongList`

## `Parser.RETURN_0_ON_EXCEPTION`
Works for: `Parser.AsInt`, `Parser.AsLong`, `Parser.AsDouble`

## Getting nested elements

File Example:

```
databases:
  type: "mongodb"
  details:
    uri: "mongodb://127.0.0.1:27017"
```

Code Example:

```
final Parser YParser = new Parser(java.nio.file.Paths.get("path/to/mny/yaml/file"));
System.out.println(YParser.AsString("databases.type", Parser.RETURN_NULL_ON_EXCEPTION));
System.out.println(YParser.AsString("databases.details.uri", Parser.RETURN_NULL_ON_EXCEPTION));
```

Output:

```text
mongodb
mongodb://127.0.0.1:27017
```
