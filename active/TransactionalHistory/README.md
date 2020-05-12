# Transactional History

### Problem Statement
Calculator in Standard Mode displays equations such that users would expect order of operations rules to be followed when in reality the calculator runs in 'immediate execution' mode similiar to a simple pocket calculator.

![image](https://user-images.githubusercontent.com/6334170/81622207-29e54680-93a5-11ea-8b22-e0f9990f466c.png)

### Evidence or User Insights

This is a complaint we often hear from users and has also been documented in [#138](https://github.com/microsoft/calculator/issues/138)

### Proposal
After we calculate the result of a binary operation due to the user inputting a second binary operator we will check to see if the Calc Engine is in immediate execution mode. If these conditions are met, the current equation will be 'completed' and added to the history pane. 

This will cause the 'running history' above the result text to clear. At which point we will add the answer from the previous equation to the 'running history' followed by the binary operation the user inputted. 

(<kbd>2</kbd><kbd>+</kbd><kbd>3</kbd><kbd>×</kbd><kbd>5</kbd> becomes <kbd>5</kbd><kbd>×</kbd><kbd>5</kbd> instead)

![prototype](https://user-images.githubusercontent.com/6334170/81622529-0cfd4300-93a6-11ea-8fc5-12b730f9bb17.gif)

### Goals

- Communicate to the user that standard mode is running in "immediate execution mode" by never displaying an equation that looks like it should be using order of operations.
- Accurately display the equation being calculated to the user.

### Non-Goals
- Make standard mode respect order of operations.

### Success Criteria
- Measure community reaction via Github and Feedback hub

### High-Fidelity Concept
Working prototype can be found here:
https://github.com/joseartrivera/calculator-1/tree/standardprototype

