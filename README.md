# movfuscator

How to use:

- Open the folder and run app.py
- go to http://localhost:5000/
- drag and drop your file
- pray the returned file works !!!

* IMPLEMENTATION AND VERY IMPORTANT THINGS TO CONSIDER *

  This implementation of the movfuscator tries to use a different approach when compared to the one we had to use as inspiration. We used the part where he made macros and took it to another level.
  This movfuscator heavily relies on the idea that the may be a bijection between any two instructions, one is the classic and one is the movfuscated. In other words, we believe that any basic instruction can be rewritten using only movs. This, of course, comes with its hurdles and limitations.

  IMPLEMENTED:

  - virtualized registers, the stack, variables and labels (meaning that they replace the in-memory counterparts during coding)
  - added a lot of new instructions as macros, with most of them having the same name, but being prefixed by "m_"
  - arithmetic, logic and boolean calculations
  - conditional and unconditional jumps
  - push, pop, function calling (with params and local vars)
  - syscall for printing strings
 
  KNOWN ISSUES / NOT IMPLEMENTED YET:

  - arrays (they are implementable but the deadline was coming closer so we had to cut corners)
  - all jumps/function calls require a return adress to be inputted manually as a label to come back to (check m_jmp implementation). This is automatically handles by the parser
  - 'lea' as adresses are also virtualized
  - reading from memory using pointer arithmetic (aside from the stack, which was implemented. NOTE: when adressing relative to %ebp (or mbp in this case), use m_movmbp)
  - some instructions weren't movfuscated like: int, jmp (when looping main)

Our goal was to make the movfuscator in our OWN way, rather than translating the already existent movfuscator.
