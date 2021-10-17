cd /work/rogerjiang01/darknet
###train
./darknet detector train data/obj.data cfg/yolo-obj.cfg yolov4.conv.137 -dont_show -mjpeg_port 8090 -map >> output.log

###test
#####有調整對比度
./darknet detector test data/obj.data_y cfg/yolo-obj.cfg backup_y/yolo-obj_best.weights ../train/GGO_JPG/GGO000501.jpg
./darknet detector test data/obj.data_y cfg/yolo-obj.cfg backup_y/yolo-obj_best.weights ../train/LLL_JPG/LLL001901.jpg
./darknet detector test data/obj.data_y cfg/yolo-obj.cfg backup_y/yolo-obj_best.weights ../train/Pneumonia_JPG/pneumonia2009701.jpg

#####無調整對比度
./darknet detector test data/obj.data_n cfg/yolo-obj.cfg backup_n/yolo-obj_best.weights ../train/GGO_JPG/GGO000501.jpg
./darknet detector test data/obj.data_n cfg/yolo-obj.cfg backup_n/yolo-obj_best.weights ../train/LLL_JPG/LLL001901.jpg
./darknet detector test data/obj.data_n cfg/yolo-obj.cfg backup_n/yolo-obj_best.weights ../train/Pneumonia_JPG/pneumonia2009701.jpg

