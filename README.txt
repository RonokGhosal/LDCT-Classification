# Stroke_CT_DLML
1. Download the data from the [Kaggle competition](https://www.kaggle.com/c/rsna-intracranial-hemorrhage-detection/data) and unzip it in the `data` folder.
The data folder structure should look like this:
```/data
        /stage_1_train_images
        /stage_1_test_images
        /stage_1_train.csv
        /stage_1_sample_submission.csv
```
2. Run the Stroke_CT_DLML.ipynb notebook to train the model
Make sure the following two lines are uncommented in the notebook, for the first run: 
#save_and_resize(filenames=sample_files, load_dir=BASE_PATH + TRAIN_DIR)
#save_and_resize(filenames=sample_files_test, load_dir=BASE_PATH + TEST_DIR)
They will save the resized images to the `data` folder, by creating a temp and a working folder.

About the code: 
The code has third portions: 
1. The first part is the data preprocessing[1], where the images are resized and saved to the `data` folder.
2. The second part is the deep learning model[1], which is a simple CNN model with a custom loss function. The model is trained on the resized images and generate features for the supervised learning model.
3. The third part is the suppervisd learning model, which applied NN, SVC, GradientBoosting, and AdaBoost to conduct the classification based on the feature extraction from depp leaning models in the portion#2.


Reference:
[1]M. Mujeeb,Kaggle Code Sharing for RSNA-intracranial-hemorrhage-detection
 https://www.kaggle.com/code/mohmujeeb/rsna-intracranial-hemorrhage-detection