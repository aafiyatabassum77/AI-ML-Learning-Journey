# Gen AI 101 — Enterprise Generative AI

## Source scope and documentation note

These notes are based on the uploaded 19-page PDF. The readable material is primarily a browser capture of the article **“Enterprise Generative AI: Unlocking Customized Solutions”** (Bombay Softwares, dated 19 March 2024, by Rohit M.). The final pages show parts of the Gen AI 101 course navigation, including Foundation Models and Point-E topics, but do not contain their full lesson content.

Accordingly, this document explains the material actually present in the source. It does **not** claim to be a complete set of notes for every Gen AI 101 course topic. Where useful, technical clarifications are labelled as such.

---

## 1. What is Enterprise Generative AI?

Enterprise Generative AI refers to the use of generative AI systems that are selected, configured, adapted, or integrated to address the needs of a particular organisation.

The source describes these models as being trained on specific datasets to generate content, solutions, or insights relevant to an organisation's requirements. It contrasts these tailored systems with general-purpose, consumer-facing assistants.

### What makes an enterprise use case different?

An enterprise solution must fit into an organisation's:
- business processes and workflows;
- approved information sources;
- security and privacy requirements;
- technology environment;
- regulatory and governance obligations;
- quality, reliability, and cost expectations.

**Technical clarification:** An organisation does not necessarily need to train a foundation model from scratch to build an enterprise generative-AI application. It may use a hosted model, an open-weight model, retrieval-augmented generation (RAG), fine-tuning, or a combination of approaches.

## 2. Benefits of custom enterprise Generative AI

The source identifies five key benefits.

### 2.1 Tailored solutions

A model or AI application can be adapted to an organisation's domain, terminology, workflows, and information needs. This can make outputs more relevant to specific business problems.

Example: An internal assistant could answer employee questions using approved HR policy documents. The answer quality depends on the freshness, completeness, and permissions of those documents.

### 2.2 Increased efficiency

Generative AI can help automate repetitive work and streamline processes such as:
- drafting and summarising documents;
- extracting information from text;
- preparing first drafts of reports;
- assisting with routine support queries;
- supporting structured decision workflows.

Automation should include human review where errors could have significant consequences. Productivity gains should be measured rather than assumed.

### 2.3 Enhanced innovation

Generative AI can support brainstorming, design exploration, prototyping, and the generation of alternative ideas. Teams may use it to explore options more quickly.

It is an aid to human creativity, not a guarantee that generated ideas are original, feasible, safe, or commercially valuable.

### 2.4 Improved customer engagement

AI systems can support personalised responses, recommendations, and customer-service interactions. Better use of customer context may make interactions more relevant.

Personalisation must respect consent, privacy, data minimisation, and applicable laws. Generated answers should be monitored for accuracy and tone.

### 2.5 Competitive advantage

Organisations may differentiate their products and services by applying AI to their specific workflows and data. A sustainable advantage usually comes from the quality of the complete solution—data, process integration, user experience, governance, and execution—not simply from using a model.

## 3. How can enterprises build or adapt foundation models?

The source presents two broad approaches.

### 3.1 Build your own model (from scratch)

This means developing and training a model rather than starting from an existing pretrained model.

Potential requirements include:
- large and carefully governed training datasets;
- substantial compute resources, often including GPUs;
- machine-learning and infrastructure expertise;
- model evaluation and safety testing;
- ongoing maintenance and deployment operations.

The source notes that this approach can be very costly and require significant computing resources and a skilled data-science team.

**When might it make sense?** Only when an organisation has a strong reason to control the model-development process, suitable data and expertise, and a justified business case. It is not the default choice for most organisations.

### 3.2 Improve an existing pretrained model

The source describes adapting an existing model as a more cost-effective alternative. It mentions fine-tuning, reinforcement learning from human feedback (RLHF), and retrieval-augmented generation (RAG).

These techniques solve different problems:

| Technique | Main idea | What changes? |
|---|---|---|
| Fine-tuning | Further train a pretrained model on selected examples or objectives | Model parameters are updated |
| RLHF | Use human preference feedback as part of a training/alignment process | Usually model behaviour/parameters are updated through an optimisation pipeline |
| RAG | Retrieve relevant external information and provide it to the model at response time | Usually the model weights do not need to change |

#### Fine-tuning

Fine-tuning continues training from a pretrained model using a task-specific or domain-specific dataset. It can help adapt style, task behaviour, or specialised patterns.

The source mentions fine-tuning with a small curated dataset. A small dataset can be useful when it is high quality and well matched to the task, but small size alone does not guarantee good results. Data coverage, evaluation, and overfitting matter.

