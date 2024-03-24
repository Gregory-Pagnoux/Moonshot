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
      - [C. Personas and Scenarios](#c-personas-and-scenarios)
        - [1. Sarah](#1-sarah)
        - [2. Michael](#2-michael)
        - [3. Emily](#3-emily)
      - [D. Assumptions and Constraints](#d-assumptions-and-constraints)
      - [E. Functional Requierements](#e-functional-requierements)
        - [1. First version](#1-first-version)
        - [2. Second version](#2-second-version)
        - [3. Futures improvements](#3-futures-improvements)
      - [F. Functional Analysis](#f-functional-analysis)
        - [1. Mirror](#1-mirror-1)
        - [2. Application](#2-application-1)
      - [G. Non-functional Requierements](#g-non-functional-requierements)
        - [1. cost](#1-cost)
        - [2. Environment](#2-environment)
        - [3. Security](#3-security)
    - [Glossary](#glossary)

</details>

![-](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

### I. Document

#### A. Information

| Document ID | Document # 01 |
|---|---|
| Document Owner | Grégory PAGNOUX |
| Issue date | 10/03/2024 |
| Document Name | Functional Specification|

#### B. History

| Version n° | Edits completed by | Date | Description of edit |
|---|---|---|---|
|01.1|Grégory PAGNOUX| 20/01/2024 | Initial Release |
|01.2|Grégory PAGNOUX| 25/02/2024 | document improvement (mirror system purpose, document architecture) |
|01.3|Grégory PAGNOUX| 03/03/2024 | document improvement (application system purpose, texts of personas and scenarios) |
|01.4|Grégory PAGNOUX| 10/03/2024 | document improvement (pictures of personas, functional analysis) |

### II. Project Overview

<center>

![Pheonix](/img/logo.png)

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

sources :
- [French Ministry of Health](https://sante.gouv.fr/soins-et-maladies/maladies/article/diabete#:~:text=Les%20chiffres%20clefs%20du%20diabète,700%20millions%20d%27ici%202045.)
- [road safety](https://www.securite-routiere.gouv.fr/dangers-de-la-route/lalcool-et-la-conduite#:~:text=Les%20accidents%20impliquant%20de%20l,pour%20les%20accidents%20sans%20alcool.)

### III. Product

#### A. System Purpose

##### 1. Mirror

![design](/img/design.png)

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

<!--TODO-->
![app design](/img/appDesign.png)

**installation**

<!--TODO-->

**opening**

<!--TODO-->

**call a doctor**

<!--TODO-->

**settings**

<!--TODO-->

**data graphs**

<!--TODO-->

#### C. Personas and Scenarios

##### 1. Sarah

The working mother who cares about her children's health

![Sarah's persona](/img/Sarah.png)

Sarah is a 35-year-old working mother with a hectic schedule. She's always concerned about her family's health, especially since they have a history of cancer and other diseases.

Sarah recently stumbled upon Phoenix, the healthy mirror, and was intrigued by its features. She envisions using it to monitor her two children's health more efficiently while seamlessly integrating it into their daily routines.
With Phoenix, Sarah can easily track their temperature, pulse, and glucose levels, ensuring she stays on top of their health despite her busy lifestyle. Plus, the breathalyzer feature gives her peace of mind regarding alcohol consumption.

Sarah appreciates the convenience of accessing all this data through her smartphone, making it easier for her to keep track of everyone's health status.

##### 2. Michael

The Fitness Enthusiast

![Michael's persona](/img/Michael.png)

Michael is a 28-year-old fitness enthusiast who's always looking for ways to optimize his health and performance.

He came across Phoenix while researching innovative health gadgets and immediately saw its potential in his daily routine. With Phoenix, Michael can monitor various health metrics like temperature, pulse, and glucose levels, helping him fine-tune his fitness regimen for optimal results. The breathalyzer feature is particularly useful for Michael, as he occasionally enjoys a few drinks with friends but wants to ensure he maintains a healthy balance.

Being able to track all this data on his smartphone motivates Michael to stay consistent with his health goals and allows him to make informed decisions about his lifestyle choices.

##### 3. Emily

The Health-Conscious Senior

![Emily's persona](/img/Emily.png)

Emily is a 68-year-old retiree who takes her health very seriously. She's always been proactive about managing her health, especially since her family has a history of diabetes and other chronic conditions.

When Emily discovered Phoenix, she was impressed by its innovative features and saw it as a valuable tool in her health maintenance routine. With Phoenix, Emily can easily monitor her temperature, pulse, and glucose levels from the comfort of her own home, giving her greater peace of mind about her health status. The breathalyzer feature also appeals to Emily, as it allows her to keep track of her alcohol intake, ensuring she stays within safe limits.

Emily appreciates the simplicity of accessing all her health data on her smartphone, making it easier for her to share important information with her healthcare provider during check-ups.

#### D. Assumptions and Constraints

**hygiene**
We need to pay close attention to the hygiene aspect of the product, as the glucose meter and breathalyzer require the deposition of particles that can dirty the mirror.

**product problem**
One of the big problems to consider with this mirror is the increase in people's paranoia about illness and the growing number of people suffering from hypochondria.

**Data**
If we want to have a connected mirror with smartphone, we need to interest us on the **the reglementation of data backups**.
There are three different archives depending on the type of data :
- **Active database archiving** where data that are no longer useful to the enterprise (for example, data on job seekers to which they have not followed up) are deleted once the reason for the study has been completed (after a maximum of two years).
- **Intermediate archiving** where data are saved even after the purpose of data collection has been achieved as they are still of interest to the enterprise. The duration is set by the person responsible and must be relevant to its usefulness.
- **Final archiving** where data that remains of great interest in the future without an end date are saved, after an upstream check.

source :
 - [Acronis](https://www.acronis.com/fr-fr/blog/posts/gdpr/)
 - [CNIL (general rules)](https://www.cnil.fr/fr/reglement-europeen-protection-donnees)
 - [CNIL (datas backups duration)](https://www.cnil.fr/fr/passer-laction/les-durees-de-conservation-des-donnees)

#### E. Functional Requierements

##### 1. First version
- take temperature
- take pulse
- print value on the mirror
- respect for hygiene
- user-friendly

##### 2. Second version
- lights
- phone connection

##### 3. Futures improvements
- take glucose level
- take alcohol level
- more aesthetics

#### F. Functional Analysis

##### 1. Mirror

![functional analysis, mirror](/img/mirror_functional_analysis.png)

##### 2. Application

<!--TODO-->
![functional analysis, application](/img/)

#### G. Non-functional Requierements

##### 1. cost

**Materials**

| WHICH PART | MATERIAL | PRICE | V0.1 | V0.2 |
| :-: | :-: | :-: | :-: | :-: |
| To built the mirror | glass (large photo frame) | 10€ | Yes | Yes |
|  | [self-adhesif mirror](https://www.amazon.fr/Lifemaison-Autocollant-Adhérence-Décoratif-50x200cm/dp/B0BCFVG4RT/ref=asc_df_B0BCFVG4RT/?tag=googshopfr-21&linkCode=df0&hvadid=627335705485&hvpos=&hvnetw=g&hvrand=9017061648460033442&hvpone=&hvptwo=&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=9055097&hvtargid=pla-1905220316044&th=1) | 14€ | Yes | Yes |
| Component add to the mirror | [transparent LED display](https://www.lg.com/fr/business/affichage-led/lg-LAT240DT1) | make a quote | Yes | Yes |
|  | [pressure sensor](https://www.amazon.fr/Capteur-Pression-Couche-Précision-Résistance/dp/B07P9Z7FR6/ref=asc_df_B07P9Z7FR6/?tag=googshopfr-21&linkCode=df0&hvadid=353896712114&hvpos=&hvnetw=g&hvrand=4898371625524598186&hvpone=&hvptwo=&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=9055097&hvtargid=pla-869632555564&psc=1&tag=&ref=&adgrpid=71676698856&hvpone=&hvptwo=&hvadid=353896712114&hvpos=&hvnetw=g&hvrand=4898371625524598186&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=9055097&hvtargid=pla-869632555564) | 9€ | Yes | Yes |
|  | [green, yellow, red lights]() | to be defined | Yes | Yes |
|  | [LED strip light](https://www.temu.com/fr/kuiper/n9.html?subj=googleshopping-landingpage&_bg_fs=1&_p_rfs=1&_x_ads_channel=google&_x_ads_sub_channel=shopping&_x_login_type=Google&_x_vst_scene=adg&mkt_rec=1&goods_id=601099519895939&sku_id=17592230663628&_x_ns_sku_id=17592230663628&_x_gmc_account=742384653&_x_ads_account=5198328713&_x_ads_set=20124197984&_x_ads_id=150623603962&_x_ads_creative_id=658287999075&_x_ns_source=g&_x_ns_gclid=Cj0KCQiAnrOtBhDIARIsAFsSe50_TImuYMK5rRoyfRWbLoIHlW83s6oJxuaxPfCDRpS9Tbou7mM7NxMaAgCTEALw_wcB&_x_ns_placement=&_x_ns_match_type=&_x_ns_ad_position=&_x_ns_product_id=17592230663628&_x_ns_target=&_x_ns_devicemodel=&_x_ns_wbraid=CjkKCQiA-62tBhDwARIoAI4OA4-y7YSNwN-9XXHfLhr6x1omCjtnJqAAgWcHpiapEaLf3moRFBoCJgo&_x_ns_gbraid=0AAAAAo4mICGlLRY-zIEBBV60NLgRSSUm6&_x_ns_targetid=pla-2092819011972&gad_source=1&gclid=Cj0KCQiAnrOtBhDIARIsAFsSe50_TImuYMK5rRoyfRWbLoIHlW83s6oJxuaxPfCDRpS9Tbou7mM7NxMaAgCTEALw_wcB&adg_ctx=f-6465104f) | 5€ | No | Yes |
| Options | [thermometer gun](https://www.amazon.fr/Thermom%C3%A8tre-IDOIT-Thermometre-Infrarouge-Affichage/dp/B08DFXYWNN/ref=sr_1_32?adgrpid=54908680263&hvadid=275507361595&hvdev=c&hvlocphy=9055097&hvnetw=g&hvqmt=b&hvrand=18183104330674911873&hvtargid=kwd-312280216289&hydadcr=14196_1754673&keywords=thermometre+laser&qid=1683279299&sr=8-32) | 30€ | Yes | Yes |
|  | [BioActive sensor](https://www.pocket-lint.com/fr-fr/montres-connectees/acheteurs-guides/samsung/157658-samsung-galaxy-watch-4-vs-galaxy-watch-4-differences-classiques-comparees/) | 200€ | Yes | Yes |
|  | [glucose meter](https://www.amazon.com/Glucose-Monitor-Glucometer-Lancets-Solution/dp/B08LYC288R/ref=zg_mw_3777171_sccl_2/147-1452400-9255329?psc=1) | 35€ | No | to be defined |
|  | [breathalyzer](https://www.ebay.fr/itm/224971220617?chn=ps&mkevt=1&mkcid=28#rpdCntId) | 13€ | No | to be defined |
|  | application | depends on host/online cost | to be defined | Yes |
| internal component | [electronic kit](https://www.temu.com/fr/kuiper/n9.html?subj=googleshopping-landingpage&_bg_fs=1&_p_rfs=1&_x_ads_channel=google&_x_ads_sub_channel=shopping&_x_login_type=Google&_x_vst_scene=adg&mkt_rec=1&goods_id=601099524164587&sku_id=17592249789383&_x_ns_sku_id=17592249789383&_x_gmc_account=742384653&_x_ads_account=5198328713&_x_ads_set=20819421092&_x_ads_id=153466930022&_x_ads_creative_id=682926604759&_x_ns_source=g&_x_ns_gclid=Cj0KCQiAnrOtBhDIARIsAFsSe50JAXP71zr0-0KJtsw1LbH1ZCLBhgt8hzMOB3I0fTk_ggOCgm5eojwaArHtEALw_wcB&_x_ns_placement=&_x_ns_match_type=&_x_ns_ad_position=&_x_ns_product_id=17592249789383&_x_ns_target=&_x_ns_devicemodel=&_x_ns_wbraid=CjkKCQiA-62tBhDwARIoAI4OA4_VL5nWuA-uApyq7C26g1POuUhjQ-nZ5dxRduvSGjARFGgjZxoCf9A&_x_ns_gbraid=0AAAAAo4mICGV_-1u5yHHLnky4O24cGqQw&_x_ns_targetid=pla-2264719103480&gad_source=1&gclid=Cj0KCQiAnrOtBhDIARIsAFsSe50JAXP71zr0-0KJtsw1LbH1ZCLBhgt8hzMOB3I0fTk_ggOCgm5eojwaArHtEALw_wcB&adg_ctx=f-6465104f) | 17€ | Yes | Yes |
|  | [electronic power supply](https://www.leroymerlin.fr/produits/electricite-et-domotique/tableau-electrique-et-disjoncteur/module-de-commande-de-signalisation-et-de-protection/alimentation-electrique-mince-ip67-36w-transformateur-etanche-de-230v-a-12v-dc-3a-bandes-led-lampes-cameras-90320990.html?Megaboost) | 14€ | Yes | Yes |
|  | [universal power socket](https://www.cdiscount.com/bricolage/electricite/alimentation-universelle-12v-dc-1-5a-ac-100-240v-5/f-16614-auc1695255794642.html) | 20€ | Yes | Yes |
| total |  |  | 314€ | 367€ |

**Time conception**

First version :
- Septembre 2024 - Mai 2025

##### 2. Environment

- MacOS on development
- Visual Studio Code
- C language

##### 3. Security

- respect RGPD and data saving law
- solid product
- moisture-resistant

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
