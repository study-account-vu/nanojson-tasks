# Task 2: Numeric Reader Accepts Strings

Please complete Task 1 before beginning this task.

## Bug Report

JSON distinguishes between numbers and strings.

For example:

```text
123
```

is a JSON number, while:

```text
"123"
```

is a JSON string.

`JsonReader` provides numeric methods for reading number values. Currently, these methods can also interpret a JSON string containing digits as a number.

## Reproduce the Bug

From the repository root, compile the project:

```sh
mvn -q -DskipTests compile
```

Start JShell:

```sh
jshell --class-path target/classes
```

Then run:

```java
import com.grack.nanojson.*;

JsonReader reader = JsonReader.from("\"123\"");

System.out.println(reader.current());
System.out.println(reader.intVal());
```

**Current:** The current value is a JSON string, but `intVal()` returns:

```text
123
```

**Expected:** A JSON string should not be accepted as a numeric value. Attempting to read it using a numeric reader method should produce a `JsonParserException`.

## Your Task

**Investigate why a JSON string can be read as a number, and modify the code to fix the bug.**

## Test Your Fix

After making a code change, exit JShell:

```text
/exit
```

Recompile:

```sh
mvn -q -DskipTests compile
```

Start JShell again:

```sh
jshell --class-path target/classes
```

Repeat the reproduction steps above to check whether your fix works.