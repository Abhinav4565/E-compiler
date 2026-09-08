# E-Compiler

E-Compiler is a C++ based compiler project for processing E++ expressions and generating corresponding target code.

The compiler reads E++ statements from an input file, parses the expressions, builds expression trees, manages variables using a symbol table, and generates target instructions into a `targ.txt` file.

---

## 📌 Project Overview

The compiler performs the following major tasks:

1. Reads E++ statements from an input file.
2. Parses variables, values, and arithmetic expressions.
3. Builds an expression tree for each expression.
4. Maintains variables using a Symbol Table.
5. Assigns memory locations to variables.
6. Generates target instructions.
7. Stores the generated target code in `targ.txt`.

### Compiler Flow

```
Input File → Parser → Expression Tree → Symbol Table → EPPCompiler → Target Code → targ.txt
```

---

## 🛠️ Technologies Used

- C++ / C++11
- Expression Trees
- Symbol Tables
- Min Heap
- Dynamic Memory Management
- File Handling

---

## 📂 Project Structure

```
E-compiler/
└── e++ compiler/
    ├── .gitignore
    ├── main.cpp
    ├── eppcompiler.cpp / .h
    ├── parser.cpp / .h
    ├── exprtreenode.cpp / .h
    ├── symtable.cpp / .h
    ├── symnode.cpp / .h
    ├── minheap.cpp / .h
    └── heapnode.cpp / .h
```

---

## 🔍 Components

**1. Parser**
Reads expressions from the input file and converts them into an expression tree. Handles variables, integer values, assignment, and arithmetic operators (`+ - * /`).

**2. Expression Tree**
Represents expressions using nodes: `ADD`, `SUB`, `MUL`, `DIV`, `VAL`, `VAR`, `DEL`, `RET`.

Example — `a + b`:
```
       ADD
      /   \
    VAR   VAR
     a     b
```

**3. Symbol Table**
Tracks variables and their memory locations (e.g., `a → mem[0]`, `b → mem[1]`, `c → mem[2]`). Supports insert, remove, search, assign address, and get table size.

**4. Memory Management**
Assigns memory locations to variables during compilation.

**5. Target Code Generation**
Generates target instructions after parsing, written to `targ.txt`.

---

## 📝 Example

**Input:**
```
a := 10
b := 20
c := a + b
ret := c
```

**Generated Target Code:**
```
PUSH 10
mem[0] = POP
PUSH 20
mem[1] = POP
PUSH mem[1]
PUSH mem[0]
ADD
mem[2] = POP
PUSH mem[2]
RET = POP
```

---

## 📋 Input Format

- Basic assignment: `a := 10`
- Variable-to-variable assignment: `b := a`
- Arithmetic expression: `c := a + b`
- Return statement: `ret := c`

## 📤 Output

Target instructions are written to `targ.txt`, using operations like `PUSH`, `ADD`, `SUB`, `MUL`, `DIV`, `RET`, and memory operations like `mem[address] = POP`.

---

## 🚀 How to Run

**1. Clone the repository**
```bash
git clone https://github.com/Abhinav4565/E-compiler.git
cd E-compiler
cd "e++ compiler"
```

**2. Compile the project**
```bash
g++ -std=c++11 main.cpp eppcompiler.cpp parser.cpp exprtreenode.cpp symtable.cpp symnode.cpp minheap.cpp heapnode.cpp -o e++
```

**3. Create an input file**
```bash
touch input.txt
nano input.txt
```
Add E++ code, e.g.:
```
a := 10
b := 20
c := a + b
ret := c
```

**4. Run the compiler**
```bash
./e++ input.txt
```

**5. View the generated target code**
```bash
cat targ.txt
```

---

## 📁 Generated Files

| File | Description |
|------|-------------|
| `e++` | Compiled executable |
| `targ.txt` | Generated target code |

These generated files don't need to be committed to the Git repository.

---

## 🔧 Future Improvements

- Better error handling
- Improved syntax validation
- More arithmetic operations
- More detailed compiler error messages
- Optimization of generated target code
- Improved memory management
- Additional test cases
- Cross-platform execution support
- Improved documentation

---

## 👨‍💻 Author

**Abhinav Yadav**
GitHub: [https://github.com/Abhinav4565](https://github.com/Abhinav4565)

## 📄 License

This project is created for educational and learning purposes.
