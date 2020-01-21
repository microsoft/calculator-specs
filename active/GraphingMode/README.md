# Graphing Mode

## Problem Statement
High school algebra is the gateway to mathematics and all other disciplines of STEM. However, algebra is the single most failed course in high school, as well as the most failed course in community college ([Washington Post](https://www.washingtonpost.com/news/answer-sheet/wp/2017/09/15/of-course-algebra-is-important-its-also-a-huge-problem/)). Graphing capabilities in their daily tools are essential for students who are beginning to explore linear algebra as early as 8th grade. Physical graphing calculators can be expensive, software solutions require licenses and configuration by school IT departments, and online solutions are not always an option. At present, Windows Calculator does not currently have the needed functionality to meet the demands of students.

## Evidence or User Insights
Graphing calculator provides an accessible and engaging method for students and teachers to learn and teach. Research has shown that graphing calculators foster conceptual understanding of developmental math students (Hopkins & Amelia, 1998; Laughbaum, 2002, 2003; Shore & Shore, 2003) by:
* Increased speed 
* Opportunity to study rich mathematics through technology
* Make connections through different data representations
* Deeper understanding on “why”

Graphing Calculator is also the top requested feature in [Feedback Hub](https://aka.ms/AA43wie).

## Proposal
Empower students to learn mathematics by improving conceptual understanding and attitudes towards math by adding graphing support to Windows Calculator targeting grades 8-12 students and teachers (math/physics). With graphing calculator, we can improve learning outcomes of students by increasing engagement and visualization of math equations.

## Goals and Non-Goals
**Goals**
* Provide a great baseline graphing calculator experience in Windows Calculator
* Support all [US common core math curriculum](http://www.corestandards.org/Math/), including:
  * Ability to build and interpret functions
  * Understand linear, quadratic, and exponential models
  * Trigonometric functions
  * Reason with equations and inequalities

**Non-Goals**
* Support advanced calculus or statistics functionality
* Parity with more advanced graphing solutions 

## Success Criteria
Success with the graphing calculator can be measured by monthly active users, engagement time, and retention.

## Overview
The specification is divided up into three sections:
1. Key graphing calculator scenarios
2. Feature requirements as highlighted by the key user scenarios
3. Specifics about information architecture and components that enable the key graphing scenarios

In order to set context on the feature requirements and components needed for the graphing calculator, a set of 11 key user scenarios were established. The golden path for each scenario will be described within the specification. With the key user scenarios establish, requirements for each component and graphing calculator were extracted and documented.

Windows calculator is built on top of the [Windows Fluent design system](https://www.microsoft.com/design/fluent/#/windows) leveraging the style, design patterns and controls. With the graphing calculator feature, the common controls within the Windows Fluent design system was not enough. We extended the design system, by creating specific components for the graphing calculator including the equation input and graph area. We stressed test the components using the key scenarios. By establishing a set of common controls, we enable the community to extend the graphing calculator and enable new user scenarios. 

### Scenarios
11 user scenarios were established and prioritized based on the core task that students and teachers need to complete within a classroom setting. Each scenario helped align and inform the feature requirements for each of the areas of the graphing calculator. The golden path of each key scenario will be described through a series of storyboards.

| Order | Scenario | Component Area(s) |
|:------:|:----------|:-------------------|
| 1 | User can enter an equation so that they can see the graphed plot. | Graphing area, Equation area, Keyboard area |
| 2 | User can enter multiple equations so that they can compare plots against each other and see the interactions between the lines. | Equation area, Keyboard area |
| 3 | User can edit an equation so that they can see how changes affect the plot and correct mistakes. | Equation area |
| 4 | User can change the graph viewing window so that they can see different parts of the plot at different levels of detail. | Graphing area |
| 5 | User can export a graph so that they can share it with others or incorporate into Office/Teams. | Graphing area |
| 6 | User can analyze equations for common features and summon key graph features in a list so that they can better understand the important features of a given function. | Equation area |
| 7 | User can easily manipulate secondary variables in equations so that they can quickly understand how changes to equations affect the graph.  | Equation area |
| 8 | User can change graph visuals so that they can clearly differentiate between multiple plots. | Graphing area |
| 9 | User can trace plots with a mouse or gesture so that they can better understand the relationship between variables in the equation on the graph. | Graphing area |
| 10 | User can use their keyboard to activate a crosshair so that they can better understand the relationship between variables in the equation on the graph. | Graphing area |
| 11 | User can see traceable key graph features as nodes/dots on the equations so that they can better understand the important features of a given function. | Graphing area |
| Future | User can enter a set of points so that they can see the multiple points graphed. | Graphing area, Equation area, Keyboard area |
| Future | User can bound their equations so that they can create step functions. | Equation area |

## Feature Details and High-Fidelity Concept
Graphing calculator can be split into four main components: (1) Graphing Area, (2) Keyboard, and (3) Equation Input Area. Leveraging the [US common core standards](http://www.corestandards.org/Math/), and the key user scenarios we were able to start defining the requirements needed for each of these components.

### Graphing Area
| # | Requirement | Notes |
|---|:-------------|:-------|
| 1 | User can change the viewing window by dragging and zooming the graphing area | Leveraging touch and mouse, a user can change the zoom level |
| 2 | User can zoom the viewing window via onscreen buttons | Keyboard accessibility support |
| 3 | User can reset the viewing window to "best fit" via onscreen buttons |  |
| 4 | User can export the graph to other applications |  |
| 5 | User can save the graph as an image | Default file name should be prefixed with "graph". Should support .png, .jpg, .jpeg, and .svg. |
| 6 | Users can change the min and max x/y values for the graph window. | Users  should be able to input a specific value of the min and max. |
| 7 | Users can switch between operating in degrees and radians. |  |
| 8 | The x and y intercepts are highlighted on the graph |  |

See more details about the graphing area component [here](./GraphingArea.md).

### Keyboard 
| # | Requirement | Notes |
|---|:-------------|:-------|
| 1 | User can input numerals and symbols for supported equation types via the keyboard |  |
| 2 | Users can both submit equations and leverage the '=' symbol in equations | The equals button in other calculator modes is submit. Graphing mode needs to distinguish the two. |
| 3 | Users can input _x_ and _y_ variables. |  |

See more details about the keyboard component [here](./Keyboard.md).

### Equation Input Area
| # | Requirement | Notes |
|---|:-------------|:-------|
| 1 | User can enter an equation with 1 or 2 variables (x, y) | An equation is an expression through an equality (e.g., =) between the two algebraic quantities or a set of quantity. We will officially support the following equation types: linear, quadratic, polynomial, trigonometric, radical, exponential, inequality, and conics/circles. |
| 2 | Equations are displayed in rich MathML styling format |  |
| 3 | Users can input their equations with freeform input |  |
| 4 | User can toggle the visibility of an equation |  |
| 5 | Users can change the color and style of equation lines |  |
| 6 | Users can manipulate a variable within an equation to see the effect it has on the graph |  |

See more details about the equation input area [here](./EquationInputArea.md).

### Layout

Windows Calculator is desgined to be responsive to window size changes. As such, we must support both large and small window sizes. Due to the complexity of graphing equations, we are optimizing for larger windows layouts, but graphing calcualtor should work great for smaller sized windows as well. See more details about layout [here](./Layout.md).
