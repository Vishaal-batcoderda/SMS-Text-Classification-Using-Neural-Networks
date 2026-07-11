# SMS Text Classification Using Neural Networks

This project is part of the **freeCodeCamp Machine Learning with Python certification**.

The objective is to build a neural network that can classify SMS messages as either **spam** or **ham (not spam)**. Throughout this project, I learned how textual data is preprocessed before being fed into a deep learning model and how recurrent neural networks can be used for text classification.

The project was developed and tested using **Google Colab**.

---

## Project Overview

This project uses an **LSTM-based Neural Network** to classify SMS messages into two categories:

- **Spam**
- **Ham (Legitimate Message)**

The complete workflow includes:

- Loading and preprocessing SMS data
- Converting labels into numerical values
- Tokenizing text messages
- Padding sequences to a fixed length
- Building an LSTM model using TensorFlow/Keras
- Training and validating the model
- Predicting whether unseen messages are spam or ham

---

## Dataset

The dataset is provided by **freeCodeCamp** and contains two files:

- `train-data.tsv`
- `valid-data.tsv`

Each message contains:

- **Label**
  - Ham
  - Spam
- **SMS Message**

---

## What I Did

### 1. Loaded the Dataset

Loaded the training and validation datasets using Pandas.

---

### 2. Encoded the Labels

Converted:

- `ham → 0`
- `spam → 1`

so the model could perform binary classification.

---

### 3. Tokenized the Text

Used Keras' `Tokenizer` to convert words into numerical tokens.

An **Out-of-Vocabulary (OOV)** token was also added so the model can handle words that were not seen during training.

---

### 4. Padded the Sequences

Since every SMS has a different length, all sequences were padded to a fixed length before training.

---

### 5. Built the Neural Network

The model consists of:

- Embedding Layer
- LSTM Layer
- Dense Output Layer with Sigmoid Activation

The model was compiled using:

- **Optimizer:** RMSprop
- **Loss:** Binary Crossentropy
- **Metric:** Accuracy

---

### 6. Trained the Model

The model was trained on the SMS dataset while using a validation split to monitor its performance.

---

### 7. Predicted New Messages

Implemented a custom `predict_message()` function that:

- preprocesses a new SMS
- converts it into tokens
- pads the sequence
- predicts whether the message is spam or ham
- returns both the prediction probability and predicted label

---

## Model Architecture

```
Embedding Layer
        ↓
LSTM Layer
        ↓
Dense (Sigmoid)
```

This architecture allows the model to capture contextual information within SMS messages before making a binary prediction.

---

## Technologies Used

- Python
- TensorFlow 2.x
- Keras
- Pandas
- NumPy
- Google Colab

---

## How to Run This Project

This project was developed and tested using **Google Colab**.

### Steps

1. Open the notebook in Google Colab.
2. Run the cells from top to bottom.
3. The SMS dataset will be downloaded automatically.
4. The model will train on the dataset.
5. Use the `predict_message()` function to classify new SMS messages.

No additional setup is required when using Google Colab.

---

## Results

- Successfully classifies SMS messages as spam or ham.
- Passes the freeCodeCamp project requirements.
- Predicts unseen messages using the trained LSTM model.

---

## What I Learned

This project helped me understand:

- Text preprocessing for NLP
- Tokenization
- Sequence Padding
- Word Embeddings
- LSTM Networks
- Binary Text Classification
- Working with textual datasets in TensorFlow/Keras

More importantly, it gave me a better understanding of how neural networks process language compared to traditional machine learning models.

---

## Future Improvements

Some ideas I'd like to explore next:

- Experiment with Bidirectional LSTMs
- Try GRU layers
- Use pretrained word embeddings such as GloVe
- Fine-tune sequence length and vocabulary size
- Compare performance with Transformer-based models

---

## Acknowledgements

This project is part of the **freeCodeCamp Machine Learning with Python Certification** and uses the dataset provided as part of the challenge.

The implementation and experimentation in this repository reflect my own understanding and learning throughout the project.
