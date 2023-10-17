# 2022-2023 - PROJECT 5 - ALGORITHMS & DATA STRUCTURE - TEAM 2

## Technical Specifications

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

<details>
<summary>📖 Table of content</summary>

- [2022-2023 - PROJECT 5 - ALGORITHMS \& DATA STRUCTURE - TEAM 2](#2022-2023---project-5---algorithms--data-structure---team-2)
  - [Technical Specifications](#technical-specifications)
    - [I. Introduction of the project](#i-introduction-of-the-project)
      - [A. Client](#a-client)
      - [B. Goal of the project](#b-goal-of-the-project)
      - [C. Team Members](#c-team-members)
    - [II. Solution](#ii-solution)
      - [A. Descritpion](#a-descritpion)
      - [B. Software architecture](#b-software-architecture)
      - [C. Technical constraints](#c-technical-constraints)
        - [1. The tanks](#1-the-tanks)
        - [2. The Complexity](#2-the-complexity)
        - [3. C# coding convention](#3-c-coding-convention)
        - [4. Objects description](#4-objects-description)
        - [5. Implementation](#5-implementation)
      - [D. How is it work ?](#d-how-is-it-work-)
      - [E. Program architecture diagram](#e-program-architecture-diagram)
    - [III. Further considerations](#iii-further-considerations)
      - [A. Cost estimation](#a-cost-estimation)
      - [B. Security](#b-security)
      - [C. Accessibility](#c-accessibility)
    - [IV. Success evaluation](#iv-success-evaluation)
    - [V. Glossary](#v-glossary)

</details>

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

### I. Introduction of the project

#### A. Client

The client is the House Krug Champagne[^1], conceptor of champagne since 1843. Based in Reims, they try to make each year the best products thanks to the respect of the vineyards. It's important to note that Krug is renowned for its production of high quality champagne and is considered one of the most prestigious houses in the Champagne region.

In addition, Krug has several labels that testify to the quality of its champagnes. One of the most prestigious labels that Krug has is "Champagne de Prestige", which designates the most upmarket and exceptional champagnes.

It also offers Grande Cuvée champagne (currently the 171st edition), Rosé, Millésime, Clos Mesnil, Clos d'Ambonnay and Collections, each with a unique history.

Krug is classified has the title of "Récoltant-Manipulant" (RM)[^2], which means that it is completely independent. It produces its own grapes and makes its own champagne in its own facilities.

#### B. Goal of the project

The objectif of the project is to implement a program who blend many wines to realize an unique blending with the lowest complexity[^3] for the program and the least loss of wine in the tanks.

#### C. Team Members

| ROLE | NAME |
| :-: | :-: |
| Project Manager | [Clement CATON](https://github.com/ClementCaton) |
| Program Manager | [Vivien Bistrel TSANGUE CHOUNOU](https://github.com/Bistrel2002) |
| Tech Leader | [Grégory PAGNOUX](https://github.com/Gregory-Pagnoux) |
| Software Engineer | [Clémentine CUREL](https://github.com/Clementine951) |
| Quality Assurance | [Alexandre BOBIS](https://github.com/AlexandreBobis) |

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/aqua.png)

### II. Solution

#### A. Descritpion

We have a configuration file where the user can enter the capacity of each tanks manually and also the formula of blending.

After entering all the parameters and validating them, the program calculates, as quickly as possible, the path between the tanks that the wine must take for the blends with the least amount of loss.

The user has a return of numbers of steps, i.e. the numbers of transfer of wine (in different tanks or same tanks that an other wine), the similarity with the original formula and which tank has been useful for the blending.

#### B. Software architecture

The software could be developed using a layered architecture[^4], with each layer responsible for a specific set of functionalities.

The presentation layer[^5] would be the user interface that the Cellar Master[^6] and her team would interact with.

The business logic layer[^7] would handle the core functionality of the software, including the blending algorithms and data validation. This layer would be developed using C# and .NET 6.0's latest features, such as C# 10 and the new record types, to ensure maximum performance and maintainability.

The data access layer[^8] would be responsible for handling data storage and retrieval, such as keeping track of the tanks and their current contents. This layer would be developed using .NET 6.0's EF Core[^9] framework, which provides a powerful and flexible ORM[^10] (Object-Relational Mapping) toolset for working with databases.

To ensure that the software is reliable and fault-tolerant, it would be designed using the SOLID principles[^11] and unit tested extensively using .NET 6.0's built-in testing framework.

Overall, this architecture would provide a robust and scalable software solution for the Krug Champagne blending process, built using the latest and most advanced technologies in the .NET ecosystem.

#### C. Technical constraints

##### 1. The tanks

Tanks cannot be half full. They must be either empty or completely full. This constraint must be taken into account with great importance, as oxidation[^12] of the wine must be avoided.

##### 2. The Complexity

The most important thing to consider throughout the project is to have an `O(X)` with X = `1`, `log n` or `n`. The values to be avoided absolutely for the efficiency of the program, is an `O(X)` with X = `n²`, `2^n` and `n!`.

##### 3. C# coding convention

| Notation | How | Usage | Example |
| :-: | :-: | :-: | :-: |
| Pascal Casing | we attach each word and capitalize it to know where the next word starts (ex: DataService) | naming Class | <pre>```public class DataService```<br>```{```<br>```}```</pre> |
|  |  | naming record | <pre>```public record PhysicalAddress(```<br>```)```</pre> |
|  |  | naming structure | <pre>```public struct ValueCoordinate```<br>```{```<br>```}```</pre> |
|  |  | naming interface | <pre>```public interface IWorkerQueue```<br>```{```<br>```}```</pre> |
|  |  | naming public members | <pre>```public class Example```<br>```{```<br>    ```public IWorkerQueue WorkerQueue { get; init; }```<br>```{```</pre> |
| Camel Casing = _ | prefix them | naming private or internal fields | <pre>```public class DataService```<br>```{```<br>    ```private IWorkerQueue _workerQueue;``` <br>```}```</pre> |
|  | prefix `s_` | static fields that are private or internal | <pre>```public class DataService```<br>```{```<br>    ```private static IWorkerQueue s_workerQueue;```<br>```}```</pre> |
|  | prefix `t_` | thread static fields that are private or internal | <pre>```public class DataService```<br>```{```<br>    ```[ThreadStatic]```<br>    ```private static TimeSpan t_timeSpan;```<br>```}```</pre> |
| dot = . |  | separate name too long | <pre>```var currentPerformanceCounterCategory = new System.Diagnostics.```<br>    ```PerformanceCounterCategory();```</pre> |
| comment = // | start each line with two slashes and an uppercase letter and finish the comment by a period. | give more information of the code | <pre>```// The following declaration creates a query. It does not run the query.```</pre> |

- Important :

Write only one statement or declaration per line.

If subsequent lines are not automatically indented, indent them by one tab stop (four spaces).

Add at least one blank line between method definitions and property definitions.

Use parentheses to make the clauses of an expression apparent.

- Example :

```C#
if ((val1 > val2) && (val1 > val3))
{
    // Take appropriate action.
}
```

*source : [learn Microsoft](https://learn.microsoft.com/en-us/dotnet/csharp/fundamentals/coding-style/coding-conventions)*

##### 4. Objects description

|  | Tanks | Wines | Main |
| :-: | :-: | :-: | :-: |
| **Vocabulary** | capacity [float] | ID [int] | margin [float] |
|  | wines [list] | quantity [float] |  |
|  | errorMargin [float] |  |  |
|  | Similarity [float] |  |  |
| **Function** | <pre>```get Similarity()```<br>    ```transferFrom(Tank[] tanks)```<br>    ```transferTo(Tank[] tanks)```</pre> | constructor : `wine(id, quantity)` | `tank[] tank_arr` |
|  | `<wines> get winePercent()` |  | <pre>```for(int i=O; i<maxTank; i++)```<br>    ```tank_arr.append(new Tank())```</pre> |
|  | `isGood(<wines> wine, errorMargin)` |  |  |
|  | <pre>```Tank()```<br>    ```this.capacity = (random % 99)+1```<br>    ```this.wine = new List<wines>();```</pre> |  |  |

##### 5. Implementation

The program is implemented by the technique of TDD[^13]. The program generate a general tree[^14] and use the BFS[^15] method and the pruning[^16] technique.

#### D. How is it work ?

**1. Tanks.cs file**

Define every function/method/file we use that is external to the page.

```cs
using System;
using System.Collections;
using System.Threading.Tasks;
```

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/solar.png)

Inside the namespace KrugApp, we start by define a new class "Tank" accessible

```cs
namespace KrugApp
{
    public class Tank
    {
        ...
    }
}
```

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/solar.png)

Create a tank array with parameter of capacity of the tank and the name of the wine

```cs
public const int MIN_CAPACITY = 1;
public const int MAX_CAPACITY = 200;

public const int MAX_WINES = 4;

public int Capacity { get; set; }
public Wine[] Wine { get; set; }
```

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/solar.png)

Create a tank with a random capacity between 10 and 100

```cs
public Tank()
{
    Random rnd = new Random();
    this.Capacity = rnd.Next(MIN_CAPACITY, MAX_CAPACITY);
    this.Wine = new Wine[MAX_WINES];
    for (int i = 0; i < MAX_WINES; i++)
        this.Wine[i] = new Wine();
}
```

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/solar.png)

Create a tank with a define capacity

```cs
public Tank(int capacity)
{
    if (capacity < MIN_CAPACITY || capacity > MAX_CAPACITY)
        throw new ArgumentException($"Capacity must be between {MIN_CAPACITY} and {MAX_CAPACITY}");
    this.Capacity = capacity;
    this.Wine = new Wine[MAX_WINES];
    for (int i = 0; i < MAX_WINES; i++)
        this.Wine[i] = new Wine();
}
```

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/solar.png)

Create a tank with a specified amount of wine at a given index.
The parameter "wine" is the amount of wine to be stored and the parameter "index" is the index of the wine in the tank.

```cs
public Tank(float wine, int index)
{
    this.Capacity = (int)wine;
    this.Wine = new Wine[MAX_WINES];
    for (int i = 0; i < MAX_WINES; i++)
        this.Wine[i] = new Wine();

    this.Wine[index].Quantity = wine;
}
```

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/solar.png)

Return if the quantity of wine in a tank is too big, too small or perfect for the capacity of the tank.
The parameter "total" is the array of the wines' capacity.

```cs
public Tank(Wine[] total)
{
    if (total.Sum(wine => wine.Quantity) == 0)
    {
        throw new Exception("The total quantity of wine is too small for the tank.");
    }
    if(total.Length == MAX_WINES)
    {
        if (total.Sum(wine => wine.Quantity) > MAX_CAPACITY)
            throw new Exception("The total quantity of wine is too big for the tank.");
        else if (total.Sum(wine => wine.Quantity) < MIN_CAPACITY)
            throw new Exception("The total quantity of wine is too small for the tank.");
        this.Capacity = (int)total.Sum(wine => wine.Quantity);
        this.Wine = total;
    }
    else
    {
        throw new Exception("Invalide number of wines");
    }
}
```

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/solar.png)

Empties the contents of the specified array by setting all elements to their default values. The parameter "array" is the array of tank to be emptied

```cs
public static void EmptyTank<T>(Wine[] array)
{
    Array.Clear(array, 0, array.Length);
}
```

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/solar.png)

Fill the tank with only one wine.
The parameter "indexOfWine" is the index of where the wine is.

```cs
public void FillWithOneWine(int indexOfWine)
{
    if (this.Wine.Sum(wine => wine.Quantity) == 0)
        this.Wine[indexOfWine].Quantity = this.Capacity;
    else
        throw new Exception("Cannot fill a full tank.");
}
```

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/solar.png)

Transfers the total quantity of wines from an array of tanks into a new tank with the combined capacity and quantity from the input tanks.

```cs
public Tank TankFrom(Tank[] tanks)
{
    float totalCapacity = tanks.Sum(tank => tank.Capacity);
    Wine[] totalWines = new Wine[MAX_WINES];

    for (int i = 0; i < MAX_WINES; i++)
    {
        float totalQuantity = tanks.Sum(tank => tank.Wine[i].Quantity);
        totalWines[i] = new Wine(totalQuantity);
    }

    return new Tank(totalWines);
}
```

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/solar.png)

Return an array of tanks with the wine from the target tank.
The parameter "tanks" is the array of tanks to transfer wine from and the parameter "tank" is the target tank to receive the transferred wine.
The tank receivers need to be empty, and their total capacity needs to be equal to the capacity of the initial tank.

```cs
public static Tank[] TransferTo(Tank[] tanks, Tank tank)
{
    if (tanks.Sum(t => t.Wine.Sum(w => w.Quantity)) != 0)
    {
        throw new Exception("Cannot transfer if the total quantity of wine in the tanks is not zero.");
    }

    if (tanks.Sum(t => t.Capacity) != tank.Capacity)
    {
        throw new Exception("Cannot transfer if the total capacity of the tanks is not equal to the capacity of the target tank.");
    }

    Tank[] res = new Tank[tanks.Length];

    for (int j = 0; j < tanks.Length; j++)
    {
        res[j] = new Tank(tanks[j].Capacity);

        for (int i = 0; i < tank.MAX_WINES; i++)
        {
            res[j].Wine[i].Quantity = (tank.Wine[i].Quantity / tank.Capacity) * tanks[j].Capacity;
        }

    }
    return res;
}
```

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/solar.png)

Calculates the percentages of the total capacity for each tank in the provided array.

```cs
public Tank[] CalculatePercentages(Tank[] tanks)
{
    float total = tanks.Sum(tank => tank.Capacity);

    return tanks.Select(tank => new Tank((int)(tank.Capacity / total * 100))).ToArray();
}
```

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/solar.png)

Calculates the similarity between a given formula of wines (represent the desired quantities of wines in the final mix.) and the quantities of wines in a set of tanks and return an array of wines representing the differences between the desired quantities and the tank quantities.

```cs
public static Wine[] CalculateSimilarity(Wine[] formula, Tank[] tanks)
{
    Wine[] diff = new Wine[formula.Length];
        
    for (int i = 0; i < formula.Length; i++)
    {
        int quantityDifference = (int)(tanks[i].Capacity - formula[i].Quantity);
        diff[i] = new Wine(quantityDifference);
    }

    return diff;
}

```

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/solar.png)

Adds two tanks together, combining their capacity and wine quantities (with operator overloads) in an other tank.
If the total quantity of wines is higher or lower than the capacity of the tank, it will return an error.

```cs
public static Tank operator +(Tank tank1, Tank tank2)
{
    Tank tank = new Tank(tank1.Capacity + tank2.Capacity);

    for (int i = 0; i < tank.Wine.Length; i++)
        tank.Wine[i] = tank1.Wine[i] + tank2.Wine[i];

    if (tank.Capacity == tank.Wine.Sum(tank => tank.Quantity) || tank.Wine.Sum(tank => tank.Quantity) == 0)
        return tank;
    else
        throw new Exception("The tank is neither full nor empty.");
}
```

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/solar.png)

Browse the list of "value" tanks and call the "GenerateSumCombinations(Tank[] tanks, int target, int[] combination, List<int[]> result, int startIndex, int length)" function for each of the values.

```cs
public static List<int[]> GenerateSumCombinations(Tank[] values)
{
    List<int[]> result = new List<int[]>();

    for (int i = 0; i < values.Length; i++)
    {
        int[] combination = new int[values.Length];
        GenerateSumCombinations(values, values[i].Capacity, combination, result, i, 0);
    }

    return result;
}
```

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/solar.png)

Create all combinations possible of length given with tanks available to make the blending of differents wines together.

```cs
private static void GenerateSumCombinations(Tank[] values, int remainingCapacity, int[] combination, List<int[]> result, int currentIndex, int currentTankIndex)
{
    if (remainingCapacity == 0)
    {
        // We have reached the desired sum, add the combination to the result
        result.Add((int[])combination.Clone());
        return;
    }

    if (currentTankIndex >= values.Length || remainingCapacity < 0 || currentIndex >= combination.Length)
    {
        // We have exhausted all tanks, exceeded the remaining capacity, or filled the combination array, backtrack
        return;
    }

    // Skip the current tank and move to the next one
    GenerateSumCombinations(values, remainingCapacity, combination, result, currentIndex, currentTankIndex + 1);

    // Try using the current tank if it doesn't exceed remaining capacity
    if (values[currentTankIndex].Capacity <= remainingCapacity)
    {
        combination[currentIndex] = values[currentTankIndex].Capacity;
        GenerateSumCombinations(values, remainingCapacity - values[currentTankIndex].Capacity, combination, result, currentIndex + 1, currentTankIndex);
        combination[currentIndex] = 0; // Reset the value to 0 for backtracking

        // Move to the next tank with the same remaining capacity
        GenerateSumCombinations(values, remainingCapacity, combination, result, currentIndex, currentTankIndex + 1);
    }
}
```

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/solar.png)

Traverses the tree widthways through each node and returns the order of the list of all nodes visited in the order in which they were visited (BFS method).

```cs
public Wine[] TraverseNodes(Wine[] nodes)
{
    // Copy the original nodes to avoid modifying the input
    Wine[] copiedNodes = new Wine[nodes.Length];
    Array.Copy(nodes, copiedNodes, nodes.Length);

    // Node path
    for (int i = 0; i < copiedNodes.Length; i++)
    {
        Wine currentNode = copiedNodes[i];

        // Implement the specific traversal logic here
        // For example, reverse the quantities of the nodes for the example
        currentNode.Quantity = Tank.MAX_WINES - currentNode.Quantity + 1;
    }

    return copiedNodes;
}
```

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/solar.png)

Compare the quantity of each wine of the tank array with the quantity wanted in the formula for the same wine and return false if the difference is superior to the variable a (tolerance of the difference) or retrun true if the difference is inferior or equal to a.

```cs
public static bool CheckFormula(Tank[] table, Wine[] formula, float a)
{
    int i = 0;
    var res = false;
    float c = 0;

    float[] output = new float[formula.Length];
           
    foreach (var tanks in table)
    {
        foreach (var wine in tanks.Wine)
        {
            if (i < formula.Length && i < tanks.Wine.Length)
            {
                c = Math.Abs(formula[i].Quantity - tanks.Wine[i].Quantity);
                        
                    if (c > a)
                    {
                        res = false;
                    break;
                    }

                    if (c <= a)
                    {
                        res = true;

                    }   
            }
            i++;
        }
    }
            
    return res;
}
```

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/solar.png)

**2. Wines.cs file**

Define every function/method/file we use that is external to the page.

```cs
using System;
```

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/solar.png)

Inside the namespace KrugApp, we start by define a new class "Wine" accessible

```cs
namespace KrugApp
{
    public class Wine
    {
        ...
    }
}
```

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/solar.png)

Create a list of wines with the quantities (default 0 otherwise value entered) (to have the index of each wine, we will use MAX_WINES = number of wines)

```cs
public float Quantity { get; set; }

public Wine()
{
    this.Quantity = 0;
}

public Wine(float quantity)
{
    this.Quantity = quantity;
}
```

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/solar.png)

Define each operator (+, -, *, /) for the quantity of wine

```cs
public static Wine operator +(Wine wine1, Wine wine2)
{
    return new Wine(wine1.Quantity + wine2.Quantity);
}

public static Wine operator -(Wine wine1, Wine wine2)
{
    return new Wine(wine1.Quantity - wine2.Quantity);
}

public static Wine operator *(Wine wine1, Wine wine2)
{
    return new Wine(wine1.Quantity * wine2.Quantity);
}

public static Wine operator /(Wine wine1, Wine wine2)
{
    if (wine2.Quantity != 0)
        return new Wine(wine1.Quantity / wine2.Quantity);
    else
        throw new DivideByZeroException("Cannot divide by zero.");
}
```

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/solar.png)

Returns the quantity in string type

```cs
public override string ToString()
{
    return "Quantity: " + this.Quantity;
}
```

**3. Program.cs file**

Define every function/method/file we use that is external to the page.

```cs
using System;
using System.Linq;
using KrugApp;

using System.Data;
using System.Data.OleDb;
using System.Globalization;
using System.IO;
```

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/solar.png)

Inside the namespace KrugApp, we start by define a new class "Program" accessible

```cs
namespace KrugApp
{
    public class Program
    {
        ...
    }
}
```

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/solar.png)

The Main function will call up all the functions it needs to calculate the mix and make verification.

```cs
public static void Main(string[] args)
{
    string csvFilePath = "formulaTest.csv";

    Wine[] wines = CSVToFormula(csvFilePath);

    //for (var i = 0; i < wines.Length; i++)
    //{
    //    Console.WriteLine($" {i} -> Quantity: {wines[i].Quantity}");
    //}
    var a = String.Empty;

    foreach (var b in wines)
        a = a + "," + b.ToString();

    a = a.TrimStart(',');

    Console.WriteLine(a);

    string filePath = "tank.csv";
    Tank[] tanks = CSVToTank(filePath, wines.Length);
    Console.WriteLine(tanks.Length);
    foreach (Tank tank in tanks)
    {
        //Console.WriteLine($"Tank Capacity: {tank.Capacity}");
        //Console.WriteLine("Wines:");
        if (tank.Wine != null)
        {
            foreach (Wine wine in tank.Wine)
            {
                Console.WriteLine($"- Quantity: {wine.Quantity}");
            }
        }
        Console.WriteLine();
    }
}
```

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/solar.png)

This function compare multiple criteria to know the similarity between two Tank[] and return the similarity indicator between 0(opposite) and 10(same)

```cs
public static int Similarity(Tank[] a, Tank[] b)
{
    if (a == null || b == null || a.Length == 0 || b.Length == 0)
        throw new ArgumentException("Both arrays must have at least one element.");

    // Number of used tank
    var usedTank = SimiPoint(NbrTank(a), NbrTank(b));

    // Number of wines in the tanks
    var nbrWine = SimiPoint(NbrWines(a), NbrWines(b));

    // The total quantity of all the wines
    var nbrQuan = SimiPoint(NbrTotalWine(a), NbrTotalWine(b));

    // The quantity for each wines
    var QuanWine = NbrEachWine(a, b);

    var similarity = usedTank + nbrWine + nbrQuan + QuanWine;

    if (similarity == 8)
        similarity += 2;
    else if (similarity == 7)
        similarity += 1;

    // return similarity (int)
    return similarity;

}
```

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/solar.png)

Add similarity points between two tanks or Tank[]

```cs
static int SimiPoint(int c, int d)
{
    if (c == d)
        return 2;
    else if (c > d && c / 2 <= d)
        return 1;
    else if (c < d && d / 2 <= c)
        return 1;
    else
        return 0;
}
```

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/solar.png)

Count number of wine in a tank of Tank[]

```cs
static int NbrWines(Tank[] a)
{
    var d = 0; // number of wines
    for (var i = 0; i < a.Length; i++)
        for (var j = 0; j < a[i].Wine.Length; j++)
            if ((int)a[i].Wine[j].Quantity > 0)
                d += 1;
    return d;
}
```

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/solar.png)

