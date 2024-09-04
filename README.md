# Model components have been described below: 
*  User Query – model accepts the input as image or text. 
*  Image search and Selection – here the images are searched for the text prompt using the datasets of different APIs. Then, the user can select any image according to their interest. 
*  API- APIs of Wikipedia and OpenImages are used to search the images.
*  Image description - A pre-trained model “clip_prefix_caption”, is used to generate image description. The model can be fine-tune on different datasets for generating relevant descriptions. 
*  Clip_prefix_caption - This CLIP model can generate semantic encodings for each image without additional information because it has previously been trained on a very large number of images. 
*  GPT – It stands for Generative Pre-trained Transformers. These models used deep learning techniques to generate natural language content. Our model uses the GPT2 and GPT3 based model to generate image and text*.
*  Caption Generation – A pre-trained model “GPT Neo” which is a replica of GPT3, is used for generating captions.
*  Sentiment analysis - model used the sentiment analysis technique for finding the relevant image and captions. 
In this, VADER is used to find the polarity score of the unlabeled datasets.
The labeled datasets are passed through the SVM model after creating 	the features vectors using Word2Vec model for finding positive and negative sentences. 
Caption formatting- PIL library is used to format the generated captions over the image. 

# Working of Model
In this model, I have applied sentiment analysis on image and text to create a relevant meme. If the user input is already in the form of an image, it directly creates its text description. Instead of image query, if the input query is in the form of text, then it searches images for the text prompt given by the user. My model uses the APIs of Wikipedia and OpenImages to search the related images. Here, an image description has been generated using a pre-trained model (Clip_prefix_caption).  Then it performs the sentiment analysis on image description to check relevant images. Now, only positive image description passes to the caption generation model to generate the meme captions. As an output, our model gives ten best relevant captions to users. Now, the model has an image and the caption selected by the user.
