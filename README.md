# Drowsiness-Detection-System
A drowsiness detection system is an application designed to monitor a person's level of drowsiness and alert them when they are at risk of falling asleep. The system typically uses computer vision techniques to track facial landmarks and analyze eye movements to determine whether a person's eyes are closing or they are exhibiting other signs of drowsiness. The system can be integrated into a variety of environments, including vehicles, industrial machinery, and workplaces where safety is critical. The main goal of a drowsiness detection system is to prevent accidents and improve safety by alerting individuals when they are at risk of falling asleep or losing concentration. The system can be used in various settings, including transportation, aviation, healthcare, and the military, to enhance safety and reduce the risk of accidents caused by drowsiness or fatigue. The drowsiness detection system is an important tool for ensuring public safety, and its application is becoming increasingly widespread.

#code explaination 
The above code is an implementation of a drowsiness detection system that uses facial landmarks and the eye aspect ratio (EAR) to detect if a person is drowsy. The code imports necessary libraries such as scipy.spatial for distance calculation, imutils for image resizing and dlib for facial landmark detection. The pygame.mixer library is used for playing an alarm sound when drowsiness is detected.

The eye_aspect_ratio function calculates the EAR given the 6 coordinates of an eye. The thresh variable is a threshold EAR value, below which the person is considered drowsy. The frame_check variable sets the number of consecutive frames the person needs to have a low EAR before triggering an alarm.

The code then initializes the video camera and starts reading frames from it. Each frame is resized to a width of 450 pixels for faster processing. The detect function from dlib is used to detect faces in the frame, and the predict function is used to detect facial landmarks.

The coordinates for the left and right eyes are extracted from the facial landmark coordinates using face_utils.FACIAL_LANDMARKS_68_IDXS. The EAR is calculated for each eye, and the average EAR is used to determine if the person is drowsy.

If the EAR is below the threshold, a counter flag is incremented. If the counter exceeds the frame_check value, an alarm is triggered, and the text "ALERT!" is displayed on the frame. The alarm sound is played using sound.play(). The counter is reset if the EAR is above the threshold.

The loop continues until the user presses the "x" key, at which point the camera is released, and all windows are closed.
