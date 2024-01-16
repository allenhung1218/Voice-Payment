# Voice-Payment
Machine Learning Final Project

為什麼機器學習工程師不喜歡訓練模型？
因為他們訓練到餓了，但模型還是沒學會做三明治QQ

---

### **How to run our code:**

0. **Run all instrcution:**
    For some simple instruction of building the model and checking results, we can just run the all code cells excepts the `Method 2 : use dataset to train model` cell and `Prediction and Output` cell, and the result will be shown in the last cell `Trained Model Performance Monitoring`.

1. **Import Libraries:**
   The script starts by importing various Python libraries, including `NumPy`, `Pandas`, `librosa`, `soundfile`, `sounddevice`, `time`, `os`, `re`, `math`, `matplotlib`, `speech_recognition`, `TensorFlow's Keras`, `pydub`, and `word2number`. 
   
   (It may need some installations.)

2. **Global Variables:**
   It defines global variables such as `Speakers`, `NumOfSpeakers`, `NumOfDataOfSpeaker`, `AudioFiles`, `DataFrame`, and several others.

3. **Read Files:**
   The `ReadFile` function reads audio files from a specified dataset directory, filters files based on their duration, loads them using librosa, and stores the resulting audio data and sample rate in the `AudioFiles` list.

4. **Extract Features:**
   It defines functions for extracting different audio features, including Mel spectrograms (`Melspectrogram`), MFCC coefficients (`MFCC`), zero-crossing rate (`Zero_crossing_rate`), and spectral band energy (`spectral_band_energy`).

5. **Build DataFrame:**
   The `BuildDataFrame` function populates a Pandas DataFrame (`DataFrame`) with extracted features and corresponding speaker labels.

6. **Split Data:**
   The `SplitData` function separates the data into training and validation sets for both features (`X`) and labels (`y`).

7. **Model:**
   It defines a class `Model` that handles the creation, compilation, training, and prediction using a neural network model. The model architecture includes different branches for Mel spectrograms, MFCC coefficients, zero-crossing rate, and spectral band energy.

8. **Training:**
   An instance of the `Model` class is created, and the model is defined, compiled, and trained using the training data. In this part, we can use `Method 1 : model.load_model` to load trained model : `Voice_Payment_final_version2.h5`.
    
    (`Method 2` is for training a new version of model.)

9. **Prediction and Output:**
    The script predicts the speaker using the trained model and prints a greeting for the identified speaker. It then processes the transcribed request, searching for the word "**transfer**" and printing a success message if found. It will start recording in your Visual Studio Code, but it requires speakers in our dataset to get a correct result. To show our results and performance, we can use the next code cell.

10. **Trained Model Performance Monitoring:**
    After training the model, a function evaluates its performance by predicting speakers for pre-recorded voice files of six members. The results display the top five predicted speakers for each member, with the correct answer highlighted in red. This evaluation helps assess how well the model generalizes to different voices.