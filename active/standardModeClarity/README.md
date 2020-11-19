
## UX Proposal to Fix Issue 138


### Feature Pitch Link
https://github.com/microsoft/calculator/issues/138


### Problem Statement
This is a request for a feature improvement that will bring clarity to how standard mode works on Microsoft’s Calculator.  


### User Need
Users find standard mode in calculator to be confusing since equations are displayed in the UI, but don't follow the order of operations. This creates an incongruent experience for some users and we want to ensure there is no doubt users have the right calculation. 


### Context

#### Definitions
Unary operators: √, X^2, %, 1/x 

Binary operators: *, +, -, ÷  

Immediate mode: The mode that Windows Calculator currently runs where calculations are being made left-to-right immediately for binary operators and immediately after the last entered number for unary operators. 
The issue is occurring because the UI displays the calculations as a multi operator equation and doesn’t explicitly state that the calculations are being made in immediate mode. 

#### Examples

Unary operator example

1 + 4% is calculating 1 + (4%) = 1.04 

Binary number operator example

When users enter a binary operator, the calculator is calculating the sum when the next binary operator is entered or when it receives an equal sign as input. 

1 + 4 * 6 is calculating 1 + 4 =5 first, then taking the result and calculating  5 * 6 = 30 

Note: While this is a UX fix to clear up confusion with immediate-mode execution, we are interested in understanding from the community if a UX fix is sufficient to resolve confusion or if we should consider integrating order of operations into our current standard mode. 



### Proposal
The suggested change is to update the equation above the total of the calculation (image 1) as well as in the History box (image 2). The change will be reflected in these updated equations by showing the output of the calculation as soon as a computation can be made.   

 ![image](https://user-images.githubusercontent.com/2113188/98874495-3703f080-242f-11eb-9c76-5e9d70a7d636.png)
 
Equation above total 

   ![image](https://user-images.githubusercontent.com/2113188/98874630-74687e00-242f-11eb-8d7e-6c79e5ae69ab.png)

Equation in the history box 

By updating these equations, users will be able to follow their calculations as the calculations are being calculated at each stage. 

### UX Proposal 
This shows the updated equation for binary operators. In this example, the user is adding 1 + 2 and then clicks a second binary operator. This will immediately display a calculation both in the equation above and in the history box.  

Note – the purple button signifies the user clicking on input. The screen following a click will be the consequence of the click.  
 
![image](https://user-images.githubusercontent.com/2113188/98876411-19388a80-2433-11eb-90bd-85514401ac93.png)
 
Here’s an example of the user experience in real time by @joseartrivera: 

https://user-images.githubusercontent.com/6334170/81622529-0cfd4300-93a6-11ea-8fc5-12b730f9bb17.gif 

![image](https://user-images.githubusercontent.com/2113188/98876669-9d8b0d80-2433-11eb-95e6-e948e8d6a006.png)

In this example, the user is adding 1 + 2 again, but instead of clicking on a binary operator, the user will click on a unary number operator (x^2), which will immediately act on the last number that was entered. The next action in this case is to click on equal symbol, but if the user had clicked on a binary operator, it would have had the same output. 


### Appendix

Resources:
  https://github.com/microsoft/calculator-specs/blob/247bbb50d6d7f1d02410e967673a7ae095778d4f/active/TransactionalHistory/README.md
