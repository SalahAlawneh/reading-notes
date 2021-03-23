# THE CALL STACK and Debugging

## THE CALL STACK
- the call stack is a way that used from JavaScript engine like google chrome v8 JavaScript, it track the inerperter to know where is it in the script.
- multible functions thats whats happen in the interperter, the call stack will stack the function that running, and the calling functions inside of it.
- when the stack finish stacking an function inside the script with all of it's calling functions, it will continue working in the script to the next stack.
- the call stack in JavaScript engine is a single call stack, and it's can do just one invoked function at a time `including the invoked inside it`
- the call stack is synchronous because the stack is managing calling functions, that mean it's know the order of calling functions`=> the order of stack frame`
- the stack frame is location in the stack that store the invoked function temporarily, it's parameters and variables.
- the mechanism that call stack known as data structor used last in first out.
- stack overflow happen when the stack inside the JavaScript engine couldn't handle storing inside the stack frame, like calling function inside of it's self.

## Debugging
- dubuggin and dealing with error massages is a crusial part in life of a programmer, and like any skill it will be more effient with time.
- the basic types of errors are:
  - type error
  - reffrence error
  - range error
  - syntax error
- `console.trace()` it give all of the function were in the call stack up to the point the you write it.
