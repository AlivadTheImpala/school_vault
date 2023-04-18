## Debugger Stack

![[Screenshot 2023-04-17 at 16.55.08.png]]
From left to right
1. Step Over: Execute the current line of code and continue to the next line.
2. Step Into: Step into the current line. For example, if the line contained a function, it would continue with the debugger inside this function.
3. Step Into my Code: Step into the line being executed but continue until it finds code you have written. For example, if you're stepping into a third-party library code that later calls your code, it will not show you the third-party code, instead of continuing through until it returns to the code that you have written.
4. Step Out: Return back out of the current code to the function or method that called it. The opposite of the _Step In_ action.