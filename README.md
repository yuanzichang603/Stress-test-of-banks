# 商业银行压力测试
A bank risk management and regulatory analysis tool used to analyze the degree of impact of assumed, extreme but possible adverse scenarios on the bank as a whole or asset portfolio, and then evaluate its impact on the bank’s asset quality, profitability, capital level and liquidity Negative impact. Stress testing helps the supervisory authority or bank make assessments and judgments on the vulnerability of individual banks, banking groups, and the banking system, and take necessary measures.
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
风险因素：按外部经济环境的恶化程度评估不同压力情景下信用风险的变化情况。外部经济环境主要考虑经济增长率（GDP）、工业生产者出厂价格指数（PPI）、房地产价格、M2增长率、企业景气等因素。
### Data
通过万德获取2010年1月至2018年12月末每个季度的GDP、PPI指数、百城住宅平均价格、m2增长率、企业景气指数等数据作为解释变量备选。

将某银行2010年1月至2018年12月末每个季度的不良贷款率NPL作为被解释变量，并引入中介变量Y，对不良贷款率做Logit函数的非线性转换，即Y=ln(NPL/(1-NPL))。可知NPL与Y同向变化。

数据详见data.xls

### Stepwise OLS with Stress_testing.py

"forward_selected" 函数用法:

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
"ADF_test" 函数用法:

    ADF test for selected variables.

    Parameters:
    -----------
    data : pandas DataFrame with all variables

    variables: string, name of column in data

    Returns:
    --------
    output: with P and Critial Values
            to evaluate ADF test 
"Cointegration_test" 函数用法:

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
参考前面实证分析过程和结果，可得到某商业银行信用风险的压力测试模型：

![image](https://user-images.githubusercontent.com/60854571/121457387-2eca5e80-c9da-11eb-98cd-3e9ce08c10f9.png)



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
