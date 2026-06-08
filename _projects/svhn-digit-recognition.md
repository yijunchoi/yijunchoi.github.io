---
layout: page
title: SVHN Digit Recognition (CNN)
description: A convolutional neural network that recognizes street-view house-number digits — 96.40% test accuracy.
img: assets/img/Sample_predictions.png
importance: 1
category: work
---

A convolutional neural network built with TensorFlow/Keras to recognize digits from the **Street View House Numbers (SVHN)** dataset — real digits photographed in natural street scenes, which is substantially harder than MNIST.

**Final result: 96.40% test accuracy** on the 26,032-image SVHN test set.

[**View the full project and code on GitHub →**](https://github.com/yijunchoi/svhn-digit-recognition)

## Approach

The model was developed through three iterations, each addressing a weakness of the previous one:

- **Baseline** — the Keras MNIST convnet ported to 32×32×3 RGB input.
- **Intermediate** — added a third convolutional block, VGG-style stacked convolutions, per-block dropout, and a 256-unit dense head for more capacity and regularization.
- **Final** — added batch normalization after every convolutional layer plus light data augmentation, which stabilized training and reached **96.40% test accuracy**.

## Highlights

- Handled real-world image data (RGB, noisy, class-imbalanced) and SVHN-specific quirks (label 10 = digit 0).
- Used dropout, batch normalization, and data augmentation for regularization and training stability.
- Evaluated and interpreted the model with a confusion matrix, feature-map visualizations, and error analysis.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Sample_predictions.png" title="Sample predictions (green = correct, red = misclassified)" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Sample predictions on the SVHN test set — green titles are correct, red are misclassified.
</div>