Count the number of tank used during the blending

```cs
static int NbrTank(Tank[] a)
{
    float c = 0; // Quantity of wine in the tank
    var d = 0; // number of used tank
    foreach (var tank in a)
    {
        foreach (var wine in tank.Wine)
            c += wine.Quantity;

        if (c != 0)
            d += 1;
        c = 0;
    }
    return d;
}
```

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/solar.png)

Calculate the quantity total used in all the array Tank.

```cs
static int NbrTotalWine(Tank[] a)
{
    int wine1 = 0;
    for (int i = 0; i < a.Length; i++)
    {
        for (int j = 0; j < a[i].Wine.Length; j++)
        {
            wine1 += (int)a[i].Wine[j].Quantity;
        }
    }
    return wine1;
}
```

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/solar.png)

Calculate the similarity of wine between 2 array of tank.

```cs
static int NbrEachWine(Tank[] a, Tank[] b)
{
    var d = 0; // number of wines
    for (var i = 0; i < a.Length; i++)
    {
        for (var j = 0; j < a[i].Wine.Length; j++)
        {
            var tankA = a[i].Wine[j].Quantity;
            var tankB = b[i].Wine[j].Quantity;
            if (tankA == tankB)
                d += 2;
            else if (tankA > tankB && tankA / 2 >= tankB)
                d += 1;
            else if (tankA < tankB && tankA >= tankB / 2)
                d += 1;
        }

    }

    d = d / NbrWines(a) / 2;
    return d;
}
```

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/solar.png)

