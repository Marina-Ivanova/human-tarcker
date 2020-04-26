# human-tracker

# Usage: 

To read and write back out to video: \
  python people_counter.py \
  --prototxt mobilenet_ssd/MobileNetSSD_deploy.prototxt \ \
	--model mobilenet_ssd/MobileNetSSD_deploy.caffemodel --input videos/TownCentreXVID.avi \ \
	--output output/output_Town_01.avi
  
# Structure and results:
To implement our people counter we used both OpenCV and dlib. We used OpenCV for standard computer vision/image processing functions, along with the deep learning object detector for people counting. We then used dlib for its implementation of correlation filters.

About 276 persons were detected on the video. FPS is approximatelly equal to 30.

Centroid based ID assignment — In its simplest form, we can assign IDs by looking at the bounding box centroids. We do this by calculating centroids for each bounding box in frame 1. In frame 2, we look at the new centroids and based on the distance from previous centroids we can assign IDs by looking at relative distance. 

The basic assumption is that frame to frame centroids would only move a little bit. This simple approach works quite well as long as centroids are spaced apart from each other. As you can imagine this approach fails when people are close to each other since it may switch IDs. 
