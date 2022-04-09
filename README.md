# Is Stain Normalisation Important in Breast Invasive Ductal Carcinoma Grading Task?

# Abstract
The staining of haematoxylin and eosin (H&E) in histopathological samples leads to inconsistent colour and intensity variations among digital datasets, thus hindering the performance of deep learning computer-aided diagnostic (CAD) systems. One proposed technique to battle colour invariance among digitalised histopathological images is stain normalisation (SN), which adjusts the source image colour to match the overall colour distribution of other similar images in a dataset. Some studies claimed that SN techniques improved CNNs' performance in histopathological classification tasks, while several contradicted their claims. Therefore, we attempt to justify the importance of SN (Reinhard and Macenko techniques) in the invasive ductal carcinoma (IDC) grading application using seven selected CNN models: EfficientNetB0, EfficientNetV2B0-21k, ResNetV1-50, ResNetV2-50, MobileNetV1, and MobileNetV2. Our findings indicated that CNN models trained in the original (non-normalised) dataset outperformed both SN techniques. Among the two SN techniques, Reinhard average scores topped the Macenko across all evaluation metrics in cv and test results while being more consistent in performance. Hence, we suggest that SN is considered unnecessary to be included in the CNN pre-processing steps to improve CNN performance if effective CNN architectures are employed.

# Methodology

<img width="364" alt="image" src="https://user-images.githubusercontent.com/56868536/162567390-75da18c4-af1a-4d2a-8c71-e74e03c62e30.png">
The overall flow of the methodology. Initially, a four-class dataset (termed the “Four Breast Cancer Grades (FBCG) dataset”) is established using the BreaKHis and BCG datasets. The dataset images are stain normalised using Reinhard and Macenko SN techniques with three different template images. The normalised and the original datasets are fed into seven pre-trained CNN architectures extended with several layers for the IDC grading task. All seven models take the 80% of the dataset to perform five-fold stratified cross-validation to evaluate the stability of the models. Finally, the seven models are evaluated using the test set (20% of the dataset). 

# Result (only show partial result)
<img width="426" alt="image" src="https://user-images.githubusercontent.com/56868536/162567466-c063d11b-0cd9-42a5-b61c-68fe28946a87.png">
<img width="430" alt="image" src="https://user-images.githubusercontent.com/56868536/162567477-93148f93-22e5-41f4-a14f-1da5b16c1aba.png">
<img width="729" alt="image" src="https://user-images.githubusercontent.com/56868536/162567528-d8f32c0c-c975-44f9-be16-78f534018f7f.png">
<img width="701" alt="image" src="https://user-images.githubusercontent.com/56868536/162567540-8eced18e-fe3a-409a-b91a-1e80ec2de554.png">
t-SNE without SN
<img width="541" alt="image" src="https://user-images.githubusercontent.com/56868536/162567733-4dc5a8b8-308a-43f1-9d1b-67fc9d3caf21.png">
t-SNE with Macenko technique
<img width="541" alt="image" src="https://user-images.githubusercontent.com/56868536/162567755-a5a17564-fba6-48ff-bb2b-4468d6c575f7.png">
t-SNE with Reinhard technique
<img width="541" alt="image" src="https://user-images.githubusercontent.com/56868536/162567777-775358c1-71c0-4a17-b20b-81ffeebbb1e5.png">


# Conclusion
This study investigated the importance of Reinhard and Macenko SN techniques in IDC grading with histopathological images using CNN. Seven pre-trained CNN architectures were employed to classify the Four-Breast-Cancer-Grades (FBCG) dataset into four classes via transfer learning: Grade 0, Grade 1, Grade 2, and Grade 3. Based on the experimental results, CNN models trained in the original FBCG dataset outperformed both SN techniques, contesting the general presumption that SN is vital to achieving top performance in the histopathological classification tasks. Comparing the two SN techniques, Reinhard average scores outperformed the Macenko across all evaluation metrics in cv and test results while being more consistent in performance. Therefore, we suggest that SN is not considered a necessary step to be included in the CNN pre-processing step to improve CNN performance, given that the effective CNN architecture is used. Finally, the outcome of three template images suggests that selecting the right template image may not necessarily enhance the performance of CNN models if ineffective SN is employed.
In our future development, we may expand our study to employ deep learning-based SN techniques in CNN pre-processing steps to compare the performance against original (non-normalised) datasets to further support our findings. Furthermore, we may consider more recent state-of-the-art CNN architectures and other breast cancer histopathological datasets to conduct our study.

# Data availability
The origin datasets combined for the current study are available in the Four Breast Cancer Grades (FBCG) Dataset, https://web.inf.ufpr.br/vri/databases/breast-cancerhistopathological-database-breakhis/, and breast carcinoma histological images from the Department of Pathology, https://zenodo.org/record/834910#.WXhxt4jrPcs.

# Tools used for stain normalisation
P. Byfield, StainTools, (2020). https://github.com/Peter554/StainTools
