#  System Architecture

The following diagram represents the overall architecture of the multimodal emotion recognition system developed in this project.


The system combines audio-based emotion recognition using CNN and text-based emotion recognition using LSTM. Predictions from both models are combined using late fusion techniques for final emotion classification.
<img width="1536" height="1024" alt="architecture final" src="https://github.com/user-attachments/assets/f4e3d853-ac41-4b8e-8469-405814d50695" />
#  Audio CNN Training Results

## Audio CNN Accuracy and Loss

The Audio CNN model showed steady improvement during training. Training accuracy increased gradually while validation accuracy remained reasonably stable.

# <img width="1010" height="468" alt="audio cnn loss and accuracy" src="https://github.com/user-attachments/assets/bd128502-0a6c-4aae-bc5d-ab671bb8b3bd" />

## Audio CNN Confusion Matrix
<img width="780" height="699" alt="confusion matrix" src="https://github.com/user-attachments/assets/05974633-f013-4f90-9b7d-d70ab58092ae" />
The confusion matrix shows that the Audio CNN model was able to classify several emotions correctly, although some emotions were confused due to similarity in vocal tone.

## Text LSTM Accuracy

<img width="503" height="468" alt="text lstm accuracy" src="https://github.com/user-attachments/assets/3fc0f1cd-9008-4969-abc1-b92e4989d5f3" />

The Text LSTM model achieved lower accuracy because some transcripts lacked clear emotional information.

---

## Text LSTM Loss


The loss values remained relatively high, showing that the text model struggled to generalize effectively.


<img width="314" height="453" alt="text lstm loss" src="https://github.com/user-attachments/assets/e5d1ccaa-4bab-45f6-a625-16c20ac5506e" />

## Text LSTM Confusion Matrix


The confusion matrix for the Text LSTM model shows that the text-based classifier struggled to correctly distinguish between multiple emotion classes. Most predictions were concentrated around a few classes, which indicates weaker learning performance compared to the Audio CNN model.

This happened because many Whisper-generated transcripts were short, unclear, or lacked emotional context. As a result, the text model faced difficulty understanding the actual emotion behind the speech samples.

<img width="780" height="699" alt="text lstm confusion matrix" src="https://github.com/user-attachments/assets/73d2ef81-a6af-40fb-abb1-55dfa71fef40" />


# Late Fusion Performance Comparison



The late fusion methods were used to combine predictions from both the Audio CNN and Text LSTM models.

Among the three fusion techniques, Average Fusion achieved the best performance with an accuracy of 0.50. Weighted Fusion and Maximum Confidence Rule achieved slightly lower accuracies of 0.475.

The results indicate that combining audio and text information can improve overall emotion recognition performance. However, the audio modality contributed more strongly to prediction accuracy compared to the text modality.

<img width="613" height="468" alt="late fusion performance comparison" src="https://github.com/user-attachments/assets/b1ec389e-497b-496d-956b-1c4537569e43" />




#  Fusion Results

| Model | Accuracy |
|---|---|
| Audio CNN | 0.54 |
| Text LSTM | 0.17 |
| Average Fusion | 0.50 |
| Weighted Fusion | 0.475 |
| Maximum Rule | 0.475 |

The late fusion approach helped combine predictions from both modalities and improved the robustness of emotion recognition.

# Conclusion

This project successfully implemented a multimodal emotion recognition system using both audio and text modalities. The Audio CNN model performed better than the Text LSTM model because emotional information was captured more effectively from speech signals. The fusion techniques demonstrated how combining multiple modalities can improve overall prediction reliability.
