[Home Page](https://github.com/TrackerLounge/Home)

# Tracking And Computor Vision
Foot Print tracking experiments with Computer Vision

# Misadventures in Machine Learning and Tracking
Summary: 
I took ~1000 images of human foot prints (my foot prints) in sandy or clay soils (at the beach or stream banks).
I tried to use TensorFlow to classify the foot prints as "Right Foot" or "Left Foot".

I was not successful. 

I think this is because Tensor Flow is scales the image down and then attempted to use edge detection.
If I run Edge Detection (e.g. Canny Edge Detection, Guassian, Prewitt, Nobel, etc.) the algorithms pick up edges around invidual grains of sand. The edge of the track is a gradient. These edge detection algorithms do not do well on gradients.
Any leaf, branch, blade of grass in the image creates a strong edge. 
Tensorflow tries to classify the images. It sees a lot of snowy images with a few images that have strong edges (with grass, leaves, etc.) and assumes those are the important features of the image. Tensorflow does not see the shape of the track and thus cannot determine "Right Foot" from "Left Foot" given these raw images.

Powerpoint:
<a id="raw-url" href="https://raw.githubusercontent.com/TrackerLounge/TrackingAndComptureVision/master/files/MachineLearningImageClassification.pptx">Download FILE - MachineLearningImageClassification.pptx</a>
[MachineLearningImageClassification.pptx Powerpoint](files/MachineLearningImageClassification.pptx)
