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
