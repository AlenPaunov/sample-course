[slide]
# Problem: Trip

[code-task title="Trip" executionStrategy="csharp-dot-net-core-code" requiresInput]

[code-editor language=csharp]
[/code-editor]

[task-description]
It is strange, but most people start planning their vacations well in advance. A young programmer has **certain budget** and spare time in a particular **season**.

Write a program that accepts **as input the budget and season**, and **as output** displays programmer's **vacation place** and **the amount of money they will spend**.

**The budget determines the destination, and the season determines what amount of the budget will be spent**. If the season is **summer**, the programmer will go **camping**, if it is **winter - they will stay in a hotel**. If it is in **Europe**, **regardless of the season**, the programmer will stay in a **hotel**. Each **camp** or **hotel**, **according to the destination**, has **its own price**, which corresponds to a particular **percentage of the budget**:

- If **100 BGN or less** – somewhere in **Bulgaria**.
  - **Summer** – **30%** of the budget.
  - **Winter** – **70%** of the budget.
- If **1000 BGN or less** – somewhere on the **Balkans**.
  - **Summer** – **40%** of the budget.
  - **Winter** – **80%** of the budget.
- If **more than 1000 BGN** – somewhere in **Europe**.
  - Upon travelling in Europe, regardless of the season, the programmer will spend **90% of the budget**.
[/task-description]

[code-io /]
[/code-task]

## Input Data

The input data will be read from the console and will consist of **two rows**:

- On the **first** row we receive **the budget** - **real number** in the range [**10.00 … 5000.00**].
- On the **second** row – **one** of two possible seasons: "**summer**" or "**winter**".

## Output Data

**Two rows** must be printed in the console.

- On the **first** row – "**Somewhere in {destination}**" among "**Bulgaria**", "**Balkans**" and "**Europe**".
- On the **second** row – "{**Vacation type**} – {**Amount spent**}".
  - The **Vacation** can be in a "**Camp**" or "**Hotel**".
  - The **Amount** must be **rounded up to the second digit after the decimal point**.

## Sample Input and Output

|      Input     |                Output                |
|----------------|--------------------------------------|
|50<br>summer    |Somewhere in Bulgaria<br>Camp - 15.00 |
|75<br>winter    |Somewhere in Bulgaria<br>Hotel - 52.50|
|312<br>summer   |Somewhere in Balkans<br>Camp - 124.80 |
|678.53<br>winter|Somewhere in Balkans<br>Hotel - 542.82|
|1500<br>summer  |Somewhere in Europe<br>Hotel - 1350.00|

## Tips and Tricks

Typically, as for the other tasks, we can separate the solution into the following parts: reading the input data, doing calculations, printing the result.

### Processing the Input Data

While reading carefully the requirements, we understand that we expect **two** rows of input data. The first parameter is a **real number**, for which we need to pick an appropriate variable type. For higher level of calculation accuracy we can pick `decimal` as a variable for the budget and - `string` for the season. 

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-4-2-images/02.Trip-01.png alt="Code" /]

<table><tr><td><img src="https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/alert-icon.png" style="max-width:50px" /></td><td>Always take into consideration what **value type** is passed in the input data, as well as what type these need to be converted to, in order for the program conditions to work properly!</td>
</tr></table>

**Example**: When you need to do money calculations in a task, use `decimal` for higher level of accuracy.

### Calculations

Let's create and initialize the variables needed for applying the logic and calculations.

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-4-2-images/02.Trip-02.png alt="Code" /]

Similarly to the example in the previous task, we can initialize variables with some of the output results, in order to spare additional initialization.

When examining once again the problem requirements, we notice that the main distribution of where the vacation will take place is determined by the **value of the budget**, i.e. our main logic is divided into two cases: 
- If the budget is **less than** a particular value.
- If it is **less than** another value, or is **more than** the specified border value. 

Based on the way we arrange the logical scheme (the order in which we will check the border values), we will have more or less conditions in the solution. **Why?**

After that, we need to apply a condition to check the value of the **season**. Based on it, we will determine what percentage of the budget will be spent, as well as where the programmer will stay - in a **hotel** or a **camp**.

### Writing the Program Code

Example of one of the possible solution approaches:

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-4-2-images/02.Trip-03.png alt="Code" /]

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-4-2-images/02.Trip-04.png alt="Code" /]

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-4-2-images/02.Trip-05.png alt="Code" /]

We can always initialize a value of the parameter and then apply only one condition. **This spares us one logical step**.

For example, the following block:

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-4-2-images/02.Trip-03.png alt="Code" /]

can be shortened to this:

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-4-2-images/02.Trip-06.png alt="Code" /]

### Printing the Result

What remains is to display the calculated result in the console:

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-4-2-images/02.Trip-07.png alt="Code" /]

## Testing in the Judge System

Test your solution here: [anchor href=https://judge.softuni.bg/Contests/Practice/Index/509#1]https://judge.softuni.bg/Contests/Practice/Index/509#1[/anchor].
[/slide]