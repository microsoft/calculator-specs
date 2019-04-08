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
<!-- How do we measure if things are successful? What’s the metric/KPI to track? Include proposed success metrics here. -->

## Feature Requirements
Below are the 9 core task that a user must be able to complete. We will leverage these core task to evaluate the design of the components. 

1. Users can enter an equation so that it can be viewed on the graph.
2. Users can enter multiple equations so that they can compare plots against each other and see the interactions between the lines.
3. Users can edit equations so that they can see how changes affect the plot and correct mistakes.
4. Users can change the graph viewing window so that they can see different parts of the plot at different levels of detail.
5. Users can change line visual options so that they can clearly differentiate between multiple plots.
6. Users can export graphs so that they can share it with others or incorporate into Office/Teams.
7. Users can easily manipulate secondary variables in equations so that they can quickly understand how changes to equations affect the graph.
8. Users can see traceable key graph features (KGF) as nodes/dots on the equations, and summon other KGFs in a list so that they can better understand the important features of a given function.
9. Users can trace plots so that they can better understand the relationship between variables in the equation on the graph.

## Feature Details and High-Fidelity Concept
The graphing mode is split into four main components: (1) Graphing Area, (2) Keyboard, (3) Equation Input Area, and (4) Settings.

### Graphing Area
See more details about the graphing area component [here](./GraphingArea.md).

### Keyboard 
See more details about the keyboard component [here](./Keyboard.md).

### Equation Input Area
See more details about the equation input area [here](./EquationInputArea.md).

### Settings
See more details about settings [here](./Settings.md).
