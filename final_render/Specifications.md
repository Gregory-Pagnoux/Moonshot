# Functional Specification

![-](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

<details>
<summary>📖 Table of content</summary>

- [Functional Specification](#functional-specification)
  - [I. Document](#i-document)
    - [A. Information](#a-information)
    - [B. History](#b-history)
  - [II. Project Overview](#ii-project-overview)
    - [A. Purpose](#a-purpose)
    - [B. What will happen for the mirror](#b-what-will-happen-for-the-mirror)
      - [1. Today](#1-today)
      - [2. Tomorrow](#2-tomorrow)
  - [III. Product](#iii-product)
    - [A. System Purpose](#a-system-purpose)
      - [1. Mirror](#1-mirror)
      - [2. Application](#2-application)
    - [B. Personas and Scenarios](#b-personas-and-scenarios)
      - [1. Sarah](#1-sarah)
      - [2. Michael](#2-michael)
      - [3. Emily](#3-emily)
    - [C. Assumptions and Constraints](#c-assumptions-and-constraints)
    - [D. Functional Requirements](#d-functional-requirements)
      - [1. First version](#1-first-version)
      - [2. Second version](#2-second-version)
      - [3. Futures improvements](#3-futures-improvements)
    - [E. Mirror Functional Analysis](#e-mirror-functional-analysis)
    - [F. Non-functional Requirements](#f-non-functional-requirements)
      - [1. cost](#1-cost)
      - [2. Environment](#2-environment)
      - [3. Security](#3-security)
  - [IV. Risk](#iv-risk)
- [Technical Specifications](#technical-specifications)
  - [I. Document](#i-document-1)
    - [A. Information](#a-information-1)
    - [B. History](#b-history-1)
    - [C. Overview](#c-overview)
  - [II. Solution](#ii-solution)
    - [A. Descritpion](#a-descritpion)
      - [1. Mirror](#1-mirror-1)
      - [2. Application](#2-application-1)
    - [B. Software architecture](#b-software-architecture)
      - [1. Architectural Components](#1-architectural-components)
        - [a. Presentation Layer](#a-presentation-layer)
        - [b. Application Layer](#b-application-layer)
        - [c. Data Management Layer](#c-data-management-layer)
      - [2. Workflow Example](#2-workflow-example)
      - [4. Technology Stack](#4-technology-stack)
    - [C. Technical Constraints](#c-technical-constraints)
      - [1. Writing Convention](#1-writing-convention)
      - [2. Documents Architecture Convention](#2-documents-architecture-convention)
      - [3. C Coding Convention](#3-c-coding-convention)
    - [D. How It Work ?](#d-how-it-work-)
    - [E. Program Architecture Diagram](#e-program-architecture-diagram)
  - [III. Quality Control](#iii-quality-control)
    - [A. Objectives](#a-objectives)
    - [B. Error Management and Corrections](#b-error-management-and-corrections)
    - [C. Documentation and Reporting](#c-documentation-and-reporting)
  - [IV. Further Considerations](#iv-further-considerations)
    - [A. Cost Estimation](#a-cost-estimation)
      - [1. Software](#1-software)
      - [2. Hardware](#2-hardware)
      - [3. Material](#3-material)
      - [4. Time \& Human](#4-time--human)
    - [B. Security](#b-security)
    - [C. Accessibility](#c-accessibility)
  - [V. Success Evaluation](#v-success-evaluation)
    - [A. Functional Performance](#a-functional-performance)
    - [B. User Experience](#b-user-experience)
    - [C. Security \& Privacy](#c-security--privacy)
    - [Glossary](#glossary)

</details>

![-](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

## I. Document

### A. Information

| Document ID | #01 |
|---|---|
| Document Owner | Grégory PAGNOUX |
| Issue date | 10/31/2024 |
| Document Name | Functional Specification|

### B. History

| Version n° | Edits completed by | Date | Description of edit |
|---|---|---|---|
| 1.1 | Grégory PAGNOUX | 2024/01/20 | Initial Release |
| 1.2 | Grégory PAGNOUX | 2024/02/25 | document improvement (mirror system purpose, document architecture) |
| 1.3 | Grégory PAGNOUX | 2024/03/03 | document improvement (application system purpose, texts of personas and scenarios) |
| 1.4 | Grégory PAGNOUX | 2024/03/10 | document improvement (pictures of personas, functional analysis) |
| 1.5 | Grégory PAGNOUX | 2024/06/02 | document improvement (application details, and design) |
| 1.6 | Grégory PAGNOUX | 2024/10/15 | end of the first version (mirror functional analysis, applications details) |
| 2.1 | Grégory PAGNOUX | 2024/11/09 | modification of components |
| 2.2 | Grégory PAGNOUX | 2024/11/14 | Update components, corections |
| 2.3 | Grégory PAGNOUX | 2025/01/30 | Update components |

## II. Project Overview

<center>

![Pheonix](/documents/img/Logo.png)

</center>

### A. Purpose

Phoenix is a healthy mirror who allows to the customer to control his temperature with a thermometer laser[^1], pulse thanks to BioActive sensor[^2], diabetes with a glucose meter[^3], and if he is alcoholic with a breathalyzer[^4].
With your Smartphone you have the possibility to track your datas.

In my family, we are the high risk type when it comes to cancer and disease like many other people. I once watched the movie "Seven Sisters" by Tommy Wirkola and saw the mirror that described every flaw in their face.
So, I decided to inspire me of this movie and of this idea, to make it a reaality. allows to people to take care of themselves in front of their mirror.
Everyone have a mirror at home.

### B. What will happen for the mirror

#### 1. Today

In 2019, 463 million people worldwide had diabetes, including 4.2 million French, according to the French Ministry of Health. with a tab, you can control your rate.
30% of road accidents last year were caused by alcohol. One breath on the mirror and you'll know whether you can hit the road or not.
Pulse rate is an indicator of potential heart problems, so it's important to monitor it regularly.
Illnesses such as influenza, bronchitis or gastroenteritis are usually discovered late, and appointments with doctors become complicated, whereas it would be enough to check one's temperature every day to take care of oneself as soon as possible.

These are habits you can start with the connected healthly mirror, Phoenix.

#### 2. Tomorrow

By 2045, there will be 700 million diabetics worldwide and the number of accidents caused by alcohol has struggled to fall in recent years, this mirror should be of use to over 22 million French people.

*sources :*

- [French Ministry of Health](https://sante.gouv.fr/soins-et-maladies/maladies/article/diabete#:~:text=Les%20chiffres%20clefs%20du%20diabète,700%20millions%20d%27ici%202045.)
- [road safety](https://www.securite-routiere.gouv.fr/dangers-de-la-route/lalcool-et-la-conduite#:~:text=Les%20accidents%20impliquant%20de%20l,pour%20les%20accidents%20sans%20alcool.)

## III. Product

### A. System Purpose

#### 1. Mirror

![design](/documents/img/Design.png)

- **Switched off**

When the mirror is switched off, the user can use it for make-up, hair styling, etc. without any problem.

To switch off the mirror, press the power button and the main light comes off, the time is disappear on the mirror's screen and the three LEDs light up for 3 seconds to prevent the customer.

- **Switched on**

If the user wants to do more, he must press the power button to switch it on after plugging it in. The main light comes on, the time is displayed on the mirror's screen and the three LEDs light up for 3 seconds to check operation.

- **Set time**

The user presses the plus button for 3 seconds and the hours blink. The user can press 1 time to increase the hours by 1 and validate with the corresponding button, which lights up the green light for 3 seconds. Now the minutes flash and the user can do the same thing, and when he validates, nothing else blinkes.

- **Breathalyzer**

To use the breathalyzer, the user must press the first button to the left of the 4 option buttons (with the image of the bottle). The yellow light flashes when the user can blow on the sensor for at least 5 seconds.
The green light flashes when the alcohol level is within the limit, and the red light when the level is over the limit.

- **Pulse**

To use the BioActive sensor, the user must press the second of the 4 option buttons (with the image of the oscillogram). The yellow light flashes when the user can press the sensor again for at least 5 seconds.
The pulse value is displayed on the mirror's screen.

- **Glucose meter**

To use the glucose meter, the user must press the third of the four option buttons (with the image of the drop). The yellow light flashes when the user can perform a blood glucose test.
The glucose level is displayed on the mirror screen.

- **Thermometer**

To use the thermometer, the user must press the last button to the right of the 4 option buttons (with the celsius image). The yellow light flashes when the user stands in front of the mirror for at least 5 seconds.
The temperature is displayed on the mirror screen.

- **Connect phone**

The user presses the validation button for 3 seconds and the yellow light flashes for 10 seconds. The user can connect their phone to the mirror during this time. When the connection is established, the green light blink for 3 secondes, otherwise the red light blink for 3 seconds.

#### 2. Application

Here are the application's functionalities.
(As this is not the main project, but an option added to the mirror to complete its use, there will be no further details).

- **Installation**

The application can be install from Google Play in the first time

- **Opening**

To open the application, you click on the icon that he appear on your smartphone when you install it and for the first time, you need to sign up with your mail adress. After, you have just to click on your profil (you can have 5 profils with one mirror).

- **Profil**

![profil1](/documents/img/Profil1.png)
![profil2](/documents/img/Profil2.png)

On your profil, you can modify your profil picture, and add information about you age, your weight, and your size to calculate your BMI.

- **Settings**

![settings1](/documents/img/Settings1.png)
![settings2](/documents/img/Settings2.png)

On the settings page, you can modify your mail adress, and your password, you can change with the night or day mode, and change the language between french or english for the first time.

- **Data graphs**

These graphs can be found on each options page for tracking their data in each category.

- **Call a doctor**

On the call page, you have the possibility to register all doctors such as general practitioners, dentists, home nurses, etc. You can put their phone number, their adress, their mail and you can contact them directly on the application.

### B. Personas and Scenarios

#### 1. Sarah

The working mother who cares about her children's health

![Sarah's persona](/documents/img/Sarah.png)

Sarah is a 35-year-old working mother with a hectic schedule. She's always concerned about her family's health, especially since they have a history of cancer and other diseases.

Sarah recently stumbled upon Phoenix, the healthy mirror, and was intrigued by its features. She envisions using it to monitor her two children's health more efficiently while seamlessly integrating it into their daily routines.
With Phoenix, Sarah can easily track their temperature, pulse, and glucose levels, ensuring she stays on top of their health despite her busy lifestyle. Plus, the breathalyzer feature gives her peace of mind regarding alcohol consumption.

Sarah appreciates the convenience of accessing all this data through her smartphone, making it easier for her to keep track of everyone's health status.

#### 2. Michael

The Fitness Enthusiast

![Michael's persona](/documents/img/Michael.png)

Michael is a 28-year-old fitness enthusiast who's always looking for ways to optimize his health and performance.

He came across Phoenix while researching innovative health gadgets and immediately saw its potential in his daily routine. With Phoenix, Michael can monitor various health metrics like temperature, pulse, and glucose levels, helping him fine-tune his fitness regimen for optimal results. The breathalyzer feature is particularly useful for Michael, as he occasionally enjoys a few drinks with friends but wants to ensure he maintains a healthy balance.

Being able to track all this data on his smartphone motivates Michael to stay consistent with his health goals and allows him to make informed decisions about his lifestyle choices.

#### 3. Emily

The Health-Conscious Senior

![Emily's persona](/documents/img/Emily.png)

Emily is a 68-year-old retiree who takes her health very seriously. She's always been proactive about managing her health, especially since her family has a history of diabetes and other chronic conditions.

When Emily discovered Phoenix, she was impressed by its innovative features and saw it as a valuable tool in her health maintenance routine. With Phoenix, Emily can easily monitor her temperature, pulse, and glucose levels from the comfort of her own home, giving her greater peace of mind about her health status. The breathalyzer feature also appeals to Emily, as it allows her to keep track of her alcohol intake, ensuring she stays within safe limits.

Emily appreciates the simplicity of accessing all her health data on her smartphone, making it easier for her to share important information with her healthcare provider during check-ups.

### C. Assumptions and Constraints

**Hygiene**
We need to pay close attention to the hygiene aspect of the product, as the glucose meter and breathalyzer require the deposition of particles that can dirty the mirror.

**Data**
If we want to have a connected mirror with smartphone, we need to interest us on the **the reglementation of data backups**.
There are three different archives depending on the type of data :

- **Active database archiving** where data that are no longer useful to the enterprise (for example, data on job seekers to which they have not followed up) are deleted once the reason for the study has been completed (after a maximum of two years).
- **Intermediate archiving** where data are saved even after the purpose of data collection has been achieved as they are still of interest to the enterprise. The duration is set by the person responsible and must be relevant to its usefulness.
- **Final archiving** where data that remains of great interest in the future without an end date are saved, after an upstream check.

*source :*

- [Acronis](https://www.acronis.com/fr-fr/blog/posts/gdpr/)
- [CNIL (general rules)](https://www.cnil.fr/fr/reglement-europeen-protection-donnees)
- [CNIL (datas backups duration)](https://www.cnil.fr/fr/passer-laction/les-durees-de-conservation-des-donnees)

### D. Functional Requirements

#### 1. First version

- take temperature
- print value on the mirror
- respect for hygiene
- user-friendly

#### 2. Second version

- take pulse
- lights
- phone connection

#### 3. Futures improvements

- take glucose level
- more aesthetics

The breathalyzer option has been abandoned because the system was too diffcult to implement and can't be compatible with the moisture-resistant criteria.

### E. Mirror Functional Analysis

![functional analysis, mirror](/documents/img/Mirror_Functional_Analysis.png)

### F. Non-functional Requirements

#### 1. cost

- **Components**

| WHICH PART | MATERIAL | PRICE | V0.1 | V0.2 |
| :-: | :-: | :-: | :-: | :-: |
| mirror | [screen]() | € | Yes | Yes |
|  | [transparent acrilic]() | € | Yes | Yes |
|  | [one way film](https://www.amazon.fr/gp/product/B07BFTRLTK/ref=as_li_ss_tl?ie=UTF8&linkCode=sl1&ta[…]21&linkId=4a5dfebd14b4c2e555694ac2f2eee4b7&language=fr_FR&th=1) | 11.99€ | Yes | Yes |
|  | [wood glue]() | € | Yes | Yes |
|  | [wooden plank]() | € | Yes | Yes |
|  | [hot glue]() | € | Yes | Yes |
| Component add to the mirror | [pressure sensor](https://www.amazon.fr/Capteur-Pression-Couche-Précision-Résistance/dp/B07P9Z7FR6/ref=asc_df_B07P9Z7FR6/?tag=googshopfr-21&linkCode=df0&hvadid=353896712114&hvpos=&hvnetw=g&hvrand=4898371625524598186&hvpone=&hvptwo=&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=9055097&hvtargid=pla-869632555564&psc=1&tag=&ref=&adgrpid=71676698856&hvpone=&hvptwo=&hvadid=353896712114&hvpos=&hvnetw=g&hvrand=4898371625524598186&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=9055097&hvtargid=pla-869632555564) | 11.89€ | No | Yes |
|  | [green, yellow, red lights](https://www.amazon.fr/Miuzei-Electronique-R%C3%A9sistances-Alimentation-Programmation/dp/B0C5CD2DJW/ref=asc_df_B0C5CD2DJW?tag=bingshoppin0f-21&linkCode=df0&hvadid=79989660653509&hvnetw=o&hvqmt=e&hvbmt=be&hvdev=c&hvlocint=&hvlocphy=&hvtargid=pla-4583589124976046&psc=1) | on the eletronic kit | No | Yes |
|  | [lights](https://www.amazon.fr/Tayire-Gradateur-3000K-R%C3%A9tro%C3%A9clairage-R%C3%A9tro-%C3%89clairage/dp/B0B3CHTS5J/ref=sxin_15_pa_sp_search_thematic_sspa?adgrpid=1364494868369871&content-id=amzn1.sym.ec09204b-08fd-4427-a6e2-1b1b8f14bc8d%3Aamzn1.sym.ec09204b-08fd-4427-a6e2-1b1b8f14bc8d&cv_ct_cx=bande%2Bled&dib=eyJ2IjoiMSJ9.l-jqxGpr3Yw69StR6JKhhmlPBu0JbSI8KgvZ8JwUSZxyb-mFqTJH8cmBSKuILTjoYBRJZ1mu_VbVC4Qsmfd74g.KU-HvzoDfHpQs146_wpm08wXliiNfWmYc3dXvvrkZ5g&dib_tag=se&hvadid=85281356732804&hvbmt=bp&hvdev=c&hvlocphy=126674&hvnetw=o&hvqmt=p&hvtargid=kwd-85281460372238%3Aloc-66&hydadcr=28259_2269076&keywords=bande%2Bled&msclkid=a0ca2681f9d8105a0c7c41ae6839ae2e&pd_rd_i=B0B3CHTS5J&pd_rd_r=41f17886-c437-46f9-8ca3-9fdbd3a859ba&pd_rd_w=oZ62s&pd_rd_wg=8KNIY&pf_rd_p=ec09204b-08fd-4427-a6e2-1b1b8f14bc8d&pf_rd_r=TFZ8Y438N0SQYGSXM2TR&qid=1731170790&sbo=RZvfv%2F%2FHxDF%2BO5021pAnSA%3D%3D&sr=1-5-1c0bc4f8-9a4b-47e4-b117-3d30b74c13f1-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9zZWFyY2hfdGhlbWF0aWM&th=1) | 11.99€ | No | Yes |
| Options | [thermometer laser]() | € | Yes | Yes |
|  | [BioActive sensor](https://fr.hwlibre.com/moniteur-de-fr%C3%A9quence-cardiaque-max30102-et-module-oxym%C3%A8tre-pour-arduino/) | 7.49€ | No | Yes |
|  | application | depends on host/online cost | No | Yes |
| internal component | [electronic kit](https://www.amazon.fr/Miuzei-Electronique-R%C3%A9sistances-Alimentation-Programmation/dp/B0C5CD2DJW/ref=asc_df_B0C5CD2DJW?tag=bingshoppin0f-21&linkCode=df0&hvadid=79989660653509&hvnetw=o&hvqmt=e&hvbmt=be&hvdev=c&hvlocint=&hvlocphy=&hvtargid=pla-4583589124976046&psc=1) | 49.99€ | Yes | Yes |
|  | [Raspberry Pi](https://www.amazon.fr/gp/product/B07BDR5PDW/ref=as_li_ss_tl?ie=UTF8&psc=1&linkCode=sl1&tag=lfpoulain-21&linkId=252056d6ac9e69159f5b96d10e9801d4&language=fr_FR) | 52.90€ | Yes | Yes |
|  | [micro SD card]() | 15€ | Yes | Yes |
|  | [telemeter sensor](9.99) | € | Yes | Yes |
|  | [male plug]() | 5€ | Yes | Yes |
|  | [cables](https://www.amazon.fr/gp/product/B07HCLY31D/ref=as_li_ss_tl?ie=UTF8&linkCode=sl1&tag=lfpoulain-21&linkId=92558ef8ffa2fded52866019426b9366&language=fr_FR&th=1) | 20.18€ | Yes | Yes |
|  | [cable screen to raspberry]() | € | Yes | Yes |
|  | [alimentation](https://www.amazon.fr/gp/product/B00MWQD43U/ref=as_li_ss_tl?ie=UTF8&linkCode=sl1&tag=lfpoulain-21&linkId=382179bbb23e9cb361d9e6ec44eb9dc8&language=fr_FR&th=1) | 14.81€ | Yes | Yes |
|  |  |  |  |  |
| total |  |  | 169.87€ | 201.24€ |

*sources :*

- [Playlist intelligent miror](https://lesfrerespoulain.fr/magicmirror/)

- **Time conception**

First version :

- November 2024 - May 2025

#### 2. Environment

- MacOS on development
- Visual Studio Code
- Arduino language (mirror)
- Java (application)

#### 3. Security

- respect RGPD and data saving law
- solid product
- moisture-resistant

## IV. Risk

- **Competitors**

For this product, there is a main competitor called [Care OS](https://www.care-os.com). The company has already marketed Poseidon, a healthy mirror and has now developed a new mirror, [BMind](../../archives/BMind/BMind%20-%20Product%20sheet.pdf), with a lot of daily hygiene functions such as tooth brushing, water monitoring or skin analysis. There are also tools and entertainment such as games, videos or music to encourage children to take care of themselves.
This product has around fifteen partners including [Teraillon](https://www.terraillon.com/en), one of the leading manufacturers of product for the home. There is also [Pierre Fabre](https://www.pierre-fabre.com/en), a major research laboratory into cancers and diseases of the body.
Their mirror is not yet available for sale, but will cost between 3,000 and 5,000 dollars depending on the options chosen.

**product problem**
One of the big problems to consider with this mirror is the increase in people's paranoia about illness and the growing number of people suffering from hypochondria.

![-](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

# Technical Specifications

![-](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

## I. Document

### A. Information

| Document ID | #02 |
|---|---|
| Document Owner | Grégory PAGNOUX |
| Issue date | 2024/02/06 |
| Document Name | Technical Specification |

### B. History

| Version | Edits completed by | Date | Description of edit |
|---|---|---|---|
| 1.1 | Grégory PAGNOUX | 2024/03/17 | Template and make part I, II and Glossary |
| 1.2 | Grégory PAGNOUX | 2024/08/11 | Finish part II/A/2 and make II/B |
| 1.3 | Grégory PAGNOUX | 2025/02/10 | Writing and documents architecture conventions |
| 1.4 | Grégory PAGNOUX | 2025/03/20 | Coding conventions and part IV and V |

### C. Overview

<center>

![Pheonix](/documents/img/Logo.png)

</center>

Phoenix is a healthy mirror who allows to the customer to control his temperature with a thermometer laser[^1], pulse thanks to BioActive sensor[^2], diabetes with a glucose meter[^3], and if he is alcoholic with a breathalyzer[^4].
With your Smartphone you have the possibility to track your datas.

## II. Solution

### A. Descritpion

![design](/documents/img/Design.png)

#### 1. Mirror

- **Switched off**

When the mirror is switched off, the user can use it for make-up, hair styling, etc. without any problem.

To switch off the mirror, press the power button and the main light comes off, the time is disappear on the mirror's screen and the three LEDs light up for 3 seconds to prevent the customer.

- **Switched on**

If the user wants to do more, he must press the power button to switch it on after plugging it in. The main light comes on, the time is displayed on the mirror's screen and the three LEDs light up for 3 seconds to check operation.

- **Set time**

The user presses the plus button for 3 seconds and the hours blink. The user can press 1 time to increase the hours by 1 and validate with the corresponding button, which lights up the green light for 3 seconds. Now the minutes flash and the user can do the same thing, and when he validates, nothing else blinkes.

- **Breathalyzer**

To use the breathalyzer, the user must press the first button to the left of the 4 option buttons (with the image of the bottle). The yellow light flashes when the user can blow on the sensor for at least 5 seconds.
The green light flashes when the alcohol level is within the limit, and the red light when the level is over the limit.

- **Pulse**

To use the BioActive sensor, the user must press the second of the 4 option buttons (with the image of the oscillogram). The yellow light flashes when the user can press the sensor again for at least 5 seconds.
The pulse value is displayed on the mirror's screen.

- **Glucose meter**

To use the glucose meter, the user must press the third of the four option buttons (with the image of the drop). The yellow light flashes when the user can perform a blood glucose test.
The glucose level is displayed on the mirror screen.

- **Thermometer**

To use the thermometer, the user must press the last button to the right of the 4 option buttons (with the celsius image). The yellow light flashes when the user stands in front of the mirror for at least 5 seconds.
The temperature is displayed on the mirror screen.

- **Connect phone**

The user presses the validation button for 3 seconds and the yellow light flashes for 10 seconds. The user can connect their phone to the mirror during this time. When the connection is established, the green light blink for 3 secondes, otherwise the red light blink for 3 seconds.

#### 2. Application

- **Installation**

The application can be install from Google Play in the first time

- **Opening**

To open the application, you click on the icon that he appear on your smartphone when you install it and for the first time, you need to sign up with your mail adress. After, you have just to click on your profil (you can have 5 profils with one mirror).

- **Profil**

On your profil, you can modify your profil picture, and add information about you age, your weight, and your size to calculate your BMI.

- **Settings**

On the settings page, you can modify your mail adress, and your password, you can change with the night or day mode, and change the language between french or english for the first time.

- **Data graphs**

These graphs can be found on each options page for tracking their data in each category.

- **Call a doctor**

On the call page, you have the possibility to register all doctors such as general practitioners, dentists, home nurses, etc. You can put their phone number, their adress, their mail and you can contact them directly on the application.

### B. Software architecture

he architecture for Phoenix, a smart health mirror, will be designed around modular, service-oriented principles to facilitate integration of various health monitoring functions and a user-friendly interface. The architecture will ensure data privacy, ease of integration, and secure communication with smartphones. Phoenix’s software architecture is divided into three primary layers:

- **Presentation Layer**: Manages user interactions with the mirror’s display and smartphone app.
- **Application Layer**: Contains core business logic, handling user inputs, controlling hardware, and data processing.
- **Data Management Layer**: Manages data storage, retrieval, and communication with the smartphone app, including user data privacy and compliance with data regulations.

#### 1. Architectural Components

##### a. Presentation Layer

The Presentation Layer provides the visual and interactive interface on the mirror and smartphone application. This includes:

- **Mirror Display Interface**

**User Interface (UI)**: A simple, intuitive UI on the mirror display shows time, temperature, pulse, glucose levels, and alcohol detection results. The interface will use dynamic visual cues, such as blinking LED indicators for status (yellow for action required, green for safe levels, red for high levels).
**User Feedback**: Provides immediate feedback for each action, such as "Blow into the breathalyzer," “Check glucose levels,” and shows results on the screen.

- **Mobile App Interface**

**User Dashboard**: A companion app on the user’s smartphone to display historical health data, trends, and alerts.
**Data Syncing**: Interfaces with the mirror over Bluetooth for real-time data synchronization and allows users to connect and view data seamlessly.

##### b. Application Layer

This layer houses the core logic responsible for managing user interactions, hardware control, and data processing. Key components include:

- **Health Monitoring Services**

**Temperature Service**: Interfaces with the thermometer sensor to collect and display the user’s body temperature.
**Pulse Monitoring Service**: Connects with the BioActive sensor to capture pulse data and display it on the screen.
**Glucose Monitoring Service**: Interacts with the glucose meter for blood glucose level readings.
**Breathalyzer Service**: Manages data from the breathalyzer to analyze alcohol levels.

- **Device Control Manager**

**Power Control Module**: Manages mirror power states, including sleep, power on/off, and LED control.
**Sensor Control Module**: Coordinates the activation and deactivation of sensors, controlling workflows for each health metric (temperature, pulse, glucose, alcohol).
**Light Control Module**: Handles visual feedback using LED lights to signal different stages or results (e.g., green for safe alcohol level, red for high levels).

- **Bluetooth Communication Module**

Facilitates data transmission between the mirror and smartphone app, managing pairing, connection stability, and secure data transfer.

- **Error Handling & User Notification**

**Notification Manager**: Provides user alerts on the mirror and app, e.g., low battery warnings, sensor errors, or invalid readings.
**Error Logging**: Logs system issues for diagnostics and maintenance.

##### c. Data Management Layer

This layer focuses on data storage, security, and regulatory compliance, especially concerning health data.

- **Local Data Storage**

**Temporary Data Cache**: Stores session data temporarily on the mirror, discarding it once synced to the smartphone.
**Data Retention Policy**: Implements time-based deletion for data, following GDPR and other regional privacy laws.

- **Data Syncing and Backup**

**Smartphone Sync**: Ensures user data is synced to their smartphone when connected. Data is encrypted during transfer.
**User-Controlled Data Backup**: Allows users to enable/disable data backups on the smartphone app, giving them control over data retention and sharing.

- **Security and Privacy Management**

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

### C. Technical Constraints

#### 1. Writing Convention

| Notation | How | Usage | Example |
| :-: | :-: | :-: | :-: |
| flatcase | we attach each word and in lowercase | naming folders | foldername |
| Pascal_Snake_Case | we attach each word and write the first letter of each word in uppercase | naming files | File_Name |
| comment = ```<!--word-->``` | write your comment inside to have a reminder of your informations without have it visible on the document | organise and summarise informations that you need to put on each part of your document | ```<!--The following declaration creates a query. It doesn't appear on the document.-->``` |
| Titles = I.A.1.a | the first index is the most general title and the last one is to have the most detail part (preceded by #) | to have a clear idea of the organisation of the document | <pre> ```# I. Title name``` <br> ```## A. Title name``` <br> ```### 1. Title name``` <br> ```#### a. Title name``` </pre> |
| Table of content | at the beginning of the document | find a specific part of the document without going through it all |  |
| Glossary | at the end of the document | understand some word that we don't know without loose time on google |  |

#### 2. Documents Architecture Convention

```txt
📦 MOONSHOT
└── 📁 archives
└── 📁 dev
|    └── 📝 ...
└── 📁 documents
|    └── 📁 img
|    |   └── 🖼️ Breathalyzer.png
|    |   └── ...
|    └── 📁 Management
|    |   └── 📁 reports
|    |   |   └── 📝 2024-05_Report.md
|    |   |   └── ...
|    |   └── 📝 POULAIN_Mail_Report.md
|    |   └── 📝 Template_Mail_Report.md
|    └── 📁 specifications
|    |   └── 📝 Functional_Specifications.md
|    |   └── 📝 Technical_Specifications.md
|    |   └── 📝 TestCase.md
|    |   └── 📝 TestPlan.md
|    └── 📝 Action_Plan.md
└── 📁 final_render
|    └── 📝 Specifications.md
|    └── 📝 Report.md
└── 📝 README.md 
```

#### 3. C Coding Convention

The language used to develop the project is Arduino

| Notation | How | Usage | Example |
| :-: | :-: | :-: | :-: |
| **Pascal Casing** | Attach each word and capitalize it to know where the next word starts (e.g., `DataService`). | Naming Classes | ```cpp\nclass DataService {\n};``` |
|  |  | Naming Records | ```cpp\nstruct PhysicalAddress {\n};``` |
| **Camel Casing** | The first word is lowercase, and each subsequent word starts with a capital letter (e.g., `readSensorData`). | Naming Variables and Functions | ```cpp\nint readSensorData() {}``` |
| **Snake Casing** | Use underscores between words (e.g., `led_status`). | Naming Constants (sometimes for readability) | ```cpp\nconst int led_status = 0;``` |
| **Upper Snake Casing** | All letters are uppercase with underscores between words (e.g., `MAX_SPEED`). | Defining Constants and Macros | ```cpp\n#define MAX_SPEED 255``` |
| **Comment `//`** | Start each line with two slashes and an uppercase letter and finish the comment with a period. | Giving more information about the code | ```cpp\n// The following declaration creates a query. It does not run the query.``` |
| **Comment `/* */`** | Multi-line comments are enclosed between `/*` and `*/`. | Explaining larger sections of code | ```cpp\n/* This function reads sensor data. \n   It processes the input and returns a value. */``` |
| **Indentation** | Use two or four spaces (no tabs) to align code blocks. | Improving readability | ```cpp\nvoid loop() {\n    digitalWrite(LED_BUILTIN, HIGH);\n}``` |
| **Curly Braces `{ }`** | Place the opening brace `{` on the same line as the function/class definition and align the closing brace `}` properly. | Structuring Code Blocks | ```cpp\nvoid setup() {\n    pinMode(13, OUTPUT);\n}``` |
| **Semicolons `;`** | Every statement must end with a semicolon (`;`). | Ending Statements | ```cpp\nint x = 10;``` |
| **Function Names** | Use verbs to describe actions in camel case (e.g., `getTemperature`). | Naming Functions | ```cpp\nfloat getTemperature() {}``` |
| **Constants** | Use `const` or `#define` with meaningful names. | Defining Fixed Values | ```cpp\nconst int LED_PIN = 13;``` |
| **Variable Names** | Use descriptive names in camel case. Avoid single-letter names except for loop counters. | Naming Variables | ```cpp\nint sensorValue = analogRead(A0);``` |
| **Pointer Notation** | Use `*` for pointer variables, and always initialize them. | Handling Memory Addresses | ```cpp\nint *ptr = &value;``` |

### D. How It Work ?

<!--TODO-->

### E. Program Architecture Diagram

![Program Architechture Diagram](/documents/img/Architecture_Diagram.png)

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

## IV. Further Considerations

### A. Cost Estimation

#### 1. Software

The software cost estimation considers development, testing, and maintenance expenses. The following factors contribute to the cost:

- Development Costs: Salaries of software engineers, UI/UX designers, and testers.
- Licensing Fees: Any third-party software or libraries required.
- Cloud Services: Costs for data storage, backup, and syncing.
- Maintenance: Updates, bug fixes, and feature enhancements.

| Item | Estimated cost |
| - | - |
| Development Tools (IDEs, Libraries) | $2,000 |
| UI/UX Design | $3,000 |
| Cloud Services | $1,500/year |
| Maintenance & Support | $5,000/year |
|  |  |
| Total | $11,500 (initial), $6,500/year |

*We have to take in consideration that the project is realised by 1 student in 5 years free of charge, some of those charge are out of date or may vary.*

#### 2. Hardware

Hardware costs include components necessary for the functionality of the Phoenix mirror:

- Microcontroller: Arduino or similar processing unit.
- Sensors: Thermometer, Pulse sensor, Glucose meter, and Breathalyzer.
- Display: Mirror-integrated LED or OLED display.
- Connectivity: Bluetooth module for smartphone sync.
- Power Supply: Adapter and battery backup.

| Component | Estimated cost |
| - | - |
| Microcontroller (Arduino) | $50 |
| Thermometer Sensor | $30 |
| Pulse Sensor | $25 |
| Glucose Meter Sensor | $40 |
| Breathalyzer Sensor | $35 |
| OLED Display | $60 |
| Bluetooth Module | $20 |
| Power Supply | $15 |
|  |  |
| Total | $275 per unit |

#### 3. Material

Materials for the mirror's construction include:

- Frame and Glass: Smart mirror surface with reflective coating.
- LED Lights: Illumination and indicator lights.
- Mounting Kit: Brackets and screws for installation.

| Material | Estimated cost |
| - | - |
| Screen |  |
| Transparent Acrilic |  |
| One Way Film | €11.99 |
| Wood Glue |  |
| Wooden Plank |  |
| Hot Glue |  |
|  |  |
| Total |  |

#### 4. Time & Human

The estimated time and human resource allocation for the project:

- Development Time: 6 months
- Team Members: 5 Developers, 1 UI/UX Designers, 2 Testers, 1 Project Manager

| Role | Number | Cost per month | Total Cost (6 months) |
| - | - | - | - |
| Developers | 5 | $5,000 | $150,000 |
| UI/UX Designers | 2 | $4,000 | $48,000 |
| Testers | 2 | $3,500 | $42,000 |
| Project Manager | 1 | $6,000 | $36,000 |
|  |  |  |  |
| Total | 10 |  | $276,000 |

*We have to take in consideration that the project is realised by 1 student in 5 years free of charge.*

### B. Security

To ensure the security of the Phoenix mirror, the following measures are implemented:

- Data Encryption: All user data is encrypted during storage and transmission.
- Secure Bluetooth Communication: Implementing authentication and encryption for pairing with smartphones.
- User Authentication: Users must authenticate via the mobile app before accessing sensitive data.
- Regular Security Updates: Patching vulnerabilities and updating security protocols.
- Compliance with GDPR: Ensuring data privacy and allowing users to control their information.

### C. Accessibility

To ensure the Phoenix mirror is accessible to all users:

- Voice Commands: Support for voice interactions to assist users with disabilities.
- Large Display and High Contrast UI: Ensuring readability for visually impaired users.
- Multiple Language Support: Available in multiple languages including English and French.
- Mobile App Compatibility: Works on both Android and iOS devices.
- Customizable Alerts: Users can receive notifications via sound, vibration, or visual cues.

These considerations ensure that Phoenix is inclusive, secure, and cost-effective while delivering a high-quality user experience.

## V. Success Evaluation

To evaluate the success of the Phoenix Mirror project, the following key performance indicators (KPIs) and assessment criteria will be considered:

### A. Functional Performance

- System Accuracy: Sensors provide at least 95% accuracy in measuring health metrics (e.g., temperature, pulse, glucose levels).
- Real-time Processing: Data is processed and displayed within 2 seconds of measurement.
- Connectivity Reliability: Bluetooth and cloud synchronization success rate of 98% or higher.
- User Authentication Efficiency: Secure login with a failure rate of less than 1%.

### B. User Experience

- Ease of Use: User feedback surveys indicate at least 85% satisfaction in usability.
- Accessibility Compliance: The mirror passes WCAG 2.1 AA standards for accessibility.
- App Responsiveness: The mobile app loads and syncs within 3 seconds in 90% of test cases.

### C. Security & Privacy

- Data Protection: No critical security vulnerabilities are detected in penetration tests.
- Compliance: The system complies with GDPR and HIPAA standards for data privacy.
- Encryption Standards: All sensitive data is encrypted using AES-256.

### Glossary

[^1]: **[Thermometer laser](https://www.amazon.fr/Thermom%C3%A8tre-IDOIT-Thermometre-Infrarouge-Affichage/dp/B08DFXYWNN/ref=sr_1_32?adgrpid=54908680263&hvadid=275507361595&hvdev=c&hvlocphy=9055097&hvnetw=g&hvqmt=b&hvrand=18183104330674911873&hvtargid=kwd-312280216289&hydadcr=14196_1754673&keywords=thermometre+laser&qid=1683279299&sr=8-32)**
![thermometer laser](/documents/img/Thermometer_Laser.jpg)
It's a device allows to mesure the temperature of the body.

[^2]: **[Samsung Galaxy Watch 4](https://www.pocket-lint.com/fr-fr/montres-connectees/acheteurs-guides/samsung/157658-samsung-galaxy-watch-4-vs-galaxy-watch-4-differences-classiques-comparees/)**
![Samsung Galaxy Watch 4](/documents/img/Samsung_Galaxy_Watch_4.jpg)
Use the BioActive sensor technologie. It's a technology developed by Samsung for its connected watches which provides simple yet powerful measurements and insights that you can use to take control of your health.
[presentation of BioActive sensor options](https://www.youtube.com/watch?v=yEoCDSwuJHc)

[^3]: **[glucose meter](https://www.amazon.com/Glucose-Monitor-Glucometer-Lancets-Solution/dp/B08LYC288R/ref=zg_mw_3777171_sccl_2/147-1452400-9255329?psc=1)**
![glucose meter](/documents/img/Glucose_Meter.png)
It's a device allows to mesure the concentration of glucose in the blood thanks a little needle and a strip glucose paper dipped.

[^4]: **[breathalyzer](https://www.ebay.fr/itm/224971220617?chn=ps&mkevt=1&mkcid=28#rpdCntId)**
![breathalyzer](/documents/img/Breathalyzer.png)
Device which evaluate if you are alcoholic thanks to sensors that analyze the air when you blow.
