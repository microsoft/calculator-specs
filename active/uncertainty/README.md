## ADDING UNCERTAINTY CALCULATIONS
<!-- See comments in Markdown for tips on how to use this spec template. -->

<!-- Update with a concise title describing your feature. -->

### Feature Pitch Link
https://github.com/Microsoft/calculator/Issues/1139
<!--
Update this to reference the approved feature pitch, as that is where ongoing discussion will occur.
-->

### Problem Statement
Scientific calculations are an area of Microsoft Calculator that has not yet been adequately addressed. It cannot be relied upon to provide precise and accurate measurements for those doing scientific calculations: from highschool science students, all the way up to professional scientists. Quantifying the level of uncertainty in one's measurements is a crucial part of science. Because no measurement can be perfect, there must be an uncertainty on each measurement. This helps to determine the limitations on the measurements and therefore, the subsequent conclusions. 

To determine the uncertainty of a single measurement is **not** the goal of this feature. This is subjective and usually done by the scientist. However, calculations with these measurements, each with pre-determined uncertainties CAN be accomplished programmatically by this calculator. This is the problem trying to be solved. 
<!--
What problem are we trying to solve? Who"s the target audience? Is there a customer need or pain
point we need to remedy? Is there a business goal or metric we are trying to improve? Do we have a
hypothesis we want to prove or disprove?
--> 

### Evidence or User Insights
This feature is a key step to broadening the use of Microsoft Calculator to many more users. Currently, calculations with uncertainty in measurements cannot be done. This would force the user to use a scientific calculator or another calculator app. I know that all highschool students must deal with this in upper-year sciences, especially physics and chemistry. As well, labs require one to take precise measurements, all of which have an uncertainty. Furthermore, in schooling and other workplaces, it is not always practical for someone to have a scientific calculator on them to compute these calculations. However, they almost always have a laptop, which has Microsoft Calculator. For this reason, adding uncertainty calculations to Microsoft Calculator is essential. 
<!--
Why should we do this? Potential sources of data: Feedback Hub, other GitHub issues, other anecdotes
from listening to customers in person or online, request from another team, telemetry data,
user research, market or competitive research.
-->

### Proposal
The proposal for a solution is to expose this in a setting in the Scientific Mode of the calculator (as opposed to a completely new mode). This new setting would allow users to enter uncertainties along with their measurements. The calculator would then compute the final answer, along with the correct final uncertainty. As well, uncertainties are linked with significant figures (as seen in the high fidelity concept below). This may be combined with that feature as well. 
<!--
How will the solution/feature help us solve the problem?
How will it meet the target audience"s needs? If there are business goals or metrics,
how does this improve them?
-->

### Goals and Non-Goals
* Goals:
   * allow users to do calculations with measurements that have pre-determined uncertainty
   * broaden the user-base and usability of Microsoft Calculator to the scientific community
   * include more complex calculations, reducing the need for an alternate scientific calculator
* NonGoals:
   * this calculator does not tell the user the uncertainty of a single measurement. Those must be subjectively determined by the user. 
<!--
Goals:
What do you want to accomplish with this idea? These are not feature requirements,
but rather broad goals you are trying to accomplish.
-->

<!--
Non-Goals:
What do you want to accomplish with this idea? These are not feature requirements,
but rather broad goals you are trying to accomplish. -->

### Success Criteria
The calculations involving measurements with pre-determined uncertainties must be correct and reliable. 
<!--
How do we measure if things are successful?
What"s the metric/KPI to track? Include proposed success metrics here.
-->

### Feature Requirements
Users will be able to enter a measurement (values). Each of those measurements may also have an uncertainty, that the user will enter in. The user can do mathematical calculations on these: (addition, multiplication, etc.) Then, the calculator will output the correct measurement as well as the correct uncertainty. As well, there should be an option/button to convert the uncertainty from absolute to relative and vice versa (see below for more details) Lastly, the uncertainty will need to be rounded to one or two significant figures, and then the value itself rounded to the number of decimal places in the uncertainty (see below for more details).
<!--
Specific feature requirements or user scenarios.
These typically starts with statements like "User can" or "API supports".
Leave details for next section.
-->

### Feature Details and High-Fidelity Concept
This feature will correctly compute measurements with uncertainties. There are multiple deterministic rules for how to handle these calculations.     
* Types:
Firstly, there are two types of uncertainties: **absolute and relative**. Absolute uncertainties are values that explicitly tell you how uncertain a measurement is, in the same units. An example of 2.0 grams +/- 0.5 grams, is an example of a measurement with an absolute uncertainty. Relative uncertainties are percentages of the original measurement. In the same example, it would be 2.0 grams ± 25%. Microsoft Calculator would need to allow for both types of uncertainties, and deal with the calculations accordingly. As well, the calculator must be able to convert absolute to relative, and vice versa. To convert relative to absolute, one would multiply the relative percentage by the measurement value. To convert absolute to relative, one would divide absolute uncertainty by the measurement, and then multiply by 100%. These calculations include addition/subtraction, multiplication/division, multiplying by a constant, averaging repeated measurements, and powers of a measurement with an uncertainty. 

