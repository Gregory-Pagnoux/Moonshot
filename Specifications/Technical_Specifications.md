# Technical Specifications

![-](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

<details>
<summary>📖 Table of content</summary>

- [Technical Specifications](#technical-specifications)
    - [I. Document](#i-document)
      - [A. Information](#a-information)
      - [B. History](#b-history)
      - [C. Overview](#c-overview)
  - [II. Solution](#ii-solution)
      - [A. Descritpion](#a-descritpion)
        - [1. Mirror](#1-mirror)
        - [2. Application](#2-application)
      - [B. Software architecture](#b-software-architecture)
      - [C. Technical constraints](#c-technical-constraints)
        - [1. C coding convention](#1-c-coding-convention)
        - [2. Implementation](#2-implementation)
      - [D. How it work ?](#d-how-it-work-)
      - [E. Program architecture diagram](#e-program-architecture-diagram)
  - [III. Quality Control](#iii-quality-control)
      - [A. Objectives](#a-objectives)
      - [B. Error Management and Corrections](#b-error-management-and-corrections)
      - [C. Documentation and Reporting](#c-documentation-and-reporting)
  - [IV. Further considerations](#iv-further-considerations)
      - [A. Cost estimation](#a-cost-estimation)
        - [1. Software](#1-software)
        - [2. Hardware](#2-hardware)
        - [3. Material](#3-material)
        - [4. Time \& Human](#4-time--human)
      - [B. Security](#b-security)
      - [C. Accessibility](#c-accessibility)
  - [V. Success evaluation](#v-success-evaluation)
    - [Glossary](#glossary)

</details>

![-](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

### I. Document

#### A. Information

| Document ID | Document # 02 |
|---|---|
| Document Owner | Grégory PAGNOUX |
| Issue date | 02/06/2024 |
| Document Name | Technical Specification|

#### B. History

| Version n° | Edits completed by | Date | Description of edit |
|---|---|---|---|
|01.1|Grégory PAGNOUX| 17/03/2024 | Initial Release |

#### C. Overview

<center>

![Pheonix](/img/logo.png)

</center>

Phoenix is a healthy mirror who allows to the customer to control his temperature with a thermometer laser[^1], pulse thanks to BioActive sensor[^2], diabetes with a glucose meter[^3], and if he is alcoholic with a breathalyzer[^4].
With your Smartphone you have the possibility to track your datas.

## II. Solution

#### A. Descritpion

![design](/img/design.png)

##### 1. Mirror

- **switched off**

When the mirror is switched off, the user can use it for make-up, hair styling, etc. without any problem.

To switch off the mirror, press the power button and the main light comes off, the time is disappear on the mirror's screen and the three LEDs light up for 3 seconds to prevent the customer.

- **switched on**

If the user wants to do more, he must press the power button to switch it on after plugging it in. The main light comes on, the time is displayed on the mirror's screen and the three LEDs light up for 3 seconds to check operation.

- **set time**

The user presses the plus button for 3 seconds and the hours blink. The user can press 1 time to increase the hours by 1 and validate with the corresponding button, which lights up the green light for 3 seconds. Now the minutes flash and the user can do the same thing, and when he validates, nothing else blinkes.

- **breathalyzer**

To use the breathalyzer, the user must press the first button to the left of the 4 option buttons (with the image of the bottle). The yellow light flashes when the user can blow on the sensor for at least 5 seconds.
The green light flashes when the alcohol level is within the limit, and the red light when the level is over the limit.

- **pulse**

To use the BioActive sensor, the user must press the second of the 4 option buttons (with the image of the oscillogram). The yellow light flashes when the user can press the sensor again for at least 5 seconds.
The pulse value is displayed on the mirror's screen.

- **glucose meter**

To use the glucose meter, the user must press the third of the four option buttons (with the image of the drop). The yellow light flashes when the user can perform a blood glucose test.
The glucose level is displayed on the mirror screen.

- **thermometer**

To use the thermometer, the user must press the last button to the right of the 4 option buttons (with the celsius image). The yellow light flashes when the user stands in front of the mirror for at least 5 seconds.
The temperature is displayed on the mirror screen.

- **connect phone**

The user presses the validation button for 3 seconds and the yellow light flashes for 10 seconds. The user can connect their phone to the mirror during this time. When the connection is established, the green light blink for 3 secondes, otherwise the red light blink for 3 seconds.

##### 2. Application

to be defined

#### B. Software architecture

The software could be developed using a layered architecture, with each layer responsible for a specific set of functionalities.

The presentation layer would be the user interface that the Cellar Master and her team would interact with.

The business logic layer would handle the core functionality of the software, including the blending algorithms and data validation. This layer would be developed using C# and .NET 6.0's latest features, such as C# 10 and the new record types, to ensure maximum performance and maintainability.

The data access layer would be responsible for handling data storage and retrieval, such as keeping track of the tanks and their current contents. This layer would be developed using .NET 6.0's EF Core framework, which provides a powerful and flexible ORM (Object-Relational Mapping) toolset for working with databases.

To ensure that the software is reliable and fault-tolerant, it would be designed using the SOLID principles and unit tested extensively using .NET 6.0's built-in testing framework.

Overall, this architecture would provide a robust and scalable software solution for the Krug Champagne blending process, built using the latest and most advanced technologies in the .NET ecosystem.

#### C. Technical constraints

##### 1. C coding convention

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

##### 2. Implementation

The program is implemented by the technique of TDD. The program generate a general tree and use the BFS method and the pruning technique.

#### D. How it work ?

**1. Tanks.cs file**

Define every function/method/file we use that is external to the page.

```cs
using System;
using System.Collections;
using System.Threading.Tasks;
```

![-](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/aqua.png)

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

![-](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/aqua.png)

**2. Wines.cs file**

Define every function/method/file we use that is external to the page.

```cs
using System;
```

![-](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/aqua.png)

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

![-](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/aqua.png)

#### E. Program architecture diagram

**1. V.1 of the algorithm**

![Program Architechture Diagram](img/Architecture_diagram.png)
This algorithm has been abandoned because :

- Big O complexity is too high
- Not the best option
- Too much cases where it won't work

**2. V.2 of the algorithm**

![Program Architechture Diagram](img)

## III. Quality Control

#### A. Objectives

To ensure that the Rubik’s Art Project achieves the desired outcomes and meets ALGOSUP's expectations, a comprehensive quality control (QC) plan is essential. The primary objectives of the QC process are:

Ensure that the fresco accurately represents the intended pixel art image.
Verify the correct application and function of the software developed.
Confirm the durability and safety of the installations.
Foster coordination and communication among the 8 teams.
Address errors efficiently and promptly.

#### B. Error Management and Corrections

Despite best efforts, errors may occur. To manage them effectively:

Error Logging: Create a system where teams can log any errors or deviations they encounter.
Prioritization: Classify errors based on their severity and impact on the project. Address critical issues first.
Correction Teams: Designate members from each team to be part of a correction team, responsible for addressing and rectifying errors.

#### C. Documentation and Reporting

Maintain a comprehensive record of the process. This should include:

Weekly Reports: A consolidated report of the week's progress, challenges, and learnings.

## IV. Further considerations

#### A. Cost estimation

##### 1. Software



##### 2. Hardware



##### 3. Material



##### 4. Time & Human



#### B. Security



#### C. Accessibility



## V. Success evaluation

The program is scored according to the following criteria :
- All features are accessible

![-](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

### Glossary

[^1]: **[Thermometer laser](https://www.amazon.fr/Thermom%C3%A8tre-IDOIT-Thermometre-Infrarouge-Affichage/dp/B08DFXYWNN/ref=sr_1_32?adgrpid=54908680263&hvadid=275507361595&hvdev=c&hvlocphy=9055097&hvnetw=g&hvqmt=b&hvrand=18183104330674911873&hvtargid=kwd-312280216289&hydadcr=14196_1754673&keywords=thermometre+laser&qid=1683279299&sr=8-32)**
![thermometer laser](/img/thermometer_laser.jpg)
It's a device allows to mesure the temperature of the body.

[^2]: **[Samsung Galaxy Watch 4](https://www.pocket-lint.com/fr-fr/montres-connectees/acheteurs-guides/samsung/157658-samsung-galaxy-watch-4-vs-galaxy-watch-4-differences-classiques-comparees/)**
![Samsung Galaxy Watch 4](/img/Samsung_Galaxy_Watch_4.jpg)
Use the BioActive sensor technologie. It's a technology developed by Samsung for its connected watches which provides simple yet powerful measurements and insights that you can use to take control of your health.
[presentation of BioActive sensor options](https://www.youtube.com/watch?v=yEoCDSwuJHc)

[^3]: **[glucose meter](https://www.amazon.com/Glucose-Monitor-Glucometer-Lancets-Solution/dp/B08LYC288R/ref=zg_mw_3777171_sccl_2/147-1452400-9255329?psc=1)**
![glucose meter](/img/glucose_meter.png)
It's a device allows to mesure the concentration of glucose in the blood thanks a little needle and a strip glucose paper dipped.

[^4]: **[breathalyzer](https://www.ebay.fr/itm/224971220617?chn=ps&mkevt=1&mkcid=28#rpdCntId)**
![breathalyzer](/img/breathalyzer.png)
Device which evaluate if you are alcoholic thanks to sensors that analyze the air when you blow.
