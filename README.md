## PIU-FR: Personal Identity Unlearning for Facial Recognition

* For privacy-conscious applications, this repository provides extensive benchmark datasets and PyTorch-based Machine Unlearning implementations, which enable AI systems to exclude particular data points while preserving their original functionality.

### 🔍 **Abstract**

To ensure privacy compliance, systems are often required to remove the personal identities of specific individuals they were trained to recognize, which has led to the emergence of machine unlearning methods. In this paper, we aim to achieve task-agnostic instance unlearning to forget specific individuals from facial images while maintaining high recognition accuracy for the model. Our approach is evaluated on the basis of the model's accuracy after the unlearning process, the forgetting score, and the final score. Specifically, we employ the ResNet-18 model to support the facial recognition task, with its weights adjusted using our proposed method, Personal Identity Unlearning for Facial Recognition (PIU-FR). Our method, named PIU-FR, combines two key techniques: a new machine unlearning approach that integrates the widely used NegGrad and SCRUB methods, and an innovative data partitioning strategy that generates an appropriate unseen dataset for each facial dataset to support the unlearning process. The results demonstrated that the ResNet-18 model retains high task accuracy after undergoing the unlearning process and meets the set objectives. Furthermore, PIU-FR outperforms previous state-of-the-art approaches and even surpasses retraining from scratch. This highlights that our approach allows machine learning models to effectively remove specific data samples used during training without the need for complete retraining.


<table align="center">
  <tr>
    <td align="center"> 
      <img src="Images/proposed_method.png" alt="Teaser" style="width: 700px;"/> 
      <br>
      <em style="font-size: 18px;">  <strong style="font-size: 18px;">Figure 1:</strong> An outline of our Personal Identity Unlearning for Facial Recognition (PIU-FR) proposal.</em>
    </td>
  </tr>
</table>

### 🗂️ **Datasets**

🔗 **MUFAC (Machine Unlearning for Facial Age Classifier)**
📌 MUFAC is a multi-class age classification dataset derived from AI HUB, containing 13,000+ Asian facial images. Each image is annotated with age group labels and personal identities, making it an ideal resource for research in machine unlearning and privacy-preserving AI.

🖼️ Dataset Preview:
<img src="./resources/MUFAC.png" width="800px"/>
 
🔗 **MUCAC (Machine Unlearning for Celebrity Attribute Classifier)**
📌 MUCAC is a multi-label facial attribute classification dataset based on CelebA, expanded to 30,000 images. It includes personal identity annotations, making it a valuable resource for machine unlearning research and privacy-preserving AI.

🖼️ Dataset Preview:
<img src="./resources/MUCAC.png" width="800px"/>

🔗 **JAFFE (Japanese Female Facial Expression TIFF Images)**
📌 JAFFE is a facial expression dataset created by Lyons, Kamachi, and Gyoba at Kyushu University, consisting of 213 grayscale images (256×256 pixels) of 10 Japanese female expressers. The images capture seven facial expressions (six basic emotions + neutral), with semantic ratings averaged from 60 Japanese viewers. The dataset, available in TIFF format, is intended for non-commercial scientific research under specific terms of use.

🖼️ Dataset Preview:
<img src="./resources/JAFFE.png" width="800px"/>

📏 **Evaluation Metrics**
Our Machine Unlearning Benchmark is evaluated based on four key aspects: model utility, forgetting performance, final score, and practical usability.

⚡ **1. Model Utility**
Accuracy: Measures the probability that the model’s predictions match the true labels in the test dataset. This serves as the primary metric for evaluating model performance.

🔄 **2. Forgetting Score**
Membership Inference Attack (MIA): Assesses the effectiveness of unlearning by determining whether specific data was used in training. With a binary classifier is trained to distinguish between (1) forgotten data and (2) unseen data. Specially, An ideal MIA accuracy of 0.5 indicates perfect unlearning, meaning the model can no longer differentiate between seen and unseen data.

📊 **3. Final Score (NoMUS – Normalized Machine Unlearning Score)**
Holistic Unlearning Metric: NoMUS combines model utility and forgetting performance into a single score. It is calculated as a weighted sum, with λ (lambda) controlling the trade-off between accuracy and forgetting. Specifically, score range is 0 (worst) → 1 (best), where higher values indicate better unlearning while preserving utility.

⏳ **4. Practical Usability**
Time Efficiency: Measures the execution time of the PIU-FR method compared to the time required for full retraining from scratch. With a lower runtime while maintaining high unlearning performance indicates a more practical and efficient approach.


## Contributors

* [Thai Hoang Le](https://orcid.org/0000-0002-6801-1924)
* [Phat Thuan Tran](https://orcid.org/0009−0004−3461−5713)
* [Nhi Man Bui Nguyen](https://orcid.org/0009−0005−2960−2755)
