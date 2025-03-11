=============================
Workflow
=============================
In order to encourage the community to develop LLMs that effectively handle multimodal data and tackle the issues of hallucinations and information, participants will follow this structured workflow:

1. **Use Scenarios**: We begin with the use scenarios that reflect professional financial regulatory activities including but not limited to 
   legal research, validation, and compliance. 
2. **Design Tasks**: By decomposing the above use scenarios, we divide them into capabilities and define corresponding tasks. In this stage, 
   there are nine novel tasks:

   - Basic Capabilities
      - Abbreviation Recognition
      - Definition Recognition
      - Named Entity Recognition (NER)
      - Question Answering
      - Link Retrieval
   - Passing Certificates 
   - Understanding the Common Domain Model (CDM)
   - Understanding the Model Openness Framework (MOF)
   - XBRL Filings
3. **Identify Failure Patterns**: After we evaluate LLMs, we will identify failure patterns.
4. **Expand Testing Datasets**: The above failure patterns instruct the expansion of testing sets: including questions for observed weaknesses. 
   We create testing questions from multimodal data collected from various data sources, such as legal texts, contracts, and financial 
   statements.
5. **Enhance Tasks**: The newly expanded question sets are integrated into the tasks. We will also integrate the new tasks and question sets into the Open FinLLM Leaderboard.

Curation Workflow
=================

The following figure illustrates the curation flow for our testing sets:

.. figure:: images/overview_method.png
   :alt: Curation Workflow Diagram
   :align: center
   :width: 80%

   The curation workflow for financial regulatory task and dataset expansion.


This workflow operates as a continuous improvement loop, ensuring that tasks and test sets remain relevant, challenging, and aligned with real-world financial applications.
