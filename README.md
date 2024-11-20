# Product-Attribute-Recognition-Meesho-Data-Challenge
# How To Run the Code :
#Setup Instructions:
For Approach 1:
For the 1st approach which uses the zero-shot classification models only need to set up the environment of Tesla-4 GPU of atleast 15-20 GB's of RAM then install the required below libraries:

!pip install pandas numpy torch torchvision torchaudio transformers Pillow scikit-learn tqdm
Then directly run the code in the jupyter notebook , it contains the Preprocessing , Training and the Inference Code all in one notebook only need to setup the dataset path correctly. 
For dataset use whole data Train.csv and directory of the train_images and for inference as well use test.csv and the image directory.
Then run the it will automatically download the model from Hugging Face without any Credentials requires , make sure to connect the notebook to the internet.
To run the saved model or checkpoints someone can use this link to download the '.pth' file which is saved model only need to load the model or place the path in the inference code which is also inside the jupyter notebook.

The Drive Links for this Models: https://drive.google.com/drive/folders/1qxOhage3zOk7gcbP1uWinTcpCmGRJIyB?usp=share_link


For Approach 2 :
For the 2nd Approach which is nothing but the finetuning of multi-modal LLM which is Qwen2VL-2B finetuned using LLama Factory well the notebook contains all the essential libraries to download only need to run  the jupyter notebook provided. 
Imprtant points:
1.  I had trained or Finetuned this Category Wise so it is better to Finetune the model Category Wise and take inference as well Category Wise to make it less time consuming and in less Computational Resources.
2.  I provided the codes only for the Category 1 which is Men T-shirts so to replicate it for the Categories only thing need to done is Change the path of Category file which also provided in the Folder name 'all_meesho_catwise' change the path of the file after downloading it.
3. Now change the output directories save the file in the name as per you in JSON format for ex : cat2.json , cat3.json .
4. Then use the same name in the dataset in the args if used cat4.json at the time of ShareGPT format Dataset building the name it as cat4 in the dataset in the args.
5. Now only change the saved model and final directories accordingly and start the training.




For Inference :
For Inference of the model the code is provided only for Category 1 as it is same for all the other categories only need to change the saved model path and selection of the category from the test_df.

Change here the model id for other Categories :


<img width="848" alt="Screenshot 2024-11-20 at 8 43 20 PM" src="https://github.com/user-attachments/assets/5cdc9f74-02d6-40a6-a948-239734bc94b9">


Change here the Category name for other Categories:


<img width="618" alt="Screenshot 2024-11-20 at 8 43 29 PM" src="https://github.com/user-attachments/assets/12835611-4471-4d21-8dec-f6e2c2b5d7d6">

The Saved Paths can be found in this drive link : https://drive.google.com/drive/folders/1ASStcQogXGdPPIStAhgQLgyZfS43oeLp?usp=share_link
Unzip the saved path then in the inference code of Cat1 change the Category name and load the model then it gives the Submission file for the particular Category then Finally it is needed to Concatenate all the Prediction Files and submit.

Futute Work :
To Speed up the inference anyone can use Flash_attention_2 as it is now only supported by Ampere GPU (A-100) and T-4(Tesla GPU) are not supported yet someone with A-100 GPU can try Flash Attention2 also I tried to Quantized the dataset with AWQ and AutoGPTQ but  I am getting wrong predictions may be i did in wrong but in future to speed up the Inference time and running in Less Computational Resources someone can definately try the Quantisation of the saved Finetuned model.










