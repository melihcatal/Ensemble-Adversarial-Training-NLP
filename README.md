# Does Ensemble Adversarial Training Improve the Robustness of NLP Models?

This project investigates the robustness of NLP models under adversarial attacks, specifically focusing on the effects of ensemble adversarial training.

## **Overview**

Adversarial attacks have been an area of concern in machine learning, more so in NLP, given the linguistic complexities and the ease of crafting adversarial samples. The project explores how ensemble adversarial training can enhance a model's resilience against such attacks while also evaluating its performance on clean data.

## **Key Findings**

**Robustness:** Models trained using ensemble adversarial training displayed a heightened resistance against adversarial attacks.
**Clean Data Accuracy: **Contrary to some findings in the domain of computer vision, our ensemble-trained NLP models exhibited improved performance on clean, untouched data.

## **Data and Model**

Sentiment Analysis binary classification task on the IMDB dataset using custom `CNN`, `RNN` and `LSTM` models have been used for this project.

## **Adversarial Attacks**

TextFooler, a state-of-the-art attack method, has been used to craft adversarial samples. The attack method is based on the premise of semantic similarity between words and uses a combination of word embeddings and paraphrase generation to generate adversarial samples. The original paper can be found [here](https://arxiv.org/pdf/1907.11932.pdf). We have used OpenAttack, an open-source Python library, to implement the attack. The library can be found [here](https://github.com/thunlp/OpenAttack/tree/master) .

An example of an adversarial sample generated using TextFooler is shown below:
![example](https://drive.switch.ch/index.php/s/R6169NAPqFugIdk/download)

The left text is the original sample and the right text is the adversarial sample. The highlighted words are the words that have been replaced by the attack method. With only 7 words changed, the prediction of the model has been flipped from negative to positive.

## **Ensemble Adversarial Training**

The target `LSTM` model was trained using ensemble adversarial training. The ensemble consisted of 3 models, each contributing 1/3rd of the training data. The ensemble was trained using the same adversarial attack method as above.

## **Results**

Ensemble adversarial training improved the robustness of the model against adversarial attacks. It also improved the performance of the model on clean data. The results are summarized below:

![result](https://drive.switch.ch/index.php/s/bz487G3QP3c1RTl/download)
**Model Parameters & Adversarial Data**

The model parameters and adversarial data can be found [here](https://drive.switch.ch/index.php/s/Zc0hXcbMeIBtahh). This data can be used to reproduce the results of the project and skip the training/attack steps.

## **Report**

For a detailed report on the project, please refer to the [report](https://drive.switch.ch/index.php/s/SzHFpdacTBKzpqd)
