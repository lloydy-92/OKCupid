# Can a user's relationship status be predicted using other variables in their dating profile using a machine learning model, and which model performs best?
**Table 1: Model Performance Summary (Mean ± Std)**
| Model |	F1 Macro Mean	| F1 Macro Std | Precision Macro Mean |	Precision Macro Std |	Recall Macro Mean |	Recall Macro Std |
|-------|---------------|--------------|----------------------|---------------------|-------------------|------------------|
| XGBoost |	0.277017 | 0.022139 |	0.274179 | 0.020856 |	0.290944 | 0.027491 |
| Logistic Regression |	0.273536 | 0.016036 |	0.276516 | 0.021627 |	0.275008 | 0.016635 |
| K-Nearest Neighbors |	0.273441 | 0.012576 |	0.271799 | 0.013077 |	0.279090 | 0.013594 |
| Random Forest |	0.267337 | 0.005170 |	0.265143 | 0.005575 |	0.271190 | 0.006330 |
| Decision Tree |	0.250588 | 0.004235 | 0.263200 | 0.003294 |	0.295085 | 0.014086 |<br/><br/>

<img width="964" height="590" alt="image" src="https://github.com/user-attachments/assets/73b81893-e02e-483e-8ef8-945efe4412e2" />

<img width="964" height="590" alt="image" src="https://github.com/user-attachments/assets/a8a5f831-0aa5-42b8-9c9a-4daa4ded76f2" />

<img width="964" height="590" alt="image" src="https://github.com/user-attachments/assets/9829a646-1905-4a0a-b0d6-f4a043f7ec9b" /><br/><br/>

**Table 2: Stability-Adjusted Model Rankings**
| Model |	F1 Macro Score | Precision Macro Score | Recall Macro Score |	Overall Score |
|-------|----------------|-----------------------|--------------------|---------------|
| Decision Tree |	0.246353 | 0.259906 |	0.280999 | 0.262419 |
| Random Forest |	0.262167 | 0.259568 |	0.264859 | 0.262198 |
| K-Nearest Neighbors |	0.260865 | 0.258722 |	0.265496 | 0.261694 |
| XGBoost |	0.254878 | 0.253323 |	0.263453 | 0.257218 |
| Logistic Regression |	0.257500 | 0.254889 |	0.258374 | 0.256921 |<br/><br/>

<img width="989" height="590" alt="image" src="https://github.com/user-attachments/assets/959e06fd-243c-4e9c-b7c3-7d1fe19e8662" /><br/><br/>

# Conclusion
Macro-averaged (weighted) scoring metrics were used in this project as the 'status' class is heavily imbalanced, as most users record 'single' as their status (as one would expect to see on a dating app), as seen in Figure 13.

#### Overall Performance Summary
Looking at Table 1, as well as Figures 14, 15, and 16, the following conclusions can be drawn:
- All 5 machine learning models achieve fairly low macro-F1 scores, ranging from around 0.25 - 0.28.
  - For comparison, simply guessing across 4-5 classes would give a macro-F1 score of around 0.20 - 0.25.
  - Therefore, in this instance, the machine learning models are only just better than random chance.
- The model with the greatest absolute performance appears to be XGBoost, with an F1 and Recall score of 0.277 and 0.291, respectively. However, with a higher standard deviation than the other models, this means that XGBoost is less stable.
- Despite being the 2nd weakest in performace, Random Forest has the lowest standard deviation across the models, making it the most stable.
- Decision Tree has the lowest F1 score of 0.251, but a relatively high recall, meaning that it successfully 'finds' more minority-class examples, but suffers in precision as a result.<br/>

#### Stability-Adjusted Model Ranking
As well as analysing the models' original scoring metrics, the standard deviation of each score for each model was subtracted from the respective mean values. This is to penalise models with high standard deviation, so models with high performance and low variability rank higher. An 'Overall Score' was computed here also, taking the mean of F1, precision, and recall.
<br/>
Tables 2, and Figure 17 reveals that:
- After stability is ensured in the scoring metrics, there is barely a siginifcant difference between model performance in terms of their Overall Score (this can especially be seen visually in Figure 17) - all models perform somewhat identically (0.256 - 0.262).
- Despite a low F1 score, a stable recall value leads to Decision Tree ranking first this time, even though its absolute performance was objectively the weakest before now.
- XGBoost and Logistic Regression, whilst higher in scoring metrics as shown by Figure 14 and 16, rank lower once stability is considered, due to their higher standard deviations.<br/>

## Overall Conclusion
Across the board, performance by the machine learning models was low, leading one to believe that this was most likely because of the heavy imbalance in the target variable 'status'. Most users have their status 'single', so the models mainly learn to predict this value. Macro-averaging the scoring metrics tried to correct for this, by giving the minority classes like 'married' or 'divorced' equal weight, which the models appeared to struggle with as a result of the imbalance, leading to the low scores.

#### Key Takeaways:
- The machine learning models used in this scenario were only slightly better than random chance, but not by much.
- For most models, they possess higher recall than precision. This means that whilst they do catch more minority-class cases, they do so with a lot of false positives and negatives.
- As for which model is the 'best', whilst Decision Tree ranks highest once accounted for stability, it still has a weak absolute performance, so it's more like the 'least bad' machine learning model rather than the superior one above the rest.

This implies that improvement in model performance will come with better data representation and handling class imbalance, rather than just trying a different machine learning algorithm.

# Next Steps - Potential Improvements
As stated, the main reason whilst a satisfying conclusion was not able to be drawn from this project was due to the imbalance in the target variable. As such, better handling of this imbalance could be worth trying out to improve performance of the models. This can be done via, for example, trying other resampling methods, or using ensemble methods in the code such as EasyEnsemble or BalancedRandomForest.

Another potential improvement to this project could be to reframe the task at the beginning. For example, if 'single' dominates the 'status' variable (which it does), predicting 'single vs not single' and then a second classifier for the smaller categories could work.


