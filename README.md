# Introduction
In the development.ipynb, a bert model is fine-tuned to classify Claim-Evidence sentence pairs.
In the demo.ipynb, you can load and test the finished model on any dataset in inference mode.

# Code Structure
The development.ipynb notebook is devided into the following sections:
1) Data Import: where training and validation data are loaded and briefly explored
2) Preprocessing: where data are tokenized then converted to torch datasets then to dataloaders ready for model input
3) Model Design: contains three main functions:
    > create_model(): loads pretrained bert model, wraps it in LoRA, and sets up optimizer and learning_rate_scheduler
    > compute_class_weights(): assigns weights to the two classes to mitigate the class imbalance
    > train_model(): contains training loop, saves model weights of epoch with best f1-score, and returns histories of train/val metrics
4) Model Development: where hyperparameters are defined and model is fine-tuned by exploring different hp settings
5) Model Evaluation: loads best model and evaluates it on development set

The structure of demo.ipynb is similar with the following sections: Data Import, Model Load, Preprocessing, and Prediction

# How to run
1. Open the notebook in google collab (if you're not using collab, comment out 'drive.mount()' command from first cell of notebook).
2. Edit the 'path' variable in the first cell of notebook and set it to where your files are. 
3. Make sure the notebook is in the same directory as your files
4. If you're in training mode, make sure the your train and development files are named 'train.csv' and 'dev.csv' respectively.
5. If you're in inference mode, download the model from the link provided and make sure your test file is named: 'test.csv'.
6. Run all cells in the notebook.

# Sources used
During the development of the model, 3 sources were used:
- Coursework 2 of COMP 34711 for to build the foundation of the bert tokenization and training structure
- Huggingface for support in sentence pair tokenization, the implementation of peft and quantization
- Chathpt for for support in creating evaluation helper methods + debugging

# Model Link
The link to the fully developed model is here: https://drive.google.com/file/d/16VMWvlhGyGHv4CLLmL4ZmkcFbI0TjAcd/view?usp=sharing
