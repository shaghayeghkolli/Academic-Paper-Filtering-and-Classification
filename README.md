# Academic Paper Filtering and Classification

## Introduction

This project is designed to filter and classify academic papers within a dataset obtained through keyword-based searches on PubMed. The dataset, provided in CSV format, includes 11,450 records. The primary objective is to identify papers that apply deep learning and neural network-based solutions within the fields of virology and epidemiology.

### Project Objectives

This project enables the following:

- **Efficient Filtering**: Provides more accurate filtering of relevant papers compared to basic keyword searches.
- **Targeted Classification**: Categorizes papers into specific, meaningful groups.
- **Focused Method Extraction**: Extracts method names related to deep learning and AI techniques used in each paper.

## Solution Components

The system comprises several core components, each outlined below:

### 1. Data Loading and Preprocessing

- **Combining Datasets**: Multiple CSV files from PubMed searches are merged to form a single dataset.
- **Data Cleaning**: Duplicate entries are removed, and missing data is addressed to maintain high data quality.
- **Text Preparation**: Titles and abstracts are combined to facilitate more comprehensive analysis.

### 2. Semantic Filtering Using NLP Techniques

- **Sentence Transformers**: A pre-trained model (`all-MiniLM-L6-v2`) generates embeddings for the papers and reference sentences.
- **Cosine Similarity**: Similarity scores between paper embeddings and reference embeddings are computed, enabling semantic filtering of relevant papers.

#### Benefits of Semantic Filtering

- **Semantic Understanding**: Captures text meaning beyond basic keyword matching.
- **Improved Accuracy**: Identifies relevant papers even if they lack specific keywords.
- **Reduced False Positives/Negatives**: Enhances filtering precision compared to traditional keyword-based approaches.

### 3. Classification of Papers

- **Zero-Shot Classification**: The `valhalla/distilbart-mnli-12-3` model classifies papers into categories such as:
  - Text Mining
  - Computer Vision
  - Both
  - Other

#### Advantages of Zero-Shot Classification

- **No Pre-Labeled Data Required**: Classifies texts without task-specific labeled data.
- **Adaptability**: Easily accommodates new categories or labels as needed.
- **Efficiency**: Capable of processing large volumes of data efficiently.

### 4. Refined Method Name Extraction

- **Targeted Keyword Matching**: A predefined list of deep learning and AI methods is employed for keyword matching.
- **Regex Matching**: Exact matches of method names within the text are located using regular expressions.
- **Contextual Filtering**: Ensures that only relevant methods are extracted, omitting unrelated terms.

#### Advantages of Refined Method Extraction

- **Accuracy**: Focuses on extracting deep learning and AI-related methods.
- **Relevance**: Excludes general or unrelated terms outside the defined method list.
- **Simplicity**: The list of methods can be easily updated as new techniques are developed.

## NLP Techniques Used

1. **Semantic Filtering with Sentence Transformers**  
   Sentence Transformers convert text into high-dimensional embeddings, allowing cosine similarity comparisons to assess the semantic similarity between each paper and reference topics.

2. **Zero-Shot Classification**  
   The Zero-Shot Classification model categorizes papers without the need for specific training data, making it adaptable to diverse classification tasks.

3. **Refined Method Extraction with Regex Matching**  
   A predefined list of deep learning and AI methods, paired with regex matching, ensures accurate extraction of relevant methods from the text.

## Advantages Over Keyword-Based Filtering

- **Semantic Understanding**: Extends beyond surface-level keywords to capture text context and meaning.
- **Enhanced Accuracy**: Minimizes irrelevant results while identifying more relevant papers.
- **Focused Method Extraction**: Limits extraction to deep learning and AI methods, improving data quality.
- **Scalability**: Efficiently handles large datasets with minimal performance impact.

## Getting Started

### Prerequisites

- Python 3.x
- [Transformers Library](https://huggingface.co/transformers/)
- Note: This project has been successfully run on a free Google Colab account.
