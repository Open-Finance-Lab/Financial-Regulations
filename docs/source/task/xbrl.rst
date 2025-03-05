=============================
eXtensible Business Reporting Language (XBRL)
=============================

Task Description
====================
eXtensible Business Reporting Language (XBRL) is the global standard that powers digital reporting. By making business reporting computer-readable, it helps make business data easy to find, access and analyse. The standard was originally based on XML, but now additionally supports reports in JSON and CSV formats, as well as the original XML-based syntax.

In this task, we assess the ability of LLMs to retrieve and interpret eXtensible Business Reporting Language (XBRL) filings and their ability to use this data to generate precise answers to financial math questions. The objective of this task is to evaluate how well LLMs can process the structured financial data encoded in XBRL format.


Dataset
====================
The XBRL benchmark dataset is used to evaluate the ability of LLMs to interpret the XBRL standards, retrieve data in XBRL filings, and answer financial math questions. This benchmark dataset comprises XBRL terms, domain queries to XBRL reports, numeric queries to XBRL reports, tag queries to XBRL reports, financial math questions, and financial ratio formula with XBRL tags.

The questions for XBRL terms is to evaluate LLMs’ ability to explain an XBRL term. Domain queries are questions about different domains, such as products and services, in XBRL reports. Numeric queries are questions asking LLMs to retrieve specific data from XBRL reports. Tag queries are questions asking LLMs to retrieve corresponding tags for an item from XBRL reports. Financial math questions asking LLMs to return the result of the given math problem. Financial ratio formula questions ask LLMs to return the calculation formula with corresponding tags for a given financial ratio.



Metrics
====================
