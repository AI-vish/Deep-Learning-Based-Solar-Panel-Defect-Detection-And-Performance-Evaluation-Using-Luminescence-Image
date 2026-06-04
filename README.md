# Deep-Learning-Based-Solar-Panel-Defect-Detection-And-Performance-Evaluation-Using-Luminescence-Image
The growing deployment of photovoltaic systems demands
automated and scalable solutions for defect inspection and performance
evaluation. This work presents a two-stage deep learning framework
for solar cell analysis using electroluminescence (EL) imaging. In the
first stage, an open-source EL dataset is preprocessed to enhance defect
visibility, after which a ResNet50-based classifier categorises images as
defect-free or defective. Images identified as defective are subsequently
processed using a YOLOv8 model to localise and identify specific defects,
including cracks, finger interruptions, and thick line anomalies, using an
open-source dataset. In the second stage, an EL dataset acquired through
an industry partner, consisting of EL images and corresponding electri
cal measurements, is analysed to predict changes in open-circuit voltage
∆Voc and short-circuit current Isc using a deep learning regression model
trained on IV-derived parameters, namely Voc, Isc, Vmp, and Imp. Finally,
both stages are integrated into a unified framework that links identified
defect characteristics with photovoltaic performance degradation.
