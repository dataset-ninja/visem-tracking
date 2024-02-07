The authors provide a **VISEM-Tracking: Human Spermatozoa Tracking Dataset** with 29,196 frames of wet sperm preparations with manually annotated bounding-box coordinates and additional clinical information about the sperm providers. They present baseline sperm detection performances using the YOLOv5 deep learning (DL) model trained on the VISEM-Tracking dataset. As a result, the authors approve that the dataset can be used to train complex DL models to analyze spermatozoa.

## Motivation

Assessing sperm motility manually involves microscopy observation, presenting challenges due to the rapid movement of spermatozoa within the field of view. Accurate manual evaluation demands extensive training, leading to the increased adoption of computer-assisted sperm analysis (CASA) in clinical settings. However, to enhance accuracy and reliability in assessing sperm motility and kinematics, there is a growing need for more data to train supervised machine learning approaches.

Machine learning (ML) is gaining prominence in the analysis of spermatozoa videos under a microscope, contributing to the development of CASA systems. Recent studies have explored the application of deep neural networks (DNNs) to automatically identify specific attributes of semen samples, such as predicting the proportion of progressive, non-progressive, and immotile spermatozoa. Nevertheless, a significant challenge in employing ML for semen analysis lies in the limited availability of data for training and validation. The existing open labeled datasets are sparse, mostly focusing on still-frames of fixed and stained spermatozoa or very brief sequences, primarily geared towards analyzing sperm morphology.

## Dataset description

The dataset was initially collected for investigating the impact of overweight and obesity on male reproductive function. Male participants, aged 18 years or older, were recruited from the general population between 2008 and 2013. The study received approval from the Regional Committee for Medical and Health Research Ethics, South East, Norway. All participants provided written informed consent, agreeing to the data's publication. The original project concluded in December 2017, and all data underwent complete anonymization.

