| Metric         | Type                   | Focus             | Strengths                                     | Weaknesses                                     |
|----------------|------------------------|-------------------|----------------------------------------------|-----------------------------------------------|
| **ROUGE**      | Lexical (N-gram)      | Recall            | Easy to compute, widely used                 | Surface-level, sensitive to phrasing          |
| **BLEU**       | Lexical (N-gram)      | Precision         | Fast to calculate                            | Lacks recall consideration, not always semantic|
| **METEOR**     | Lexical + Semantic    | Precision/Recall  | Considers synonyms and stems                 | Computationally intensive                      |
| **BERTScore**  | Contextual (Embedding)| F1                | Context-aware, captures meaning              | Computationally heavy                          |
| **GLEU**       | Lexical (N-gram)      | Precision/Recall  | Balances precision and recall                | Surface-level                                  |
| **CIDEr**      | Lexical (TF-IDF Weighted) | Informativeness | Highlights relevant content                  | Complex implementation                         |
| **MoverScore** | Contextual (Embedding + EMD) | Semantic    | Captures nuanced similarities               | Expensive to compute                           |
| **Human Evaluation** | Subjective       | Quality           | Directly assesses readability and relevance  | Time-consuming, subjective                    |
| **F1 Score**   | Lexical/Contextual    | Precision/Recall  | Balances precision and recall                | Does not account for fluency or meaning       |
