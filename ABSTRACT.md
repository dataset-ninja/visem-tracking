The authors provide a **VISEM-Tracking: Human Spermatozoa Tracking Dataset** with 29,196 frames of wet sperm preparations with manually annotated bounding-box coordinates and additional clinical information about the sperm providers. They present baseline sperm detection performances using the YOLOv5 deep learning (DL) model trained on the VISEM-Tracking dataset. As a result, the authors approve that the dataset can be used to train complex DL models to analyze spermatozoa.

## Motivation

Assessing sperm motility manually involves microscopy observation, presenting challenges due to the rapid movement of spermatozoa within the field of view. Accurate manual evaluation demands extensive training, leading to the increased adoption of computer-assisted sperm analysis (CASA) in clinical settings. However, to enhance accuracy and reliability in assessing sperm motility and kinematics, there is a growing need for more data to train supervised machine learning approaches.

Machine learning (ML) is gaining prominence in the analysis of spermatozoa videos under a microscope, contributing to the development of CASA systems. Recent studies have explored the application of deep neural networks (DNNs) to automatically identify specific attributes of semen samples, such as predicting the proportion of progressive, non-progressive, and immotile spermatozoa. Nevertheless, a significant challenge in employing ML for semen analysis lies in the limited availability of data for training and validation. The existing open labeled datasets are sparse, mostly focusing on still-frames of fixed and stained spermatozoa or very brief sequences, primarily geared towards analyzing sperm morphology.

## Dataset description

The dataset was initially collected for investigating the impact of overweight and obesity on male reproductive function. Male participants, aged 18 years or older, were recruited from the general population between 2008 and 2013. The study received approval from the Regional Committee for Medical and Health Research Ethics, South East, Norway. All participants provided written informed consent, agreeing to the data's publication. The original project concluded in December 2017, and all data underwent complete anonymization.

To capture the samples, a heated microscope stage (37°C) was used, and examinations were conducted at 400× magnification with an Olympus CX31 microscope. Recordings were performed using a microscope-mounted UEye UI-2210C camera from IDS Imaging Development Systems in Germany. Following WHO recommendations, a light microscope equipped with phase-contrast optics was deemed necessary for examining unstained preparations of fresh semen. The bounding box annotation was performed by data scientists in close collaboration with researchers in the field of male reproduction. The data scientists labeled each image using the tool [LabelBox](https://labelbox.com), which was then verified by the three biologists to ensure that the annotations were correct.

<img src="https://github.com/dataset-ninja/visem-tracking/assets/120389559/4209fc19-f80a-41d2-a875-99904fd1f400" alt="image" width="1000">

<span style="font-size: smaller; font-style: italic;">Video frames of wet semen preparations with corresponding bounding boxes. Top: large images showing different classes of bounding boxes, red - sperm, green - sperm cluster, and blue - small or pinhead sperm. Bottom: presenting different sperm concentration levels from high to low (from left to right, respectively).</span>

<img src="https://github.com/dataset-ninja/visem-tracking/assets/120389559/8e59a005-0f3b-4be2-a3e9-7f8524608da4" alt="image" width="1000">

<span style="font-size: smaller; font-style: italic;">Summary of quantitative information about the VISEM-Tracking dataset.</span>



