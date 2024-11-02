# Digit Recognition System

This project implements a digit recognition system from scratch that processes audio files to identify spoken digits from 0 to 9. Utilizing a custom recurrent neural network (RNN) architecture, the model leverages digital signal processing techniques to transform audio signals into features suitable for classification.

## Dataset Overview

The dataset consists of **120 audio files**, categorized into:

- **Training Dataset**: 96 audio files (80% of the total)
- **Testing Dataset**: 24 audio files (20% of the total)
- **Audio File Format**: WAV
- **Sampling Frequency**: 8 kHz
- **Length per File**: Approximately 1 second
- **Total Features**: 14 (13 Mel Frequency Cepstral Coefficients (MFCCs) + 1 Zero-Crossing Rate (ZCR))
- **Total Classes**: 10 (Digits 0 to 9)

### Digital Signal Processing Parameters

- **Frame Length**: 256 samples (32 ms)
- **Hop Length**: 128 samples (16 ms)
- **Total Frames per File**: 59

This structured approach to framing allows us to efficiently extract features from the audio signals, facilitating better model training and performance.

## Hyperparameters

To achieve optimal results, we fine-tuned the following hyperparameters:

- **Recurrent Layers**: 1
- **Recurrent Activation Function**: tanh
- **Output Activation Function**: Softmax
- **Loss Function**: Categorical Cross Entropy (CCE)
- **Number of Neurons**: 256
- **Sequence Length**: 59
- **Learning Rate**: 0.0005
- **Optimizer**: Adam
- **Epochs**: 50

These parameters were chosen to balance model complexity and performance, ensuring that our system learns effectively without overfitting.

## Performance Results

![Model Architecture](https://firebasestorage.googleapis.com/v0/b/common-e8332.appspot.com/o/cost%20vs%20epochs.png?alt=media&token=69c31118-45f3-4bce-85db-019545ead5a3)

![Model Architecture](https://firebasestorage.googleapis.com/v0/b/common-e8332.appspot.com/o/accuracy_train.png?alt=media&token=e52452d5-ba08-465b-8055-cb99bea8241c)

![Model Architecture](https://firebasestorage.googleapis.com/v0/b/common-e8332.appspot.com/o/accuracy_test.png?alt=media&token=6a157c82-3795-47f5-9493-352f9f12525b)

The model demonstrated impressive results, showcasing its effectiveness in recognizing digits:

- **Training Dataset Accuracy**: 100.00% 
- **Training Dataset Loss (CCE)**: 0.0373 
- **Testing Dataset Accuracy**: 95.83%
- **Testing Dataset Loss (CCE)**: 0.3199

### Confusion Matrix 

![Model Architecture](https://firebasestorage.googleapis.com/v0/b/common-e8332.appspot.com/o/cm_rnn.png?alt=media&token=e3c0cfaf-7d59-4be7-bf59-d14d3fe88f74)

### Classification Report

| Digit | Precision | Recall | F1-Score | Support |
|-------|-----------|--------|----------|---------|
| 0     | 1.00      | 1.00   | 1.00     | 2       |
| 1     | 1.00      | 1.00   | 1.00     | 3       |
| 2     | 1.00      | 1.00   | 1.00     | 3       |
| 3     | 1.00      | 1.00   | 1.00     | 2       |
| 4     | 1.00      | 1.00   | 1.00     | 3       |
| 5     | 1.00      | 1.00   | 1.00     | 2       |
| 6     | 0.67      | 1.00   | 0.80     | 2       |
| 7     | 1.00      | 1.00   | 1.00     | 2       |
| 8     | 1.00      | 0.67   | 0.80     | 3       |
| 9     | 1.00      | 1.00   | 1.00     | 2       |

- **Overall Accuracy**: 96.00%
- **Macro Average Precision**: 0.97
- **Macro Average Recall**: 0.97
- **Macro Average F1-Score**: 0.96

These metrics reflect the model's robustness and its capacity to generalize well to unseen data.

## Conclusion

This Digit Recognition System effectively demonstrates the application of RNNs in audio signal processing and achieved a high level of accuracy on both training and testing datasets.
