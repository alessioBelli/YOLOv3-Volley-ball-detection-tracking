# Detection and tracking in volleyball match :mag_right:
Our software detects players and the ball in volleyball games. Furthermore, it is possible to track the ball within a video of a match. The detector used is YOLOv3, while the tracker is CSRT, which is available in OpenCV. 

## Weights :page_with_curl:
### Player detection
In order to perform the player detection we used yolov3's default weights, which can be downloaded at the following [link](https://pjreddie.com/media/files/yolov3.weights).
### Ball detection
Regarding ball detection, Yolov3 was trained specifically for volleyball using a [custom dataset](https://drive.google.com/file/d/1NUJIKjXq0BO84ipHVLFN9xxuy0RfRaWg/view?usp=sharing), and the weights created can be downloaded from that [link](https://drive.google.com/file/d/134TUXIisUhudCI5CO8rZinv-CR9K7P_r/view?usp=sharing).

## How to run
### Player detection
`python player_detection.py -l obj_person.names -cfg yolov3.cfg -w yolov3.weights -v video.mp4 -s -out_txt video.txt`
### Ball detection
`python ball_detection.py -l obj_ball.names -cfg yolov3_custom.cfg -w yolov3_custom_last.weights -v video.mp4 -s -out_txt video.txt`
### Ball tracking
`python ball_tracker.py --det video.txt --video video.mp4 --out_tracker tracker_output.txt`
