<!-- Improved compatibility of back to top link: See: https://github.com/othneildrew/Best-README-Template/pull/73 -->
<a name="readme-top"></a>
<!--
*** Thanks for checking out the Best-README-Template. If you have a suggestion
*** that would make this better, please fork the repo and create a pull request
*** or simply open an issue with the tag "enhancement".
*** Don't forget to give the project a star!
*** Thanks again! Now go create something AMAZING! :D
-->



<!-- PROJECT SHIELDS -->
<!--
*** I'm using markdown "reference style" links for readability.
*** Reference links are enclosed in brackets [ ] instead of parentheses ( ).
*** See the bottom of this document for the declaration of the reference variables
*** for contributors-url, forks-url, etc. This is an optional, concise syntax you may use.
*** https://www.markdownguide.org/basic-syntax/#reference-style-links
-->
[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![MIT License][license-shield]][license-url]
[![LinkedIn][linkedin-shield]][linkedin-url]



<!-- PROJECT LOGO -->
<br />
<div align="center">
  <a href="https://github.com/othneildrew/Best-README-Template">
    <img src="images/logo.png" alt="Logo" width="80" height="80">
  </a>

  <h3 align="center">Best-README-Template</h3>

  <p align="center">
    An awesome README template to jumpstart your projects!
    <br />
    <a href="https://github.com/othneildrew/Best-README-Template"><strong>Explore the docs »</strong></a>
    <br />
    <br />
    <a href="https://github.com/othneildrew/Best-README-Template">View Demo</a>
    ·
    <a href="https://github.com/othneildrew/Best-README-Template/issues">Report Bug</a>
    ·
    <a href="https://github.com/othneildrew/Best-README-Template/issues">Request Feature</a>
  </p>
</div>


## Table of Contents