Calculates the number of tanks in the array of tank call "a" that have at least two wines.

```cs
public static int NbrMix(Tank[] a)
{
    var sum = 0;
    var total = 0;
    for (var i = 0; i < a.Length; i++)
    {
        for (var j = 0; j < a[i].Wine.Length; j++)
        {
            if (a[i].Wine[j].Quantity >= 1)
                sum++;
        }
        if (sum >= 2)
            total++;
        sum = 0;
    }
    return total;
}
```

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/solar.png)

Check if the child node moves away from the target in relation to a parent node and return a booleen.

```cs
public static bool IsMovingAway(Tank[] parent, Tank[] child, Tank[] target)
{
    var parentSimilarity = Similarity(parent, target);
    var childSimilarity = Similarity(child, target);

    if (childSimilarity > parentSimilarity)
        return true;
    else
        return false;
}
```

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/solar.png)

Parses a CSV file containing wine data and returns an array of Wine objects based on the specified quantity index.

```cs
static Wine[] CSVToFormula(string path)
{
    int quantityIndex = 1;
    using (var reader = new StreamReader(path))
    {
        List<Wine> wines = new List<Wine>();

        // Skip the header line
        reader.ReadLine();

            while (!reader.EndOfStream)
        {
            var line = reader.ReadLine();
            var values = line.Split(',');

            // Parse the quantity value from the CSV column
            float quantity = float.Parse(values[quantityIndex]);

            // Replace -1 with 0
            if (quantity == -1)
            {
                quantity = 0;
            }

            wines.Add(new Wine(quantity));
        }

        return wines.ToArray();
    }
}
```

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/solar.png)

