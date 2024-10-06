
# OWASP-TOP-10 SAST Project
https://owasp.org/www-project-top-ten/

# SAST Analysis  OWASP
https://owasp.org/www-community/Source_Code_Analysis_Tools

## SAST analysis with "Classical ML Algorithmic" Techniques 

This Project is about  SAST  based Application Security using Source code testing and 
Machine Learning.

### Getting started
All the ML models used for automated learning of Security Threat signatures, models can be found in the ```models``` folder.

1. ```$ cd models```

For Example
2. ```$ python3 Ensemble_model.py -t scraper
   
3. ```$ python3 LSTM_model.py -t  <path_to_code_to_test>```

### Introduction: 
Static application security testing (SAST) is a set of technologies designed to analyze application source code, byte code and binaries for coding and design conditions that are indicative of security vulnerabilities. SAST solutions analyze an application from the “inside out” in a non-running state. Our goals with respect to this project are:

### Project Goals:

1. Use open source/Proprietary Fuzzers to analyze source code for vulnerabilities in a non-running state.
2. Work with the features presented by fuzzers to eliminate false-positives
3. Use a learning algorithm (such as ensemble learning) for the above.


### Targeted Information/Data Flow Vulnerabilities:

We have shortlisted 7 information flow vulnerabilities that are featured in the list: OWASP Top 10 Application Security Risks - 2017.

* **Injection:** SQL, NoSQL, OS, and LDAP injection.
  - Error-Based SQL Injection
  - Boolean-Based SQL Injection
  - Time-Based SQL Injection
  - Out-of-Band SQL Injection Vulnerability
* **Broken Authentication:** Incorrectly implemented functions related to authentication and session management.
* **XML External Entities (XXE):** External entities can be used to disclose internal files.
* **Broken Access Control:** access unauthorized functionality and/or data.
* **Cross-Site Scripting (XSS):** Application includes untrusted data in a new web page without proper validation.
* **Using Components with Known Vulnerabilities:** Components, such as libraries, frameworks, and other software modules with known vulnerabilities being used.
* **Insecure Deserialization:** Insecure deserialization often leads to remote code execution.


### Evaluating the Selected Features/Metrics:

Simply defining a large set of arbitrary features may lead the learning algorithm to discover false correlations.
For this reason, we would have to make a careful selection of features, which can only be done once we have data to test the fuzzers on and experiment with the various features they present.

### Classical Machine Learning Models:

The potential models that would possibly work the best to eliminate false positives are:

**1. Ensemble Learning -** Instead of selecting the highest ranked learning model, create an ensemble of the chosen learning models. The technique used to create the ensemble could either be bootstrap aggregation or boosting (Adaboosting, GBMs)

**2. RNN with LSTM Units -** Correlate the vulnerabilities generated(as opposed to treating them as independent events) , to detect a pattern. This could be achieved using an LSTM model.


### Framewroks Technologies use:
We will also be able to test the open-source fuzzers once we have data, so while the following seem promising, we will not be able to confirm unless we test it on actual code.

* **w3af -** Open-source web application security scanner
* **Vega -** Open-source fuzzer by Subgraph
* **js-fuzz -** American Fuzzy Lop-inspired fuzz tester for JavaScript code
* **Fun-fuzz -** JavaScript-based fuzzer by the Mozilla Organization
* **OWASP Xenotix XSS Exploit Framework -** XSS detection and exploitation


### Future Enhancements and Plan

Quoting the AI Security Research paper titled **ALETHEIA:** Improving the Usability of Static Security Analysis, the experimental analysis they have used is. “an extensive set of 3,758 security warnings output by a commercial JavaScript security checker when applied to 1,706 HTML pages taken from 675 top-popular Web sites. These Web sites include all Fortune 500 companies, the top 100 Websites”. 

https://arxiv.org/pdf/2210.07465
https://arxiv.org/pdf/2109.13916

There is also a Plan to use  GENAI based Techniques with LLM  ReACT Agents based design pattern to do application Security Testing and analysis with SAST.
Ref: https://arxiv.org/html/2401.17459v1