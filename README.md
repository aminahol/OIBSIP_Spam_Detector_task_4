# Email Spam Detection Using Naive Bayes

A text classification project that identifies spam emails using natural language processing techniques and Multinomial Naive Bayes algorithm to enhance email security and productivity.

## Objectives

- Build an accurate binary classifier to distinguish spam from legitimate emails
- Implement text preprocessing pipeline for optimal feature extraction
- Apply TF-IDF vectorization to capture distinctive spam characteristics
- Evaluate model performance with emphasis on precision to minimize false positives

## Dataset

The email dataset contains 5,572 samples with two variables:
- **Text**: Email message content
- **Target**: Binary classification (spam/ham)

**Data Preprocessing Results:**
- Removed 403 duplicate entries, resulting in 5,169 unique samples
- Applied text cleaning including lowercase conversion and punctuation removal
- Class distribution: 87.4% ham, 12.6% spam (moderately imbalanced)

## Methodology

### Text Preprocessing Strategy
Implemented comprehensive text cleaning pipeline addressing common email text challenges:
- **Lowercase normalization** to ensure case-insensitive feature extraction
- **Punctuation removal** to focus on semantic content rather than formatting
- **Duplicate elimination** to prevent model bias toward repeated messages

### Feature Engineering Approach
Selected TF-IDF (Term Frequency-Inverse Document Frequency) vectorization over simple bag-of-words for several strategic reasons:
- **Emphasis on distinctive terms**: Downweights common words while highlighting spam-specific vocabulary
- **Reduced false positive risk**: Prevents legitimate emails containing common words from being misclassified
- **Enhanced precision**: Amplifies importance of characteristic spam terms like "free," "offer," "urgent"

### Model Selection Rationale
Chose Multinomial Naive Bayes for spam detection due to:
- **Text classification optimization**: Specifically designed for discrete count data like word frequencies
- **Handling of class imbalance**: Performs well with unequal class distributions
- **Computational efficiency**: Fast training and prediction suitable for real-time email filtering
- **Feature independence assumption**: Reasonable for bag-of-words text representations

### Evaluation Framework
Applied stratified train-test split (80-20) to maintain class proportions across training and testing sets. Prioritized precision over recall in evaluation, as false positives (legitimate emails marked as spam) have higher business cost than false negatives.

## Results

### Model Performance
- **Overall Accuracy**: 96%
- **Ham Classification**: 96% precision, 100% recall, 98% F1-score
- **Spam Classification**: 100% precision, 71% recall, 83% F1-score

### Confusion Matrix Analysis
- **True Negatives**: 903 ham emails correctly identified
- **False Positives**: 0 ham emails incorrectly marked as spam
- **True Positives**: 93 spam emails correctly identified
- **False Negatives**: 38 spam emails missed

### Key Findings
The model achieved perfect precision for spam detection (100%), meaning every email classified as spam was genuinely spam. The trade-off resulted in 71% recall, indicating some spam messages were missed but no legitimate emails were incorrectly filtered.

Word cloud analysis revealed distinct vocabulary patterns:
- **Spam characteristics**: Heavy use of promotional terms, monetary incentives, urgency indicators
- **Ham characteristics**: Conversational language, personal communication patterns

## Conclusion

The Multinomial Naive Bayes model with TF-IDF vectorization demonstrates excellent performance for email spam detection, particularly excelling in precision-critical scenarios. The 100% spam precision ensures zero false positives, making it suitable for production environments where user trust is paramount.

The model's conservative approach (high precision, moderate recall) aligns with email filtering best practices where missing some spam is preferable to blocking legitimate communications. The 96% overall accuracy combined with perfect spam precision makes this approach reliable for automated email filtering systems.

The moderate class imbalance (87% ham, 13% spam) was effectively handled through stratified sampling and the inherent robustness of Naive Bayes to unequal class distributions. TF-IDF vectorization proved crucial in distinguishing spam-specific vocabulary from normal email language patterns.
