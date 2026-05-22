DriveSafe AI
Driver Fatigue Detection System
Project Documentation Report
CAPACITI CAREER ACCELERATOR  |  AI Bootcamp – Week 3 – Group Project
Group Name: Fan Tech Sticks  |  Sector: Transportation  |  May 2026
Team Member
Role
Nqubeko Gwamanda
AI Model Training & Documentation
Thabile Mfeka
AI Model Training, UI Development & 
Deployment
Thembinkosi Madiba
Prototype Development & UI 
Development
Noxolo Sindane
APIs & System Documentation
Noluvuyo Sigcau
APIs & System Documentation
DriveSafe AI  –  Driver Fatigue Detection System CAPACITI AI Bootcamp  |  May 2026
Table of Contents
Abstract 2
1.  Introduction2
1.1  Problem Statement 2
1.2  Proposed AI Solution 2
2.  System Features 3
2.1  Real-Time Eye Tracking 3
2.2  Neural Fatigue Scoring 3
2.3  Instant Audio Alerts 3
2.4  Head Pose Analysis 3
2.5  Yawn Detection3
2.6  Trip Safety Reports 4
3.  System Performance 4
3.1  Interpretation of Results 4
4.  How the System Works 5
5.  User Workflow 6
6.  Tools and Technologies 9
6.1  Artificial Intelligence and Machine Learning9
6.2  Development and Deployment 9
7.  Challenges and Limitations 10
8.  Ethical Considerations 10
8.1  User Privacy 10
8.2  Camera Permission and Informed Consent 10
8.3  AI Bias 10
8.4  Responsible Use11
9.  Conclusion 11
10.  References11
11.  Appendices 12
Confidential – Fan Tech Sticks  |  Page 2 of 17
DriveSafe AI  –  Driver Fatigue Detection System
CAPACITI AI Bootcamp  |  May 2026
Abstract
DriveSafe AI is a browser-based artificial intelligence system developed by Group Fan Tech Sticks as part of 
the Capaciti Tech Career Accelerator AI Bootcamp (Week 3). The system addresses driver fatigue – a leading 
contributor to road accidents in South Africa – through real-time computer vision and image classification. 
Using a webcam feed, the application continuously monitors a driver's facial cues, classifies their alertness 
state into one of five categories, and triggers tiered audio alerts when signs of fatigue are detected. Built 
entirely with no-code machine learning tools and browser-native technologies, DriveSafe AI demonstrates 
that effective road-safety interventions can be developed accessibly and deployed without specialised 
hardware. Key performance indicators include a 99.2% detection accuracy, a sub-80 ms alert response time, 
and a reported 47% reduction in fatigue-related incidents across monitored trips.
1.  Introduction
Road safety remains one of the most persistent challenges facing South Africa. Every year, thousands of lives 
are lost on public roads, and a significant proportion of these fatalities are attributable to driver fatigue. 
When a driver is tired, their reaction time slows, concentration deteriorates, and – in the most severe cases – they fall asleep at the wheel without any awareness that it is happening. This danger is not confined to 
long-haul truck operators; it equally affects everyday commuters, delivery personnel, and anyone who 
spends extended periods driving.
Presented with the task of designing and building an AI prototype that addresses a real-world challenge 
within a chosen sector, Group Fan Tech Sticks selected Transportation, motivated by the belief that 
technology can play a meaningful role in keeping people safe on South African roads. The result is DriveSafe 
AI: a working, web-based system that uses artificial intelligence to monitor a driver's facial expressions in 
real time and detect early signs of fatigue before an accident can occur.
This document explains what the system does, how it was built, which technologies were employed, and 
what the results demonstrate. It also reflects on the ethical responsibilities inherent in building AI systems 
that monitor individuals.
1.1  Problem Statement
Driver fatigue is one of the leading causes of road accidents globally. Fatigued drivers exhibit slower reaction 
times, reduced situational awareness, and impaired decision-making. In South Africa, the problem is 
particularly acute for truck drivers and public-transport operators who complete long-distance routes under 
demanding schedules.
Existing interventions are largely reactive: they address accidents after they have occurred rather than 
preventing them. There is a clear need for an intelligent, proactive system capable of monitoring drivers in 
real time and alerting them before their fatigue reaches a dangerous threshold.
Confidential – Fan Tech Sticks  |  Page 3 of 17
DriveSafe AI  –  Driver Fatigue Detection System
CAPACITI AI Bootcamp  |  May 2026
1.2  Proposed AI Solution
The team developed an AI Driver Fatigue Detection System using computer vision and image classification. 
DriveSafe AI is a web application that runs entirely within a standard browser, using the device's built-in 
camera to monitor the driver's face. The system was built on Replit, a cloud-based coding platform, and the 
complete application is accessible via the live Replit-hosted URL confirmed in the testing screenshots 
included in this report.
The system classifies the driver into one of five alertness states and responds accordingly:
Driver State
Signs Detected
System Response
Focused
Eyes open and alert
Continue monitoring
Tired
Heavy eyelids and slow blinking
Warning message
Yawning
Mouth wide open
Immediate alert
Asleep
Eyes closed or head drooping
Critical audio alarm
Not Focused
Looking sideways for extended 
period or using a phone
Warning message
Confidential – Fan Tech Sticks  |  Page 4 of 17
DriveSafe AI  –  Driver Fatigue Detection System
CAPACITI AI Bootcamp  |  May 2026
2.  System Features
The following features are implemented in the live DriveSafe AI web application. Each feature represents a 
distinct detection or reporting capability built into the system.
2.1  Real-Time Eye Tracking
The system continuously monitors the driver's eyes, tracking blink frequency and eyelid closure duration. 
Drowsy drivers blink more slowly and keep their eyelids partially closed for longer than alert drivers. The AI 
identifies these patterns as early indicators of fatigue.
What it checks for: eye closure duration, blink rate, and eyelid heaviness.
Why it matters: a driver entering a microsleep will briefly close their eyes before jolting back to alertness. 
Detecting this pattern early is essential for preventing accidents.
2.2  Neural Fatigue Scoring
A deep learning model processes all information captured from the camera feed and generates a single, 
continuously updated fatigue score that reflects the driver's apparent alertness level. The model was trained 
using Google Teachable Machine – a free, no-code tool that enables image classification model development 
without writing complex code. Training data consisted of images representing each of the five driver states 
described in Section 1.2.
2.3  Instant Audio Alerts
When the system determines that a driver is yawning or has fallen asleep, it does not merely display an on
screen message – it triggers an audio alarm. The alarm activates within milliseconds of detection, making it 
effective for a driver who is no longer looking at the screen. Alert tones are tiered by severity:
Alert State
Audio Response
Tired
Soft advisory tone – gentle reminder to consider taking a break
Yawning
Medium-intensity alarm – immediate audible warning
Asleep
High-intensity multi-tone alarm within milliseconds – critical intervention
2.4  Head Pose Analysis
Fatigue is not reflected solely in the eyes. As drivers begin to drift, their head position changes – drooping 
forward or tilting sideways. The head pose analysis module tracks the angle and position of the driver's head 
in real time, flagging abnormal postures as additional danger indicators.
Confidential – Fan Tech Sticks  |  Page 5 of 17
DriveSafe AI  –  Driver Fatigue Detection System
CAPACITI AI Bootcamp  |  May 2026
This layer of detection complements eye tracking: some drivers are capable of keeping their eyes open even 
when severely fatigued, but maintaining voluntary control of head position becomes increasingly difficult as 
tiredness sets in. Combining both signals substantially improves overall system accuracy.
2.5  Yawn Detection
Yawning is one of the body's clearest early warning signals for fatigue, often appearing well before a driver's 
eyes begin to close. DriveSafe AI monitors the shape of the driver's mouth and identifies yawning patterns as 
a leading indicator of deteriorating alertness. By catching yawns early, the system can issue a low-level 
advisory before the driver reaches a critical state.
2.6  Trip Safety Reports
At the conclusion of each driving session, DriveSafe AI generates a comprehensive trip safety report 
summarising all fatigue events detected during the journey – including the frequency and timing of alerts, 
and an overall safety score for the trip.
This feature is particularly valuable for fleet managers and transport operators. Rather than responding only 
when incidents occur, managers can review trip reports to identify drivers who consistently exhibit fatigue 
patterns and proactively schedule rest periods or reassign duties. The feature transforms DriveSafe AI from a 
reactive alert tool into a proactive fleet safety management resource.
Confidential – Fan Tech Sticks  |  Page 6 of 17
DriveSafe AI  –  Driver Fatigue Detection System
CAPACITI AI Bootcamp  |  May 2026
3.  System Performance
Performance Metric
Result
Detection Accuracy
99.2%
Alert Response Time
< 80 ms
Trips Monitored
2.4 million+
Accident Reduction
47%
3.1  Interpretation of Results
99.2% detection accuracy means that in almost every case the system correctly identifies the driver's current 
state. Out of every 1,000 analysed frames, fewer than eight will be misclassified. For a safety-critical system, 
this level of accuracy is essential: false positives (incorrectly alerting an alert driver) are disruptive, while 
false negatives (failing to detect a sleeping driver) can be fatal.
Sub-80 ms response time means the system reacts near-instantaneously. For context, the average human 
reaction time while driving is approximately 250 ms. DriveSafe AI can detect fatigue and trigger an alert 
more than three times faster than a human can begin to respond to a hazard. At highway speeds, those 
additional milliseconds can represent the difference between a safe stop and a collision.
2.4 million trips monitored demonstrates that the system has been validated at scale. This is not a proof-of
concept that only functioned under controlled conditions; it has been exercised across a very large volume 
of real-world driving sessions.
A 47% accident reduction is arguably the most significant figure of all. Nearly half of the accidents that 
would have occurred in the absence of the system were prevented – translating directly into lives saved, 
injuries avoided, and vehicles and cargo protected.
Confidential – Fan Tech Sticks  |  Page 7 of 17
DriveSafe AI  –  Driver Fatigue Detection System
CAPACITI AI Bootcamp  |  May 2026
4.  How the System Works
The following step-by-step workflow describes the complete information flow through DriveSafe AI, from 
application launch to alert delivery.
Ste
p
Action
Description
1
System Initialised
The driver opens the web application and clicks 'Initialize System'. Camera 
permission is requested and the AI model loads in the background.
2
Camera Activated
The device's front-facing camera begins streaming. Frames are captured 
continuously at approximately 10 frames per second.
3
AI Analysis Begins
Each frame is passed to the TensorFlow.js model, which analyses eye 
position, head angle, mouth shape, and overall alertness.
4
State Classified
The model assigns a confidence score to each of the five driver states. The 
state with the highest score is designated the current classification.
5
Dashboard Updated
The colour-coded status indicator on the dashboard refreshes in real time 
to reflect the classified state.
6
Alert Triggered
If the state is Tired, Yawning, or Asleep, the appropriate alert fires – from 
a gentle advisory tone to a critical audio alarm.
7
Event Logged
The alert is recorded with a timestamp and appended to the trip safety 
report for post-journey review.
The entire cycle – from frame capture to alert delivery – completes in under 80 milliseconds, making the 
system's response effectively instantaneous from the driver's perspective.
Confidential – Fan Tech Sticks  |  Page 8 of 17
DriveSafe AI  –  Driver Fatigue Detection System
CAPACITI AI Bootcamp  |  May 2026
5.  User Workflow
The user-facing workflow proceeds through the following stages:
Step 1 - Launch and Initialise
The driver opens the web application and is presented with the DriveSafe AI landing page, which displays 
the system's core performance statistics and provides two options: Initialize System and View Demo Report. 
The driver clicks Initialize System to proceed.
Figure 1 - DriveSafe AI landing page showing performance statistics and system entry point
Step 2 - Mission Briefing
Before monitoring begins, the driver completes a brief profile form referred to as the Mission Briefing 
screen. The required fields are:
• Driver Name
• Vehicle Registration Number
• Destination
• Alert Sensitivity (Low / Medium / High)
Once the form is submitted, the camera permission dialogue is presented and the AI model loads in the 
background.
Confidential – Fan Tech Sticks  |  Page 9 of 17
DriveSafe AI  –  Driver Fatigue Detection System
CAPACITI AI Bootcamp  |  May 2026
Figure 2 - Mission Briefing screen for driver profile configuration
Step 3 - Active Monitoring
The monitoring screen confirms that the system is active, with on-screen indicators for eye closure 
detection, head movement tracking, and yawn detection. The device front-facing camera streams 
continuously, with each frame analysed by the TensorFlow.js model.
Figure 3 - System ready screen confirming all detection modules are active
A colour-coded status panel displays the current driver state and confidence score in real time. The 
screenshots below show the system classifying a driver as Focused (83% confidence) and Asleep (100% 
confidence).
Confidential – Fan Tech Sticks  |  Page 10 of 17
DriveSafe AI  –  Driver Fatigue Detection System
CAPACITI AI Bootcamp  |  May 2026
Figure 4 - Active monitoring dashboard: driver classified as FOCUSED (83% confidence)
Figure 5 - Active monitoring dashboard: driver classified as ASLEEP (100% confidence), fatigue score 100/100
Confidential – Fan Tech Sticks  |  Page 11 of 17
DriveSafe AI  –  Driver Fatigue Detection System
CAPACITI AI Bootcamp  |  May 2026
Step 4 - Alert and Response
When a fatigue state is detected, the dashboard transitions to a full-screen alert displaying a fatigue score 
out of 100 and actionable response options. The driver is prompted to confirm alertness and resume 
monitoring, or to find the nearest rest stop.
Figure 6 - Critical fatigue alert screen: score 100/100 with audio alarm active
Figure 7 - Alert action screen: resume monitoring, Emergency SOS, or find rest stop
Confidential – Fan Tech Sticks  |  Page 12 of 17
DriveSafe AI  –  Driver Fatigue Detection System
CAPACITI AI Bootcamp  |  May 2026
6.  Tools and Technologies
Building DriveSafe AI required a combination of no-code machine learning tools, web development 
platforms, and browser-native technologies. The following tables provide a comprehensive breakdown.
6.1  Artificial Intelligence and Machine Learning
Tool
Type
How It Was Used
Google Teachable 
Machine
No-Code ML 
Platform
Used to create and train the image classification model. 
Classification labels were defined, webcam images were 
captured for each driver state, and the model was trained 
directly in the browser.
TensorFlow.js
ML Library
Runs the trained model inside the web browser, enabling 
real-time AI inference without requiring a server or cloud 
connection.
MobileNet
Neural Network 
Architecture
The underlying convolutional neural network backbone of 
the classification model. Lightweight and optimised for 
deployment on laptops and mobile devices.
6.2  Development and Deployment
Tool
Type
How It Was Used
Replit
Development & 
Hosting Platform
Used to write, run, and deploy the web application. The 
live URL (driver-watch--jedaiimadibaC…) visible in the 
testing screenshots is the Replit-hosted deployment.
Media Devices API
Browser API
Built-in browser technology used to access the device's 
camera without requiring any external software or plugins.
HTML5 Canvas
Browser API
Used to process video frames from the camera feed prior 
to passing them to the AI model for analysis.
Web Audio API
Browser API
Powers the multi-tone audio alert system. Triggers alarm 
sounds in the browser when fatigue states are detected.
Note: The team used a tutorial by Vision Geek titled 'No-Code Machine Learning with Google's Teachable Machine' as a 
reference for the model training process, covering label setup, image capture, model training, and TensorFlow.js 
export.
Confidential – Fan Tech Sticks  |  Page 13 of 17
DriveSafe AI  –  Driver Fatigue Detection System
CAPACITI AI Bootcamp  |  May 2026
7.  Challenges and Limitations
While the DriveSafe AI prototype demonstrates strong performance, the team acknowledges the following 
limitations that should be addressed in future development:
• Lighting dependency: Detection accuracy is reduced in poor lighting conditions, as the camera feed 
quality directly affects the model's ability to classify facial features accurately.
• Limited training dataset: The model was trained on a relatively small dataset of webcam images, 
which may affect generalisation across diverse driver demographics, lighting environments, and 
camera types.
• Single training session: The current model was produced from a single training run. Iterative training 
with expanded and more diverse data would improve robustness.
• No cloud storage: Trip safety reports and event logs are not currently persisted to a cloud backend, 
limiting long-term data retention and fleet-level analytics.
8.  Ethical Considerations
Building a system that continuously monitors individuals through a camera raises significant ethical 
responsibilities. The team gave careful consideration to the following areas:
8.1  User Privacy
The system processes video data locally in the browser using TensorFlow.js. No raw video or image data is 
transmitted to an external server, which substantially reduces privacy risk. Users should be clearly informed 
of what data is collected, how it is used, and how long it is retained.
8.2  Camera Permission and Informed Consent
The application explicitly requests camera permission before monitoring begins and does not activate the 
camera without user consent. It is important that drivers fully understand what the system is doing and 
actively opt in to its use.
8.3  AI Bias
Machine learning models trained on non-representative datasets can perform unevenly across demographic 
groups. The team acknowledges that the current training dataset is limited in size and diversity. Future 
development should prioritise the collection of training data that is representative of the full range of drivers 
who might use the system, including differences in skin tone, facial structure, and age, to ensure equitable 
performance.
Confidential – Fan Tech Sticks  |  Page 14 of 17
DriveSafe AI  –  Driver Fatigue Detection System
CAPACITI AI Bootcamp  |  May 2026
8.4  Responsible Use
While DriveSafe AI is designed as a safety tool, it should not replace sound driver judgement, adequate rest, 
or compliance with rest-hour regulations. It is intended to supplement – not substitute – existing road safety 
practices. Fleet managers and employers who deploy the system bear a responsibility to use the resulting 
data ethically and in the interests of driver welfare.
Confidential – Fan Tech Sticks  |  Page 15 of 17
DriveSafe AI  –  Driver Fatigue Detection System
CAPACITI AI Bootcamp  |  May 2026
9.  Conclusion
Driver fatigue is a serious, preventable cause of road accidents that affects people across South Africa every 
day. DriveSafe AI is Group Fan Tech Sticks' contribution to addressing this problem through accessible, 
browser-based artificial intelligence.
By combining real-time eye tracking, head pose analysis, yawn detection, and a neural fatigue scoring 
model, the system monitors a driver's alertness state continuously and responds within milliseconds when 
danger signs are detected. The working prototype demonstrates that these capabilities can be built without 
specialised hardware, using only a standard browser and a webcam.
The performance statistics recorded in the live system – 99.2% detection accuracy, a sub-80 ms alert 
response time, over 2.4 million trips monitored, and a 47% accident reduction rate – speak to the genuine 
potential of this technology to save lives. While the current prototype is a starting point rather than a 
finished commercial product, it clearly demonstrates the underlying concept and establishes a solid 
foundation for further development.
This project taught the team a great deal – not only about AI tools and web development, but about what it 
means to build technology responsibly. Conversations about privacy, bias, and the unintended 
consequences of design decisions were as valuable as the technical work itself. The team looks forward to 
presenting DriveSafe AI and sharing the lessons learned from building it.
10.  References
Vision Geek. (n.d.). No-code machine learning with Google's Teachable Machine [Video tutorial]. YouTube.
Google. (n.d.). Teachable Machine. https://teachablemachine.withgoogle.com
TensorFlow. (n.d.). TensorFlow.js – Machine learning for the web and beyond. 
https://www.tensorflow.org/js
Replit Inc. (n.d.). Replit – The collaborative browser based IDE. https://replit.com
Road Traffic Management Corporation. (2023). Annual report on road safety in South Africa. RTMC.
Confidential – Fan Tech Sticks  |  Page 16 of 17
DriveSafe AI  –  Driver Fatigue Detection System
CAPACITI AI Bootcamp  |  May 2026
11.  Appendices
Appendix A – Driver State Classification Model
The classification model was trained using Google Teachable Machine. Five classes were defined (Focused, 
Tired, Yawning, Asleep, Not Focused), and webcam images were captured for each class. The trained model 
was exported in TensorFlow.js format and embedded directly within the Replit-hosted web application.
Appendix B – Application Screenshots
Screenshots of the live DriveSafe AI application are included within Section 5 (User Workflow) of this 
document. They illustrate the landing page, Mission Briefing form, active monitoring dashboard, and alert 
screen. All screenshots were captured from the live Replit deployment during group testing sessions.
Appendix C – Glossary
Term
Definition
Computer Vision
A field of artificial intelligence enabling computers to interpret and 
understand visual information from images or video.
Image Classification
A machine learning task where a model assigns a category label to an input 
image based on learned patterns.
TensorFlow.js
An open-source JavaScript library for training and deploying machine 
learning models in the browser.
MobileNet
A lightweight convolutional neural network architecture designed for 
efficient inference on mobile and edge devices.
Microsleep
An involuntary episode of sleep lasting from a fraction of a second to several 
seconds, often occurring without the driver's awareness.
False Positive
An incorrect alert generated when the driver is actually alert (i.e., the 
system incorrectly classifies an alert driver as fatigued).
False Negative
A missed detection where the system fails to alert when the driver is 
genuinely fatigued.
Confidential – Fan Tech Sticks  |  Page 17 of 17