Counts the number of lines in a CSV file given in the parameter "filepath".

```cs
static int CountLinesInCSV(string filePath)
{
    try
    {
        int lineCount = 0;
        using (StreamReader reader = new StreamReader(filePath))
        {
            while (reader.ReadLine() != null)
            {
                lineCount++;
            }
        }
        return lineCount;
    }
    catch (IOException e)
    {
        Console.WriteLine("An error occurred while reading the CSV file: " + e.Message);
        return 0;
    }
}
```

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/solar.png)

Parses a CSV file given in parameter "path" containing tank data and returns an array of Tank objects. The parameter "size" is the size of the Wine array in each Tank object.

```cs
public static Tank[] CSVToTank(string path, int size)
{
    using (var reader = new StreamReader(path))
    {
        int lines = CountLinesInCSV(path);
        Tank[] tanks = new Tank[lines];
        var i = 0;

        // Skip the header row
        reader.ReadLine();

        while (!reader.EndOfStream)
        {
            var line = reader.ReadLine();
            var values = line.Split(',');

            var tank = new Tank();
            tank.Capacity = int.Parse(values[0]);

            int wineIndex = int.Parse(values[1]);
            tank.Wine = new Wine[size];
            for (var j = 0; j < size; j++)
            {
                tank.Wine[j] = new Wine();
                if (wineIndex > -1)
                    tank.Wine[j].Quantity = (j == wineIndex) ? tank.Capacity : 0;
            }
            tanks[i] = tank;
            i++;
        }

        return tanks;
    }
}
```

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/solar.png)

