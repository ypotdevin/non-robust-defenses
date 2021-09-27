On this page I collect neural network defenses against adversarial examples, which have been proven to be at most as robust as a simple baseline (the corresponding undefended model or a random guessing), or not robust at all.
Many defenses listed here were proposed, when there was not yet consent regarding how to thoroughly evaluate neural network defenses.
By publishing [On Evaluating Adversarial Robustness](http://arxiv.org/abs/1902.06705) and [On Adaptive Attacks to Adversarial Example Defenses](https://proceedings.neurips.cc/paper/2020/hash/11f38f8ecd71867b42433548d1078e38-Abstract.html), Carlini et al. and Tramèr et al. gave suggestions on how to properly claim robustness of a newly developed neural network defense mechanism.
A key suggestion was to adaptively attack the considered defense.

An attacker model, which assumes the attacker to be oblivious to the protection mechanism in place, is merely enough to perform sanity checks, but not enough to make reliable claims regarding robustness.
Therefore, when faced with an adaptive attacker, many proposed defenses turned out to be quite less robust than previously claimed.

My goal by curating this collection is not at all to blame the authors of the listed defenses.
As mentioned above, the methodology of how to properly evaluate a defense had to develop over the past few years.
Instead, my goals are to

  1. urge practitioners not aware of the state of the art in the machine learning robustness research, to not blindly use the collected defense mechanism in their applications
  2. gather in a single place ideas, which (in the way they were implemented) do not enhance robustness of neural networks

If you are instead looking for state of the art robust models, I refer you to the collections hosted at [Robust-ML](https://www.robust-ml.org/defenses/) and [RobustBench](https://robustbench.github.io/).

---

These are the sources I used to curate my collection:
 * [Adversarial Examples Are Not Easily Detected: Bypassing Ten Detection Methods](http://dl.acm.org/citation.cfm?doid=3128572.3140444), Carlini and Wagner 2017
 * [MagNet and "Efficient Defenses Against Adversarial Attacks" are Not Robust to Adversarial Examples](http://arxiv.org/abs/1711.08478), Carlini and Wagner 2017
 * [Towards Evaluating the Robustness of Neural Networks](http://ieeexplore.ieee.org/document/7958570/), Carlini and Wagner 2017
 * [Adversarial Example Defense: Ensembles of Weak Defenses are not Strong](https://www.usenix.org/conference/woot17/workshop-program/presentation/he), He et al. 2017
 * [On the Robustness of the CVPR 2018 White-Box Adversarial Example Defenses](http://arxiv.org/abs/1804.03286), Athalye and Carlini 2018
 * [Obfuscated Gradients Give a False Sense of Security: Circumventing Defenses to Adversarial Examples](http://arxiv.org/abs/1802.00420), Athalye et al. 2018
 * [Evaluating and Understanding the Robustness of Adversarial Logit Pairing](http://arxiv.org/abs/1807.10272), Engstrom et al. 2018
 * [Adversarial Risk and the Dangers of Evaluating Against Weak Attacks](http://proceedings.mlr.press/v80/uesato18a.html), Uesato et al. 2018
 * [Is AmI (Attacks Meet Interpretability) Robust to Adversarial Examples?](http://arxiv.org/abs/1902.02322), Carlini 2019
 * [Logit Pairing Methods Can Fool Gradient-Based Attacks](http://arxiv.org/abs/1810.12042), Mosbach et al. 2019
 * [Reliable evaluation of adversarial robustness with an ensemble of diverse parameter-free attacks](http://proceedings.mlr.press/v119/croce20b.html), Croce and Hein 2020
 * [Adversarial Machine Learning in Image Classification: A Survey Towards the Defender's Perspective](http://arxiv.org/abs/2009.03728), Machado et al. 2020
 * [On Adaptive Attacks to Adversarial Example Defenses](https://proceedings.neurips.cc/paper/2020/hash/11f38f8ecd71867b42433548d1078e38-Abstract.html), Tramèr et al. 2020
 * [Evading Adversarial Example Detection Defenses with Orthogonal Projected Gradient Descent](http://arxiv.org/abs/2106.15023), Bryniarski et al. 2021
 * [Indicators of Attack Failure: Debugging and Improving Optimization of Adversarial Examples](http://arxiv.org/abs/2106.09947), Pintor et al. 2021
 * [Robust-ML](https://www.robust-ml.org/defenses/)
 * [RobustBench](https://robustbench.github.io/)

---

This is the actual collection of non-robust defenses:

| **Defense**                                                                                                     | **Basic Description**                                                                                                  | **Author(s)**         | **Year** | **Attacker Publication**                                                                            | **Author(s)**        | **Year** |
| --------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- | --------------------- | -------- | --------------------------------------------------------------------------------------------------- | -------------------- | -------- |
| [A Kernelized Manifold Mapping to Diminish the Effect of Adversarial Perturbations](https://arxiv.org/abs/1903.01015) |  | Taghanaki et al. | 2019 | [Reliable evaluation of adversarial robustness with an ensemble of diverse parameter-free attacks](http://proceedings.mlr.press/v119/croce20b.html) | Croce and Hein | 2020 |
| [A New Defense Against Adversarial Images: Turning a Weakness into a Strength](https://arxiv.org/abs/1910.07629) | randomly perturbing input, checking if closest AE is further away than some threshold | Yu et al. | 2019 | [On Adaptive Attacks to Adversarial Example Defenses](https://proceedings.neurips.cc/paper/2020/hash/11f38f8ecd71867b42433548d1078e38-Abstract.html) | Tramer et al. | 2020 |
| [Adversarial and Clean Data Are Not Twins](https://arxiv.org/abs/1704.04960) | adversarial retraining (binary classifier) | Gong et al. | 2017 | [Adversarial Examples Are Not Easily Detected: Bypassing Ten Detection Methods ](https://dl.acm.org/doi/10.1145/3128572.3140443) | Carlini and Wagner | 2017 |
| [Adversarial Defense by Restricting the Hidden Space of Deep Neural Networks](https://arxiv.org/abs/1904.00887) |  | Mustafa et al. | 2019 | [Reliable evaluation of adversarial robustness with an ensemble of diverse parameter-free attacks](http://proceedings.mlr.press/v119/croce20b.html) | Croce and Hein | 2020 |
| [Adversarial Example Detection and Classification With Asymmetrical Adversarial Training](https://arxiv.org/abs/1905.11475) | combine base classifier with robust, binary »class-predicate-classifiers« | Yin et al. | 2019 | [On Adaptive Attacks to Adversarial Example Defenses](https://proceedings.neurips.cc/paper/2020/hash/11f38f8ecd71867b42433548d1078e38-Abstract.html) | Tramer et al. | 2020 |
| [Adversarial Examples Detection in Deep Networks with Convolutional Filter Statistics](https://arxiv.org/abs/1612.07767) | hidden layer statistics (PCA on conv) | Li and Li | 2016 | [Adversarial Examples Are Not Easily Detected: Bypassing Ten Detection Methods ](https://dl.acm.org/doi/10.1145/3128572.3140444) | Carlini and Wagner | 2017 |
| [Adversarial Logit Pairing](https://arxiv.org/abs/1803.06373) | Adversarial retraining (force logit similarity of benign and adversarial image pairs) | Kannan et al. | 2018 | [Evaluating and Understanding the Robustness of Adversarial Logit Pairing](http://arxiv.org/abs/1807.10272) | Engstrom et al. | 2018 |
| [APE-GAN: Adversarial Perturbation Elimination with GAN](https://arxiv.org/abs/1707.05474) | APE-GAN (similar to MagNet) | Shen et al. | 2017 | [MagNet and "Efficient Defenses Against Adversarial Attacks" are Not Robust to Adversarial Examples](http://arxiv.org/abs/1711.08478) | Carlini and Wagner | 2017 |
| [Are Generative Classifiers More Robust to Adversarial Attacks?](https://arxiv.org/abs/1802.06552) |  | Li et al. | 2018 | [On Adaptive Attacks to Adversarial Example Defenses](https://proceedings.neurips.cc/paper/2020/hash/11f38f8ecd71867b42433548d1078e38-Abstract.html) | Tramer et al. | 2020 |
| [Attacks Meet Interpretability: Attribute-steered Detection of Adversarial Samples](https://arxiv.org/abs/1810.11580) | Retraining by amplifying »important« neuron weigths | Tao et al. | 2018 | [Is AmI (Attacks Meet Interpretability) Robust to Adversarial Examples?](http://arxiv.org/abs/1902.02322) | Carlini | 2019 |
| [Characterizing Adversarial Subspaces Using Local Intrinsic Dimensionality](https://arxiv.org/abs/1801.02613) | Input statistics (local intrinsic dimensionality, LID) | Ma et al. | 2018 | [Obfuscated Gradients Give a False Sense of Security: Circumventing Defenses to Adversarial Examples](https://arxiv.org/abs/1802.00420) | Athalye et al. | 2018 |
| [Countering Adversarial Images using Input Transformations](https://arxiv.org/abs/1711.00117) | Input preprocessing (cropping, scaling, compression, …) | Guo et al. | 2017 | [Obfuscated Gradients Give a False Sense of Security: Circumventing Defenses to Adversarial Examples](https://arxiv.org/abs/1802.00421) | Athalye et al. | 2018 |
| [Deep k-Nearest Neighbors: Towards Confident, Interpretable and Robust Deep Learning](https://arxiv.org/abs/1803.04765) |  | Papernot and McDaniel | 2018 | [On the Robustness of Deep K-Nearest Neighbors](https://arxiv.org/abs/1903.08333) | Sitawarin and Wagner | 2019 |
| [Defense against Adversarial Attacks Using High-Level Representation Guided Denoiser](https://arxiv.org/abs/1712.02976) | Input preprocessing (denoising based on network trained on latent vectors) | Liao et al. | 2017 | [On the Robustness of the CVPR 2018 White-Box Adversarial Example Defenses](https://arxiv.org/abs/1804.03286) | Athalye and Carlini | 2018 |
| [Defense-GAN: Protecting Classifiers Against Adversarial Attacks Using Generative Models](https://arxiv.org/abs/1805.06605) | Defense-GAN (Like PixelDefend, but with a GAN instead of a PixelCNN) | Samangouei et al. | 2018 | [Obfuscated Gradients Give a False Sense of Security: Circumventing Defenses to Adversarial Examples](https://arxiv.org/abs/1802.00424) | Athalye et al. | 2018 |
| [Deflecting Adversarial Attacks with Pixel Deflection](https://arxiv.org/abs/1801.08926) | Pixel Deflection (input preprocessing) | Prakash et al. | 2018 | [On the Robustness of the CVPR 2018 White-Box Adversarial Example Defenses](https://arxiv.org/abs/1804.03286) | Athalye and Carlini | 2018 |
| [Detecting Adversarial Examples from Sensitivity Inconsistency of Spatial-Transform Domain](https://arxiv.org/abs/2103.04302) | primal & dual classifier + sensitivity statistics | Tian et al. | 2021 | [Evading Adversarial Example Detection Defenses with Orthogonal Projected Gradient Descent](http://arxiv.org/abs/2106.15024) | Bryniarski et al. | 2021 |
| [Detecting Adversarial Samples from Artifacts](https://arxiv.org/abs/1703.00410) | distributional detection (density) | Feinman et al. | 2017 | [Adversarial Examples Are Not Easily Detected: Bypassing Ten Detection Methods ](https://dl.acm.org/doi/10.1145/3128572.3140443) | Carlini and Wagner | 2017 |
| [Detecting Adversarial Samples from Artifacts](https://arxiv.org/abs/1703.00410) | distributional detection (Bayesian uncertainty) | Feinman et al. | 2017 | [Adversarial Examples Are Not Easily Detected: Bypassing Ten Detection Methods ](https://dl.acm.org/doi/10.1145/3128572.3140443) | Carlini and Wagner | 2017 |
| [Detection based Defense against Adversarial Examples from the Steganalysis Point of View](https://arxiv.org/abs/1806.09186) | Input preprocessing (analysize images for »hidden features« and train a binary classifier to detect Aes) | Liu et al. | 2018 | [Evading Adversarial Example Detection Defenses with Orthogonal Projected Gradient Descent](http://arxiv.org/abs/2106.15024) | Bryniarski et al. | 2021 |
| [Dimensionality Reduction as a Defense against Evasion Attacks on Machine Learning Classifiers](https://arxiv.org/abs/1704.02654v2) | dimensionality reduction  | Bhagoji et al. | 2017 | [Adversarial Examples Are Not Easily Detected: Bypassing Ten Detection Methods ](https://dl.acm.org/doi/10.1145/3128572.3140442) | Carlini and Wagner | 2017 |
| [Distillation as a Defense to Adversarial Perturbations Against Deep Neural Networks](https://ieeexplore.ieee.org/document/7546524) | Retraining with soft labels | Papernot et al. | 2016 | [Towards Evaluating the Robustness of Neural Networks](https://ieeexplore.ieee.org/document/7958570) | Carlini and Wagner | 2017 |
| [DLA: Dense-Layer-Analysis for Adversarial Example Detection](https://arxiv.org/abs/1911.01921) | DLA: advernarial retraining on Benign/Adversarial pairs, binary classifier on hidden layer activations | Sperl et al. | 2019 | [Evading Adversarial Example Detection Defenses with Orthogonal Projected Gradient Descent](http://arxiv.org/abs/2106.15023) | Bryniarski et al. | 2021 |
| [Early Methods for Detecting Adversarial Images](https://arxiv.org/abs/1608.00530) | dimensionality reduction (PCA) | Hendrycks and Gimpel | 2016 | [Adversarial Examples Are Not Easily Detected: Bypassing Ten Detection Methods ](https://dl.acm.org/doi/10.1145/3128572.3140444) | Carlini and Wagner | 2017 |
| [Efficient Defenses Against Adversarial Attacks](https://arxiv.org/abs/1707.06728) | Training data augmentation, BReLU activation | Zantedeschi et al. | 2017 | [MagNet and "Efficient Defenses Against Adversarial Attacks" are Not Robust to Adversarial Examples](http://arxiv.org/abs/1711.08478) | Carlini and Wagner | 2017 |
| [EMPIR: Ensembles of Mixed Precision Deep Networks for Increased Robustness against Adversarial Attacks](https://arxiv.org/abs/2004.10162) | Training an ensemble of classifiers with different precision in weights and activation | Sen et al. | 2020 | [On Adaptive Attacks to Adversarial Example Defenses](https://proceedings.neurips.cc/paper/2020/hash/11f38f8ecd71867b42433548d1078e38-Abstract.html) | Tramer et al. | 2020 |
| [Ensemble Adversarial Training: Attacks and Defenses](https://arxiv.org/abs/1705.07204) |  | Tramèr et al. | 2017 | [GenAttack: Practical Black-box Attacks with Gradient-Free Optimization](https://arxiv.org/abs/1805.11090) | Alzantot et al. | 2018 |
| [Error Correcting Output Codes Improve Probability Estimation and Adversarial Robustness of Deep Neural Networks](https://papers.nips.cc/paper/2019/hash/cd61a580392a70389e27b0bc2b439f49-Abstract.html) | Training a diverse ensemble of binary classifiers (on partitions of the classes) | Verma and Swami | 2019 | [On Adaptive Attacks to Adversarial Example Defenses](https://proceedings.neurips.cc/paper/2020/hash/11f38f8ecd71867b42433548d1078e38-Abstract.html) | Tramer et al. | 2020 |
| [Feature Squeezing: Detecting Adversarial Examples in Deep Neural Networks](https://arxiv.org/abs/1704.01155) | dimensionality reduction (color space and median filter) | Xu et al. | 2017 | [Adversarial Example Defenses: Ensembles of Weak Defenses are not Strong](https://www.usenix.org/conference/woot17/workshop-program/presentation/he) | He et al. | 2017 |
| [Gotta Catch 'Em All: Using Honeypots to Catch Adversarial Attacks on Neural Networks](https://arxiv.org/abs/1904.08554) | Honeypot: Lure attackers to generate obvious Aes | Shan et al. | 2019 | [Evading Adversarial Example Detection Defenses with Orthogonal Projected Gradient Descent](http://arxiv.org/abs/2106.15023) | Bryniarski et al. | 2021 |
| [Improving Adversarial Robustness via Promoting Ensemble Diversity](https://arxiv.org/abs/1901.08846) |  | Pang et al. | 2019 | [Reliable evaluation of adversarial robustness with an ensemble of diverse parameter-free attacks](http://proceedings.mlr.press/v119/croce20b.html) | Croce and Hein | 2020 |
| [Improving Adversarial Robustness via Promoting Ensemble Diversity](https://arxiv.org/abs/1901.08846) | training via regularization a diverse ensemble of classifiers | Pang et al. | 2019 | [On Adaptive Attacks to Adversarial Example Defenses](https://proceedings.neurips.cc/paper/2020/hash/11f38f8ecd71867b42433548d1078e38-Abstract.html) | Tramer et al. | 2020 |
| [Jacobian Adversarially Regularized Networks for Robustness](https://arxiv.org/abs/1912.10185) |  | Chan et al. | 2019 | [Reliable evaluation of adversarial robustness with an ensemble of diverse parameter-free attacks](http://proceedings.mlr.press/v119/croce20b.html) | Croce and Hein | 2020 |
| [MagNet: a Two-Pronged Defense against Adversarial Examples](https://arxiv.org/abs/1705.09064) | MagNet | Meng and Chen | 2017 | [MagNet and "Efficient Defenses Against Adversarial Attacks" are Not Robust to Adversarial Examples](http://arxiv.org/abs/1711.08478) | Carlini and Wagner | 2017 |
| [ME-Net: Towards Effective Adversarial Robustness with Matrix Estimation](https://arxiv.org/abs/1905.11971) | Preprocess input by randomly discarding parts of it, use matrix estimation on gaps, train on that input | Yang et al. | 2019 | [On Adaptive Attacks to Adversarial Example Defenses](https://proceedings.neurips.cc/paper/2020/hash/11f38f8ecd71867b42433548d1078e38-Abstract.html) | Tramer et al. | 2020 |
| [Mitigating Adversarial Effects Through Randomization](https://arxiv.org/abs/1711.01991) | Input preprocessing (randomized rescaling and randomized padding) | Xie et al. | 2017 | [Obfuscated Gradients Give a False Sense of Security: Circumventing Defenses to Adversarial Examples](https://arxiv.org/abs/1802.00422) | Athalye et al. | 2018 |
| [Mitigating Evasion Attacks to Deep Neural Networks via Region-based Classification](https://arxiv.org/abs/1709.05583) |  | Cao and Gong | 2017 | [Decision Boundary Analysis of Adversarial Examples](https://openreview.net/forum?id=BkpiPMbA-) | He et al. | 2018 |
| [Mixup Inference: Better Exploiting Mixup to Defend Adversarial Attacks](https://arxiv.org/abs/1909.11515) | Inject randomness into inference (interpolate input multiple times with random samples and average prediction on those) | Pang et al. | 2019 | [On Adaptive Attacks to Adversarial Example Defenses](https://proceedings.neurips.cc/paper/2020/hash/11f38f8ecd71867b42433548d1078e38-Abstract.html) | Tramer et al. | 2020 |
| [On Detecting Adversarial Perturbations](https://arxiv.org/abs/1702.04267) | adversarial retraining (binary classifier) | Metzen et al. | 2017 | [Adversarial Examples Are Not Easily Detected: Bypassing Ten Detection Methods ](https://dl.acm.org/doi/10.1145/3128572.3140444) | Carlini and Wagner | 2017 |
| [On the (Statistical) Detection of Adversarial Examples ](https://arxiv.org/abs/1702.06280) | adversarial retraining (»trash class«) | Grosse et al. | 2017 | [Adversarial Examples Are Not Easily Detected: Bypassing Ten Detection Methods ](https://dl.acm.org/doi/10.1145/3128572.3140444) | Carlini and Wagner | 2017 |
| [On the (Statistical) Detection of Adversarial Examples ](https://arxiv.org/abs/1702.06280) | distributional detection (maximum mean discrepancy) | Grosse et al. | 2017 | [Adversarial Examples Are Not Easily Detected: Bypassing Ten Detection Methods ](https://dl.acm.org/doi/10.1145/3128572.3140444) | Carlini and Wagner | 2017 |
| [PixelDefend: Leveraging Generative Models to Understand and Defend against Adversarial Examples](https://arxiv.org/abs/1710.10766) | PixelDefend (Use a generative model [PixelCNN] to project data back to the manifold) | Song et al. | 2017 | [Obfuscated Gradients Give a False Sense of Security: Circumventing Defenses to Adversarial Examples](https://arxiv.org/abs/1802.00423) | Athalye et al. | 2018 |
| [Resisting Adversarial Attacks by k-Winners-Take-All](https://arxiv.org/abs/1905.10510v2) | Retraining, k-Winner-Take-All layers (instead of ReLU) | Xiao et al. | 2019 | [On Adaptive Attacks to Adversarial Example Defenses](https://proceedings.neurips.cc/paper/2020/hash/11f38f8ecd71867b42433548d1078e38-Abstract.html) | Tramer et al. | 2020 |
| [Rethinking Softmax Cross-Entropy Loss for Adversarial Robustness](https://arxiv.org/abs/1905.10626) | Training using MMC loss | Pang et al. | 2019 | [On Adaptive Attacks to Adversarial Example Defenses](https://proceedings.neurips.cc/paper/2020/hash/11f38f8ecd71867b42433548d1078e38-Abstract.html) | Tramer et al. | 2020 |
| [Robustness to Adversarial Examples through an Ensemble of Specialists](https://arxiv.org/abs/1702.06856) | Ensemble of classifiers operating on class subsets | Abbasi and Gagné | 2017 | [Adversarial Example Defenses: Ensembles of Weak Defenses are not Strong](https://www.usenix.org/conference/woot17/workshop-program/presentation/he) | He et al. | 2017 |
| [Stochastic Activation Pruning for Robust Adversarial Defense](https://arxiv.org/abs/1803.01442) | Inject randomness into inference (»weighted dropout«) | Dhillon et al. | 2018 | [Obfuscated Gradients Give a False Sense of Security: Circumventing Defenses to Adversarial Examples](https://arxiv.org/abs/1802.00421) | Athalye et al. | 2018 |
| [The Odds are Odd: A Statistical Test for Detecting Adversarial Examples](https://arxiv.org/abs/1902.04818) | Inject randomness into inference (noisy input), statistical test | Roth et al. | 2019 | [On Adaptive Attacks to Adversarial Example Defenses](https://proceedings.neurips.cc/paper/2020/hash/11f38f8ecd71867b42433548d1078e38-Abstract.html) | Tramer et al. | 2020 |
| [Thermometer Encoding: One Hot Way To Resist Adversarial Examples](https://openreview.net/forum?id=S18Su--CW) | Retraining with discretized inputs | Buckman et al. | 2018 | [Obfuscated Gradients Give a False Sense of Security: Circumventing Defenses to Adversarial Examples](https://arxiv.org/abs/1802.00420) | Athalye et al. | 2018 |
| [Thwarting Adversarial Examples: An L0-RobustSparse Fourier Transform](https://arxiv.org/abs/1812.05013) | Input preprocessing (»compression« and projection to discrete cosine transformation coefficients) | Bafna et al. | 2018 | [On Adaptive Attacks to Adversarial Example Defenses](https://proceedings.neurips.cc/paper/2020/hash/11f38f8ecd71867b42433548d1078e38-Abstract.html) | Tramer et al. | 2020 |
| [Your Classifier is Secretly an Energy Based Model and You Should Treat it Like One](https://arxiv.org/abs/1912.03263) |  | Grathwohl et al. | 2019 | [Reliable evaluation of adversarial robustness with an ensemble of diverse parameter-free attacks](http://proceedings.mlr.press/v119/croce20b.html) | Croce and Hein | 2020 |

If you are aware of a defense, for which it has been proven that it is essentially less robust than the corresponding undefended neural network, or than random guessing, please let me know! I would be very glad if you'd open an issue or submit a pull request, providing the necessary information (defense publication and attacker publication most importantly). You may also send me an email to [ypo@informatik.uni-kiel.de](mailto:ypo@informatik.uni-kiel.de). This collection is meant to be updated over time.