#### Reinforcement Learning from Human Feedback (RLHF)

RLHF uses human feedback—often preferences between candidate responses—to help shape model behaviour. A typical pipeline may involve collecting demonstrations or preferences, training a reward model, and optimising the language model against that reward signal.

RLHF is not simply “asking users for feedback during every conversation.” It is a training and alignment approach that requires careful data design and evaluation.

#### Retrieval-Augmented Generation (RAG)

RAG connects a generative model to an external knowledge source. At query time, the system retrieves relevant passages and supplies them as context for the model to use when generating an answer.

A simplified RAG flow:

1. Collect and prepare trusted documents.
2. Split documents into manageable passages.
3. Convert passages into searchable representations (often embeddings) and index them.
4. Receive a user's question.
5. Retrieve relevant passages.
6. Provide the question and retrieved context to the language model.
7. Generate an answer, ideally with references to the source material.
8. Evaluate the answer and retrieval quality.

**Key distinction:** RAG provides information at inference time; fine-tuning changes model parameters through additional training. RAG is often useful when information changes frequently or must remain in an organisation-controlled knowledge base.

## 4. Enterprise Generative AI use cases

The source lists five application areas.

### 4.1 Code generation

Generative AI can assist developers by:
- suggesting code snippets;
- explaining unfamiliar code;
- drafting functions or modules;
- helping with repetitive coding tasks;
- suggesting tests or documentation.

Generated code must be reviewed, tested, and checked for security, licensing, correctness, and compatibility. Developers remain responsible for the code they ship.

### 4.2 Product development

Generative AI can help explore product concepts, designs, and prototypes. The source gives examples such as fashion designs informed by trends and customer preferences, and automotive designs or components.

Generated designs still require engineering validation, safety checks, intellectual-property review, and user testing.

### 4.3 Sales and marketing

Possible applications include:
- drafting personalised email campaigns;
- generating product descriptions;
- creating variations of marketing content;
- helping analyse customer preferences.

Campaigns should be reviewed for accuracy, appropriate targeting, privacy compliance, and misleading claims.

### 4.4 Customer support and service

Chatbots and support assistants can respond to common questions and help users find information. They may reduce routine workload and allow human agents to focus on complex cases.

A production support assistant should have:
- access only to approved information;
- clear escalation to a human;
- monitoring for incorrect or harmful answers;
- protections for personal and account data;
- a way to report and correct failures.

### 4.5 Fraud detection

The source describes analysing large volumes of data to identify suspicious patterns or anomalies in areas such as financial transactions and healthcare claims.

**Technical clarification:** Generative AI may help summarise alerts or support analyst workflows, but fraud detection is often built using specialised statistical or machine-learning detection systems. A generative model's output should not be treated as proof of fraud. Decisions need validated signals, explainability appropriate to the context, and human or formal review.

## 5. Challenges of custom enterprise Generative AI

The source identifies five major challenge areas.

### 5.1 Data quality and quantity

Models and AI applications depend on data that is relevant, accurate, sufficiently representative, and appropriately governed.

Common issues:
- missing, duplicated, outdated, or inconsistent records;
- biased or unrepresentative samples;
- unclear data ownership or usage rights;
- sensitive information appearing in training or retrieval data;
- poor labels or weak documentation.

Practical controls:
- define data ownership and permitted use;
- clean and validate datasets;
- remove or protect sensitive information where appropriate;
- track data provenance and versions;
- create representative evaluation datasets;
- monitor data freshness.

### 5.2 Model complexity

Custom models can be difficult to build, evaluate, secure, and maintain. They require specialist skills and must be updated as models, libraries, infrastructure, and threats evolve.

Practical controls:
- start with the simplest approach that meets requirements;
- use established model and serving tools;
- define measurable quality targets;
- version models, prompts, and datasets;
- test before releases and monitor after deployment.

### 5.3 Compute resources

Training and serving models can require substantial processing power, memory, storage, and energy. The amount depends on model size, context length, workload, hardware, and optimisation.

Practical controls:
- estimate total cost before implementation;
- benchmark representative workloads;
- consider hosted models or smaller models where appropriate;
- use quantisation, batching, caching, or other optimisations when suitable;
- monitor latency, throughput, and cost per task.

### 5.4 Integration and deployment

Integrating AI into existing systems may require changes to data pipelines, applications, identity systems, APIs, monitoring, and operational processes.

Practical controls:
- define system boundaries and API contracts;
- apply authentication and least-privilege access;
- test failure handling and fallback behaviour;
- log system health without unnecessarily logging sensitive content;
- plan for version changes, rollback, and incident response.