To capture the samples, a heated microscope stage (37°C) was used, and examinations were conducted at 400× magnification with an Olympus CX31 microscope. Recordings were performed using a microscope-mounted UEye UI-2210C camera from IDS Imaging Development Systems in Germany. Following  World Health Organization(WHO) recommendations, a light microscope equipped with phase-contrast optics was deemed necessary for examining unstained preparations of fresh semen. The bounding box annotation was performed by data scientists in close collaboration with researchers in the field of male reproduction. The data scientists labeled each image using the tool [LabelBox](https://labelbox.com), which was then verified by the three biologists to ensure that the annotations were correct.

<img src="https://github.com/dataset-ninja/visem-tracking/assets/120389559/4209fc19-f80a-41d2-a875-99904fd1f400" alt="image" width="1000">

<span style="font-size: smaller; font-style: italic;">Video frames of wet semen preparations with corresponding bounding boxes. Top: large images showing different classes of bounding boxes, red - sperm, green - sperm cluster, and blue - small or pinhead sperm. Bottom: presenting different sperm concentration levels from high to low (from left to right, respectively).</span>

This dataset contains mainly 20 videos (collected from 20 different patients), each with a fixed duration of 30 seconds with the corresponding annotated bounding boxes. The 20 were chosen based on how different they are to all the videos in the dataset in order to obtain as many diverse tracking samples as
possible. A length of 30 seconds was chosen to make it easier to annotate and process the video files. These videos can also be used for a possible extension of the tracking data in the future.

| Description                                 | Count          |
|---------------------------------------------|----------------|
| #annotated 30s video clips                  | 20             |
| Frames per second (FPS) per video           | 45−50          |
| # of annotated frames                       | 29,196         |
| # Frames with at least one sperm            | 28,974         |
| # Frames with at least one cluster          | 10,199         |
| # Frames with at least one small or pinhead sperm | 13,532  |
| # bounding boxes                            | 656,334        |
| # classes                                   | 3 (sperm-0, cluster-1, small or pinhead-2) |
| # unique sperms (with tracking IDs)         | 1,121          |
| # unique clusters (with tracking IDs)       | 20             |
| # unique small or pinheads (with tracking IDs) | 35          |
| # unlabeled 30s video clips                 | 336            |
| # remaining 30s video clips from the 20 annotated videos | 166 |


<span style="font-size: smaller; font-style: italic;">Summary of quantitative information about the VISEM-Tracking dataset.</span>

The folder containing annotated videos has 20 sub-folders with annotations of each video. Each folder of videos has a folder containing extracted frames of the video, a folder containing bounding box labels of each frame, and a folder containing bounding box labels and the corresponding tracking identifiers. In addition to these, a complete video file (.mp4) is provided in the same folder. All bounding box coordinates are given using the YOLO format. The folder containing bounding box details with tracking identifiers has ‘.txt‘ files with unique tracking ids to identify individual spermatozoa throughout the video. It is worth noting that the area of the bounding boxes of the same sperm changes over time depending on its position and movement in the videos. 

<img src="https://github.com/dataset-ninja/visem-tracking/assets/120389559/8ac1d74d-dd00-48bf-8f37-1bb737e74de7" alt="image" width="500">

<span style="font-size: smaller; font-style: italic;">Changing bounding box area over time for the same sperm head.</span>

**Note:** dataset contains several .csv files with additional important information. These files include general information about participants (participant_related_data_Train.csv), the standard semen analysis results (semen_analysis_data_Train.csv), serum levels of sex hormones (sex_hormones_Train.csv: measured from blood samples), serum levels of the fatty acids in the phospholipids (fatty_acids_serum_Train.csv: measured from blood samples), fatty acid levels of spermatozoa (fatty_acids_spermatoza_Train.csv). You can download them from the [link](https://zenodo.org/records/7293726/files/VISEM-Tracking.zip?download=1).

| File name                             | File headers                                                                                          |
|---------------------------------------|-------------------------------------------------------------------------------------------------------|
| participant_related_data_Train.csv   | ID, Abstinence time(days), Body mass index (kg/m²), Age (years)                                      |
| semen_analysis_data_Train.csv        | ID, Sperm concentration (x10^6/mL), Total sperm count (x10^6), Ejaculate volume (mL), Sperm vitality (%), Normal spermatozoa (%), Head defects (%), Midpiece and neck defects (%), Tail defects (%), Cytoplasmic droplet (%), Teratozoospermia index, Progressive motility (%), Non-progressive sperm motility (%), Immotile sperm (%), High DNA stainability, HDS (%), DNA fragmentation index, DFI (%) |
| sex_hormones_Train.csv               | ID, Seminal plasma anti-Müllerian hormone (AMH) (pmol/L), Serum total testosterone (nmol/L), Serum oestradiol (nmol/L), Serum sex hormone-binding globulin, SHBG (nmol/L), Serum follicle-stimulating hormone, FSH (IU/L), Serum Luteinizing hormone, LH (IU/L), Serum inhibin B (ng/L), Serum anti-Müllerian hormone, AMH (pmol/L) |
| fatty_acids_serum_Train.csv          | ID, Serum C14:0 (myristic acid), Serum C16:0 (palmitic acid), Serum C16:1 (palmitoleic acid), Serum C18:0 (stearic acid), Serum C18:1 n-9 (oleic acid), Serum total C18:1, Serum C18:2 n-6 (linoleic acid, LA), Serum C18:3 n-6 (gamma-linoleic acid, GLA), Serum C20:1 n-9, Serum C20:2 n-6, Serum C20:3 n-6, Serum C20:4 n-6, Serum C20:5 n-3 (eicosapentaenoic acid, EPA), Serum C22:5 n-3 (docosapentaenoic acid, DPA), Serum C22:6 n-3 (docosahexaenoic acid, DHA) |
| fatty_acids_spermatoza_Train.csv     | ID, Sperm C14:0 (myristic acid), Sperm C15:0 (pentadecanoic acid), Sperm C16:0 (palmitic acid), Sperm C16:1 n-7 (palmitoleic acid), Sperm C17:0, Sperm C18:0 (stearic acid), Sperm C18:1 trans n-6 to n-11, Sperm C18:1 n-9 (oleic acid), Sperm C18:1 n-7 to n-11, Sperm C18:2 n-6 (Linoleic acid, LA), Sperm C20:0, Sperm C18:3 n-6 (gamma-linoleic acid, GLA), Sperm C18:3 n-3 (a-linoleic acid, ALA), Sperm C20:1 n-9, Sperm C20:2 n-6, Sperm C22:0, Sperm C20:3 n-6, Sperm C20:4 n-6 and C22:1 n-9 combined, Sperm C20:5 n-3 (eicosapentaenoic acid, EPA), Sperm C24:0, Sperm C24:1 n-9, Sperm C22:5 n-3 (docosapentaenoic acid, DPA), Sperm C22:6,n3 (docosahexaenoic acid, DHA) |

<span style="font-size: smaller; font-style: italic;">Summary of content of CSV files included in the VISEM-Tracking dataset.</span>