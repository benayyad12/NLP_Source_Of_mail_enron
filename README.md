# NLP_Source_Of_mail_enron

<img src="https://0901.static.prezi.com/preview/v2/2a4mgil4d6kupwfmp7trbkgllt6jc3sachvcdoaizecfr3dnitcq_3_0.png" style="width:800px;height:300px;">

__Dataset Enron corporation :__


- __[Enron Dataset](http://www.cs.cmu.edu/~enron/)__ - 
(about 1.7Gb, tarred and gzipped)
  

## NLP :
---

#  Natural Language Processing : 

   __What is NLP ?__
     - NLP is a field in machine learning with the ability of a computer to understand, analyze, manipulate, and potentially generate human language.
     
     
  <img src="https://deeplearninganalytics.org/wp-content/uploads/2019/04/nlp.png" style="width:800px;height:300px;">
  
## Tokenazition
   __What is Tokenazition ?__
   
   <img src="https://miro.medium.com/max/1400/1*UhfwmhMN9sdfcWIbO5_tGg.jpeg" style="width:800px;height:300px;">

## Lemmatization
   __What is Lemmatization ?__
   
   <img src="https://res.cloudinary.com/dyd911kmh/image/upload/f_auto,q_auto:best/v1539984207/stemminglemmatization_n8bmou.jpg" style="width:800px;height:500px;">

   

## Removing StopWords
   __What is StopWords ?__
   In english stopwords are : 
   
   
   ['i', 'me', 'my', 'myself', 'we', 'our', 'ours', 'ourselves', 'you', "you're", "you've", "you'll", "you'd", 'your', 'yours', 'yourself', 'yourselves', 'he', 'him', 'his', 'himself', 'she', "she's", 'her', 'hers', 'herself', 'it', "it's", 'its', 'itself', 'they', 'them', 'their', 'theirs', 'themselves', 'what', 'which', 'who', 'whom', 'this', 'that', "that'll", 'these', 'those', 'am', 'is', 'are', 'was', 'were', 'be', 'been', 'being', 'have', 'has', 'had', 'having', 'do', 'does', 'did', 'doing', 'a', 'an', 'the', 'and', 'but', 'if', 'or', 'because', 'as', 'until', 'while', 'of', 'at', 'by', 'for', 'with', 'about', 'against', 'between', 'into', 'through', 'during', 'before', 'after', 'above', 'below', 'to', 'from', 'up', 'down', 'in', 'out', 'on', 'off', 'over', 'under', 'again', 'further', 'then', 'once', 'here', 'there', 'when', 'where', 'why', 'how', 'all', 'any', 'both', 'each', 'few', 'more', 'most', 'other', 'some', 'such', 'no', 'nor', 'not', 'only', 'own', 'same', 'so', 'than', 'too', 'very', 's', 't', 'can', 'will', 'just', 'don', "don't", 'should', "should've", 'now', 'd', 'll', 'm', 'o', 're', 've', 'y', 'ain', 'aren', "aren't", 'couldn', "couldn't", 'didn', "didn't", 'doesn', "doesn't", 'hadn', "hadn't", 'hasn', "hasn't", 'haven', "haven't", 'isn', "isn't", 'ma', 'mightn', "mightn't", 'mustn', "mustn't", 'needn', "needn't", 'shan', "shan't", 'shouldn', "shouldn't", 'wasn', "wasn't", 'weren', "weren't", 'won', "won't", 'wouldn', "wouldn't"]
   
   
   __Example__
   
   <img src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/Stop-word-removal-using-NLTK.png" style="width:800px;height:300px;">


# Text Vectorazition : 
  __What is text vectorazition ?__

```python
# change input text to vectors : 
from sklearn.feature_extraction.text import TfidfVectorizer
```


```python
feature_extraction = TfidfVectorizer(min_df=1,stop_words='english')
x_train_vec = feature_extraction.fit_transform(x_train)
x_test_vec  = feature_extraction.fit_transform(x_test)
```







## Gradio for Interface :
   __Instal gradio :__
   
```python
!pip install -q gradio
```
  __Code of interface :___

```python
import gradio as gr
body=['burlington ha bid default lost creek fuel purchase october cig plus send reminder email future bid due th month next business day th fall weekend scott sitter bear paw energy crestone energy venture l l c ph fax ssitter enron com']
join_body=' '.join(body)
def sender(join_body):
    
    Body_vec = feature_extraction.transform(body)
    Result = model.predict(Body_vec)
    return(Result)


iface = gr.Interface(fn=sender, inputs="text", outputs="text")
iface.launch()
```
    
    






