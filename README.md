# nanojson Debugging Tasks

You will complete two debugging tasks in this repository.

## About JSON and nanojson

**JSON (JavaScript Object Notation)** is a text format used to represent and exchange structured data. It can contain strings, numbers, booleans, arrays, and objects with key-value pairs.

For example:

```json
{
  "name": "Ada",
  "languages": ["Java", "Python"]
}
```

**nanojson** is a Java library for reading and writing JSON. It provides several ways to work with JSON, including a parser, writer, and `JsonReader`.

`JsonReader` allows a program to move through JSON data one value at a time. Both debugging tasks involve this reader functionality.

## Tools

This project uses **Maven** to compile and build the Java project. The commands you need are provided in each task.

The reproduction steps also use **JShell**, which allows you to run Java statements directly from the Terminal without creating a separate Java program.

To exit JShell:

```text
/exit
```

## Tasks

Complete the tasks in order:

1. [Task 1: Skipping a Nested Value](debugging-tasks/task-1-skipping-nested-value.md)
2. [Task 2: Numeric Reader Accepts Strings](debugging-tasks/tasktask-2-numeric-reader-accepts-strings.md)

Please complete Task 1 before beginning Task 2.