# WISE - Waste Image Sorting and Evaluation

## Overview
The **WISE** (Waste Identification and Sorting using Enhanced vision) project leverages deep learning to automate waste classification through image recognition. This initiative addresses the global waste management crisis, where less than 20% of the 2 billion tons of annual waste is recycled, leading to environmental degradation and health risks. WISE aims to optimize recycling, reduce human exposure to hazardous materials, and recover valuable resources. This repository implements an ensemble Convolutional Neural Network (CNN) pipeline, evaluating ResNet-50, GoogLeNet, and EfficientNet-B0 on a dataset of 19,762 labeled waste images across 10 classes.

## Research Goals
- Develop an AI-driven solution for accurate and efficient waste classification.
- Compare ResNet-50, GoogLeNet, and EfficientNet-B0 on accuracy, precision, recall, F1-score, and training time.
- Provide insights for real-world deployment in smart bins, industrial sorting systems, and mobile applications.

## Dataset
The dataset comprises 19,762 waste images across 10 classes:
- Shoes, Batteries, Clothes, Trash, Glass, Cardboard, Metal, Paper, Plastic, Biological
- Manually classified into: *Recyclable*, *Organic*, *Specialty Recycling*, *Non-Recyclable*

Preprocessing included resizing, normalization, and data augmentation (random flips, rotations, shifts) for model generalization.

![Dataset Classes](https://raw.githubusercontent.com/WISE-DL-Project/WISE/refs/heads/main/Project%20Docs/report_images/dataset_classes.png)
*Figure 1: Item classification across garbage classes*

## Models
Three CNN architectures were evaluated:
- **ResNet-50**: A 50-layer residual network with skip connections to mitigate vanishing gradients and enhance feature learning.
  ![ResNet-50 Architecture](https://raw.githubusercontent.com/WISE-DL-Project/WISE/refs/heads/main/Project%20Docs/report_images/resnet50.png)
  *Figure 2: ResNet-50 Architecture*
- **GoogLeNet (Inception v1)**: A computationally efficient model using inception modules and 1x1 convolutions for dimension reduction.
  ![GoogLeNet Architecture](https://raw.githubusercontent.com/WISE-DL-Project/WISE/refs/heads/main/Project%20Docs/report_images/googlenet.png)
  *Figure 3: GoogLeNet Architecture*
- **EfficientNet-B0**: A compound-scaled model optimizing depth, width, and resolution for performance and speed.
  ![EfficientNet Architecture](https://raw.githubusercontent.com/WISE-DL-Project/WISE/refs/heads/main/Project%20Docs/report_images/efficientnet.png)
  *Figure 4: EfficientNet Architecture*

## Key Findings
The models were evaluated on classification accuracy, precision, recall, F1-score, and training time:
- **GoogLeNet**:
  - **Fastest training**: 760 seconds (12.67 minutes).
  - **Highest performance**: Accuracy (0.966), Precision (0.959), Recall (0.961), F1-Score (0.960).
  - Best suited for real-time applications and edge devices due to speed and accuracy.
  ![GoogLeNet Metrics](https://raw.githubusercontent.com/WISE-DL-Project/WISE/refs/heads/main/Project%20Docs/report_images/gnet_metrics.png)
  *Figure 5: Classification Metrics for GoogLeNet*
- **ResNet-50**:
  - **High accuracy**: Accuracy (0.955), Precision (0.947), Recall (0.945), F1-Score (0.946).
  - **Longer training**: 2136 seconds (35.6 minutes).
  - Viable for high-accuracy applications, potentially with different datasets.
  ![ResNet-50 Metrics](https://raw.githubusercontent.com/WISE-DL-Project/WISE/refs/heads/main/Project%20Docs/report_images/rnet_metrics.png)
  *Figure 6: Classification Metrics for ResNet-50*
- **EfficientNet-B0**:
  - **Lowest performance**: Accuracy (0.871), Precision (0.849), Recall (0.873), F1-Score (0.892).
  - **Longest training**: 2471 seconds (41.18 minutes).
  - Needs further tuning for waste classification tasks.
  ![EfficientNet Metrics](https://raw.githubusercontent.com/WISE-DL-Project/WISE/refs/heads/main/Project%20Docs/report_images/enet_metrics.png)
  *Figure 7: Classification Metrics for EfficientNet*

**Summary**: GoogLeNet outperformed others in accuracy and training speed, making it ideal for resource-constrained environments. ResNet-50 offered strong accuracy but required more training time, while EfficientNet-B0 underperformed. Inference times were similar across models, suggesting comparable deployment overhead. These findings guide model selection based on speed, accuracy, or trade-offs for applications like smart bins or industrial sorting.

For details, see the [Final Report](Final_Report.tex).

## Repository Structure
```
WISE/
├── data/                    # Dataset and preprocessing scripts
├── models/                  # Model architectures and training scripts
├── Project Docs/report_images/           # Images used in the report
├── Final_Report.tex         # LaTeX source for the project report
├── README.md                # This file
└── requirements.txt         # Python dependencies
```

## Future Work
- Implement transfer learning and advanced data augmentation for improved performance.
- Deploy models on embedded systems for real-time smart bins and industrial sorting.
- Add bounding box identification for precise object detection in images/videos.
- Integrate with technologies like Near-Infrared Spectroscopy for enhanced accuracy.
- Develop a mobile app and smart bin interface to promote public waste sorting.
- Train on diverse lighting and edge cases for robust real-world performance.
- Explore ensemble methods to combine model strengths for better predictions.

## Citation
```bibtex
@article{wise2025,
  title={WISE - Waste Image Sorting and Evaluation: Ensemble CNN Pipeline for Trash Detection and Classification},
  author={Castro, Brett and Gorecki, Tyler and Guruvayur, Vishwanath and Kamdar, Akaash and Levy, Isaac},
  journal={University of Virginia Technical Report},
  year={2025}
}
```

## Contributors
- Brett Castro ([gry6ks@virginia.edu](mailto:gry6ks@virginia.edu))
- Tyler Gorecki ([ttg6nx@virginia.edu](mailto:ttg6nx@virginia.edu))
- Vishwanath Guruvayur ([vish@virginia.edu](mailto:vish@virginia.edu))
- Akaash Kamdar ([ak2znr@virginia.edu](mailto:ak2znr@virginia.edu))
- Isaac Levy ([gbz6qn@virginia.edu](mailto:gbz6qn@virginia.edu))

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgments
Developed at the University of Virginia, with gratitude to our advisors and peers for their support.