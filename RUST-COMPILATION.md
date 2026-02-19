## RUST : 
# STEP 1 : Lexing and parsing
-> The Rust compiler(rustc) reads your source code as text
-> Lexer breaks text into tokens 
-> Parser Turns tokens into a syntax tree (AST) reprsenting the structure of your code 

# STEP 2: Name Resolution and Type checking
-> Rust resolves what each variable , function , and macro refers to
-> Then it checks types and ensure everything matches Rust's strong typing rules

# STEP 3 : Borrow Checker & Lifetime Analysis
The compiler checks :
-> Who owns the data?
-> Who is allowed to use it?
-> When should it be destroyed (freed from memory)?
Rust checks all of this while compiling, not while running.
That’s why Rust doesn’t need a garbage collector.

# STEP 4 : Intermediate Representations ( HIR & MIR )
Rust converts AST into simpler code forms internally
HIR (High Level intermediate representation) -> Simplified RUST
HIR removes a fancy syntax , shortcuts , ambiguities 

MIR (Mid Level Intermediate Representation) -> verified RUST
MIR is where rust verifes the ownership rules s, borrow rules , lifetimes , moves & drops
This is the stage that prevents crashes and memory bugs.

# Step 5 : LLVM ( Close to machine instructions ) :
After MIR, Rust translates instructions into LLVM IR which is very close to CPU instructions.

# Step 6: Linking
Rust combines your machine code with Rust standard library code.
Example: println! relies on Rust’s library to talk to your operating system and display text.
The result: a single executable file (main or main.exe).

# Step 7: Running the Program
When you type:
./main

The operating system:
1- Loads the executable into memory.
2- Starts running the instructions from main.
3- Calls the Rust library code for println!.
4- Displays "Hello, world!" on your terminal.
5- Program finishes, OS cleans up memory.

Result: You see Hello, world!!
