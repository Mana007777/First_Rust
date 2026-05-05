## LEXING
the first step of converting is converting TEXT into Tokens usually
let x = 5; becomes [let] [x] [=] [5] [;]
this is called tokenize which is Lexing

## PARSING
Rust build something called AST Tree (Abstract Syntax Tree)
so basically instead of tokens or texts it changes to something like this
VariableDeclaration
 ├── name: x
 └── value: 5
 So now rust can understand it

 ## Macro Expansion
 when i have wrote println! line this will expand to something else like this :
 std::io::_print(format_args!("Value is {}", x));
 so even format_args! is macro but then it goes into some other phases then it'll
 get rid of the macros then it'll be ready

 ## Name Resolution
then in here rust will resolve the types and other things like when we write 
let x = 5; rust will decide x: i32 and it knows that is integer 

## Borrow Checker 
Rust Analyze memory usage like 
who owns data ? ,,, who borrows it? ,,, is anything unsage?

## HIR --> MIR 
rust simplifies the program into Mid-level IR

## Optimization + LLVM
Rust send MIR to LLVM 
basically LLVM is responsible for removing unnecessary work , optimizes performance
converts to machine code

## LINKING
in this phase rust will combine my code with standart libraries and system libraries and in this phase it'll create final executable file 


<RUNTIME PHASE>

## OS Loads your program
when you run ./main.rs ,, the OS will loads program into RAM and prepare stack & heap and jumps to main()

## Execution starts at main
fn main() --> this is entry point 
-Stack : 
variables will store in stack and it's very fast

Heap : 
data stored in heap , pointer stored in stack

## CPU Executes Instructions
The CPU runs machine code like:

MOV R1, 5
CALL print_function


<FULL PIPLINE>
Rust Code (.rs)
   ↓
Lexing (text → tokens)
   ↓
Parsing (tokens → AST)
   ↓
Macro Expansion
   ↓
Name Resolution
   ↓
Type Checking
   ↓
Borrow Checking
   ↓
HIR → MIR
   ↓
LLVM (optimization + machine code)
   ↓
Linking
   ↓
Executable File
   ↓
OS loads program
   ↓
CPU executes
   ↓
Output appears
