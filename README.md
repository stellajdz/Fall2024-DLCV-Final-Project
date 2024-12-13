# Fall2024-DLCV-Final-Project
Deep Learning for Computer Vision Final Project -- Nutritional Value Prediction from Food Images (CLIP model)

We used Nutrition5k data from [CVPR 2021 Paper](https://arxiv.org/abs/2103.03375) to generate food image - caption pairs as input data for deep learning models. This code specifically tests the performance of the CLIP model on description generations based on food image - caption data.

To apply the CLIP model to the nutrient description task, image-description pairings from the pre-processed dataset is passed into the model to create image features and text features. We use the names of all unique ingredients and macronutrients and generate all possible combination of sentences as the image, text pairing comparison. Cosine similarity scores are calculated and CrossEntropyLoss is used for the training. The model was trained with $50$ epochs and an early stopping patience of $10$ with a $1e-5$ learning rate. The model reached to a $69 \%$ validation accuracy and $3.9$ validation loss.

From test evaluations and sample outputs, it's evident that CLIP lacks the ability to achieve high accuracy for this specific task since there are 117 unique ingredients that contains very similar texts. This is one of the limitations of CLIP. Although it excels at high-level tasks, it may struggle with intricate nuances and subtle distinctions within images or texts, thus limiting its effectiveness in applications requiring granular analysis.