Add comma between values in array (debug function)

```cs
static string printable(int[] input)
{
    var a = String.Empty;

    foreach (var b in input)
        a = a + "," + b.ToString();

    a = a.TrimStart(',');

    a = a + " : " + input.Sum();
    return a;
}
```

#### E. Program architecture diagram

1. V.1 of the algorithm

![Program Architechture Diagram](Images/Architecture_diagram.png)
This algorithm has been abandoned because :

- Big O complexity is too high
- Not the best option
- Too much cases where it won't work

2. V.2 of the algorithm

![Program Architechture Diagram](Images/Architecture_diagram2.png)

### III. Further considerations

#### A. Cost estimation

To make the project, we don't have a cost.

#### B. Security

Each data used by the program aren't saved when your close the program and avoids any security problems regarding data theft.

#### C. Accessibility

The program will be accessible by a text file to enter data like the formula (in percentage), the similarity expected (in percentage) or also each tank available and returns a text file with the steps, the percentage of similarity

### IV. Success evaluation

The program is scored according to the following criteria :

1. Correctness: no crash, no half full or half empty tanks
2. How close your final product is from the input formula
3. Comments and idiomatic style
4. Minimum number of steps to get to the result
5. Complexity and Speed of the code

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/aqua.png)

### V. Glossary

