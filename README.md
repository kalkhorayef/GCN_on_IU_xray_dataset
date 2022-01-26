# Applying GCN-LSTM Model with Knowledge Graph on IU Chest Xray Dataset for Report Generation Task
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/15o7Oo0bZrM0pmkriuotNbymNWs79PhZG?usp=sharing)

This is for training a preconstructed knowledge graph for a report generation task. 
The work is an adaptation from the code base of the AAAI 2020 paper "When Report Generation Meets Knowledge Graph".
See paper at: https://arxiv.org/abs/2002.08277
and https://paperswithcode.com/paper/when-radiology-report-generation-meets

The Indiana University X-ray dataset is used to test the model, a download link for the preprocessed version is available in the colab notebook.

In the colab notebook "IU Knowledge graph v1.7" run the first four cells to download the editted codebase and the IU dataset.
If you want to skip the first section of training and start with an already trained gcn classifier, use the codebase from the cell:
https://colab.research.google.com/drive/1_LbnSxa2chJbylANAcBhWXOsO4g0EDxw#scrollTo=KIml1w0xaGdV&line=1&uniqifier=1 

To train the model:
first we need to train the preconstructed knowledge graph on the classification task of disease labels when we run "!python train_gcnclassifier_mimic.py" in the cell:
https://colab.research.google.com/drive/15o7Oo0bZrM0pmkriuotNbymNWs79PhZG#scrollTo=Ah-9tx2bYWlB&line=1&uniqifier=1


Afterwards we train the already classification trained knowledge graph for report generation using LSTM using the cell afterwards:
https://colab.research.google.com/drive/1_LbnSxa2chJbylANAcBhWXOsO4g0EDxw#scrollTo=pzdBOWnOaHsV&line=1&uniqifier=1
The code for the report generation task can be found in sent_gcn.py



Afterwards we run the tensorboard command below to view results:
%load_ext tensorboard
%tensorboard --logdir '/content/ReportGenerationMeetsGraph14labels_v2/workspace/biview/logs'
