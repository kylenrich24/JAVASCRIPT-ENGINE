# JAVASCRIPT ENGINE

## Javascript Engine 

- reads JS code 
- converts it to machine code (binaries)
- ie V8 by Google (written with C++)

## What is Inside JS Engine

- the bigges thing is reading our code and executing it
1. MEMORY HEAP - we need a place to store and write information (ie variables, ...)
               - all programs are just read and write operations
               - memory allocation
               - watch out for MEMORY LEAKS (when garbage collection fails)
2. CALL STACK - a place to run our code in order
              - keeps track of where we're at in our code in execution
              - watch out for STACK OVERFLOW
              
## Single Threaded

- only one instruction at a time - 1 call stack 
- no instructions in parallel
- what if we have an instruction that takes a while to resolve

## JS Runtime

- we also have JS RUNTIME on top of the CALL STACK
- if we have an instruction that runs for a while, we can't continue on in our CALL STACK
- JS RUNTIME has WEB API that runs in the background - WEB API is the WINDOW OBJECT
- So if CALL STACK sees async code (ie event listeners, HTTP request, etc) it goes, "this is not for me, send it to WEB API)
  and it continues executing
- When async code is done WEB API sends it to CALLBACK QUEUE
- EVENT LOOP regulates CALL STACK and CALLBACK QUEUE; if call stack is empty queue the function call

## What is Inside JS Engine II

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
                
## Optimized Code

1. Inline Caching - replacing codes with just the 'results' of it, so any instance of it will be optimized
2. Hidden Classes - instantiate your classes in order

```javascript
function Animal(x,y) {
  this.x = x
  this.y = y
}

const obj1 = new Animal(1,2)
const obj2 = new Animal(3,4)

obj1.a = 30       // compiler will be slower here because of orders
obj1.b = 100
obj2.b = 30
obj2.a = 100
```

- write codes that are predictable to humans and to the computer

## ECMAscript Engine 

- standard in JS 