1. [About the Work with Power-BI](#about-the-work-with-power-bi)
2. [Data preparation](#data-preparation)
3. [Categorical and binary features](#categorical-and-binary-features)
4. [Role of product quality variants](#Role-of-product-quality-variants)
5. [Feature Distributions](#feature-distributions)
6. [Heatmap](#heatmap)
7. [Histograms](#histograms)
8. [Influences](#influences)
9. [Built With](#built-with)
10. [Usage](#usage)
11. [Contributing](#contributing)
12. [License](#license)
13. [Contact](#contact)


<!-- ABOUT THE WORK WITH POWER BI -->
## About The Work with Power BI

For the EDA part of the project we need the Microsoft Power BI software that gives a good help in the exploratory data analysis and visualization. The dataset for this competition, train.csv, had also been used for diverse reports like "XGBoost Binary Classifier" or "Binary Classification of Machine Failures" and is downloadable.

<!-- DATA PREPARATION -->
## Data preparation
1) Data description

     A further description of the data is available in: https://github.com/farnazashrafi/portfolio_project/blob/main/README_new.md

2)  Data download
   
     Download the file via this link: https://www.kaggle.com/code/yantxx/xgboost-binary-classifier-machine-failure/input?select=train.csv
   
3)  Read in with Power BI
   
    Now we go into the Power BI software and open the csv-file by clicking on "Daten abrufen" (engl.: "recall data"). We choose Text/CSV and choose     "train.csv" from the home folder. After showing an example window, we click on "Laden" (engl.: "load") and the data is available.

    ![image](https://github.com/farnazashrafi/portfolio_project/assets/155962705/d7d8a4d0-6e79-4b59-ac5b-5b7385b2bb61)

    IMPORTANT: you have to pay attention to the right comma placement. In a region where dots are not usual as decimal symbol you have to go to the editor via "Daten transformieren" (engl. "transform data") and replace them with commas. Rightclick on the columns "Air Temperature [K]", "Process Temperature [K]", "Torque [Nm]", choose "Werte ersetzen" (engl.: "replace values") and put a "." in the upper and a "," in the lower cell. All dots in these columns are now replaced by commas.

5) Choosing the right elements

   Go to the "Visuelles Element erstellen" part (engl.: "create visual element) of the Power BI working space. Here you can choose between the histograms, bar diagrams, circles, curves or "Wichtige Einflussfaktoren", showing which values have the biggest influence on the data.

6) Using the data columns
   
   Here you can the drag the columns of your table and drop them into the empty working field. Dependent on the kind of graphics, you can also drag the    column into the x-bar or y-bar description of the visuals section or in the "Werte" (engl. "values") and "Legende" (dt. legend) description, e.g., if it is a circle diagram.

![image](https://github.com/farnazashrafi/portfolio_project/assets/155962705/4dc81bd0-2e97-4587-869f-a48b0485f87b)

6) Improve the visualization

   You want to change the size of the graphics, letter colors, change position, etc.? No problem, then click on the button "Visual formatieren" (engl.:    "formatting visual"). You also can change the number of bars in the "Allgemein" (engl.: "common") section. 

<!-- CATEGORICAL AND BINARY FEATURES -->
## Categorical and binary features
For this graphic we plotted the categorical and binary features as bar diagrams. Therefore we put the categorical features like air temperature on the x-bar and the sum of machine failures on the y-bar, divided in the values 0 (failure=False), and 1 (failure=True). 

As shown in the graphic above, failure mode HDF has the highest sum of machines failures = 1 with 698 units whereas RNF has the lowest number with just six. Sorted by types, the group with the highest sum of failures was the L-group.

<!-- ROLE OF PRODUCT QUALITY VARIANTS -->
## Role of product quality variants
This graphic contained the categorical features (OSF, HDF, PWF, RNF, TWF) on the x-bar, divided in the binary features 0 and 1, and the sum of machine failures on the y-bar. Here, the legend of the sums of machine failures showed us the three types, H-L-M. 

![image](https://github.com/farnazashrafi/portfolio_project/assets/155962705/2dd0fe7e-175e-49cd-9aa0-0fb3019c97d0)

The biggest difference between the H-L-M-groups is visible in the the PWF mode whereas the RNF feature has the biggest difference between 0 and 1.

<!-- FEATURE DISTRIBUTIONS -->
## Feature Distributions
For the Feature Distributions we visualized the five categorical features, with machine failures and types on seven slides á five boxplots, whereas every boxplot is divided into the groups 0 and 1. Using the Jupyter lab and importing several tools this time (import pandas as pd, seaborn as sns,
numpy as np, matplotlib.pyplot as plt, pickle, sqlalchemy as sa), the following code has been applied for the boxplots:
  
    fig, ax = plt.subplots()
    df.boxplot(column='Process temperature [K]', by='HDF', ax=ax)
    plt.tight_layout(pad=1.0)
    plt.show()
with the "column" order always using the numerical features like air temperature, process temperature, tool wear, torque and rotational speed. On the contrary, the categorical features, with type and machine failures themself, had been used for the "by" order.

![image](https://github.com/farnazashrafi/portfolio_project/assets/155962705/b99fb757-66da-47ab-a42a-f7ba0ec1c675)

The highest scattering we mostly had in the rotational speed features (torque as second), maybe because of very many different values, and most of them in class 0. The boxplots with the widest range of definitive values was in the tool wear [min] feature, with machine failure = 1. Sorted by types, the L-group also had the widest range in tool wear, with the highest scattering in rotational speed.

An oversight over all boxplots and the most important key figures you find in the following file:

https://github.com/farnazashrafi/portfolio_project/blob/main/pictures/jupyter_boxplots.pdf

<!-- HEATMAP -->
## Heatmap
The Table Heatmap 3.5.0 had been used to compare the categorical features with the id classes. For these variants we went into the editor, making an additional column that only showed the first three letters of the ids: 

![image](https://github.com/farnazashrafi/portfolio_project/assets/155962705/0cda4444-d419-469c-8926-53d50defeded)

Back to the Power Bi space we used the features OSF, HDF, PWF, RNF, TWF for the y-bar and the id classes for category. The order from left to right was grouped by the height of the machine failures the id class had on the TWF mode. The tiles with the highest values were on the left side, the lowest ones on the right side. 

![image](https://github.com/farnazashrafi/portfolio_project/assets/155962705/fb740435-5651-4297-b663-e1af8934f3da)

The most failures, for almost all features, occured in the variants M19, H33 and L51, whereas the id classes H29, H39 and M14 were reliable because of no machine failures. 

<!-- HISTOGRAMS -->
## Histograms
Two sets of histograms were created, one for both binary features (0 and 1) and one only for feature 1. In every set five histograms (made by Histogram 2.1.1) had been created, one for every numerical feature. This histogram sets worked with number of machine failures as frequency and the values of the numerical features as values. For the two air temperature histograms it was important to filter out three outliers, having much higher values than the other ones and changing the look of the visuals drastically. You could change the number of bars by going to "Visual formatieren", choose common options and change the number of classes (German: "Klassen).

![image](https://github.com/farnazashrafi/portfolio_project/assets/155962705/06f6cb15-4bdf-4ced-86fd-4e8a4ee27a14)

The most numerical features have - on both sets - the look of a climate curve. Only exception is the number of machine failures by Tool Wear [min] which has a decreasing curve in the set with both binary features - 0 and 1. In the histogram set with machine failure = 1 however, the number of machine failures is increasing with the tool wear.
<!-- INFLUENCES -->
## Influences
For the last set of graphics we inspected the size range of the numerical features that had the biggest influence on machine failures. Here we chose the visual "Wichtige Einflussfaktoren" (engl.: important influence factors) with the sum of machine failures in the analysis part and the numerical features in the explanation part. Due to the fact that the tool wear didn't have a direct influence on the machine failures, we used here the sum of tool wear, combined with the normal value, as analysis.

![image](https://github.com/farnazashrafi/portfolio_project/assets/155962705/3e3f7827-929c-4576-9f68-a528e75223db)

With 49,36 units more than in the other size classes, and with 30,99 % of all values, a range between 310-312 Kelvin was the process temperature with the biggest influence on the sum of machine failures. On the contrary, the torque between 44 and 56 nanometers, containing 26,5 % of all values, was the torque value with the highest influence on of machine failures, but with just 4,65 units difference to the other size classes very small.  

An oversight of all graphics created for this project you find in the following file:

https://github.com/farnazashrafi/portfolio_project/blob/main/pictures/Power-Bi-Grafix.pdf


## Built With

- [Python](https://www.python.org/)
- [NumPy](https://numpy.org/)
- [Pandas](https://pandas.pydata.org/)
- [Matplotlib](https://matplotlib.org/)
- [Seaborn](https://seaborn.pydata.org/)
- [Jupyter Notebooks](https://jupyter.org/)
- [Power BI](//https://powerbi.microsoft.com/de-de/)



<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- GETTING STARTED -->
## Getting Started

This is an example of how you may give instructions on setting up your project locally.
To get a local copy up and running follow these simple example steps.

### Prerequisites

This is an example of how to list things you need to use the software and how to install them.
* npm
  ```sh
  npm install npm@latest -g
  ```

### Installation

_Below is an example of how you can instruct your audience on installing and setting up your app. This template doesn't rely on any external dependencies or services._

1. Get a free API Key at [https://example.com](https://example.com)
2. Clone the repo
   ```sh
   git clone https://github.com/your_username_/Project-Name.git
   ```
3. Install NPM packages
   ```sh
   npm install
   ```
4. Enter your API in `config.js`
   ```js
   const API_KEY = 'ENTER YOUR API';
   ```

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- USAGE EXAMPLES -->
## Usage

Use this space to show useful examples of how a project can be used. Additional screenshots, code examples and demos work well in this space. You may also link to more resources.

_For more examples, please refer to the [Documentation](https://example.com)_

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- ROADMAP -->
## Roadmap

- [x] Add Changelog
- [x] Add back to top links
- [ ] Add Additional Templates w/ Examples
- [ ] Add "components" document to easily copy & paste sections of the readme
- [ ] Multi-language Support
    - [ ] Chinese
    - [ ] Spanish

See the [open issues](https://github.com/othneildrew/Best-README-Template/issues) for a full list of proposed features (and known issues).

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- CONTRIBUTING -->
## Contributing

Contributions are what make the open source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

If you have a suggestion that would make this better, please fork the repo and create a pull request. You can also simply open an issue with the tag "enhancement".
Don't forget to give the project a star! Thanks again!

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- LICENSE -->
## License

Distributed under the MIT License. See `LICENSE.txt` for more information.

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- CONTACT -->
## Contact

Your Name  - domenic-saheb@web.de

Project Links: 

[https://github.com/Ruddelduddel/Project_Portfolio_2024](https://github.com/Ruddelduddel/Project_Portfolio_2024),

[https://github.com/farnazashrafi/portfolio_project](https://github.com/farnazashrafi/portfolio_project)

<p align="right">(<a href="#readme-top">back to top</a>)</p>


<!-- ACKNOWLEDGMENTS -->
## Acknowledgments

Use this space to list resources you find helpful and would like to give credit to. I've included a few of my favorites to kick things off!

* [Choose an Open Source License](https://choosealicense.com)
* [GitHub Emoji Cheat Sheet](https://www.webpagefx.com/tools/emoji-cheat-sheet)
* [Malven's Flexbox Cheatsheet](https://flexbox.malven.co/)
* [Malven's Grid Cheatsheet](https://grid.malven.co/)
* [Img Shields](https://shields.io)
* [GitHub Pages](https://pages.github.com)
* [Font Awesome](https://fontawesome.com)
* [React Icons](https://react-icons.github.io/react-icons/search)

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/othneildrew/Best-README-Template.svg?style=for-the-badge
[contributors-url]: https://github.com/othneildrew/Best-README-Template/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/othneildrew/Best-README-Template.svg?style=for-the-badge
[forks-url]: https://github.com/othneildrew/Best-README-Template/network/members
[stars-shield]: https://img.shields.io/github/stars/othneildrew/Best-README-Template.svg?style=for-the-badge
[stars-url]: https://github.com/othneildrew/Best-README-Template/stargazers
[issues-shield]: https://img.shields.io/github/issues/othneildrew/Best-README-Template.svg?style=for-the-badge
[issues-url]: https://github.com/othneildrew/Best-README-Template/issues
[license-shield]: https://img.shields.io/github/license/othneildrew/Best-README-Template.svg?style=for-the-badge
[license-url]: https://github.com/othneildrew/Best-README-Template/blob/master/LICENSE.txt
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://linkedin.com/in/othneildrew
[product-screenshot]: images/screenshot.png
[Next.js]: https://img.shields.io/badge/next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white
[Next-url]: https://nextjs.org/
[React.js]: https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB
[React-url]: https://reactjs.org/
[Vue.js]: https://img.shields.io/badge/Vue.js-35495E?style=for-the-badge&logo=vuedotjs&logoColor=4FC08D
[Vue-url]: https://vuejs.org/
[Angular.io]: https://img.shields.io/badge/Angular-DD0031?style=for-the-badge&logo=angular&logoColor=white
[Angular-url]: https://angular.io/
[Svelte.dev]: https://img.shields.io/badge/Svelte-4A4A55?style=for-the-badge&logo=svelte&logoColor=FF3E00
[Svelte-url]: https://svelte.dev/
[Laravel.com]: https://img.shields.io/badge/Laravel-FF2D20?style=for-the-badge&logo=laravel&logoColor=white
[Laravel-url]: https://laravel.com
[Bootstrap.com]: https://img.shields.io/badge/Bootstrap-563D7C?style=for-the-badge&logo=bootstrap&logoColor=white
[Bootstrap-url]: https://getbootstrap.com
[JQuery.com]: https://img.shields.io/badge/jQuery-0769AD?style=for-the-badge&logo=jquery&logoColor=white
[JQuery-url]: https://jquery.com 
