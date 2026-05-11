# Laboratory Work 4 Activity 1 — Improving CNN Performance Using Regularization, Fine-Tuning, and Advanced Evaluation

# DRIVE LINK
https://drive.google.com/drive/folders/1g-Vgu4Yj6xixsyCDvRQ-L7J9eWEpkQhd?usp=sharing

---

# Activity 1: Evaluation Metrics + Visualization

### Classification Report
<img width="472" height="413" alt="image" src="https://github.com/user-attachments/assets/ea72664e-af66-497d-9516-e20bc361b61c" />



**Description:**
This report shows how well the model classified each plant species using Precision, Recall, and F1-score. It highlights strong results for plants like boston_fern (bostoniensis) with perfect scores and high performance for anthurium_red_champion and snake_plant, while plants such as alocasia and fiddle_leaf_fig had lower scores because they are harder to distinguish from similar species.

---

### 2. Confusion Matrix
<img width="731" height="684" alt="image" src="https://github.com/user-attachments/assets/c0dfda43-a693-4a05-b711-5868a2de238a" />



**Description:**
The matrix provides a visual map of the LW3 Baseline model's errors by plotting actual plant species against the model's predictions. The dark blue diagonal line represents successful matches, such as the high accuracy seen for the ZZ plant. Any values outside that line pinpoint exactly which species are being mistaken for one another, such as the confusion between the Croton Petra and Croton Mammy. This is crucial for identifying if certain plants are visually too similar for the current CNN architecture to distinguish.

---

### 3. (ROC) Curve and Area Under the Curve (AUC) Score
<img width="1008" height="692" alt="image" src="https://github.com/user-attachments/assets/5e9a9f4e-5805-475e-9ab1-37a9c0366d17" />





**Description:**

The ROC curve illustrates the LW3 Baseline model's ability to distinguish each plant species by plotting the true positive rate against the false positive rate. The closer a line hugs the top-left corner, the better the model performs for that class. Most plants scored exceptionally high, with the snake plant, boston fern, and anthurium red champion achieving perfect AUC scores of 1.00. The relatively lower performance of the areca palm (0.91) and fiddle leaf fig (0.92) highlights where the model faces the most difficulty. The overall AUC score of 0.9734 indicates the model is highly reliable at distinguishing between the 20 plant species, even if specific individual predictions occasionally falter.

---

### 4. Precision, Recall, F1-score per Class
<img width="1076" height="415" alt="image" src="https://github.com/user-attachments/assets/e1d14ea1-85ed-49ca-a0dd-a26857c8beb6" />




**Description:**

The bar graph displays the Precision, Recall, and F1-score metrics for all 20 plant species in the baseline model. The Boston fern stands out with perfect scores across all metrics, while species like areca palm, fiddle leaf fig, and philodendron xanadu received the lowest marks, likely due to their visual similarities with other plants in the dataset. In general, the model achieved solid results, as evidenced by an overall Precision of 0.79, Recall of 0.77, and F1-score of 0.77, supported by a high AUC of 0.9734.

---

# Activity 2: Model Interpretability using Gradient-weighted Class Activation Mapping (Grad-CAM) - Visualizing CNN Decisions Using Grad-CAM for Explainable Image Classification


### 5. Grad-CAM Heatmap
<img width="365" height="359" alt="image" src="https://github.com/user-attachments/assets/a79bf2b2-43b4-457c-be6e-516d61d888c9" />



**Description:**
This Grad-CAM heatmap shows where the model focused when predicting croton(mammy). The warm yellow and red areas are what influenced the decision most, but the activation is spread out across the whole image rather than focused on the plant's distinctive colorful leaves, suggesting the model still needs improvement in identifying the most relevant features.

---

### 6. Grad-CAM Overlay
<img width="684" height="369" alt="image" src="https://github.com/user-attachments/assets/b02b1e24-f201-4a41-8a27-58f3f323e8d1" />



**Description:**
The Grad-CAM overlay shows where the model looked when it predicted croton(mammy) with 50.95% confidence. The highlighted regions are spread across the entire plant rather than focused on one specific area, which explains the relatively low confidence score. The model is picking up on the colorful leaf patterns overall but hasn't pinpointed the most defining features yet, suggesting there is still room to improve how the model recognizes this species.

---
### Grad-CAM Interpretation 

