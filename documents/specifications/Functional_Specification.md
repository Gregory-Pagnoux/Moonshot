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
    - [Glossary](#glossary)

</details>

![-](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

### I. Document

#### A. Information

| Document ID | #01 |
|---|---|
| Document Owner | Grégory PAGNOUX |
| Issue date | 10/31/2024 |
| Document Name | Functional Specification|

#### B. History

| Version n° | Edits completed by | Date | Description of edit |
|---|---|---|---|
| 1.1 | Grégory PAGNOUX | 01/20/2024 | Initial Release |
| 1.2 | Grégory PAGNOUX | 02/25/2024 | document improvement (mirror system purpose, document architecture) |
| 1.3 | Grégory PAGNOUX | 03/03/2024 | document improvement (application system purpose, texts of personas and scenarios) |
| 1.4 | Grégory PAGNOUX | 03/10/2024 | document improvement (pictures of personas, functional analysis) |
| 1.5 | Grégory PAGNOUX | 06/02/2024 | document improvement (application details, and design) |
| 1.6 | Grégory PAGNOUX | 10/15/2024 | end of the first version (mirror functional analysis, applications details) |
| 2.1 | Grégory PAGNOUX | 11/09/2024 | modification of components |
| 2.2 | Grégory PAGNOUX | 11/14/2024 | Update components, corections |
| 2.3 | Grégory PAGNOUX | 01/30/2025 | Update components |

### II. Project Overview

<center>

![Pheonix](/documents/img/Logo.png)

</center>

#### A. Purpose

Phoenix is a healthy mirror who allows to the customer to control his temperature with a thermometer laser[^1], pulse thanks to BioActive sensor[^2], diabetes with a glucose meter[^3], and if he is alcoholic with a breathalyzer[^4].
With your Smartphone you have the possibility to track your datas.

In my family, we are the high risk type when it comes to cancer and disease like many other people. I once watched the movie "Seven Sisters" by Tommy Wirkola and saw the mirror that described every flaw in their face.
So, I decided to inspire me of this movie and of this idea, to make it a reaality. allows to people to take care of themselves in front of their mirror.
Everyone have a mirror at home.

#### B. What will happen for the mirror

##### 1. Today

In 2019, 463 million people worldwide had diabetes, including 4.2 million French, according to the French Ministry of Health. with a tab, you can control your rate.
30% of road accidents last year were caused by alcohol. One breath on the mirror and you'll know whether you can hit the road or not.
Pulse rate is an indicator of potential heart problems, so it's important to monitor it regularly.
Illnesses such as influenza, bronchitis or gastroenteritis are usually discovered late, and appointments with doctors become complicated, whereas it would be enough to check one's temperature every day to take care of oneself as soon as possible.

These are habits you can start with the connected healthly mirror, Phoenix.

##### 2. Tomorrow

By 2045, there will be 700 million diabetics worldwide and the number of accidents caused by alcohol has struggled to fall in recent years, this mirror should be of use to over 22 million French people.

*sources :*

- [French Ministry of Health](https://sante.gouv.fr/soins-et-maladies/maladies/article/diabete#:~:text=Les%20chiffres%20clefs%20du%20diabète,700%20millions%20d%27ici%202045.)
- [road safety](https://www.securite-routiere.gouv.fr/dangers-de-la-route/lalcool-et-la-conduite#:~:text=Les%20accidents%20impliquant%20de%20l,pour%20les%20accidents%20sans%20alcool.)

### III. Product

#### A. System Purpose

##### 1. Mirror

![design](/documents/img/Design.png)

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

Here are the application's functionalities.
(As this is not the main project, but an option added to the mirror to complete its use, there will be no further details).

**installation**

The application can be install from Google Play in the first time

**opening**

To open the application, you click on the icon that he appear on your smartphone when you install it and for the first time, you need to sign up with your mail adress. After, you have just to click on your profil (you can have 5 profils with one mirror).

**profil**

![profil1](/documents/img/Profil1.png)
![profil2](/documents/img/Profil2.png)

On your profil, you can modify your profil picture, and add information about you age, your weight, and your size to calculate your BMI.

**settings**

![settings1](/documents/img/Settings1.png)
![settings2](/documents/img/Settings2.png)

On the settings page, you can modify your mail adress, and your password, you can change with the night or day mode, and change the language between french or english for the first time.

**data graphs**

These graphs can be found on each options page for tracking their data in each category.

**call a doctor**

On the call page, you have the possibility to register all doctors such as general practitioners, dentists, home nurses, etc. You can put their phone number, their adress, their mail and you can contact them directly on the application.

#### B. Personas and Scenarios

##### 1. Sarah

The working mother who cares about her children's health

![Sarah's persona](/documents/img/Sarah.png)

Sarah is a 35-year-old working mother with a hectic schedule. She's always concerned about her family's health, especially since they have a history of cancer and other diseases.

Sarah recently stumbled upon Phoenix, the healthy mirror, and was intrigued by its features. She envisions using it to monitor her two children's health more efficiently while seamlessly integrating it into their daily routines.
With Phoenix, Sarah can easily track their temperature, pulse, and glucose levels, ensuring she stays on top of their health despite her busy lifestyle. Plus, the breathalyzer feature gives her peace of mind regarding alcohol consumption.

Sarah appreciates the convenience of accessing all this data through her smartphone, making it easier for her to keep track of everyone's health status.

##### 2. Michael

The Fitness Enthusiast

![Michael's persona](/documents/img/Michael.png)

Michael is a 28-year-old fitness enthusiast who's always looking for ways to optimize his health and performance.

He came across Phoenix while researching innovative health gadgets and immediately saw its potential in his daily routine. With Phoenix, Michael can monitor various health metrics like temperature, pulse, and glucose levels, helping him fine-tune his fitness regimen for optimal results. The breathalyzer feature is particularly useful for Michael, as he occasionally enjoys a few drinks with friends but wants to ensure he maintains a healthy balance.

Being able to track all this data on his smartphone motivates Michael to stay consistent with his health goals and allows him to make informed decisions about his lifestyle choices.

##### 3. Emily

The Health-Conscious Senior

![Emily's persona](/documents/img/Emily.png)

Emily is a 68-year-old retiree who takes her health very seriously. She's always been proactive about managing her health, especially since her family has a history of diabetes and other chronic conditions.

When Emily discovered Phoenix, she was impressed by its innovative features and saw it as a valuable tool in her health maintenance routine. With Phoenix, Emily can easily monitor her temperature, pulse, and glucose levels from the comfort of her own home, giving her greater peace of mind about her health status. The breathalyzer feature also appeals to Emily, as it allows her to keep track of her alcohol intake, ensuring she stays within safe limits.

Emily appreciates the simplicity of accessing all her health data on her smartphone, making it easier for her to share important information with her healthcare provider during check-ups.

#### C. Assumptions and Constraints

**hygiene**
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

#### D. Functional Requirements

##### 1. First version

- take temperature
- print value on the mirror
- respect for hygiene
- user-friendly

##### 2. Second version

- take pulse
- lights
- phone connection

##### 3. Futures improvements

- take glucose level
- more aesthetics

The breathalyzer option has been abandoned because the system was too diffcult to implement and can't be compatible with the moisture-resistant criteria.

#### E. Mirror Functional Analysis

![functional analysis, mirror](/documents/img/Mirror_Functional_Analysis.png)

#### F. Non-functional Requirements

##### 1. cost

**Components**

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

- [Playlist intelligent miror](https://www.youtube.com/playlist?list=PLuyMGpc2xoZvJq_z1ZdqRLJSnPR_1JWfb)

**Time conception**

First version :

- November 2024 - May 2025

##### 2. Environment

- MacOS on development
- Visual Studio Code
- Arduino language (mirror)
- Java (application)

##### 3. Security

- respect RGPD and data saving law
- solid product
- moisture-resistant

### IV. Risk

**Competitors**

For this product, there is a main competitor called [Care OS](https://www.care-os.com). The company has already marketed Poseidon, a healthy mirror and has now developed a new mirror, [BMind](../../archives/BMind/BMind%20-%20Product%20sheet.pdf), with a lot of daily hygiene functions such as tooth brushing, water monitoring or skin analysis. There are also tools and entertainment such as games, videos or music to encourage children to take care of themselves.
This product has around fifteen partners including [Teraillon](https://www.terraillon.com/en), one of the leading manufacturers of product for the home. There is also [Pierre Fabre](https://www.pierre-fabre.com/en), a major research laboratory into cancers and diseases of the body.
Their mirror is not yet available for sale, but will cost between 3,000 and 5,000 dollars depending on the options chosen.

**product problem**
One of the big problems to consider with this mirror is the increase in people's paranoia about illness and the growing number of people suffering from hypochondria.

![-](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

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
