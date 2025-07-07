# Healthcare Diagnostic Chatbot

## Project Overview
This AI-powered diagnostic assistant leverages machine learning to help users identify potential health conditions based on reported symptoms. The system combines multiple medical datasets with intelligent algorithms to provide preliminary diagnoses, detailed disease information, and personalized care recommendations.

## Key Features

### Intelligent Symptom Analysis
- **Dynamic Input Handling**: Uses regex pattern matching to interpret varied symptom descriptions
- **Symptom Severity Scoring**: Weighted analysis based on symptom intensity and duration
- **Multi-Symptom Correlation**: Evaluates symptom combinations for more accurate predictions

### Comprehensive Output
- **Differential Diagnosis**: Presents multiple potential conditions when appropriate
- **Detailed Descriptions**: Provides medical explanations for each predicted condition
- **Actionable Recommendations**: Suggests specific precautions and indicates when professional care is needed
- **Accessibility Option**: Text-to-speech functionality for visually impaired users

## Data Pipeline

### Core Datasets
1. **Training.csv**  
   - Contains 5,000+ symptom-disease associations  
   - Used to train the primary prediction models  
   - Features 132 symptoms across 41 common conditions

2. **Testing.csv**  
   - Validation set with 1,200+ test cases  
   - Ensures model generalization capability  
   - Maintains same feature structure as training set

3. **symptom_Description.csv**  
   - Patient-friendly disease explanations  
   - Standardized descriptions from medical sources  
   - Covers all conditions in training set

4. **Symptom_severity.csv**  
   - Clinical severity weights (1-3 scale)  
   - Enables risk stratification algorithm  
   - 132 symptoms with validated weights

5. **symptom_precaution.csv**  
   - Four-tiered precaution system per disease  
   - Includes self-care and professional advice  
   - Evidence-based recommendations

## Technical Implementation

### Machine Learning Models
- **Primary Classifier**: Decision Tree (97.47% cross-validated accuracy)
- **Secondary Validator**: Support Vector Machine (100% test accuracy)
- **Ensemble Approach**: Combines predictions for robust results

### Core Dependencies
```requirements
python==3.9.13
scikit-learn==1.0.2
pandas==1.4.3
numpy==1.21.5
pyttsx3==2.90