### 5.5 Ethical and legal considerations

The source highlights regulatory compliance, ethical guidelines, sensitive data, societal impact, accountability, and transparency.

Practical controls:
- identify applicable laws and organisational policies;
- document intended and prohibited uses;
- assess privacy, bias, safety, and misuse risks;
- disclose AI involvement where appropriate;
- provide human oversight for consequential decisions;
- keep records of evaluation, approvals, and incidents.

## 6. Future of Generative AI in the enterprise

The source identifies five trends.

### 6.1 Continued advances in AI technology

Models and tools are expected to continue evolving in capability and efficiency. Organisations should evaluate new technology against actual business needs rather than adopting it solely because it is new.

### 6.2 Increased adoption across industries

The source expects generative AI adoption to expand across industries. Adoption should be guided by measurable value, risk assessment, user needs, and readiness.

### 6.3 Integration with other technologies

The source mentions integration with:
- blockchain;
- Internet of Things (IoT);
- augmented reality (AR).

Such combinations may support new workflows and experiences. Each integration introduces additional security, reliability, privacy, and operational considerations.

### 6.4 Ethical and regulatory considerations

As adoption grows, organisations will need stronger attention to privacy, fairness, transparency, accountability, and compliance. Governance should be part of system design rather than added only after deployment.

### 6.5 Collaboration and partnerships

The source anticipates collaboration among businesses, AI experts, and researchers. Partnerships can provide access to specialist expertise and help organisations adapt models to different industries and needs.

## 7. Choosing an approach: a practical decision guide

| Requirement | Approach worth evaluating |
|---|---|
| Need answers grounded in frequently changing internal documents | RAG |
| Need consistent task format, style, or specialised behaviour | Fine-tuning |
| Need to shape response preferences or alignment | Preference optimisation / RLHF-style methods |
| Need a prototype quickly | Existing model through a controlled API or approved deployment |
| Need full control over model development and have major resources | Training from scratch |

This is a starting point, not an automatic decision rule. Approaches can be combined. A team should compare quality, security, privacy, latency, cost, maintainability, and legal constraints.

## 8. Key takeaways

1. Enterprise Generative AI adapts AI capabilities to organisational needs and workflows.
2. Potential benefits include tailored solutions, efficiency, innovation, customer engagement, and differentiation.
3. Training a foundation model from scratch is resource-intensive.
4. Existing pretrained models can be adapted or connected to enterprise knowledge.
5. Fine-tuning, RLHF, and RAG are distinct techniques.
6. Enterprise use cases include coding, product development, sales and marketing, customer support, and fraud-analysis workflows.
7. Data, complexity, compute, integration, and governance are major implementation challenges.
8. Successful deployment requires evaluation, monitoring, security, and human accountability.

## 9. Revision questions

1. What is Enterprise Generative AI?
2. How does an enterprise AI solution differ from a general-purpose consumer assistant?
3. What are five potential benefits of custom enterprise Generative AI?
4. What are the main costs and requirements of training a model from scratch?
5. What is fine-tuning, and what kinds of adaptation can it support?
6. What does RLHF stand for, and what role does human preference feedback play?
7. What is RAG? Describe its main steps.
8. How does RAG differ from fine-tuning?
9. Give five enterprise use cases from the source.
10. Why are data quality and data governance important?
11. What compute and deployment issues should an organisation consider?
12. What ethical and legal responsibilities arise when deploying enterprise AI?
13. Why should generated code and customer-support answers be reviewed?
14. What does human oversight mean in a high-impact workflow?

## 10. Topics visible in the course navigation but not covered in the uploaded material

The last pages show course items including:
- Foundation Models: Working and Risks
- How Do Foundation Models Work?
- How to Pick the Right AI Foundation Model
- Future of Foundation Models
- Future of AI with Foundation Models
- How Does Point-E Work?
- How Point-E Can Help Businesses
- Applications, Benefits and Drawbacks of Point-E
- Generative AI vs … (the remainder of the title is not visible)

The uploaded PDF does not include the detailed lesson content for these items. They should be documented from the corresponding course lessons or source material before being added as course-derived notes.

---

## Source reference

Primary source visible in the uploaded PDF:
- Bombay Softwares, Rohit M., “Enterprise Generative AI: Unlocking Customized Solutions,” 19 March 2024.
- The PDF is a 19-page browser capture; the article content occupies most of the readable pages, while the final pages show course navigation.

**Documentation note:** Explanatory clarifications in this document are included to distinguish concepts accurately. They are not presented as quotations from the source article.
