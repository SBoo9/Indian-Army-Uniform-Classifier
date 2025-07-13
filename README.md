# Indian-Army-Uniform-Classifier
Classifying Indian Army officers into CRPF BSF and JnK Police based upon there uniform into the following cateogeries:
- BSF
- CRPF
- J&K Police

# Dataset
For this I have used the following datasets "my_datasets.zip". It consistes of the following folders
  - dataset
  - cropped_dataset
  - train
  - val
  - test
  - Dataset Link: https://drive.google.com/file/d/1AygR_j0jceeVO85dmVs0-BhiQjvvZglq/view?usp=sharing
 
The dataset folder is our base dataset file which we have used for our application. It consists of 3 class folders each containing their respective images used in our project, this is then passed through our code to get cropped_dataset which crops each indivisual officer into a seperate image which is further utilised in our project. 

# Model
This project uses a transfer learning approach with a pretrained ResNet18 model from PyTorch’s torchvision.models. The model is fine-tuned to classify soldier images based on uniform into three categories: BSF, CRPF, and Jammu & Kashmir Police.
- Base Model: ResNet18 pretrained on ImageNet
- Final Layer: Replaced the fully connected (FC) layer to output 3 classes
- Loss Function: CrossEntropyLoss
- Optimizer: Adam with a learning rate of 0.0001
- Epochs: Trained for 15 epochs
- Device: Automatically uses GPU (cuda) if available, else falls back to CPU

# Interface
A simple Gradio-powered web UI is integrated to allow easy testing of the model. Users can upload an image of a soldier, and the application will classify the uniform as one of the classes

# Evaluation Metrics
The trained model was evaluated on separate validation and test sets.
- Validation Accuracy: 89.00%
- Test Accuracy: 78.12%

Despite high validation accuracy, the drop in test accuracy indicates a potential distribution shift or overfitting, particularly visible in BSF class performance.

# Key Improvements in future
- Addition of edge case scenarios: Due to lack of time currently proper data argumentation has not been set up, adding it up, generating more data for each case may result in a better performing model.
- Utilizing mobilenet or Yolo further for classification instead of just detection.
- Better deployment options with better UI addition