**Description:**
Grad-CAM represents the process used by the neural network in deciding how to classify the image by showing the areas of the image that have contributed most to the decision. In this case, the heatmap is not only localized in some areas but covers the entire plant as opposed to concentrating on one unique aspect of croton(mammy), which is the brightly colored and multicolored leaves. This could explain the lower level of confidence at 50.95%.

---

# Activity 3: Model Enhancement and Performance Optimization


### 7. Train Improved Model (using 20 epochs)
<img width="1097" height="668" alt="image" src="https://github.com/user-attachments/assets/57179c9e-4055-4b76-a335-a86718d40009" />
<img width="1102" height="428" alt="image" src="https://github.com/user-attachments/assets/7d6c5b83-7019-4e6d-8fb3-38ff6f585fc3" />


**Description:**
The training logs show the model's progression over 30 epochs, demonstrating consistent improvement. While the model started with a very low accuracy of 27.18% and a high loss of 2.66 at Epoch 1, it steadily refined its performance throughout the session. By the final Epoch 30, the model achieved a training accuracy of 92.18% and a validation accuracy of 88.99%. The close alignment between training and validation metrics indicates that the model is well-generalized and not suffering from significant overfitting, likely thanks to the implementation of dropout layers and data augmentation.

---

### 8. Improved Classification Report
<img width="553" height="408" alt="image" src="https://github.com/user-attachments/assets/42040066-ce08-4d01-b2ec-f52038183242" />


**Description:**
The classification report for the LW4 Improved CNN showcases the impact of adding BatchNormalization, enhanced augmentation, and larger dropouts. Overall, the model achieved a significant increase in performance compared to the baseline, reaching an accuracy of 0.89. The macro-average F1-score also improved to 0.89, indicating a much more robust model. While most classes like the Boston fern and Caladium achieved near-perfect results, others like the Areca palm (0.71 F1-score) and Fiddle leaf fig (0.70 F1-score) still lag slightly behind. This improved balance across the board suggests that the stronger regularization has successfully helped the model generalize better across the 20 plant species.

---

### 9. Improved Confusion Matrix
<img width="747" height="682" alt="image" src="https://github.com/user-attachments/assets/d9c42118-5188-473f-90fb-09c52b4d2f25" />



**Description:**
The confusion matrix for the LW4 Improved CNN reveals that the enhanced model significantly increased its accuracy, correctly identifying the majority of species. This is evidenced by the much cleaner, darker diagonal line, with the boston fern, anthurium, and zz plant achieving near-perfect or perfect scores. While some confusion remains between visually similar species like croton(mammy) and croton(petra), the errors are now much more localized and less frequent. Compared to the baseline, this model demonstrates a far more uniform and reliable ability to distinguish between the 20 plant classes.

---

### 10. Improved (ROC) Curve and Area Under the Curve (AUC) Score
<img width="1035" height="688" alt="image" src="https://github.com/user-attachments/assets/ec91fe3a-dbfd-4b9a-a133-75bc8db936ec" />


**Description:**
The ROC curve for the LW4 Improved CNN shows an exceptional overall AUC of 0.9933, which is a significant jump from the baseline performance. Most classes, including the boston fern, alocasia, and snake plant, achieved a perfect AUC of 1.00, meaning the model can distinguish them with near-perfect accuracy. Even the lowest-performing species, such as the areca palm (0.97), show much higher discriminative power than in the previous model. The fact that the curves are packed tightly in the top-left corner indicates that the improved architecture and regularization have made the model much more reliable at separating these 20 plant categories.



---

### Compare Results (Before vs After)
<img width="520" height="262" alt="image" src="https://github.com/user-attachments/assets/669e3ea4-cdb2-4a72-b1fb-9ab540ff603e" />




**Description:**
The comparison table highlights the significant leap in performance for the LW4 Improved model across every key metric. Unlike the baseline, which had a validation accuracy of 76.40%, the improved model reached 88.99%. Furthermore, the improved model achieved a high F1-Score of 0.8889 and an AUC Score of 0.9933, outperforming the baseline in both precision and reliability. With a Generalization Gap of only 3.20%, the model demonstrates a "Good Fit," proving that the addition of regularization and better data augmentation created a far more robust system that maintains high accuracy on unseen data without the risk of overfitting.

---

## 12. GUIDE QUESTIONS

**A. Model Evaluation Analysis**