* **Addition/Subtraction:**
When adding or subtracting measurements with uncertainties, the **absolute uncertainties** must be **added** together. If the measurement included a relative uncertainty, it would first have to be converted to an absolute uncertainty. Then, the uncertainties, along with the measurements, are added together. 
> * 5.0 ± 0.1 mm + 2.0 ± 0.1 mm = 7.0 ± 0.2 mm 
> * 5.0 ± 0.1 mm - 2.0 ± 0.1 mm = 3.0 ± 0.2 mm
* **Multiplication/Division:**

When multiplying or dividing measurements with uncertainties, the **relative uncertainties** are **added**. If the absolute uncertainties are given, the calculator must convert it to relative uncertainty before adding the quantities. The user can then have the option for the final uncertainty to remain in relative uncertainty, or be converted back to absolute. 
> * 5.0 ± 0.1 mm x 2.0 ± 0.1 mm = (5.0 × 2.0) ± ((0.1/5 × 100%) + (0.1/2 × 100%)) = 5.0 ± 2% x 2.0 ± 5% = 10.0 ± 7%
* **Multiplying/Dividing by a Constant**

When multiplying or dividing by a constant, both absolute and relative uncertainties can be handled. A constant can be any number (12, pi, -4)
  * A measurement with an absolute uncertainty
 
  To do this, one would also multiply/divide the uncertainty by the constant. 
  > * 2 × (5.0 ± 0.1 mm ) = 10.0 ± 0.2 mm
  * A measurement with a relative uncertainty
  
  To do this, only the measurement value is multiplied/divided. There is *no change* in uncertainty.
  > * 2 × (5.0 ± 2%) = 10.0 ± 2% (Note: When converted back to absolute uncertainties, it is the same value as above)
* **Averaging Values:**

When finding the average/mean of a number of repeated values, the uncertainty in the average is **one-half** of the range between the maximum and minimum measurements. 
> (5.0 + 4.8 + 5.1 + 5.1 + 5.5 + 4.5) / 6 = 5.0 ± ((5.5-4.5)/2) = 5.0 ± 0.5

* **Powers of an Uncertain Measurement**

To do powers of a measurement with uncertainty, one could simply multiply or divide that measurement a certain number of times. For example 5^2 = 5x5. However, there are limitations to this. First of all, it takes longer to type in the calculator, and thus is not most efficient. As well, the math becomes more complex if there are fractional powers. An alternative way is the one shown here. One must first convert the uncertainties to **relative** uncertainties. Then, the relative uncertainty is multiplied by the number inside the power. 
> * (5 cm ± 5%)^2 = (5^2 ± (2 × 5%)) cm^2 = 25 cm^2 ± 10%
> * (10 m ± 3%)^3 = (10^3 ± (3 × 3%)) m^3 = 1,000 m^3 ± 9%
> * (100 m ± 2%)^0.5 = (100^0.5 ± (0.5 × 2%)) m^0.5 = 10 m^0.5 ± 1%

* **Important Note about Significant Figures**

Experimental uncertainties like these have a specific way of being stated. Some scientists and teachers prefer all these uncertainties to be rounded to **ONE** significant figure. Then, the number of decimal places in the uncertainty (with one significant figure) is the number of decimal places allowed on the *value*
> * 9.81734 ± 0.0287 m/s^2 should be written as 9.82 ± 0.03 m/s^2. The uncertainty is rounded to one significant figure, and then the value itself is rounded to the number of decimal places in the uncertainty. 

In some cases, when the uncertainty is small, two significant digits are allowed in the uncertainty. The rules would be the same. Perhaps the implementation of this would be to allow the user to pick how many significant figures are in the final uncertainty. As well, the rounding of uncertainties to one significant figure would need the implementation of significant figure setting/mode, which could be implemented alongside or including this feature. 



<!--
Show a detailed look at the experience. Make sure you cover all possible flows.
Include any alternative designs that were considered. Call out if strings being used are proposed
or final. Don't forget about edge and error cases. Keep in mind compliance and other quality
considerations. This should take the form of polished design comps and/or screenshots combined
with textual descriptions.
-->

### Appendix
<!--
Phases:
  For larger projects, it may be useful to break the plan into phases (e.g., crawl, walk, run).
  If applicable, detail that plan here.

Risks and Open Issues:
  Call out any open issues, if applicable. Waht's left to solve or agree on?

Resources:
  Include links to any additional documentation or resources, if applicable.
-->https://sciencing.com/how-to-calculate-uncertainty-13710219.html
http://spiff.rit.edu/classes/phys273/uncert/uncert.html
https://web.ics.purdue.edu/~lewicki/physics218/significant
https://www.thestudentroom.co.uk/showthread.php?t=2661762




<!-- REMEMBER: Rename this to README.md before sending out your PR. -->
