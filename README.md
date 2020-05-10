# JAVASCRIPT ENGINE

## Javascript Engine 

- reads JS code 
- converts it to machine code (binaries)
- ie V8 by Google (written with C++)

## ECMAscript Engine 

- standard in JS 


## What is Inside JS Engine 

1. PARSER - lexical analysis; breaks the code into tokens
2. AST - abstract syntax tree
3. INTERPRETER - JS is mostly interpreted <br>
               - translates and reads the files line by line <br>
               - no conversion to lower language first; goes straight to running the code line by line <br>
               - perfect for JS on the fact that the program has to be user friendly on the web <br>
               - it will get slower and slower though; ie it always has to iterate a loop whereas compiler will optimize this<br>
4. COMPILER - goes through the source code once to understand and optimize it (by compiling it to another programming language) <br>
            - takes a little bit more time to start up because of compiling but optimizes code, ie replacing a function with just its return 
5. JIT COMPILER - combination of both <br>
                - the INTERPRETER part will run the code line by line ( bytecode) <br>
                - a PROFILER watches the INTERPRETER and does optimization on it simulataneously (passes the problematic code to COMPILER) <br>
                - COMPILER replaces parts of the bytecode => OPTIMIZED CODE 
                
## 
