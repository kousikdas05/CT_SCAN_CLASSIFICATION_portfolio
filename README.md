## CT SCAN Image Exploratory Analysis and Contrast Classifier Model building
#### Prepared by : Kousik Das
<img src="https://images.unsplash.com/photo-1576671414121-aa0c81c869e1?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1050&q=80"/>

Source of Image : Unsplash by National Cancer Institute

### Table of Contents:
### [1. Problem Statement ](#problem)
### [2. Datasets](#dataset)
### [3. What is CT Scan ?](#ctscan)
### [4. How CT Scan Works ?](#how)
### [5. What Is It Used For?](#what)
### [6. Few Useful Terms considered as a part of Analysis:](#terms)
### [7. Conclusion](#conclusion)
### [8. Reference](#ref)


<a id='problem'></a>
### 1. Problem Statement
Based on a sample set of CT Scan Images ( with Contrast value as label), a model need to be prepared which can predict Contrast value of a new CT Scan Image.
  This problem has been approached in two parts:
  1. First Source data sets has been explored to find more insights  , those are are captured in a Jupyter Notebook file in this repository ( ".....EDA_Analysis.ipnyb")

  2. Secondly A CNN image classifier model has been created based on understandinng from EDA analysis. Find another Jupyter Notebook file for this in this repository ("....Classification.ipnyb")

<a id='dataset'></a>
### 2. Datasets :

CT images from cancer imaging archive with contrast and patient age has been considered from Kaggle Data set library.

The dataset is designed to allow for different methods to be tested for examining the trends in CT image data associated with using contrast and patient age. The basic idea is to identify image textures, statistical patterns and features correlating strongly with these traits and possibly build simple tools for automatically classifying these images when they have been misclassified (or finding outliers which could be suspicious cases, bad measurements, or poorly calibrated machines).

Dataset Link: https://www.kaggle.com/kmader/siim-medical-images

The data are a tiny subset of images from the cancer imaging archive. They consist of the middle slice of all CT images taken where valid age, modality, and contrast tags could be found. This results in 475 series from 69 different patients.

TCIA Archive Link - https://wiki.cancerimagingarchive.net/display/Public/TCGA-LUAD

For this study, pulmonary adenocarcinoma tests, publicly available on The Cancer Imaging Archive (TCIA), were used. This image dataset is heterogeneous in terms of scanner modalities, manufacturers and acquisition protocols. In most cases, images were acquired as part of routine care rather than as part of a controlled research study or clinical trial (Albertina, Watson, Holback, et al, 2016).

The images used in this study are chest (chest) and lung (lung) images.

There are 4 inputs from above dataset link.  2 directories: 'tiff_images','dicom_dir' and 1 csv file :'overview.csv' and a 'full_archive.npz' file.

<a id='ctscan'></a>
### 3. What is CT Scan ?

A computed tomography (CT or CAT) scan allows doctors to see inside your body. It uses a combination of X-rays and a computer to create pictures of your organs, bones, and other tissues. It shows more detail than a regular X-ray.

You can get a CT scan on any part of your body. The procedure doesn't take very long, and it's painless.

Reference : https://www.webmd.com/cancer/what-is-a-ct-scan

<a id='how'></a>
### 4. How Do CT Scans Work?
They use a narrow X-ray beam that circles around one part of your body. This provides a series of images from many different angles. A computer uses this information to create a cross-sectional picture. Like one piece in a loaf of bread, this two-dimensional (2D) scan shows a “slice” of the inside of your body.

This process is repeated to produce a number of slices. The computer stacks these scans one on top of the other to create a detailed image of your organs, bones, or blood vessels. For example, a surgeon may use this type of scan to look at all sides of a tumor to prepare for an operation.

Reference : https://www.webmd.com/cancer/what-is-a-ct-scan
<a id='what'></a>
### 5. What Is It Used For?
Doctors order CT scans for a long list of reasons:

