## Goal

The primary goal is to distinguish one main category (the tire) from the rest of the image. Each pixel should be classify as either "tire" or "background".

## Semantic or Instance Segmentation?

| Aspect              | Semantic Segmentation                                                                                               | Instance Segmentation                                                                                              |
| ------------------- | ------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------ |
| **Definition**      | Labels each pixel in an image with a class, but does not distinguish between different instances of the same class. | Labels each pixel in an image with a class and also differentiates between separate instances of the same class.   |
| **Differentiation** | Treats all instances of a class as a single entity.                                                                 | Each instance of a class is uniquely identified.                                                                   |
| **Pros**            | Simplifies complex images by classifying areas, good for understanding the scene at a class level.                  | Allows for detailed analysis, including counting, tracking, and distinguishing between individual objects.         |
| **Cons**            | Cannot differentiate between individual objects of the same class, which limits its use in counting or tracking.    | More computationally intensive and complex due to the added layer of instance differentiation.                     |
| **Example**         | In an aerial photo of a forest, all trees are labeled as 'tree' without distinguishing between each tree.           | In the same aerial photo, each tree is individually distinguished and labeled, allowing for counting of the trees. |

## Why Semantic Segmentation for This Task?

- **Consistence Scene Composition:** 
	- The tire is always in the same position and no need to distinguish between multiple tires.
	
- **Background Complexity:** 
	- Allows for clear differentiation between the tire of interest and background elements, even if they are in similar appearance.
	
- **Efficiency:** 
	- For this task it can be more data efficient, because the task does not require distinguishing between multiple instances of the same class.
	- For the main objective to isolate a specific tire from the rest of the image without identifying individual tires, semantic segmentation models can be simpler and faster.
	- This simplicity can result faster training times and lower computational requirements.
	
- **Integration with Subsequent Tasks:**
	- If the segmented tire is to be analyzed further, such as for pattern recognition, having a precise pixel-wise mask of the tire can improve accuracy of the subsequent task.
	- The clear delineation of the tire provided by semantic segmentation ensures that only relevant pixels are analyzed, reducing the risk of background noise interfering.
	
## Approach

### 1. Understanding the Task

- The goal is to accurately segment a specific tire from images, isolating it from the background and irrelevant objects for subsequent classification.
- The segmented tire image will be input into an already developed model that determines the tire's orientation (right side or left side of the vehicle), making the segmentation precision critical for accurate classification.

### 2. Data Preparation and Annotation

- Annotate the images at the pixel level, labeling the regions corresponding to the tire and background, using annotation tools like LabelMe, VIA, or CVAT.
- Apply data augmentation techniques, such as rotation, scaling, and flipping, to improve the model's robustness and its ability to generalize across various tire positions and orientations.

#### Annotation Tool

- **[Segment Anything Model (SAM)](https://segment-anything.com/):**
	- [Auto Annotation using YOLOv8 and SAM **(Github)**](https://github.com/AarohiSingla/Auto-Annotation-Using-YOLOv8-and-SAm?tab=readme-ov-file)
	- [**(Roboflow)** How to Use the Segment Anything Model (SAM)](https://blog.roboflow.com/how-to-use-segment-anything-model-sam/)
	- 
- **[Label Studio](https://labelstud.io/)**
- **VGG Image Annotator**
- **CVAT**
- **Labelme**
- **Dash Doodler**
- **LabelImg**
- **Make Sense**
- **Labelbox (Paid)**
- **Scale (Paid)**
- **SuperAnnotate (Paid)**

### 3. Model Selection and Implementation

- Start with simpler semantic segmentation models like FCN, assessing their suitability based on their performance in terms of segmentation accuracy and computational efficiency.
- Explore more complex models such as U-Net or DeepLab for potentially improved segmentation detail, utilizing pre-implemented versions from libraries in TensorFlow/Keras or PyTorch, which often include the advantage of pretrained weights.

#### Semantic Segmentation Models

1. **Fully Convolutional Networks (FCN)**
	- **Rationale**: FCN is a foundational model in semantic segmentation, relatively straightforward in architecture. It's a good starting point to establish a baseline performance on your dataset.
	- **Consideration**: While it might not capture as much detail as more complex models, it can offer quick insights into the challenges of your specific segmentation task.

2. **SegNet**
	- **Rationale**: SegNet introduces an encoder-decoder architecture but remains efficient by reusing pooling indices for upsampling in the decoder. It's a step up in complexity from FCN but still focuses on efficiency.
	- **Consideration**: Useful for understanding how much improvement can be gained from a more structured decoding process without a significant increase in complexity.

3. **ENet (Efficient Neural Network)**
	- **Rationale**: ENet is designed for efficiency, making it an excellent next step if you're looking for models that balance performance and speed. It's particularly suitable for applications where inference time is critical.
	- **Consideration**: Assess if the model's efficiency translates to real-world applicability for your segmentation task without sacrificing too much accuracy.

4. **U-Net**
	- **Rationale**: With its symmetric architecture and skip connections, U-Net is slightly more complex but known for its high accuracy in segmentation tasks, particularly where detail is crucial.
	- **Consideration**: A good midpoint to evaluate if the increased complexity leads to a significant improvement in segmentation quality for your images.

5. **MobileNetV3 + DeepLabV3**
	- **Rationale**: This combination offers a balance between efficiency (from MobileNetV3) and segmentation performance (from DeepLabV3). It's a modern approach that leverages advancements in architecture design.
	- **Consideration**: Ideal for exploring how well lightweight backbones perform when paired with powerful segmentation heads.

6. **DeepLabV3+**
	- **Rationale**: As a standalone, DeepLabV3+ incorporates atrous convolutions and spatial pyramid pooling for robust segmentation. It's more complex and suitable for detailed segmentation tasks.
	- **Consideration**: Test this model to see if the added complexity further refines the segmentation accuracy for your application.

7. **High-Resolution Networks (HRNet)**
	- **Rationale**: HRNet maintains high-resolution representations through the network, making it highly effective for capturing fine details, albeit with increased complexity.
	- **Consideration**: Consider this model if previous ones fail to capture the level of detail needed for accurate tire segmentation, especially if the tire patterns are intricate.

### 4. Training and Evaluation

- Configure the training with an appropriate loss function, such as cross-entropy loss, choose an optimizer like Adam, and set a suitable learning rate.
- Use metrics like IoU (Intersection over Union) for evaluating the segmentation performance, ensuring regular validation checks to monitor the model's learning progress and to prevent overfitting.
- Consider early stopping mechanisms to halt training when the validation performance no longer improves, ensuring the model remains generalizable to new, unseen data.








