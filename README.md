# NLG_Project
## Markov Chains Model

- This code was built in Google Colab so if you would like to replicate this process then please follow this link to the colab file: "https://colab.research.google.com/drive/1xOCWS3-FBKdIrPI1TU1V1D2yrGAna36O?usp=sharing".
-If you do decide to run this on colab, make sure you change the "runtime type" to "GPU" or "TPU" for the best possible experience.
- If you prefer to run this on your own IDE then the ipynb file for the code is provided along with the dataset that we built the model on.
- Please find the datasets used to train the model at this google drive link "https://drive.google.com/drive/folders/1oZCwQFwzhkndHimdmbqG5UISqmgXCm-N?usp=sharing"
- If you want the original websites find them below:
- "http://help.sentiment140.com/home" & "https://www.kaggle.com/datasets/thoughtvector/customer-support-on-twitter"


## Features

- Natural language model built upon Twitter posts
- Ability to easily modify the parameters of Markov
- Evaluation of the AI generated text
- Ability to post your favorite generated text via Twitter.

## Installation

Our NLG model works best with any Python IDE

Install the dependencies below when running the code.
*Disclaimer:* Only install openai if you wish to use their GPT language model.

```bash
!pip install markovify
!pip install transformers
!pip install language_tool_python
!pip install openai
```

For colab environments; you should be able to run this line of code if you have clicked this link "https://drive.google.com/drive/folders/1oZCwQFwzhkndHimdmbqG5UISqmgXCm-N?usp=sharing" and were granted access, but if you come upon any errors then please download the datasets yourself and bring them into the colab session manually. *If this is the case then you do not need to run the line of code below*

```sh
from google.colab import drive
drive.mount('/gdrive')
!ln -s "/gdrive/MyDrive/AI Introduction" "/content/AI Introduction/Datasets"
```
## List of adjustable parameters
Below you are allowed to adjust *state size* to change the amount of n-grams on which the model is trained on.
```bash
model_1 = markovify.NewlineText(train_text, state_size=1)
model_2 = markovify.NewlineText(train_text, state_size=2)
model_3 = markovify.NewlineText(train_text, state_size=3)
```
Below you are allowed to adjust both *tries* and *max_overlap_ratio*. Adjusting *tries* will limit the amount of time the model will try to generate a sentence based on your input seed. Adjusting *max_overlap_ratio* determines how hard the model will work in terms of making sure that there are no overlapping tokens or n_grams.

```bash
sentence_1 = model_1.make_sentence(tries=10000, max_overlap_ratio=0.7)
sentence_2 = model_2.make_sentence(tries=10000, max_overlap_ratio=0.6
sentence_3 = model_3.make_sentence(tries=10000, max_overlap_ratio=0.5)
```

## License

MIT
