

Smart Sentiment Analysis System
==================================

An advanced, real-world-ready Sentiment Analysis system that uses deep learning (LSTM), NLP pipelines, and a Flask web interface. Supports custom .csv uploads, real-time text analysis, and sentiment visualization.

Features
-----------

*  **Data Preprocessing** with stopword removal, stemming, punctuation cleaning
    
*   **LSTM Model** trained on labeled dataset
    
*    Model saved in .h5 format and loaded dynamically
    
*    **Accuracy & Loss Plotting**
    
*    Predicts sentiment (Positive / Negative) for:
    
    *   Real-time user input
        
    *   Uploaded .csv files (with text column)
        
*    Interactive **Flask Web App**
    
*    Logs predictions with timestamp
    
*    Modular file structure (easy to extend)
    
*    Generalized for **any .csv** with a text column



## Code Hierarchy

```
- config.py # good practice to centralize hyper parameters

- preprocess.py # Step 1, preprocess, store numpy/meta 'cache' at ./preprocess/

- train_segmentation.py # Step 2, segmentation with UNet Model
- model_UNet.py # UNet model definition

- train_classificaion.py # Step 3, classificaiton with VGG/Inception/ResNet/DenseNet
- model_VGG.py # VGG model definition
- model_Inception.py # Inception model definition
- model_ResNet.py # ResNet model definition
- model_DenseNet.py # DenseNet model definition

- generators.py # generator for segmentation & classificaiton models
- visual_utils.py # 3D visual tools

- dataset/ # dataset, changed in config.py
- preprocess/ # 'cache' preprocessed numpy/meta data, changed in config.py

- train_ipynbs # training process notebooks
```
    
Installation
---------------

   
``` bash
git clone https://github.com/your-username/sentiment_project.git  
cd sentiment_project  

# Create virtual environment  
python -m venv venv  
source venv/bin/activate  # On Windows: venv\Scripts\activate  

# Install dependencies  
pip install -r requirements.txt   



``` 


Model Training
-----------------

You can train your own model on any labeled dataset.

### Step 1: Prepare your CSV

Your dataset should contain:

*   A text column for input
    
*   A label column with 0 (negative) or 1 (positive)
    

Place it in the dataset/ folder and name it sentiment.csv.

### Step 2: Train the model

```bash
python utils/train_model.py   
```

*   Saves model as:/Users/amanagarwal/Desktop/DESKTOP/PLACEMENT/Projects/sentiment\_project/model/sentiment\_model.h5
    

 Run the Web App
------------------

```bash
python app.py 
```  

*   Open browser at: [http://127.0.0.1:5000](http://127.0.0.1:5000/)
    

How It Works
---------------

*   Load trained model (.h5)
    
*   Load tokenizer and padding settings
    
*   Accept input:
    
    *   Text from form input
        
    *   .csv with a column named text
        
*   Preprocess the text
    
*   Predict with LSTM
    
*   Display result: Positive or Negative
    

Sample Data Format
---------------------
```bash
text,label  
"I love this product, it's amazing!",1  
"This is terrible. Worst experience ever.",0  "Decent, but could be better.",1  
"Horrible, would not recommend.",0 
```

 Training Visualization
-------------------------

Training metrics are automatically plotted and saved.

 Improvements and Future Features
-----------------------------------

*    Add **neutral** sentiment detection
    
*    Support for **multilingual sentiment** via langdetect + translation
    
*    More advanced **transformer-based models** (e.g., BERT)
    
*    Add **comment toxicity analysis**
    
*    Upload and download predictions in Excel
    
*    Add API endpoints for backend integration
    

 Requirements
---------------
```bash
tensorflow  
keras  
flask  
nltk  
pandas  
scikit-learn  
matplotlib   
```

Install via:
```bash
pip install -r requirements.txt   
```



License
----------

MIT License © 2025 Aman Agarwal