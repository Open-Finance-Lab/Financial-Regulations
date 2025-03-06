=============================
eXtensible Business Reporting Language (XBRL)
=============================

Task Description
====================
In this task, we assess the ability of LLMs to retrieve and interpret eXtensible Business Reporting Language (XBRL) filings and their ability to use this data to generate precise answers to financial math questions. The objective of this task is to evaluate how well LLMs can process the structured financial data encoded in XBRL format.

Companies need to provide accurate and standardized financial information to stakeholders, including investors, regulators, and auditors. XBRL is a globally recognized standard for electronic communication of business and financial data. Using XBRL will help ensure consistency and comparability across different companies and jurisdictions. Using LLMs to retrieve and process financial data in XBRL format is an important application in financial regulation.


**Example Input and Output:**
--------------------

**XBRL Term**
--------------------
Q: What does the term 'abstract' mean in the context of the XBRL standard? Please provide a detailed explanation of this term.

A: An attribute of an element to indicate that the element is only used in a hierarchy to group related elements together. An abstract element cannot be used to tag data in an instance document.

**Domain Query to XBRL Reports**
--------------------
Q: Among operations, investing, and financing activities, which brought in the most net (or lowest net) cash flow for Nike in FY2023?

A: Among the three, cash flow from operations was the highest for Nike in FY2023.


**Financial Math**
--------------------
Q: A project expects annual cash inflows of $6,000 over 7 years. If the discount rate is 8%, what is the Net Present Value (NPV) of the project?

A: 21462.58

**Numeric Query to XBRL Reports**
--------------------
Q: What is the FY2015 unadjusted EBITDA margin for Netflix? Calculate unadjusted EBITDA using unadjusted operating income and D&A.

A: 0.054


Dataset
====================
The XBRL benchmark dataset is used to evaluate the ability of LLMs to interpret the XBRL standards, retrieve data in XBRL filings, and answer financial math questions. This benchmark dataset comprises XBRL terms, domain queries to XBRL reports, numeric queries to XBRL reports, tag queries to XBRL reports, financial math questions, and financial ratio formula with XBRL tags.

The questions for XBRL terms is to evaluate LLMs’ ability to explain an XBRL term. Domain queries are questions about different domains, such as products and services, in XBRL reports. Numeric queries are questions asking LLMs to retrieve specific data from XBRL reports. Tag queries are questions asking LLMs to retrieve corresponding tags for an item from XBRL reports. Financial math questions asking LLMs to return the result of the given math problem. Financial ratio formula questions ask LLMs to return the calculation formula with corresponding tags for a given financial ratio.

## Data statistics

.. list-table::
   :header-rows: 1

   * - **Data**
     - **Size**
     - **XBRL reports**
     - **Data Source**
   * - XBRL Term
     - 500
     - Not provided
     - `XBRL International Website` <br> `XBRL Documents on the SEC Website`
   * - Domain Query to XBRL Reports
     - 50
     - Selectively provided
     - `XBRL Reports in FinanceBench`
   * - Financial Math
     - 1000
     - Not provided
     - `ChatGPT for formulas and code, verified by a human`
   * - Numeric Query to XBRL Reports
     - 50
     - Selectively provided
     - `XBRL Reports in FinanceBench`
   * - XBRL Tag Query to XBRL Reports
     - 50
     - Selectively provided
     - `XBRL Reports of Companies in Dow Jones 30 from the SEC`
   * - Financial Ratio Formula with XBRL Tags
     - 50
     - Selectively provided
     - `XBRL Reports of Companies in Dow Jones 30 from the SEC`
   * - **Total**
     - **1700**
     - 
     - 

Users can fine-tune or evaluate LLMs using this dataset, call additional tools, using additional open-source. 

Metrics
====================

We use accuracy for financial math questions, numeric queries to XBRL reports, tag queries to XBRL reports, and financial ratio formulas. We use FActScore for XBRL terms and domain queries to XBRL reports.

##Baseline Performance

.. list-table::
   :header-rows: 1

   * - **Model**
     - **Method**
     - **XBRL Term (FActScore)**
     - **Domain and Numeric Query to XBRL Reports (FActScore)**
     - **Financial Math (Accuracy)**
     - **Tag Query to XBRL Reports (Accuracy)**
     - **Score (Average)**
   * - Llama 3.1-8B
     - Zero-shot
     - 0.7083
     - 0.5845
     - 0.7667
     - 0.1667
     - 0.5565
   * - GPT-4o
     - Zero-shot
     - 0.8503
     - 0.5851
     - 0.8842
     - 0.7778
     - 0.7743
   * - Mistral Large 2
     - Zero-shot
     - 0.8221
     - 0.6831
     - 0.7444
     - 0.8667
     - 0.7791

Reference
====================
[1] Sewon Min et al. (2023). FactScore: Fine-grained atomic evaluation of factual precision in long-form text generation. arXiv preprint arXiv:2305.14251. Available at: https://arxiv.org/abs/2305.14251

Shijie Han, et al. XBRL-Agent: Leveraging Large Language Models for Financial Report Analysis. Proceedings of the Conference ICAIF '24: Proceedings of the 5th ACM International Conference on AI in Finance
https://doi.org/10.1145/3677052.3698614.
