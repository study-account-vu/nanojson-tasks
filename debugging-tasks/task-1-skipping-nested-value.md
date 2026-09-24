# Task 1: Skipping a Nested Value

## Bug Report

`JsonReader` can be used to move through JSON data one value at a time.

When a nested value is skipped, the reader should finish that value and continue at the next value in the surrounding container.

Currently, skipping a nested object can leave the reader inside the object that was supposed to be skipped.

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
import java.io.*;

JsonReader reader = JsonReader.from(new FileInputStream("src/test/resources/reader-pop.json"));

reader.object();
reader.next();
reader.array();
reader.next();
reader.object();

System.out.println(reader.pop());
System.out.println(reader.current());
System.out.println(reader.string());
```

**Current:**

```text
STRING
Ada
```

The reader remains inside the first user instead of continuing to the next user.

**Expected:** After the first user is skipped, the reader should continue at the second user object (`Grace`).

## Your Task

**Investigate why skipping the nested value does not continue at the correct location, and modify the code to fix the bug.**

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