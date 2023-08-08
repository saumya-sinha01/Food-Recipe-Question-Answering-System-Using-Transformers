# Food-Recipe-Question-Answering-System-Using-ransformers
RecipeQA Dataset source - https://hucvl.github.io/recipeqa/

Original source datasets from RecipeQA have been downloaded and can be accessed from our shared folder https://drive.google.com/drive/folders/1oWazhCfs2S2XAKmf5RcbRkkKFTqpsfMq?usp=share_link

Fine tuning Generative Question Answering task learnt from Hugging Face course: https://huggingface.co/learn/nlp-course/chapter7/7?fw=pt
# Files
preprocessing.ipynb: Contains the Preprocessing class responsible for preprocessing and combining the body and delete unnecessary attributes: videos, images, id.
QA_Saumya_DeBERTa_Base|Albert|DistilBert.ipynb: Contains the QADataset class for downloading and converting the question answering dataset from original dataset,  Model class to perform fine-tuning on different pre-trained model and HyperParameter optimization class to perform hyper-parameter optimization.


