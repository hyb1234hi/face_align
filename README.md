# GSOC 2017: Face Alignment Module for OpenCV
The project aims to implement state of the art Face alignment Technique proposed by Vahid Kazemi

## Project Description
The GSOC proposal can be found on [Drive](https://drive.google.com/open?id=10LIfoV-pRIjoH-xNmLwaQOANavfMYT-5cS-4FpwTSPE).
We aim to implement the paper [One Millisecond Face Alignment with an Ensemble of Regression Trees](https://pdfs.semanticscholar.org/d78b/6a5b0dcaa81b1faea5fb0000045a62513567.pdf) using OpenCV.

<a href="https://www.youtube.com/watch?v=IOlAuQkZ4fM" target="_blank"><img src="https://github.com/sakshamgupta006/face_align/blob/master/Results/test_1.jpg" 
alt="FACE_ALIGNMENT" width="360" height="360" border="10" /></a>
<a href="https://www.youtube.com/watch?v=IOlAuQkZ4fM" target="_blank"><img src="https://github.com/sakshamgupta006/face_align/blob/master/Results/test_2.jpg" 
alt="FACE_ALIGNMENT" width="360" height="360" border="10" /></a>

# License
By downloading, copying, installing or using the software you agree to this license. If you do not agree to this license, do not download, install, copy or use the software.

License Agreement
For Open Source Computer Vision Library
(3-clause BSD License)
Redistribution and use in source and binary forms, with or without modification, are permitted provided that the following conditions are met:

Redistributions of source code must retain the above copyright notice, this list of conditions and the following disclaimer.
Redistributions in binary form must reproduce the above copyright notice, this list of conditions and the following disclaimer in the documentation and/or other materials provided with the distribution.
Neither the names of the copyright holders nor the names of the contributors may be used to endorse or promote products derived from this software without specific prior written permission.
This software is provided by the copyright holders and contributors “as is” and any express or implied warranties, including, but not limited to, the implied warranties of merchantability and fitness for a particular purpose are disclaimed. In no event shall copyright holders or contributors be liable for any direct, indirect, incidental, special, exemplary, or consequential damages (including, but not limited to, procurement of substitute goods or services; loss of use, data, or profits; or business interruption) however caused and on any theory of liability, whether in contract, strict liability, or tort (including negligence or otherwise) arising in any way out of the use of this software, even if advised of the possibility of such damage.

## Pre-requisites
The module has been tested on **Ubuntu 16.04** with **OpenCV 3.2** , but it should be easy to compile in other platforms.

### C++11 or C++0x Compiler
The code is based on C++, so a C++ compiler is must.

### OpenCV 3.x.x
The code is compatible with every version of OpenCV after version 3.0.0 including 3.0.0 .

### Face Detector Trained Model
The default trained tree was trained on OpenCV's **HAAR cascade** which can be downloaded from [OpenCV's repository](https://github.com/opencv/opencv/blob/master/data/haarcascades/haarcascade_frontalface_alt.xml).

## Building Face-Alignment Module and Examples

Clone the repository:
```
https://github.com/sakshamgupta006/face_align.git
```
Then follow the following steps:
```
cd face_align
mkdir build
cd build
cmake ..
make
```

## Running Samples
The module comes with examples demonstrating the results on **Video, Image, Multiple Images, External Capturing Devices.** Additionally, the module also includes examples to:
* **Train** Face Alignment on new dataset and parameters.
* **Test Accuracy** of the trained model.
* **A Snapchat Filter** Like application 

### Sample Training Example

```
./Train_ex -cascade <location of HAAR cascade model> -path <path to the dataset> <Output Name of Trained Model>
```
or you can simply run
```
./Train_ex -path <path to the dataset>
```
This will take the default values and an output file with name **68_landmarks_face_align.dat** will be generated after training.
### Sample Face Alignment Prediction
#### For Videos
```
./Landmark_prediction -cascade <location of HAAR cascade model> -model <path to trained model> <path to video file / external capturing device id>
```
If no <path to video file> is defined the code will capture the web camera, if available.

#### For Images
```
./Landmark_prediction -cascade <location of HAAR cascade model> -model <path to trained model> <path to image / path to txt file containig images location>
```
or you can simply run
```
./Landmark_prediction <path to image / path to txt file containig images location>
```
This will take the default values of cascade and trained model.

### Sample Filter Application

## Dataset
The module was trained on a combination of HELEN, LFPW, iBug, and AFW datasets and their mirror images. The combined dataset can be downloaded from [Drive](https://drive.google.com/file/d/0B8t1D28N36RXTGIxd1o5QnBRT1E/view?usp=sharing).

## Mentor
I am being mentored by [Simon Niklaus](https://www.google.co.in/url?sa=t&rct=j&q=&esrc=s&source=web&cd=2&cad=rja&uact=8&ved=0ahUKEwjLtZSM-bPUAhXIgI8KHXKwCuoQFggqMAE&url=http%3A%2F%2Fwww.sniklaus.com%2F&usg=AFQjCNFbkMT3hq7F2D-SSMwDmVMIkBXZAg&sig2=wHJv3K7Zb5IvDuFeGWY7yg) from Portland State University.

## Timeline
A detailed timeline of the project can be found on [Google Calander](https://calendar.google.com/calendar/embed?src=q5686lb1opb5kfrqatjslo2060%40group.calendar.google.com&ctz=Asia/Calcutta)

## Blog
Blog regarding the GSOC project journey can be found [Here](saksham-gsoc2017.blogspot.com).