CT scans can detect bone and joint problems, like complex bone fractures and tumors.
If you have a condition like cancer, heart disease, emphysema, or liver masses, CT scans can spot it or help doctors see any changes.
They show internal injuries and bleeding, such as those caused by a car accident.
They can help locate a tumor, blood clot, excess fluid, or infection.
Doctors use them to guide treatment plans and procedures, such as biopsies, surgeries, and radiation therapy.
Doctors can compare CT scans to find out if certain treatments are working. For example, scans of a tumor over time can show whether it’s responding to chemotherapy or radiation.

Reference: https://www.webmd.com/cancer/what-is-a-ct-scan

<a id='terms'></a>
### 6. Few Useful Terms considered as a part of Analysis:

##### pixel spacing
Pixel Spacing :Physical distance in the patient between the center of each pixel, specified by a numeric pair - adjacent row spacing (delimiter)and  adjacent column spacing in mm. In Imaging Pixel Spacing, the attribute refers to the distance between pixels on the sensor.

Reference: https://dicom.innolitics.com/ciods/rt-dose/image-plane/00280030

##### slice_thickness
Slice thickness refers to the (often axial) resolution of the scan. 

DICOM has an attribute called Spacing Between Slices (0018, 0088) that gives the distance between two adjacent slices (perpendicular to the image plane) and it also has an attribute called Slice Thickness (0018, 0050) that gives the thickness of the imaged slice.

Reference: https://stackoverflow.com/questions/14930222/how-to-calculate-space-between-dicom-slices-for-mpr

##### axial_aspect_ratio
Axial ratio, for any structure or shape with two or more axes, is the ratio of the length (or magnitude) of those axes to each other - the longer axis divided by the shorter.

##### sagital plane and coronal plane :
The transverse plane or axial plane (horizontal) divides the body into cranial and caudal (head and tail) portions.

In anatomy, the sagittal plane , or longitudinal plane, is an anatomical plane which divides the body into right and left parts. The plane may be in the center of the body and split it into two halves (mid-sagittal) or away from the midline and split it into unequal parts (para-sagittal).

A coronal plane (also known as the frontal plane) is any vertical plane that divides the body into ventral and dorsal (belly and back) sections.

It is one of the three main planes of the body used to describe the location of body parts in relation to each other axis.

Reference: https://en.wikipedia.org/wiki/Anatomical_plane

<a id='conclusion'></a>
### 7.Conclusion

Please have a look to the notebook files or more detail analysis and results. This is an attempt to create a Neural network model to predic contrast of CT Scan Image. You are welcome to copy the code and explore further.Don't forget to inform that at kousikdas05@gmail.com.


<a id='ref'></a>
### 8.References:
1. MITA - Medical Imaging Technology Association. DICOM PS3.1 2021b - Introduction and Overview. NEMA, DICOM Standards Committee (2021).Available HERE: http://dicom.nema.org/medical/dicom/current/output/html/part01.html#sect_1.1. Accessed on 07/25/2021.

2. Albertina, B., Watson, M., Holback, et al. Radiology Data from The Cancer Genome Atlas Lung Adenocarcinoma [TCGA-LUAD] collection. The Cancer Imaging Archive. (2016). 
https://wiki.cancerimagingarchive.net/display/Public/TCGA-LUAD .Accessed on 07/25/2021.

3. Innolitics. DICOM Standard Browser. (2021) https://dicom.innolitics.com/ciods . Accessed on 07/25/2021.

4. Pydicom. Introduction to pydicom - Brief overview of pydicom. (2021). https://pydicom.github.io/pydicom/stable/old/getting_started.html . Accessed on 07/25/2021.

5. Clark K, Vendt B, Smith K, Freymann J, Kirby J, Koppel P, Moore S, Phillips S, Maffitt D, Pringle M, Tarbox L, Prior F. The Cancer Imaging Archive (TCIA): Maintaining and Operating a Public Information Repository, Journal of Digital Imaging, Volume 26, Number 6, December, 2013, pp 1045-1057. (paper)
