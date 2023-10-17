# Technical Specifications

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

<details>
<summary>📖 Table of content</summary>

- [Technical Specifications](#technical-specifications)
  - [I. Introduction of the project](#i-introduction-of-the-project)
      - [A. Client](#a-client)
      - [B. Goal of the project](#b-goal-of-the-project)
  - [II. Solution](#ii-solution)
      - [A. Descritpion](#a-descritpion)
      - [B. Software architecture](#b-software-architecture)
      - [C. Technical constraints](#c-technical-constraints)
        - [1. The Complexity](#1-the-complexity)
        - [2. C# coding convention](#2-c-coding-convention)
        - [3. Implementation](#3-implementation)
      - [D. How is it work ?](#d-how-is-it-work-)
      - [E. Program architecture diagram](#e-program-architecture-diagram)
  - [VI. Quality Control](#vi-quality-control)
      - [A. Quality Control Objectives](#a-quality-control-objectives)
      - [B. Team Coordination](#b-team-coordination)
      - [C. Evaluation Criteria](#c-evaluation-criteria)
      - [D. Error Management and Corrections](#d-error-management-and-corrections)
      - [E. Documentation and Reporting](#e-documentation-and-reporting)
  - [III. Further considerations](#iii-further-considerations)
      - [A. Cost estimation](#a-cost-estimation)
        - [1. Software](#1-software)
        - [2. Hardware](#2-hardware)
        - [3. Material](#3-material)
        - [4. Time \& Human](#4-time--human)
      - [B. Security](#b-security)
      - [C. Accessibility](#c-accessibility)
  - [IV. Success evaluation](#iv-success-evaluation)
    - [Glossary](#glossary)

</details>

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

## I. Introduction of the project

#### A. Client

The client is the House Krug Champagne[^1], conceptor of champagne since 1843. Based in Reims, they try to make each year the best products thanks to the respect of the vineyards. It's important to note that Krug is renowned for its production of high quality champagne and is considered one of the most prestigious houses in the Champagne region.

In addition, Krug has several labels that testify to the quality of its champagnes. One of the most prestigious labels that Krug has is "Champagne de Prestige", which designates the most upmarket and exceptional champagnes.

It also offers Grande Cuvée champagne (currently the 171st edition), Rosé, Millésime, Clos Mesnil, Clos d'Ambonnay and Collections, each with a unique history.

Krug is classified has the title of "Récoltant-Manipulant" (RM)[^2], which means that it is completely independent. It produces its own grapes and makes its own champagne in its own facilities.

#### B. Goal of the project

The objectif of the project is to implement a program who blend many wines to realize an unique blending with the lowest complexity[^3] for the program and the least loss of wine in the tanks.

## II. Solution

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

##### 1. The Complexity

The most important thing to consider throughout the project is to have an `O(X)` with X = `1`, `log n` or `n`. The values to be avoided absolutely for the efficiency of the program, is an `O(X)` with X = `n²`, `2^n` and `n!`.

##### 2. C# coding convention

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

*source : []()*

##### 3. Implementation

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

#### E. Program architecture diagram

**1. V.1 of the algorithm**

![Program Architechture Diagram](Images/Architecture_diagram.png)
This algorithm has been abandoned because :

- Big O complexity is too high
- Not the best option
- Too much cases where it won't work

**2. V.2 of the algorithm**

![Program Architechture Diagram](Images/Architecture_diagram2.png)

## VI. Quality Control

#### A. Quality Control Objectives

To ensure that the Rubik’s Art Project achieves the desired outcomes and meets ALGOSUP's expectations, a comprehensive quality control (QC) plan is essential. The primary objectives of the QC process are:

Ensure that the fresco accurately represents the intended pixel art image.
Verify the correct application and function of the software developed.
Confirm the durability and safety of the installations.
Foster coordination and communication among the 8 teams.
Address errors efficiently and promptly.

#### B. Team Coordination

Given that multiple teams are involved in the project, coordinated quality control is crucial. Steps for effective coordination include:

Centralized Communication: Establish a centralized platform for communication where teams can raise concerns, provide updates, and request resources.
Regular Check-ins: Schedule periodic check-ins where teams showcase their progress and receive feedback.
Shared Documentation: Maintain shared documentation that logs errors, corrections, and observations for all teams to access and learn from.

#### C. Evaluation Criteria

To maintain consistency across all teams, standardized evaluation criteria should be adopted. Some of the key criteria include:

Accuracy: The orientation and color scheme of the Rubik’s cubes should align with the design specifications.
Software Performance: The application should be user-friendly, provide accurate instructions, and have minimal bugs or errors.
Installation Durability: Whether using the showcase or the frame with polycarbonate sheets, the installation should be sturdy, and with all components securely fixed.

#### D. Error Management and Corrections

Despite best efforts, errors may occur. To manage them effectively:

Error Logging: Create a system where teams can log any errors or deviations they encounter.
Prioritization: Classify errors based on their severity and impact on the project. Address critical issues first.
Correction Teams: Designate members from each team to be part of a correction team, responsible for addressing and rectifying errors.

#### E. Documentation and Reporting

Maintain a comprehensive record of the QC process. This should include:

Daily Reports: A summary of the day’s work, including any errors encountered and how they were addressed.
Weekly Summaries: A consolidated report of the week's progress, challenges, and learnings.
Final QC Report: To conclude the project, compile a final report outlining the QC process, results, and recommendations for future projects.

## III. Further considerations

#### A. Cost estimation

##### 1. Software

The application has been implemented without paid resources and it’s not hosted by a server. There is no cost for the software side.

##### 2. Hardware

We don’t have a device to rotate Rubik’s Cubes and the application only needs a computer. There is no cost for the hardware side.

##### 3. Material

We have 2 different solutions to present and highlight the fresco. You have the choice between the showcase (667€) and the frame with polycarbonate sheet (364€). you can refer to the previous price table (IV and V categories) to decide which installation you want.

##### 4. Time & Human

To create the fresco, the 8 teams, each composed of 6 or 7 members (49 students in total), have been assigned a section with approximately 370 Rubik’s cubes to create the image, so between 52 and 62 Rubik’s per person.
We estimate that each team requires between 9 and 10 hours to complete their portion of the mural, assuming an average of 90 seconds per Rubik’s.


#### B. Security

Each data used by the program aren't saved when your close the program and avoids any security problems regarding data theft.

#### C. Accessibility

The program will be accessible by a text file to enter data like the formula (in percentage), the similarity expected (in percentage) or also each tank available and returns a text file with the steps, the percentage of similarity

## IV. Success evaluation

The program is scored according to the following criteria :

1. Correctness: no crash, no half full or half empty tanks
2. How close your final product is from the input formula
3. Comments and idiomatic style
4. Minimum number of steps to get to the result
5. Complexity and Speed of the code

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/aqua.png)

### Glossary

[^1]: **RM (Récoltant-Manipulant = Harvester-Handler):**
The abbreviation RM precedes the professional registration number issued by the Comité Champagne and indicates the professional category of the producer.
In order, there is Handler Trader, Handler Harvester, Harvester-Cooperator, Handler Cooperative, Distributor Trader, Buyer Brand.
*source : [Ministry of the Economy](https://www.economie.gouv.fr/dgccrf/Publications/Vie-pratique/Fiches-pratique/Champagne)*
