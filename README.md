# ARPA-paraphrase-corpus

We provide a paraphrase detection model for Armenian sentences which obtains state-of-the-art result.

To train a model for Armenian language it was created paraphrase detection corpus, which did not exist before․ To create the dataset [Hetq](https://hetq.am/) and [Panarmenian](http://www.panarmenian.net/) news websites articles from the last 10 years were taken. In the initial step, the pairs of paraphrase sentences were obtained by comparing the sentences of the taken articles with each other and were selected, the sentences whose:

1. Overlap coefficient >= 0.5.
2. levenshtein distance <= 50.
3. The number of words in a sentence is greater than 6 and less than 22.

At the next step the selected sentences were translated from Armenian to English and vise versa. After which the obtained sentences pairs were labeled by linguists.

|number of examples|all|strict paraphrases|non-paraphrases|loose paraphrases|
|  :---: |     :---:    | :---:  |          :---:          | :---:  |
|Train   | 4233         |1339   |2683               | 211 |
|Test    | 1682         |1021   |448                  | 213 |

The created test set was translated to Russian and English to test the results on Paraphraser.ru Train and [MRPC](https://www.microsoft.com/en-us/download/details.aspx?id=52398) Train. Also Paraphraser.ru and MRPC train sets were translated into Armenian.

|Models Results|   F1   |  Acc.     |
|  :---: |     :---:    |     :---:    |
|multilingual BERT trained on Paraphraser.ru Train data transleted into Armenian and tested on our test data | 83.81  | 77.09  | 
|multilingual BERT trained on MRPC Train data transleted into Armenian and tested on our test data   | 80.07        | 69.87 | 
|multilingual BERT trained on translated MRPC, Paraphraser.ru, and our Train data and tested on our test data | 84 |77.6  |
|RUBERT tested on our test data translated into Russian| 83.73         | 76.45  | 
|BERT trained on MRPC Train data and tested on our test data translated into English | 77.96  |  65.69     | 
|multilingual BERT trained on our Train data and tested on our test data (ARPA)| 84.27|  78.06|

ARPA model is available for use, and can be downloaded from this [Drive.](https://drive.google.com/uc?id=14owW5kkZ1JiNa6P-676e-QIj8m8i5e_8)
