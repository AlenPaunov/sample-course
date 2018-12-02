[slide]
# Problem: Hotel Room

[code-task title="Hotel Room" executionStrategy="csharp-dot-net-core-code" requiresInput]

[code-editor language=csharp]
[/code-editor]

[task-description]
A hotel offers **two types of rooms**: **studio or apartment**.

Write a program that calculates **the price of the whole stay for a studio and apartment**. **Prices** depend on the **month** of the stay:

|       **May and October**      |      **June and September**       |       **July and August**      |
|--------------------------------|-----------------------------------|--------------------------------|
|Studio – **50** BGN/per night   |Studio – **75.20** BGN/per night   |Studio – **76** BGN/per night   |
|Apartment – **65** BGN/per night|Apartment – **68.70** BGN/per night|Apartment – **77** BGN/per night|

The following **discounts** are also offered:

- For a **studio**, in case of **more than 7** stays in **May and October**: **5% discount**.
- For a **studio**, in case of **more than 14** stays in **May and October**: **30% discount**.
- For a **studio**, in case of **more than 14** stays in **June and September**: **20% discount**.
- For an **apartment**, in case of **more than 14** stays, **no limitation regarding the month: 10% discount**.
[/task-description]

[code-io /]
[/code-task]

## Input Data

The input data is read from the **console** and contains **exactly two rows**:

- The **first** row contains the **month** – **May**, **June**, **July**, **August**, **September** or **October**.
- The **second** row is the **number of stays** – **integer within the range** [**0 … 200**].

## Output Data

**Print** the following **two rows** in the console:

- On the **first row**: "**Apartment: { price for the whole stay } lv**".
- On the **second row**: "**Studio: { price for the whole stay } lv**".

**The price for the whole stay must be formatted up to two symbols after the decimal point**.

## Sample Input and Output

|  Input  |                   Output                  |   Comments   |
|---------|-------------------------------------------|--------------|
|May<br>15|Apartment: 877.50 lv.<br>Studio: 525.00 lv.| In **May**, in case of more than **14 stays**, the discount for a **studio is 30%** (50 – 15 = 35), and the **apartment – 10%** (65 – 6.5 =58.5).<br>The whole stay in the **apartment – 877.50** lv.<br>The whole stay **in the studio  – 525.00** lv.|

|   Input    |                  Output                     |
|------------|---------------------------------------------|
|June<br>14  |Apartment: 961.80 lv.<br>Studio: 1052.80 lv  |
|August<br>20|Apartment: 1386.00 lv.<br>Studio: 1520.00 lv.|

## Tips and Tricks

We will read the input data and do the calculations according to the provided price list and the discount rules, and finally print the result.

### Processing the Input Data

According to the task requirements we expect to receive two rows of input data - on the first row **the month in which the stay is planned**, and on the second one - **the number of stays**.

Let's process and store the input data in the appropriate parameters:

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-4-2-images/05.Hotel-room-01.png alt="Code" /]

### Creating Helper Variables

Now let's create and initialize the variables needed for the calculations:

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-4-2-images/05.Hotel-room-02.png alt="Code" /]

When doing an additional analysis of the requirements, we understand that our main logic depends on what **month** is passed and what is the number of **stays**.

In general, there are different approaches and ways to apply the above conditions, but let's examine a basic `switch-case` conditional statement, as in the individual `case` blocks** we will use `if` and `if-else` conditional statements.

### Calculating Prices for Stay in May and October

Let's start with the first group of months: **May** and **October**. For these two months **the price for stay is the same** for both types of accommodation - in a **studio** or in an **apartment**. Therefore, the only thing that remains is to apply an internal condition regarding the **number of stays**, and recalculate **the relevant price** (if needed).

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-4-2-images/05.Hotel-room-03.png alt="Code" /]

### Calculating Prices for Stay in June, September, July and August

To some extent, the **logic** and **calculations** will be **identical** for the following months. 

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-4-2-images/05.Hotel-room-04.png alt="Code" /]

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-4-2-images/05.Hotel-room-05.png alt="Code" /]

### Formatting the Output Data

After calculating the relevant prices and the total amount for the stay, now let's prepare the formatted result. Before that, we should store it in our output **parameters** - `studioInfo` and `apartmentInfo`.

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-4-2-images/05.Hotel-room-06.png alt="Code" /]

In order to calculate the output parameters, we will use the `decimal.Round(Decimal, Int32)` **method** .
This method **rounds the decimal** number up to a **specified number of characters** after the decimal point. To do that, we pass to the method `decimal` (`studioRent`, `apartamentPrice`) and integer (`int`) data types. In our case, we will round the decimal number up to **two digits** after the decimal point.

### Printing the Result

Finally, what remains is to print the calculated results in the console.

## Testing in the Judge System

Test your solution here: [anchor href=https://judge.softuni.bg/Contests/Practice/Index/509#4]https://judge.softuni.bg/Contests/Practice/Index/509#4[/anchor].
[/slide]