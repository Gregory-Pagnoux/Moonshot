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
      - [1. Architectural Components](#1-architectural-components)
        - [a. Presentation Layer](#a-presentation-layer)
        - [b. Application Layer](#b-application-layer)
        - [c. Data Management Layer](#c-data-management-layer)
      - [2. Workflow Example](#2-workflow-example)
      - [4. Technology Stack](#4-technology-stack)
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

## I. Document

### A. Information

| Document ID | #02 |
|---|---|
| Document Owner | Grégory PAGNOUX |
| Issue date | 02/06/2024 |
| Document Name | Technical Specification |

### B. History

| Version | Edits completed by | Date | Description of edit |
|---|---|---|---|
| 1.1 | Grégory PAGNOUX | 03/17/2024 | Template and make part I, II and Glossary |
| 1.2 | Grégory PAGNOUX | 08/11/2024 | Finish part II/A/2 and make II/B |

### C. Overview

<center>

![Pheonix](/img/logo.png)

</center>

Phoenix is a healthy mirror who allows to the customer to control his temperature with a thermometer laser[^1], pulse thanks to BioActive sensor[^2], diabetes with a glucose meter[^3], and if he is alcoholic with a breathalyzer[^4].
With your Smartphone you have the possibility to track your datas.

## II. Solution

### A. Descritpion

![design](/img/design.png)

#### 1. Mirror

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

#### 2. Application

- **installation**

The application can be install from Google Play in the first time

- **opening**

To open the application, you click on the icon that he appear on your smartphone when you install it and for the first time, you need to sign up with your mail adress. After, you have just to click on your profil (you can have 5 profils with one mirror).

- **profil**

On your profil, you can modify your profil picture, and add information about you age, your weight, and your size to calculate your BMI.

- **settings**

On the settings page, you can modify your mail adress, and your password, you can change with the night or day mode, and change the language between french or english for the first time.

- **data graphs**

These graphs can be found on each options page for tracking their data in each category.

- **call a doctor**

On the call page, you have the possibility to register all doctors such as general practitioners, dentists, home nurses, etc. You can put their phone number, their adress, their mail and you can contact them directly on the application.

### B. Software architecture

he architecture for Phoenix, a smart health mirror, will be designed around modular, service-oriented principles to facilitate integration of various health monitoring functions and a user-friendly interface. The architecture will ensure data privacy, ease of integration, and secure communication with smartphones. Phoenix’s software architecture is divided into three primary layers:

- **Presentation Layer**: Manages user interactions with the mirror’s display and smartphone app.
- **Application Layer**: Contains core business logic, handling user inputs, controlling hardware, and data processing.
- **Data Management Layer**: Manages data storage, retrieval, and communication with the smartphone app, including user data privacy and compliance with data regulations.

#### 1. Architectural Components

##### a. Presentation Layer

The Presentation Layer provides the visual and interactive interface on the mirror and smartphone application. This includes:

**Mirror Display Interface**

**User Interface (UI)**: A simple, intuitive UI on the mirror display shows time, temperature, pulse, glucose levels, and alcohol detection results. The interface will use dynamic visual cues, such as blinking LED indicators for status (yellow for action required, green for safe levels, red for high levels).
**User Feedback**: Provides immediate feedback for each action, such as "Blow into the breathalyzer," “Check glucose levels,” and shows results on the screen.

**Mobile App Interface**

**User Dashboard**: A companion app on the user’s smartphone to display historical health data, trends, and alerts.
**Data Syncing**: Interfaces with the mirror over Bluetooth for real-time data synchronization and allows users to connect and view data seamlessly.

##### b. Application Layer

This layer houses the core logic responsible for managing user interactions, hardware control, and data processing. Key components include:

**Health Monitoring Services**

**Temperature Service**: Interfaces with the thermometer sensor to collect and display the user’s body temperature.
**Pulse Monitoring Service**: Connects with the BioActive sensor to capture pulse data and display it on the screen.
**Glucose Monitoring Service**: Interacts with the glucose meter for blood glucose level readings.
**Breathalyzer Service**: Manages data from the breathalyzer to analyze alcohol levels.

**Device Control Manager**

**Power Control Module**: Manages mirror power states, including sleep, power on/off, and LED control.
**Sensor Control Module**: Coordinates the activation and deactivation of sensors, controlling workflows for each health metric (temperature, pulse, glucose, alcohol).
**Light Control Module**: Handles visual feedback using LED lights to signal different stages or results (e.g., green for safe alcohol level, red for high levels).

**Bluetooth Communication Module**

Facilitates data transmission between the mirror and smartphone app, managing pairing, connection stability, and secure data transfer.

**Error Handling & User Notification**

**Notification Manager**: Provides user alerts on the mirror and app, e.g., low battery warnings, sensor errors, or invalid readings.
**Error Logging**: Logs system issues for diagnostics and maintenance.

##### c. Data Management Layer

This layer focuses on data storage, security, and regulatory compliance, especially concerning health data.

**Local Data Storage**

**Temporary Data Cache**: Stores session data temporarily on the mirror, discarding it once synced to the smartphone.
**Data Retention Policy**: Implements time-based deletion for data, following GDPR and other regional privacy laws.

**Data Syncing and Backup**

**Smartphone Sync**: Ensures user data is synced to their smartphone when connected. Data is encrypted during transfer.
**User-Controlled Data Backup**: Allows users to enable/disable data backups on the smartphone app, giving them control over data retention and sharing.

**Security and Privacy Management**

**Compliance with GDPR**: Ensures data collection, storage, and deletion processes align with GDPR. Users can control their data visibility and deletion settings in the app.

#### 2. Workflow Example

**Power On**: When the user powers on the mirror, the Device Control Manager initializes the mirror’s display and checks connectivity status.
**Health Metric Measurement**: When the user selects a function, like pulse monitoring, the Device Control Manager activates the relevant sensor, and the Application Layer processes and displays results in real-time.
**Data Syncing with Smartphone**: If the smartphone is connected, the Bluetooth Communication Module sends data to the app, where it’s displayed on the dashboard and saved for future reference.
**Data Privacy**: All sensitive data is temporarily stored on the mirror and deleted after syncing, or per user preference, aligned with privacy regulations.

#### 4. Technology Stack

**Frontend (UI)**: HTML/CSS/JavaScript (for Mirror UI), Java or Swift (for mobile app UI)
**Backend (Logic & Processing)**: Arduino for embedded system logic, Java (mobile app backend)
**Data Storage**: SQLite (on-device), local storage on the app
Communication Protocols: Bluetooth Low Energy (BLE) for mirror-to-phone data sync
**Security**: GDPR compliance modules

This architecture allows Phoenix to be a connected, privacy-conscious, and user-friendly health monitoring solution, integrating multiple health sensors into a modular design for ease of future updates and enhancements.

### C. Technical constraints

#### 1. C coding convention

<!--TODO-->

The language used to develop the project is ...

| Notation | How | Usage | Example |
| :-: | :-: | :-: | :-: |
| Pascal Casing | we attach each word and capitalize it to know where the next word starts (ex: DataService) | naming Class | <pre>```public class DataService```<br>```{```<br>```}```</pre> |
|  |  | naming record | <pre>```public record PhysicalAddress(```<br>```)```</pre> |
| comment = // | start each line with two slashes and an uppercase letter and finish the comment by a period. | give more information of the code | <pre>```// The following declaration creates a query. It does not run the query.```</pre> |
|  |  |  |  |

*source : []()*

#### 2. Implementation

The program is implemented by the technique of TDD. The program generate a general tree and use the BFS method and the pruning technique.

### D. How it work ?

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

### E. Program architecture diagram

**1. V.1 of the algorithm**

![Program Architechture Diagram](img/Architecture_diagram.png)
This algorithm has been abandoned because :

- Big O complexity is too high
- Not the best option
- Too much cases where it won't work

**2. V.2 of the algorithm**

![Program Architechture Diagram](img)

## III. Quality Control

### A. Objectives

To ensure that the Rubik’s Art Project achieves the desired outcomes and meets ALGOSUP's expectations, a comprehensive quality control (QC) plan is essential. The primary objectives of the QC process are:

Ensure that the fresco accurately represents the intended pixel art image.
Verify the correct application and function of the software developed.
Confirm the durability and safety of the installations.
Foster coordination and communication among the 8 teams.
Address errors efficiently and promptly.

### B. Error Management and Corrections

Despite best efforts, errors may occur. To manage them effectively:

Error Logging: Create a system where teams can log any errors or deviations they encounter.
Prioritization: Classify errors based on their severity and impact on the project. Address critical issues first.
Correction Teams: Designate members from each team to be part of a correction team, responsible for addressing and rectifying errors.

### C. Documentation and Reporting

Maintain a comprehensive record of the process. This should include:

Weekly Reports: A consolidated report of the week's progress, challenges, and learnings.

## IV. Further considerations

### A. Cost estimation

#### 1. Software

<!--TODO-->

#### 2. Hardware

<!--TODO-->

#### 3. Material

<!--TODO-->

#### 4. Time & Human

<!--TODO-->

### B. Security

<!--TODO-->

### C. Accessibility

<!--TODO-->

## V. Success evaluation

The program is scored according to the following criteria :

- All features are accessible

![-](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

## Glossary

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
