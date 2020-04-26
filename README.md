# human-tracker
# USAGE
To read and write back out to video: \
  python people_counter.py \
  --prototxt mobilenet_ssd/MobileNetSSD_deploy.prototxt \ \
	--model mobilenet_ssd/MobileNetSSD_deploy.caffemodel --input videos/TownCentreXVID.avi \ \
	--output output/output_Town_01.avi
  
To implement our people counter we’ll be using both OpenCV and dlib. We’ll use OpenCV for standard computer vision/image processing functions, along with the deep learning object detector for people counting. We’ll then use dlib for its implementation of correlation filters.
