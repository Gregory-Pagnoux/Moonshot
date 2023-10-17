# Functional Specification

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

<details>
<summary>Table of content</summary>

- [Functional Specification](#functional-specification)
    - [1. Overview](#1-overview)
    - [2. Goals and constraints](#2-goals-and-constraints)
    - [3. Personas and scenario](#3-personas-and-scenario)
        - [a. Hervé](#a-hervé)
    - [4. Use case](#4-use-case)
    - [5. What will happen for the site](#5-what-will-happen-for-the-site)
        - [Today](#today)
        - [Tomorrow](#tomorrow)
    - [6. Risks and Assumptions](#6-risks-and-assumptions)
    - [7. Development, environment and Requirements](#7-development-environment-and-requirements)
    - [Glossary](#glossary)

</details>

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

### 1. Overview

![Jacobi logo](img/Jacobi-logo.jpg)

[Jacobi](http://www.jacobi.net)[^1] is a company **developing innovative air and water filtration products** with active coals and resin. The company created by Ferdinand Adolphe Wilhelm Jacobi has been in existence since 1916 and continues to develop around the world, such as in Allemangne, Philadelphia, India and Malaysia.
Remko Goudappel, CEO of Jacobi Company, makes a point of the **safety** of these customers and products, but also the **respect of the environment** during each stage of production. To contribute to the success of all these goals, the company can count on these employees whose well-being within the company is also a key point in Jacobi’s success.

The company commissioned ALGOSUP to create a communication tool to **centralize the information** to be transmitted to all employees.
Currently, the company share and send the informations via different application like Team, Email or Yammer, but also with a paper display. However, these means of communication are too numerous and even outdated. The company would like to facilitate communication and make it more modern with the digital tools that exist.
Mr. Saeed, the Project owner of the company, would like a **simple and secure communication tool**.

sources :
 - []()

### 2. Goals and constraints

**Goals :**

- site very **secure**

**Constraints :**

- Do not use the screen for entertainment purposes

### 3. Personas and scenario

##### a. Hervé

Hervé has been Jacobi's communications director for 10 years. He is a vigorous 52 year old man. He divorced his wife 3 years ago with whom he had two children, Jessica and Nathan.

He leaves Salbris, his home, and arrives at Jacobi for 7:15 am. He turns on the two screens in the locker room and in the cafeteria. Then he goes on his computer, on the administrator account of the site, then he chooses the "Create" option and he sets each element of the scene (number of parts, widgets, text, image...) with the news of the day that his boss asked him to share with all the employees of the company the day before. Once the settings are complete, he saves the scene and shares it on both screens simultaneously.
Saving his scene will allow him to load it later if he wants to use it again and to modify it.
At 7:30 a.m., When all employees arrive at the plant, they can see the news directly when they prepare in the locker room or when they have their coffee.

### 4. Use case
![use case](/img/use_case.png)

### 5. What will happen for the site

##### Today

When the administrator, logs in with his account, He has the possibility, thanks to the "scene" tab in the navigation bar, to see the scenes that are shared on the screens, manage the scenes saved on the site for reuse or even modify them. But it can also create scenes in which it can integrate basic widgets like text or images, but also optional widgets like date, time, weather or news.
Thanks to the second tab "my account" the administrator can manage the various options of his account such as his password or his email address, but he can also have access to the site setting.
The "home" tab presents the company, its history and these values. You can access the company’s main site and have the site administrators email address so that employees can contact them if a problem is observed when sharing scenes on the screens.
Of course, employees will have limited access to the site. On their phone they will only be able to access the home page and the shared scene on the screen they decide to view.

##### Tomorrow

In the future, on the amdinistrator side, it will be possible to add videos, files (PDF type) via links or QR code or to see the state of the internet network or having more color choices for scenes. We can also add the feature of decorating the scenes during the holidays with decorative frames for Christmas, Halloween or Easter.
The page may also be translated into several languages to promote the export of the website to other Jacobi production sites.

### 6. Risks and Assumptions

**the reglementation of data backups :**

There are three different archives depending on the type of data :
- **Active database archiving** where data that are no longer useful to the enterprise (for example, data on job seekers to which they have not followed up) are deleted once the reason for the study has been completed (after a maximum of two years).
- **Intermediate archiving** where data are saved even after the purpose of data collection has been achieved as they are still of interest to the enterprise. The duration is set by the person responsible and must be relevant to its usefulness.
- **Final archiving** where data that remains of great interest in the future without an end date are saved, after an upstream check.

source :
 - []()

### 7. Development, environment and Requirements

  - MacOS on development
  - Visual Studio Code
  - C or C#

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

### Glossary

[^1]: **Jacobi**
It's an air and water purification solutions company. The company is based in Vierzon since 1956.
*sources : []()* 
