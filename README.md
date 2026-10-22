# AgroConnect Implementation Details : 
- Completed with 60 % of development for the Project
Based on Flutter for cross-platform  (Web and Android)

# Features :
- Analyze Image Using Pre-Trained CNN Model
- Using Pre-defined Prompt to qeury RAG Model for Response
- Generating Context-Aware Reponses using LLM GEMMA 
- Mutli-Lingual integration for broader accessibility


# Frontend : Android
<table>
  <tr>
    <td><img src="https://github.com/user-attachments/assets/717b233b-062e-430a-b9d3-981c186acf73" alt="Image 1" /></td>
    <td><img src="https://github.com/user-attachments/assets/e70b6ab2-ce07-41fa-9f34-535ad9071672" alt="Image 2" /></td>
    <td><img src="https://github.com/user-attachments/assets/3da01ddb-2c61-44fb-b771-7fb6a159e66c" alt="Image 3" /></td>
  </tr>
  <tr>
    <td><img src="https://github.com/user-attachments/assets/066f6cf5-efe6-49ae-923d-5372ba0c8032" alt="Image 4" /></td>
    <td><img src="https://github.com/user-attachments/assets/13d9ae42-4f82-4df6-bd6e-74e4ea827c12" alt="Image 6" /></td>
    <td><img src="https://github.com/user-attachments/assets/f03c8635-302d-4183-9e17-069889d3b58e" alt="Image 5" /></td>
  
  </tr>
</table>

# Backend : 

## Dataset 

### Prepared and Pre-processed the Images of the Crop Diseases to create dataset of 450 + Crop diseases and Pest across India.
#### Data Sources :
-  https://agritech.tnau.ac.in/crop_protection/crop_prot.html
-  https://plantix.net/en/library/plant-diseases/
  
### Collected and Embbeded Crop Mangement and Disease Information Documents for causes symptoms and treatments.
#### Data Sources :
-  https://icar.org.in/
-  https://dare.gov.in/en
-  https://ppqs.gov.in/

## Models

### Crop Disease  Notebook: Shows the output of predicted disease using CNN Model
- Loads each image from your dataset.
- Extracts the feature embeddings using ResNet50.
- Stores the image path, class (disease name), and corresponding feature vector in features_db
- Feature Extraction: The uploaded image's features are extracted using the pretrained ResNet50 model.
- Cosine Similarity: Each uploaded image is compared with the stored embeddings using cosine similarity. The image with the highest similarity score is considered the best match.
- Disease Prediction: The disease class associated with the most similar image is returned as the predicted disease.
- Fine-tuning the Pretrained Model: After initial testing, fine-tuning the ResNet50 model with dataset to improve the feature extraction for crop disease images.
  
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1Ofhbm7w5_ieNhxDtnmfKlPlw8ZnU7sO-?usp=sharing)


### RAG  Notebook: Shows the output for the treatment and causes of the detected disease
- Load the Crop disease management and treatment information pdfs from the directory and create chunks of them.
- Chunks are converted into embbedings using SENTENCE-BERT Model. 
- Embeddings are Stored in Index.
- Semantic Search is Carried with respective to query defined for Context Retrival.
- LLM generates Context-Aware Answers accordingly to the context and prompt. GEMMA 2-B

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1V5oEq-q5Ypiri3eCXti7sOdwXQVyHoQB)




