# Custom-Named-Entity-Recognition-Using-spaCy
->Describes how to implement our own Named Entity Recognition using spaCy and how to store the model for future use.

->TRAIN_DATA is the data which is used to train the model. TRAIN_DATA is a list of tuples consisting of entity name and entity position along with text. The format should be as follows.

### [('text'{'entities':[(start_position,end_postion,'Entity_Name')]}).........]


->start_postion,end_postion are positions of keyword that represents entity. 

Example : [('I want to access facebook webpage', {'entities': [(17, 22, 'Application Name')]})]

->TRAIN_DATA is given to nlp.update() function of spaCy to create our own NER model and the model name is saved according. Refer spaCy documentation for further information.

-> You load use your stored model with the following lines:
import spacy
nlp=spacy.load('Model Name')

->And you can use this model to get the entity names.

doc=nlp('Can you provide access for amazon')

print([(X.text, X.label_) for X in doc.ents])

Output: ['amazon','Application Name']
