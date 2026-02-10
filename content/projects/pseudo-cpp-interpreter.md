+++
title = "Pseudo CPP Interpreter"
date = 2023-04-30
description = "Pseudo C++ Interpreter (Bash)"
github = "https://github.com/patkarmandar/Pseudo-CPP-Interpreter/" # Optional
demo = "" # Optional
tags = ["cpp"]
categories = ["experiment"]
featured = false
+++

Pseudo-C++ Interpreter is a Bash-based interactive interpreter that simulates a basic C++ REPL-like experience in the terminal.

It allows users to write and execute C++ statements line by line without manually creating a full C++ program. Internally, the script dynamically wraps user input into a valid C++ source file, compiles it using G++, and executes the binary.

This project demonstrates process automation, shell scripting, and dynamic code generation.

### How It Works
- User inputs C++ statements interactively
- Each statement is appended to a temporary buffer
- The script automatically generates a complete C++ program:
    - Adds headers
    - Wraps input inside `main()`
- Compiles the code using `g++`
- Executes the compiled binary
- Invalid or problematic statements are commented out automatically

{{< alert type="note" >}}
This is not a full C++ interpreter — it relies on runtime compilation.
{{< /alert >}}

### Supported Commands
| Command      | Description                                |
| ------------ | ------------------------------------------ |
| `help`       | Display available commands                 |
| `clear`      | Clear the terminal screen                  |
| `reset`      | Reset current code buffer                  |
| `exit`       | Exit interpreter and cleanup               |
| `cpp <file>` | Compile & execute a C++ file               |
| `cout`       | Supported (auto-commented after execution) |
| `cin`        | Not supported                              |

### Requirements
- Linux / macOS (or WSL)
- Bash shell
- G++ compiler

Verify installation:
```bash
g++ --version
```

### Usage
1. Clone the Repository
    ```bash
    git clone https://github.com/patkarmandar/Pseudo-CPP-Interpreter.git
    cd Pseudo-CPP-Interpreter
    ```
2. Make Script Executable
    ```bash
    chmod +x interpreter.sh
    ```
3. Run the Interpreter
    ```bash
    ./interpreter.sh
    ```
4. Example Session
    ```cpp
    >> cout << "Hello World";
    Hello World
    >> int a = 5;
    >> cout << a;
    5
    ```

### Limitations
- `cin` input is not supported
- Each command triggers recompilation
- Not suitable for large programs
- Intended for learning and experimentation

### Future
- Real REPL behavior
- Syntax validation before compile
- cin support via input buffering
- Unit tests for interpreter logic
