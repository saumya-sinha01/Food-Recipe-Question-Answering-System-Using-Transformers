# Food-Recipe-Question-Answering-System-Using-ransformers
RecipeQA Dataset source - https://hucvl.github.io/recipeqa/

Original source datasets from RecipeQA have been downloaded and can be accessed from our shared folder https://drive.google.com/drive/folders/1oWazhCfs2S2XAKmf5RcbRkkKFTqpsfMq?usp=share_link

Fine tuning Generative Question Answering task learnt from Hugging Face course: https://huggingface.co/learn/nlp-course/chapter7/7?fw=pt
# Files
* preprocessing.ipynb: Contains the Preprocessing class responsible for preprocessing and combining the body and delete unnecessary attributes: videos, images, id.
* QA_Saumya_DeBERTa_Base|Albert|DistilBert.ipynb: Contains the QADataset class for downloading and converting the question answering dataset from original dataset,                                                     Model class to perform fine-tuning on different pre-trained model and HyperParameter optimization class to perform                                                    hyper-parameter optimization.
# Classes
Datasets
* Download data from Google Drive and convert data to desired format for Extractive Question Answering
Methods:
* filter_data_from_original(): create two dataframes, textual and visual from textual_cloze and visual_coherence
* combine_steps(): combine all step titles in the recipe set
* combine_textual_visual_df(): merge and clean textual and visual dataframe created
* generate_questions(): create questions for the dataset
* generate_full_instruction(): create full context/instruction for each recipe
* generate_answer_and_index(): create spanned answer and answer start index
 *make_final_data(): make the final data (apply for train, test, and validation set)
Processing
Methods:
* make_dataset(): convert dataframes into DatasetDict structure to easier access train and val set
* tokenizer(): call instance of tokenizer by given pretrained model checkpoint
* preprocess_training(): Preprocesses the training instances by tokenizing the questions and context, and generating start and end positions for the answer spans. Returns the preprocessed inputs.
* preprocess_validation(): Preprocesses the validation instances by tokenizing the questions and context, and modifying the offset mapping to handle tokenization differences between training and validation examples. Returns the preprocessed inputs.
* preprocessed_train(): Apply preprocess_training() function to the whole training set and return results
* preprocessed_val(): Apply preprocess_validation() function to the whole validation set and return results
* train_dataloader(): Creates a PyTorch DataLoader for the preprocessed training dataset. Returns the training DataLoader.
* eval_dataloader(): Creates a PyTorch DataLoader for the preprocessed validation dataset. Returns the validation DataLoader.
Model
Methods:
* call_model(): Loads the pre-trained question answering model.
* prepare_fine_tuning(): Prepares the model, optimizer, and data loaders for fine-tuning.
* train(): Performs the training loop.
* evaluate(): Performs the evaluation on the validation set.
* fine_tune(): Executes the fine-tuning process.
HPO
Methods:
* hyperparameter_opimization(): Optimizes the hyper-parameters.


