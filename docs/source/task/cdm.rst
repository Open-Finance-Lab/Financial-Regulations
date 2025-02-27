=============================
Common Domain Model (CDM)
=============================

Task Description
====================
The Common Domain Model (CDM) is a standardized, machine-readable, and 
machine-executable data and process model for financial products, transactions, 
and lifecycle events. Developed in collaboration with the International Capital 
Market Association (ICMA), the International Swaps and Derivatives Association (ISDA), 
and the International Securities Lending Association (ISLA), CDM is maintained within 
the Fintech Open Source Foundation (FINOS). Its goal is to enhance interoperability, 
streamline transaction processing, and improve regulatory oversight.

This task evaluates the capability of large language models (LLMs) to accurately 
interpret and respond to questions related to the CDM framework, covering its 
structure, use cases, and implementation. Specifically, the task challenges LLMs to:

- Understand key CDM concepts, including trade events, product models, process models, and legal agreements.
- Retrieve and generate precise responses based on CDM documentation and FAQs.
- Assist in CDM implementation and deployment by addressing technical inquiries.

**Input Format**
--------------------
Each input consists of:

- **Primary Request**: A specific question related to CDM, requiring the model to extract relevant information.
- **Content**: The regulatory or documentation-based data that the model needs to act upon.

**Output Format**
--------------------
The expected output is a concise, well-structured answer to the given prompt, based 
on accurate retrieval and interpretation of CDM documentation.

Example Input-Output
--------------------

**Input**  
::

    "Provide a concise answer to the following question related to the Financial Industry Operating Network’s (FINO) Common Domain Model (CDM): 
    What are the key components of a CDM product model?"

**Expected Output**  
::

    "The CDM product model consists of a standardized representation of financial 
    products, including their attributes, lifecycle events, and contractual agreements. 
    It provides a unified schema for derivatives, securities, and lending transactions 
    to ensure interoperability and automation in financial systems."


Dataset
====================
The dataset is designed to test how well LLMs understand and apply CDM-related knowledge. 
It includes:

- A curated collection of questions and answers derived from CDM documentation.
- A diverse range of topics covering product models, event models, legal agreements, and process models.
- A focus on basic CDM concepts, implementation guidelines, and practical deployment issues.

**Dataset Composition**
--------------------
.. list-table::
   :header-rows: 1

   * - **Data Category**
     - **Size**
     - **Source**
   * - Product Model
     - 20
     - CDM Documentation
   * - Event Model
     - 20
     - CDM Documentation
   * - Legal Agreements
     - 12
     - CDM Documentation
   * - Process Model
     - 19
     - CDM Documentation
   * - General and Other
     - 9
     - CDM Documentation
   * - Implementation & Deployment
     - 46
     - FAQs, FINOS CDM organizers, CDM Documentation
   * - **Total**
     - **126**
     - 

**Data Usage**
--------------------
Users can:

- Use the provided dataset to fine-tune or evaluate their **LLMs**.
- Supplement the dataset with additional regulatory materials for improved model performance.

Metrics
====================
The performance of LLMs on the CDM task is evaluated using **FActScore**\ :sup:`[1]`, a factual accuracy 
metric designed to measure the precision of model-generated responses.

**FActScore Evaluation Process**
--------------------
1. **Atomic Fact Extraction**: The model’s generated response is decomposed into atomic facts—short statements that contain single pieces of information.
2. **Validation Against Knowledge Source**: Each atomic fact is assessed against CDM documentation to determine its correctness.
3. **Evaluation Methods**:

   - No-context LM: Evaluates the model’s response without additional retrieval.
   - Retrieve → LM: Uses retrieval-augmented generation to enhance response accuracy.
   - Nonparametric Probability (NP): Assigns probabilities to each fact’s correctness.
   - Retrieve → LM + NP: Combines retrieval and probability-based validation.
4. **Final Score Calculation**: The FActScore is computed as the average factual accuracy across all responses.

**Metric Interpretation**
--------------------
- High FActScore: The model provides factually precise and well-supported responses.
- Low FActScore: The model generates factually incorrect or unsupported claims, indicating poor regulatory comprehension.

By using FActScore, this task ensures that LLMs are assessed not just on fluency, 
but also on their ability to accurately reflect regulatory guidelines and CDM principles.

Baseline Performance
--------------------
Below are FActScore results for three baseline models on the CDM dataset:

.. list-table::
   :widths: 40 40
   :header-rows: 1

   * - **Baseline Model**
     - **FActScore**
   * - Llama 3.1-8B
     - 0.7980
   * - GPT-4o
     - 0.8820
   * - Mistral Large 2
     - 0.8632

As shown, GPT-4o achieved the highest FActScore among the baselines, followed by 
Mistral Large 2 and Llama 3.1-8B. These metrics serve as reference points for 
teams aiming to improve factual accuracy in responses to CDM-related queries.

**Reference**
--------------------
[1] Sewon Min et al. (2023). *FactScore: Fine-grained atomic evaluation of factual precision in long-form text generation.* arXiv preprint arXiv:2305.14251.  
Available at: `https://arxiv.org/abs/2305.14251 <https://arxiv.org/abs/2305.14251>`_