**1. What were the weakest-performing classes based on the confusion matrix?**<br>
Based on the confusion matrix, the weakest classes are the ones that had a lot of wrong predictions. You can see it clearly because the numbers outside the diagonal are high, which means the model kept predicting those images as a different class. These are the classes the model had the hardest time recognizing correctly.

**2. How did Precision, Recall, and F1-score vary across classes?**<br>
Not all classes got the same scores. Some classes had really high precision and recall, which means the model was good at identifying them. But some classes got lower scores, probably because they look similar to other classes and the model got confused. The bar graph I made showed clearly which classes performed well and which ones didn't.


**3. What does a low recall indicate in your model?** <br>
Low recall means the model is missing a lot of images from that class. Like, even if the image is actually a cat, the model is classifying it as something else. So basically the model is not detecting that class well enough.

**4. How does AUC score reflect model performance compared to accuracy?** <br>
Accuracy just tells you how many predictions were correct. But AUC is more detailed because it shows how well the model can separate the classes from each other. Even if the accuracy looks okay, the AUC can reveal if the model is struggling. A higher AUC means the model is doing a better job overall, so it's a more reliable metric than just accuracy alone.

**B. Model Improvement**

**5. How did data augmentation affect validation accuracy?** <br>
Data augmentation helped a lot because the model got to see different versions of the same image during training, like flipped or rotated versions. So instead of just memorizing the training images, the model learned more general features. This made it perform better on the validation data, which is why the validation accuracy improved.

**6. Why is Batch Normalization important in CNNs?** <br>
Batch Normalization is important because it keeps the values inside the layers stable while training. Without it, training can become unstable or really slow. It also helps the model generalize better, so it's not just good at the training data but also on new images it hasn't seen before.


**7. What role did Dropout play in improving your model?** <br>
Dropout randomly turns off some neurons during training so the model doesn't rely too much on specific neurons. This prevents the model from just memorizing the training data. In our model we used 0.4 dropout, which helped reduce overfitting and made the model perform more consistently on validation data.

**8. How did Early Stopping prevent overfitting?**<br>
Early Stopping monitors the validation accuracy while training. If it doesn't improve after a certain number of epochs (we set patience to 6), it automatically stops training and brings back the best weights. This way the model doesn't overtrain on the training data and stays generalizable.

**C. Performance Comparison**

**9. What improvements were observed after modifying the model?**<br>
After we applied the improvements, the validation accuracy went up and the loss went down compared to the baseline model. The precision, recall, F1-score, and AUC score also improved. Overall the improved model was better at correctly classifying images and didn't overfit as much as before..

**10. Which enhancement contributed the most to performance improvement? Why?**<br>
I think data augmentation contributed the most because it directly addressed the overfitting problem. By showing the model more varied versions of the training images, it learned better and more general features. Batch Normalization also helped a lot by making training more stable, but without data augmentation the model would have still struggled on new data.

**11. Did the gap between training and validation accuracy decrease? Explain.** <br>
Yes, the gap got smaller. The baseline model had a bigger difference between training and validation accuracy, which is a sign of overfitting. But after adding dropout, data augmentation, and early stopping, the gap decreased. Our code even automatically checks this and prints whether the model is a good fit or overfitting, and the improved model showed a much healthier gap.

**D. Explainability (Grad-CAM Integration)**

**12. How did Grad-CAM help in understanding model predictions?**<br>
Grad-CAM helped us see where exactly the model was looking when it made a prediction. It creates a heatmap on top of the image showing the hot areas (red/yellow) which are the parts the model focused on. This way we can check if the model is actually looking at the right thing or just focusing on the background.

**13. Did the improved model focus on more relevant regions? Provide evidence.**<br>
Yes. When we ran Grad-CAM on the improved model, the heatmap showed that the highlighted areas were on the actual subject of the image, not on random parts of the background. This means the model learned to focus on the right features. Compared to what a weaker model would show, the improved model's overlay was more concentrated and accurate on the object itself.

**14. Why is explainability important in real-world AI applications?**<br>
Explainability is important because we need to understand why the model made a certain decision, especially in serious applications like healthcare or security. If the model makes a wrong prediction, we need to know the reason so we can fix it. Without explainability, we're just blindly trusting the model without knowing if it's actually learning the right things. Grad-CAM is one way to build that trust and make sure the model is working the way it should.

---

