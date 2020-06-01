[Home Page](https://github.com/TrackerLounge/Home)

# Tracking, Image Processing and Computer Vision
Foot Print tracking experiments with Image Processing and Computer Vision

# Misadventures in Machine Learning and Tracking
Summary: 
I took ~1000 images of human foot prints (my foot prints) in sandy or clay soils (at the beach or stream banks).
I tried to use TensorFlow to classify the foot prints as "Right Foot" or "Left Foot".

I was not successful. 

I think this is because Tensor Flow is scales the image down and then attempted to use edge detection.
If I run Edge Detection (e.g. Canny Edge Detection, Guassian, Prewitt, Nobel, etc.) the algorithms pick up edges around invidual grains of sand. The edge of the track is a gradient. These edge detection algorithms do not do well on gradients.

Original Track (foot print)
<img src='/files/trackInSand.jpg' width=800>

Track after running Edge-detection 
<img src='/files/trackInSand_edge_detection.jpg' width=800>

Any leaf, branch, shadow, or blade of grass in the image creates a strong edge. 
Tensorflow tries to classify the images. It sees a lot of snowy images with a few images that have strong edges (with grass, leaves, etc.) and assumes those are the important features of the image. Tensorflow does not see the shape of the track and thus cannot determine "Right Foot" from "Left Foot" given these raw images.

Powerpoint:
<a id="raw-url" href="https://raw.githubusercontent.com/TrackerLounge/TrackingAndComptureVision/master/files/MachineLearningImageClassification.pptx">Download FILE - MachineLearningImageClassification.pptx</a>
[MachineLearningImageClassification.pptx Powerpoint](files/MachineLearningImageClassification.pptx)

# Photogrametry and Tracking
Summary: 
I want to detect the edge of a track reliably.

I took ~40 images of a track (my human footprint) and used free photogrametry software (e.g. Meshroom or regard3D) to convert these images into a wireframe mesh model of the track. Even on a high-end graphics card, this can take 40 minutes to 23 hours to complete and may produce garbage.

Using Blender3D, I filled in model holes and colored the track based on elevation.
Using GIMP, I attempted edge detection on these colorized images.

This approach produced better results than raw images but is not fool-proof. 
It is critical to level the model before colorization. If the ground before the track was made, had a natural bulge, dip or grade, calculating the average ground-level elevation compared to the track can be easily thrown off.

Original Track (foot print) with Pressure Release formation
<img src='/files/trackTo3DScan.jpg' width=800>

Track converted to a 3D Model and colorized based on Elevation
<img src='/files/trackAs3DScanColoredByElevation01.jpg' width=800>

Track converted to a 3D Model and colorized based on Elevation - From another angle
<img src='/files/trackAs3DScanColoredByElevation02.jpg' width=800>

Track after running Edge-detection on colorized image of 3D model
<img src='/files/trackAs3DScanColoredEdgeDetected.jpg' width=800>

3D Model colored by Elevation using more colors
<img src='/files/trackTo3DScanMoreColorsByElevation.jpg' width=800>

Track after running Edge-detection on image of more colors by elevation of 3D model
<img src='/files/trackAs3DScanMoreColorsByElevation_edge_detected.jpg' width=800>

I also experimented with converting a footprint or track 3D model into a topographic map image using 1-30 layers.
I ran edge detection on the results of these images. Here is an example.
<img src='/files/trackAsTopographicMap.jpg' width=800>

These approaches produced better edge detection than raw images and may fit into an track edge detection workflow but it is not a complete robust solution in and of itself.

I have a powerpoint but Github allows files that are 25 MB or smaller. The powerpoint is ~167 MB in size - too big.

For a youtube video looking at reading a track pressure release see
[![Alt text](https://github.com/TrackerLounge/TrackingAndComputerVision/blob/master/files/PressureReleaseInSand.jpg)](https://www.youtube.com/watch?v=EHe-8T_7E3w)
