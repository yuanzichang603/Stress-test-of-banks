# 商业银行压力测试
<!--
*** Thanks for checking out the Best-README-Template. If you have a suggestion
*** that would make this better, please fork the repo and create a pull request
*** or simply open an issue with the tag "enhancement".
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


<!-- TABLE OF CONTENTS -->
<details open="open">
  <summary>Table of Contents</summary>
  <ol>
    <li><a href="#built-with">Built With</a></li>
<!--     <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li> -->
    <li><a href="#usage">Usage</a></li>
<!--     <li><a href="#roadmap">Roadmap</a></li> -->
    <li><a href="#contributing">Contributing</a></li>
<!--     <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li> -->
    <li><a href="#acknowledgements">Acknowledgements</a></li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->

## Built With

Here are some major frameworks built when project using.
* [pandas](https://pandas.pydata.org/)
* [statsmodels](https://www.statsmodels.org/stable/index.html)



<!-- GETTING STARTED -->
<!-- ## Getting Started

This is an example of how you may give instructions on setting up your project locally.
To get a local copy up and running follow these simple example steps.

### Prerequisites

This is an example of how to list things you need to use the software and how to install them.
* npm
  ```sh
  npm install npm@latest -g
  ```

### Installation

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
   ```JS
   const API_KEY = 'ENTER YOUR API';
   ```
 -->


<!-- USAGE EXAMPLES -->
## Usage
Take the credit risk stress test issued by the Hebei Banking Regulatory Commission in 2015 as a demo to operate Stress Test.
### Data
From January 2010 to the end of December 2018, we can obtain data such as GDP, PPI index, average residential price in 100 cities, m2 growth rate, and business climate index of each quarter from January 2010 to the end of December 2018 as candidates for explanatory variables.

Taking the non-performing loan rate NPL of a bank from January 2010 to the end of December 2018 as the explained variable, and introducing the intermediary variable Y, the non-performing loan rate is a non-linear transformation of the Logit function, that is, Y=ln(NPL/ (1-NPL)). It can be seen that NPL and Y change in the same direction.

data.xls in details

### Stepwise OLS with Stress_testing.py

"forward_selected" fucntion in file:

    Linear model designed by forward selection.

    Parameters:
    -----------
    data : pandas DataFrame with all possible variables and response

    response: string, name of column in data

    Returns:
    --------
    model: an "optimal" fitted statsmodels linear model
           with an intercept
           selected by forward selection
           evaluated by adjusted R-squared and p_value
"ADF_test" function in file:

    ADF test for selected variables.

    Parameters:
    -----------
    data : pandas DataFrame with all variables

    variables: string, name of column in data

    Returns:
    --------
    output: with P and Critial Values
            to evaluate ADF test 
"Cointegration_test" function in file:

    Cointegration test for resid.

    Parameters:
    -----------
    data : pandas arrary with resid

    resid: string, name of column in model

    Returns:
    --------
    output: with P and Critial Values
            to evaluate Cointegration test 

### Tests output
With reference to the previous empirical analysis process and results, a stress test model of a commercial bank's credit risk follows：

![image](https://user-images.githubusercontent.com/60854571/121458024-35a5a100-c9db-11eb-8374-a91e923ea95d.png)



<!-- ROADMAP -->
<!-- ## Roadmap

See the [open issues](https://github.com/othneildrew/Best-README-Template/issues) for a list of proposed features (and known issues). -->



<!-- CONTRIBUTING -->
## Contributing

The Stress tests of banks in my class are operated in Eviews, but I'd like examples in Python and other languages too. Please add examples in other languages!


<!-- LICENSE -->
<!-- ## License

Distributed under the MIT License. See `LICENSE` for more information. -->



<!-- CONTACT -->
<!-- ## Contact

Your Name - [@your_twitter](https://twitter.com/your_username) - email@example.com

Project Link: [https://github.com/your_username/repo_name](https://github.com/your_username/repo_name) -->



<!-- ACKNOWLEDGEMENTS -->
## Acknowledgements
* [Forward Selection with statsmodels](https://planspace.org/20150423-forward_selection_with_statsmodels/)
