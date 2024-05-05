# Fabric-defect-detection-with-YOLOv9
## Fabric defect detection
Fabric defect detection is a part of fabric quality control in textile production. In textile companies, the detection of defects and unacceptable areas of fabrics at the quality control stage has great importance for apparel production, although it is also a post-manufacturing operation for weaving and knitting mills.

The fabric defects may cause a 45-65% incurred loss in sale prices. Besides, approximately 85% of the product rejects in the apparel industry are related to fabric defects.

## Dataset
Using [TILDA dataset for fabric defect detection in roboflow](https://universe.roboflow.com/irvin-andersen/tilda-fabric/dataset/2)

The dataset contains 896 total images (train: 776, valid: 80, test: 40)

There are 4 classes in the dataset: holes, oil spots, thread errors, objects

## Train model
Using GELAN-C (YOLOv9 model for object detection) to custom-train for fabric defect

| Model | Test Size | Param. | FLOPs | AP<sup>box</sup> |
| :-- | :-: | :-: | :-: | :-: |
| [**GELAN-C-DET**](https://github.com/WongKinYiu/yolov9/releases/download/v0.1/gelan-c-det.pt) | 640 | 25.3M | 102.1G |**52.3%** |

Training model using Google Colab environment with T4 GPU

Fine-tuning the model to get better results
## Result
After 200 epochs, mAP reach 93,7%

                 Class     Images  Instances          P          R      mAP50   mAP50-95
                   all         80        103      0.856        0.9      0.937      0.659
                  hole         80         25      0.892          1      0.973      0.682
               objects         80         25      0.816      0.886      0.921      0.758
              oil spot         80         24      0.962      0.875      0.987      0.743
          thread error         80         29      0.753       0.84      0.868      0.453

Results after 30 epochs:
![results](https://github.com/khued200/Fabric-defect-detection-with-YOLOv9/assets/139615350/50d521ed-0c8c-4d6f-8c57-470b6812b633)

![F1_curve](https://github.com/khued200/Fabric-defect-detection-with-YOLOv9/assets/139615350/163a90ef-e056-4ec5-b211-788af48236c3)

Detect result:

![c1r1e1n10_jpg rf 302df4c62380ef189aeb08d7dbc54397](https://github.com/khued200/Fabric-defect-detection-with-YOLOv9/assets/139615350/9a46c467-911c-4ba9-9b5d-fa2a72b50baf)
![c1r1e2n26_jpg rf 397a04a8f89051055723d42e8d428c3f](https://github.com/khued200/Fabric-defect-detection-with-YOLOv9/assets/139615350/81c616c7-323b-4e3c-88bb-f12cb5e3a32a)
![c1r1e4n10_jpg rf c87f0bf21c6e9c849ae2b88c3be1a415](https://github.com/khued200/Fabric-defect-detection-with-YOLOv9/assets/139615350/b19891ed-4b29-4e54-ac90-7b17deb5d0ad)
![c1r1e3n26_jpg rf c06496de2418cb3b7ea2198ec487daca](https://github.com/khued200/Fabric-defect-detection-with-YOLOv9/assets/139615350/6b416655-ca6b-4870-8b7c-7027183045a4)




