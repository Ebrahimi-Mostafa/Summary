# Java
Source: https://www.youtube.com/watch?v=xk4_1vDrzzo&t=3305s

## 📋 Table of Contents  
- [Run a simple Java program](#run-a-simple-java-program)

## Run a simple Java program
Assume that is structure of our project:
```
.
├── README.md
├── bin
│   └── Main.class
├── lib
└── src
    └── Main.java
```

Compile the source code:
```bash
javac -d bin src/Main.java
```

Run the program:
```bash
java -cp bin Main
```

> **Note:** `-cp` is short for `--class-path` which is used to specify where to find classes files.