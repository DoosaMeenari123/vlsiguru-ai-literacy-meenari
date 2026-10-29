# Mission 1 — Data Behind Deep Learning

##  Introduction

Deep learning models learn patterns from examples rather than understanding information exactly as humans do. Before training begins, raw data must be collected, cleaned, transformed into a suitable numerical format, and labelled when supervised learning is used.

In semiconductor engineering, inspection images can contain scratches, particles, stains, and other possible defects. Preparing these images correctly helps a neural network learn useful patterns and make more reliable predictions.

##  From Raw Images to Numerical Data

A digital image is made up of small elements called **pixels**. Each pixel stores a numerical value representing brightness or colour.

- **Grayscale images:** An 8-bit image commonly uses values from `0` to `255`, where `0` represents black and `255` represents white.
- **Colour images:** An RGB image stores three values for each pixel: red, green, and blue.
- **Model input:** These pixel values are represented as numerical arrays or tensors that a neural network can process.

For example, a semiconductor inspection image can be converted into numerical pixel values and used as input to a model that classifies an image as defective or defect-free.

##  Data Preparation Steps

Raw images cannot always be used directly. They may need several preprocessing steps before training.

| Step | Explanation | Semiconductor Example |
|---|---|---|
| Data collection | Gather relevant and representative examples | Collect wafer inspection images |
| Cleaning | Identify corrupted, unusable, or duplicate samples | Remove unreadable images and investigate duplicates |
| Resizing | Make image dimensions consistent when required | Resize images to a common resolution |
| Formatting | Convert images into the structure expected by the model | Represent images as numerical tensors |
| Normalisation | Scale pixel values to a suitable numerical range | Convert pixel values from `0–255` to `0–1` |
| Labelling | Assign the expected class or output | Label images as `defect` or `no_defect` |
| Dataset splitting | Separate data for training, validation, and testing | Keep related wafer images in the same split where appropriate |

### Example of Normalisation

For an 8-bit image, pixel values can be scaled to the range from `0` to `1` by dividing each value by `255`.

\[
\text{Normalised Pixel Value}=\frac{\text{Original Pixel Value}}{255}
\]

For example, a pixel value of `128` becomes approximately `0.502`.

Normalisation can make numerical inputs easier to work with during training. The exact preprocessing method depends on the model and the data.

##  Understanding Images and Labels

In supervised learning, an image is the **input**, and its label is the **expected output** used to train the model.

| Sample | Image Description | Label | Reason |
|---|---|---|---|
| A | Image showing a scratch | `defect` | A visible defect is present |
| B | Image with no visible defect | `no_defect` | No defect is identified under the inspection criteria |
| C | Image showing a stain-like region | `defect` | The region meets the defined defect criteria |
| D | Blurry or unclear image | `review_required` | The image needs human inspection before a reliable label can be assigned |

Labels must follow consistent inspection criteria. An uncertain image should not be labelled arbitrarily because incorrect labels can teach the model misleading patterns.

The `review_required` category is a workflow status, not necessarily a final class used by the trained model.

##  Data Quality Problems and Their Solutions

The quality of the training data strongly affects what a neural network learns.

| Data Quality Problem | Possible Effect | Recommended Solution |
|---|---|---|
| Incorrect labels | Model learns incorrect associations | Review labels using consistent inspection criteria |
| Duplicate images | Evaluation may become misleading if similar images cross dataset splits | Detect duplicates and group related samples before splitting |
| Blurry or noisy images | Important defect details may be hidden | Improve image capture and assess image quality |
| Missing rare defects | Model may fail to recognise uncommon defects | Collect representative examples of rare defect categories |
| Class imbalance | Model may favour the majority class | Improve data coverage and evaluate each class separately |
| Inconsistent image conditions | Model may learn lighting or tool-specific patterns instead of defects | Include representative imaging conditions and validate across tools |

**Key point:** More data does not automatically mean better learning. Data must be accurate, relevant, diverse, and representative of the conditions in which the model will be used.

## Conclusion

Data preparation is a fundamental stage of deep learning because the model learns from the examples it receives. Poor-quality images, incorrect labels, class imbalance, and unrepresentative data can lead to unreliable predictions even when a sophisticated neural network is used.

In semiconductor engineering, careful data preparation and evaluation can help develop more reliable defect-detection systems. The quality of the data is therefore just as important as the choice of model architecture.

## References

1. TensorFlow — Image Classification Tutorials: https://www.tensorflow.org/tutorials/images/classification
2. scikit-learn — Data Leakage: https://scikit-learn.org/stable/common_pitfalls.html#data-leakage
3. scikit-learn — Model Evaluation: https://scikit-learn.org/stable/modules/model_evaluation.html

