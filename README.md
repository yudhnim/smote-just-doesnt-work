# smote-just-doesnt-work
Later this year, i worked on my bachelor's thesis about credit risk and machine learning, using the Lending Club dataset. During working with the data, i thought about class imbalance problems a lot, should i try some SMOTE, or just let it be, real and authentic.

Here are my point, SMOTE and any other resampling methods dont work, at least in the case of tabular data.

## Introduction

Class imbalance is a common challenge in machine learning, particularly in tabular data applications such as fraud detection, medical diagnosis, and credit risk assessment. A prevalent approach to mitigate this issue is resampling, with techniques like Synthetic Minority Oversampling Technique (SMOTE) being widely adopted. However, resampling methods, including SMOTE, are not always suitable for tabular data due to concerns about data authenticity, statistical integrity, and overfitting risks. 

## My main points

First of all, whenever I built a statiscal/machine learning models, I always think of the famous saying from George Box, "All models are wrong" which  is often expanded as "All models are wrong, but some are useful". Yes, I think that is a beacon of guidance for me. The reason why we built models is to catch the pattern, is to signal the trend, not to satisfy our choice, a good performance but after dozens of "techniques" like: sampling or hyperparemeter tuning means nothing. To me, that performance, that result is only on the seed we set, on the train-test split we apply, our goal is to build and to explain the models, not to build a sophisticated one but struggle to understand a bit, at least in tabular data.

As I said above, statistical modeling emphasizes interpreting and analyzing results based on the true data distribution. Resampling to balance classes artificially manipulates this distribution to suit model performance, which conflicts with the goal of understanding the underlying population. "Resampling to suit our wants is not how statistics works; we build models, and whatever the result is, we interpret and analyze". This perspective aligns with the principle that models should reflect reality rather than be coerced into producing desired outcomes through data manipulation.

Moreover, resampling techniques, particularly oversampling methods like SMOTE, increase the risk of overfitting in tabular data. By duplicating or generating synthetic minority class samples, models may "learn by heart," memorizing patterns that do not generalize to real-world instances. This is especially problematic in high-dimensional or sparse tabular datasets, where synthetic samples may not capture the nuanced variability of the minority class. For example, in fraud detection, SMOTE-generated fraud cases may lead a model to overfit to specific patterns, failing to detect novel fraud instances that deviate from the synthetic data.

So, how can we address the problems of class imbalance in tabular dataset ? If we still want, there are variety of techniques, from class weights, cost-sensitive learning to well-done feature engineering, etc. But from my perspective, we dont solve it, we accept it as an assumption, all models are builts on assumptions, and our goal is to make use of it, not to be dependent on it.

## Academic papers that have the same opinion

(will update later)



Resampling and augmentation techniques are often more effective in computer vision, where the data's continuous and spatial nature allows synthetic variations to remain realistic. Techniques like image rotation, flipping, or feature embedding augmentations help models learn invariant patterns (e.g., object shapes) without compromising authenticity. In contrast, tabular data's heterogeneous feature space and domain-specific constraints make synthetic samples less reliable, as interpolated values may not adhere to real-world relationships or categorical boundaries.