[^1]: [House Krug Champagne](https://www.krug.com/fr/la-maison-krug)

[^2]: **RM (Récoltant-Manipulant = Harvester-Handler):**
The abbreviation RM precedes the professional registration number issued by the Comité Champagne and indicates the professional category of the producer.
In order, there is Handler Trader, Handler Harvester, Harvester-Cooperator, Handler Cooperative, Distributor Trader, Buyer Brand.
*source : [Ministry of the Economy](https://www.economie.gouv.fr/dgccrf/Publications/Vie-pratique/Fiches-pratique/Champagne)*

[^3]: **Complexity :**
It is a measure of the time it would take an algorithm to run with an input of size n. The complexity is denoted O(X) (big-O). It can be linear if the search time is proportional to the size of the input (X=n). It is logarithmic if as the input increases, the number of significant operations increases very slowly (X=log n). It is constant if the execution time does not increase when the input increases massively (X=1). It is quadratic when the input is doubled, and the execution time of the calculations is multiplied by 4 (X=n^2).
*source : [Devopedia](https://devopedia.org/algorithmic-complexity) / [Towards data science](https://towardsdatascience.com/logarithms-exponents-in-complexity-analysis-b8071979e847#9063) / [University of Picardie](https://home.mis.u-picardie.fr/~furst/docs/3-Complexite.pdf)*

[^4]: **layered architecture :**
The layered architecture style is one of the most common architectural styles. The idea behind layered architecture is that modules or components with similar functionality are organised in horizontal layers. Thus, each layer plays a specific role in the application.
The layered architecture style places no restrictions on the number of layers the application can have, to support the concept of separation of concerns.
*source : University of Waterloo* [PDF](https://cs.uwaterloo.ca/~m2nagapp/courses/CS446/1195/Arch_Design_Activity/Layered.pdf)

[^5]: **Presentation layer :**
The presentation layer is the first of two layers in the so-called "three-tier architecture" (based on the client-server environment, see attached diagram).
The presentation layer is the "Client" part thanks an interface to use the program.
![(Three-tier architecture)](Images/Three_Tier_Architecture.png)
*source : [Wikipedia](https://fr.wikipedia.org/wiki/Architecture_trois_tiers)*

[^6]: **Cellar Master :**
A person who supervises the making of wine in a winery.
*source : [Merriam-Webster](https://www.merriam-webster.com/dictionary/cellar%20master)*

[^7]: **Business logic layer :**
Also known as the business processing of data, corresponding to the second tier "Server" of the diagram in Definition 4. It is the implementation of all the business rules and application logic.
*source : [Wikipedia](https://fr.wikipedia.org/wiki/Architecture_trois_tiers)*

[^8]: **Data access layer :**
Data access or persistent data is data that is intended to be retained over time or even permanently. This is the third tier "Database"  of the diagram in Definition 4.
*source : [Wikipedia](https://fr.wikipedia.org/wiki/Architecture_trois_tiers)*

[^9]: **EF Core (Entity Framework Core) :**
Entity Framework (EF) Core is an extensible, open source, cross-platform version of Entity Framework. EF Core can serve as an object-relational mapper (O/RM), which allows .NET developers to work with a database using .NET objects and eliminates the need for much of the data access code that typically must be written. It supports many database engines.
With EF Core, data is accessed using a model. A model consists of entity classes and a context object that represents a session with the database. The context object allows the interrogation and registration of data. With this, it can generate a model from an existing database, manually code a model to match the database.
Once a model is created, it is possible to use EF Migrations to create a database from the model, allowing the database to grow as the model changes.
*source : [learn Microsoft](https://learn.microsoft.com/en-gb/ef/core/)*

[^10]: **ORM (Object-Relational Mapping) :**
The ORM is the layer that links object-oriented programming (OOP) to relational databases and simplifies the interaction between the two.
*source : [Free code camp](https://www.freecodecamp.org/news/what-is-an-orm-the-meaning-of-object-relational-mapping-database-tools/)*

[^11]: **SOLID principles :**
The SOLID Principles are five principles of Object-Oriented class design. They are a set of rules and best practices to follow while designing a class structure.
The 5 principles are : Single Responsibility (a class should do one thing and therefore it should have only a single reason to change) / Open-Closed (classes should be open for extension and closed to modification) / Liskov Substitution (subclasses should be substitutable for their base classes) / Interface Segregation (separating the interfaces) / Dependency Inversion (classes should depend upon interfaces or abstract classes instead of concrete classes and functions)
*source : [Free code camp](https://www.freecodecamp.org/news/solid-principles-explained-in-plain-english/)*

[^12]: **Oxydation :**
Chimical reaction between body and oxygen. If the wine is oxydised, it's not usable anymore.
*source : [Le Robert](https://dictionnaire.lerobert.com/google-dictionnaire-fr?param=oxydation)*

[^13]: **TDD (Test-Driven Development):**
TDD can be represent by the formula `TDD = Refactor + TFD` (Test First Development)
The first steps of TFD is to quickly add a test, basically just enough code to fail.
Next you run your tests to ensure that the new test does in fact fail.
You then update your functional code to make it pass the new tests.
The fourth step is to run your tests again. If they fail you need to update your functional code and retest. Once the tests pass the next step is to start over (you may first need to refactor any duplication out of your design as needed, turning TFD into TDD).
![(TFD-TDD)](Images/TFD-TDD.png)
TDD is primarily a specification technique with an effect of ensuring that your source code is thoroughly tested. However, there is more to testing than this. Particularly at scale you'll still need to consider other testing techniques. Much of this testing can also be done early in your initiative.
*source : [Agile data](http://agiledata.org/essays/tdd.html)*

[^14]: **General tree :**
A tree is an abstract data type that represents a hierarchical tree structure with a set of nodes connected in a "parent-child" fashion. They are made up of several elements : a node, the root (the top-most element of a tree, a node with no parent) and a leaf (a bottom-most element of a tree, has no children).
There is also another type of tree called a "binary tree". Its special feature is that it has only two children (left and right) for each nodes.
When we have multiple trees, we call that a forest.
Other vocabulary : sibling (two or more nodes that share the same parent), heigth (the distance from the root to the furthest leaf, counting the nodes)
*source : [Wikipedia](https://en.wikipedia.org/wiki/Tree_(data_structure)) / [tree lesson by Christopher Diggins](doc_link/trees.pptx)*

[^15]: **BFS (Breadth First Search):**
It's an algorithm for searching for data in a tree (binary or not) starting from the root and first visiting each child who is a sister (at the same height in the tree) before moving on to the "grandchildren".
The depth-first search (DFS) method also includes: pre-order (self, child A, child B), in-order (child A, self, child B), post-order (child A, child B, self)
*source : [Wikipedia](https://en.wikipedia.org/wiki/Breadth-first_search#Time_and_space_complexity) / [tree lesson by Christopher Diggins](doc_link/trees.pptx)*

[^16]: **Pruning :**
This involves deleting branches of a tree that are no longer needed. This makes the programme faster and more efficient.
*source : [DEV Community](https://dev.to/ml_82/what-is-pruning-in-decision-tree-30e0#:~:text=Pruning%20is%20a%20technique%20used,the%20tree%20by%20reducing%20overfitting.)*
