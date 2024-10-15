
![image](https://github.com/user-attachments/assets/4403efcf-21ee-4383-b35e-00c1d886ee3c)
![image](https://github.com/user-attachments/assets/b65e13ac-3643-4ccd-94a2-e3e136f397fc)

PEGASUS performed the best among the models not just because of the scores, but due to its underlying architecture and design, which are specifically optimized for text summarization. Here’s why PEGASUS excelled:

### 1. **Specialized Pre-Training Objective (Gap-Sentence Generation)**:
   - PEGASUS uses a unique pre-training method called **gap-sentence generation**, where entire sentences are masked during training, and the model learns to predict these as summaries. This approach effectively teaches PEGASUS to understand which parts of the text are most critical and how to generate concise, informative summaries.
   - This method aligns well with the goal of summarization, which is to identify and distill essential information, making PEGASUS particularly powerful in generating high-quality, coherent summaries.

### 2. **Abstractive Summarization Capability**:
   - Unlike models like BART, which are less specialized for summarization tasks, PEGASUS is optimized for **abstractive summarization**, where the model generates entirely new text rather than simply extracting key phrases from the input.
   - Its architecture allows it to rephrase information while maintaining the core meaning, which is why it scored highest in both fluency and accuracy metrics (like GLEU and BLEU).

### 3. **Encoder-Decoder Transformer Architecture**:
   - PEGASUS uses an encoder-decoder architecture similar to FLAN-T5 but is specifically fine-tuned for summarization through its gap-sentence mechanism. This design allows PEGASUS to leverage the encoder to understand the context deeply and the decoder to generate precise and coherent outputs.
   - The combination of understanding context and generating fluent, human-like summaries makes PEGASUS effective, especially when handling complex, domain-specific texts like medical articles.

### 4. **Fine-Tuning on Domain-Specific Texts**:
   - PEGASUS's adaptability to domain-specific texts (e.g., medical articles) through fine-tuning ensures it captures terminology and context-specific nuances better than more generic models like BART. This fine-tuning advantage likely contributed to its higher ROUGE-2 and ROUGE-L scores, reflecting its ability to accurately capture and generate relevant information.

### Conclusion:
PEGASUS performed the best because it combines an architecture and training strategy specifically tailored for summarization tasks. The gap-sentence generation pre-training makes it highly effective at identifying and conveying critical information, while its encoder-decoder structure enables it to generate fluent, coherent summaries. These features give it a clear edge over other models, leading to its superior performance.











| Metric    | Good Score   | Average Score | Bad Score    |
|-----------|--------------|---------------|--------------|
| BLEU      | 0.4 - 0.6    | 0.2 - 0.4     | 0.0 - 0.2    |
| ROUGE-1   | Above 0.5    | 0.3 - 0.5     | Below 0.3    |
| ROUGE-2   | Above 0.2    | 0.1 - 0.2     | Below 0.1    |
| ROUGE-L   | Above 0.4    | 0.2 - 0.4     | Below 0.2    |
| GLEU      | Above 0.6    | 0.3 - 0.6     | Below 0.3    |


**GLEU**, **ROUGE**, and **BLEU** are popular metrics used for evaluating text summarization models and other natural language generation tasks. Here's an overview of each and their scoring ranges:

### 1. **BLEU (Bilingual Evaluation Understudy)**
- **Purpose**: Measures the overlap between the generated summary and the reference (human-written) summary at the n-gram level (typically up to 4-grams).
- **Calculation**: BLEU computes the precision of n-grams (small chunks of words) between the generated summary and the reference summary. It also includes a brevity penalty to discourage overly short outputs.
- **Score Range**: 0 to 100 (commonly shown as 0 to 1.0 in decimal form).
- **Interpretation**:
  - **Good Score**: 0.4 to 0.6 (or 40-60%); values in this range indicate a summary that captures much of the relevant information accurately.
  - **Average Score**: 0.2 to 0.4 (or 20-40%); indicates partial relevance and overlap but might miss important details.
  - **Bad Score**: 0.0 to 0.2 (or 0-20%); the generated summary does not capture the reference well and might have significant discrepancies.

### 2. **ROUGE (Recall-Oriented Understudy for Gisting Evaluation)**
- **Purpose**: Measures the overlap between the generated summary and reference summary based on recall. There are different types:
  - **ROUGE-1**: Overlap of unigrams (single words).
  - **ROUGE-2**: Overlap of bigrams (two-word sequences).
  - **ROUGE-L**: Longest common subsequence (LCS), focusing on fluency and coherence.
- **Calculation**: ROUGE calculates recall, precision, and F1-score based on n-gram overlaps.
- **Score Range**: 0 to 100 (or 0 to 1.0 in decimal form).
- **Interpretation**:
  - **Good Score**: 
    - **ROUGE-1**: Above 0.5 (or 50%) indicates a high degree of word-level overlap.
    - **ROUGE-2**: Above 0.2 (or 20%) is good, showing phrase-level matching.
    - **ROUGE-L**: Above 0.4 (or 40%) demonstrates strong structural similarity.
  - **Average Score**: 
    - **ROUGE-1**: 0.3 to 0.5 (30-50%).
    - **ROUGE-2**: 0.1 to 0.2 (10-20%).
    - **ROUGE-L**: 0.2 to 0.4 (20-40%).
  - **Bad Score**: 
    - **ROUGE-1**: Below 0.3 (30%).
    - **ROUGE-2**: Below 0.1 (10%).
    - **ROUGE-L**: Below 0.2 (20%).

### 3. **GLEU (Google-BLEU)**
- **Purpose**: Variation of BLEU, designed specifically for evaluating text generation tasks, emphasizing fluency and grammar. It’s particularly useful when multiple references are available.
- **Calculation**: Like BLEU but considers both precision and recall, providing a more balanced view. It rewards summaries that align closely with the references.
- **Score Range**: 0 to 1.0 (same as BLEU).
- **Interpretation**:
  - **Good Score**: Above 0.6; indicates the generated text is very close to the reference in terms of fluency and word usage.
  - **Average Score**: 0.3 to 0.6; shows moderate similarity with some missing details.
  - **Bad Score**: Below 0.3; suggests poor alignment and insufficient fluency or grammar.

### Summary
- **Good Scores**:
  - **BLEU**: 0.4 to 0.6
  - **ROUGE-1**: Above 0.5
  - **ROUGE-2**: Above 0.2
  - **ROUGE-L**: Above 0.4
  - **GLEU**: Above 0.6
- **Average Scores**:
  - **BLEU**: 0.2 to 0.4
  - **ROUGE-1**: 0.3 to 0.5
  - **ROUGE-2**: 0.1 to 0.2
  - **ROUGE-L**: 0.2 to 0.4
  - **GLEU**: 0.3 to 0.6
- **Bad Scores**:
  - **BLEU**: 0.0 to 0.2
  - **ROUGE-1**: Below 0.3
  - **ROUGE-2**: Below 0.1
  - **ROUGE-L**: Below 0.2
  - **GLEU**: Below 0.3

Each metric has its strengths, so it's often beneficial to use them together for a more comprehensive evaluation.
