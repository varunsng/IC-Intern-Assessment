
# Gender Recognition from Speech

The aim of this assessment is to identify the speaker's gender and the number of speakers.



# Dataset

This portion of the RAVDESS contains 1440 files: 60 trials per actor x 24 actors = 1440. The RAVDESS contains 24 professional actors (12 female, 12 male), vocalizing two lexically-matched statements in a neutral North American accent. Speech emotions includes calm, happy, sad, angry, fearful, surprise, and disgust expressions. Each expression is produced at two levels of emotional intensity (normal, strong), with an additional neutral expression.

File naming convention
Each of the 1440 files has a unique filename. The filename consists of a 7-part numerical identifier (e.g., 03-01-06-01-02-01-12.wav). These identifiers define the stimulus characteristics



## Filename Identifiers


- Modality (01 = full-AV, 02 = video-only, 03 = audio-only)
- Vocal channel (01 = speech, 02 = song)
- Emotion (01 = neutral, 02 = calm, 03 = happy, 04 = sad, 05 = angry, 06 = fearful, 07 = disgust, 08 = surprised)
- Emotional intensity (01 = normal, 02 = strong). NOTE: There is no strong intensity for the 'neutral' emotion
- Statement (01 = "Kids are talking by the door", 02 = "Dogs are sitting by the door")
- Repetition (01 = 1st repetition, 02 = 2nd repetition)
- Actor (01 to 24. Odd numbered actors are male, even numbered actors are female)


Filename example: 03-01-06-01-02-01-12.wav

- Audio-only (03)
- Speech (01)
- Fearful (06)
- Normal intensity (01)
- Statement "dogs" (02)
- 1st Repetition (01)
- 12th Actor (12)

# Feature Extraction

Feature extraction is very effective in increasing the accuracy and efficiency of machine learning algorithms in emotional speech recognition. The input audio file is reduced to a set of features which represent or summarise the original input. The extracted features are then fed into the neural network to identify the respective emotion.
Here I have used the MFCC for feature extraction.

## Mel-frequency cepstral coefficients (MFCCs)
The Fourier spectrum is obtained by using the FFT on an audio signal. Taking the log of the Fourier spectrum’s magnitude and then taking the spectrum of this log through a cosine transformation allows us to calculate the cepstrum of the signal (ceps is the reverse of spec, called so due to being a non-linear ‘spectrum of a spectrum’). The amplitudes of this resulting cepstrum are the cepstral coefficients. Representing the frequencies in terms of the mel scale (discussed above) instead of a linear scale converts the cepstrum to a mel-frequency cepstrum and the cepstral coefficients to mel-frequency cepstral coefficients (MFCCs). The cepstrum represents the rate of change in the different spectrum bands, and the coefficients are widely used in machine learning algorithms for sound processing.


![App Screenshot](https://user-images.githubusercontent.com/58522706/130082550-8378cb95-f9c0-41bb-a3de-2b765214cad5.jpeg)

# Models Used

- MLP Model
- LSTM Model

# Results

- The accuracy obtained on the test set for MLP model comes out to be 96.53%
- The accuracy obtained on the test set for LSTM model comes out to be 98.61% 

## Accuracy vs epochs plots

## For MLP model
![screenshot](https://github.com/varunsng/IC-Intern-Assessment/blob/main/mlp.png)

## For LSTM model
![screen](https://github.com/varunsng/IC-Intern-Assessment/blob/main/Lstm.png)

# Observations

- We can see that by taking a better model such as LSTM model the accuracy is increased.
- The model was trained for 50 epochs only so accuracy can also be improved by training on more number of epochs
- Using dropouts between layers enhances the accuracy
- The dataset has 1440 files in total so a larger dataset will allow for a better training and testing of the model
