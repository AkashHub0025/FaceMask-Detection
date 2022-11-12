# Face mask detection(image preprocessing) using deep neural network

Flow:-
input -> convolution (feature map) -> max pooling -> fully connected -> output

but instead of convolution we will use mobilenet, so our flow will look like
input -> mobilenet -> max pooling -> fully connected -> output

Advantage of mobilenet
mobilenet is faster
it has less parameter

Disadvantage of mobilenet
less acurate

Note : For camera operation we are using opencv

Procedure

data preprocessing and model training is done in train_mask_detector.py which creates mask_detector.model and plot.png
run train_mask_detector to train the model
(and we have a face_detector file in face_detector folder which identify face and )

create a new file detect_mask_video.py for camera operation i.e opencv .
In this we are using cv2.dnn.readnet to detect face and created a model for face detection i.e facenet and masknet = load_model(mask_detector.model)
Now we have to load the camera using video stream
VideoStream(src=0).start()
then video camera will open and takes a video i.e frames (we loop through all the frame .Here frame is an image and sequece of image forms a video)

we are keeping all three model in function called detect_and_predict_mask and it returns position of video frame and prediction

Run file detect_mask_video
