# Small Language Models (SLMs)

> Beginner-friendly study notes. Written as a learning summary and refined for technical accuracy.

## 1. What is a Small Language Model?

A **Small Language Model (SLM)** is a language model designed to perform language tasks with a comparatively compact model size and lower compute or memory requirements than many larger language models.

SLMs can be useful when an application needs lower latency, lower operating cost, on-device processing, or a model specialised for a narrower task.

**Important:** There is no single universal parameter-count cutoff that defines every SLM. “Small” depends on the model, hardware, task, and deployment context.

## 2. How does a language model work?

At a high level, a language model learns statistical patterns and relationships from text during training. At inference time, it uses the input context to produce an output. Many generative language models produce text by predicting one token at a time.

### A simplified workflow

1. **Data collection and preparation**  
   Text data is gathered, filtered, cleaned, and prepared. Data quality, licensing, privacy, and representation matter.

2. **Tokenization**  
   A tokenizer converts text into tokens. A token may be a word, part of a word, punctuation, or another text unit. Tokens are represented by IDs.

3. **Embeddings**  
   Token IDs are mapped to learned numerical vectors. These vectors are used by the model to represent token information.

4. **Model processing**  
   In transformer-based models, layers process token representations. Attention mechanisms help the model use relevant context and relationships among tokens.

5. **Training and adaptation**  
   During pretraining, model parameters are learned from training data. A model may later be fine-tuned or otherwise adapted for a particular task or style. Not every deployed model is fine-tuned by its end user.

6. **Inference / output generation**  
   A user supplies a prompt. The model processes the context and, for an autoregressive generative model, predicts a next token repeatedly until it produces an answer or reaches a stopping condition.

7. **Evaluation and deployment**  
   The model is tested for quality, reliability, speed, memory use, and safety before being integrated into an application.

**A useful distinction:** training changes model parameters; inference uses the trained model to produce an output. Fine-tuning is a form of additional training/adaptation, not another name for inference.

## 3. Key terms

| Term | Meaning |
|---|---|
| Foundation model | A model trained on broad data that can be adapted to multiple downstream tasks. |
| Parameter | A learned numerical value inside a model. |
| Dataset | A collection of data used for training, validation, or testing. |
| Token | A unit produced by a tokenizer. |
| Tokenization | The process of converting text into tokens. |
| Embedding | A learned numerical vector representation. |
| Transformer | A neural-network architecture used by many modern language models. |
| Attention | A mechanism that lets a model weigh information from different positions in its input. |
| Training | The process of adjusting model parameters using data and an optimisation method. |
| Fine-tuning | Further training a pretrained model on a more specific dataset or objective. |
| Inference | Running a trained model to obtain predictions or generated output. |

## 4. Examples mentioned in my lesson

These examples are not all the same kind of model, and their capabilities and intended uses differ.

- **BERT:** A transformer encoder model designed to build context-aware representations. It is commonly used for language-understanding tasks; it is not a general-purpose, autoregressive chat model.
- **DistilBERT:** A smaller model distilled from BERT, designed to retain useful language-understanding capability with a lighter footprint.
- **MobileBERT:** A compact BERT-style model designed with mobile and resource-constrained deployment in mind.
- **Phi-2:** A 2.7-billion-parameter language model released by Microsoft Research. It is an example of a relatively compact generative model; the “small” label is relative to larger models.
- **Orca 2:** A Microsoft research model family with 7B and 13B variants, developed to study improved reasoning in smaller language models. These are compact relative to very large models, but 13B is not tiny and may need substantial hardware.

**Reminder:** A model's parameter count alone does not tell the whole story. Architecture, quantisation, context length, runtime, hardware, and task all affect resource needs and performance.

## 5. SLM vs LLM

| Dimension | SLM | LLM |
|---|---|---|
| Typical size | Comparatively compact | Usually much larger |
| Compute and memory | Often lower, depending on model and task | Often higher |
| Cost | Can be cheaper to run | Can cost more to run |
| Speed | Can be faster for suitable tasks | Depends on model, hardware, and serving setup |
| Deployment | May fit on phones, laptops, or edge devices | Often served on powerful machines or in the cloud |
| Strengths | Focused tasks, local use, constrained environments | Broad capabilities and more demanding tasks |
| Limitations | May have less capacity or weaker performance on complex tasks | Higher resource requirements; not automatically better for every task |

There is no universal winner. Choose a model based on task quality, latency, privacy, hardware, cost, and reliability requirements.

## 6. Potential use cases

- **Customer support:** answering common, well-scoped questions from approved support information.
- **Mobile applications:** text suggestions, language features, and voice-command processing.
- **Healthcare administration:** helping with general administrative information, with appropriate privacy controls and human oversight. A model should not replace qualified medical judgement.
- **Education:** explaining concepts, generating practice questions, and providing learning support.
- **Coding assistance:** helping explain code, suggest completions, or identify possible errors. Outputs still need testing and review.
- **Smart devices and IoT:** enabling selected language or voice features on connected devices.

A use case should be selected only after checking accuracy, privacy, safety, and the consequences of an incorrect answer.

## 7. Why teams consider SLMs

Potential advantages include:

- Lower compute and operating costs for suitable workloads
- Lower latency in some deployments
- Possibility of running locally or on edge hardware
- Reduced need to send some data to a remote service when processing is genuinely local
- Easier specialisation for a narrow task
- Possible offline operation after the model and required components have been installed

These are possibilities, not guarantees. Local models still use device resources, and local execution does not automatically make an application private or secure.

## 8. Advantages and limitations

| Potential advantages | Potential limitations |
|---|---|
| Lower resource requirements for suitable workloads | May have less general knowledge or capability |
| Can be fast for focused tasks | May struggle with complex reasoning or broad tasks |
| May run on local or edge devices | Device memory and processing limits still apply |
| Can be adapted for a specific task | Fine-tuning requires suitable data and evaluation |
| Local processing may support privacy goals | Can still produce incorrect or unsafe outputs |

**Key takeaway:** SLMs are not always better than LLMs. The right choice depends on the application and its requirements.

## 9. Future opportunities

Areas worth watching and learning about include:

- More capable on-device AI
- Efficient inference and model compression
- Quantisation and distillation
- Task-specific models
- Private and offline AI workflows
- Combining small models with larger models or retrieval systems

These are active areas of development, not guaranteed outcomes.

## 10. What I learned

In this lesson, I learned that:
- SLMs are comparatively compact language models.
- Language models use tokenization and learned representations to process text.
- Transformer attention helps models use context.
- Training and inference are different stages.
- Fine-tuning adapts a pretrained model for a more specific task.
- SLMs can be useful for focused, lower-resource, or local applications.
- Model choice involves trade-offs; smaller does not automatically mean better.

## 11. Questions to explore next

1. What is the difference between pretraining, fine-tuning, and prompt engineering?
2. What are quantisation and knowledge distillation?
3. How can I run a small pretrained model locally?
4. How do I measure inference latency and memory use?
5. How can I evaluate a model's accuracy for a specific task?

## 12. Suggested hands-on exercise

Create a small comparison experiment:
1. Choose two openly available models suitable for your computer.
2. Give both the same small set of simple prompts.
3. Record response quality, response time, and memory usage.
4. Note the hardware and software setup.
5. Explain which model is more suitable for your chosen task and why.

Do not publish API keys, private data, or restricted model files in the repository.
