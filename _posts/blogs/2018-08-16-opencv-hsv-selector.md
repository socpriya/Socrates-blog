---
layout: post
title:  How to arrive at HSV and RGB range of an Object for Computer Vision applications?
category: blog
keywords: HSV pick, HSV range, RGB pick, RGB range 
---
If a Computer Vision (CV) related application deals with detecting or tracking a specific object, then it is necessary to determine the range of HSV (Hue, Saturation, and Value) or RGB (Red, Green, and Blue) values of that object. This range is required to be specified as part of the coding to detect that object. If the correct range is not specified, the CV algorithm may pick-up noises as well, besides the actual object, leading to false detection and tracking.
{: .text-justify}

In the below OpenCV code snippet, a Tennis ball is about to be detected and tracked when it is moved in front of a webcam. To identify the ball alone, not any other objects/ noises, it is necessary to specify a correct range of corresponding HSV numbers.
{: .text-justify}

<script src="https://gist.github.com/socratesk/fd6354507ee3c9cc122655d7f391a5fb.js"></script>

Refer to the article _[What is the HSV Color Model?](https://www.lifewire.com/what-is-hsv-in-design-1078068){:target="_blank"}_ to know more about HSV. Here is the quick look at what HSV is.
{: .text-justify}

![HSV]({{site.baseurl}}/assets/img/hsv.png){:height="300px" width="400px"}
{: .text-center}

The exact HSV or RGB range can be determined programmatically using OpenCV for an object to be identified or tracked. In the below clip, a Tennis ball, which needs to be detected and tracked, is used to determine its HSV range.
{: .text-justify}

![HSV-track]({{site.baseurl}}/assets/img/ColorPicker.gif){:height="500px" width="700px"}

Grab the python code [ColorPicker.py](https://github.com/socratesk/ComputerVision/blob/master/ColorPicker.py){:target="_blank"} from my GIT repository, copy the same to a local machine, and issue one of the below commands in _Command Line Interface (CLI)_, based on your requirement. The source code is taken from _Adrian Rosebrock_'s [repository](https://github.com/jrosebr1/imutils/blob/master/bin/range-detector){:target="_blank"}.
{: .text-justify}

To determine HSV range based on an image,<br>
&nbsp;&nbsp;&nbsp;&nbsp;`python ColorPicker.py --filter HSV --image /path/image.png`
	
To determine RGB range based on an image,<br>
&nbsp;&nbsp;&nbsp;&nbsp;`python ColorPicker.py --filter RGB --image /path/image.png`

To determine HSV range based on webcam video,<br>
&nbsp;&nbsp;&nbsp;&nbsp;`python ColorPicker.py --filter HSV --webcam`

To determine RGB range based on webcam video,<br>
&nbsp;&nbsp;&nbsp;&nbsp;`python ColorPicker.py --filter RGB --webcam`

This script launches three windows as shown in the above clip:
1. Original: shows original video/image
2. Trackbars: shows sliders to adjust the HSV/RGB Min and Max range
3. Thresh: shows video/image adjusted to the selected HSV/RGB range
	
Adjust the _Min_ and _Max_ slide bars in _Trackbars_ window till you get the desired object alone appear in _White_ in _Thresh_ window. Take the corresponding HSV/RGB range and use them in the code as indicated earlier.
{: .text-justify}

---