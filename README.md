# Speed-Detection
Skip to content
Product
Solutions
Open Source
Pricing
Search
Sign in
Sign up
This repository has been archived by the owner on Jun 1, 2022. It is now read-only.
kraten
/
vehicle-speed-check
Public archive
Code
Issues
10
Pull requests
1
Actions
Projects
Security
Insights
vehicle-speed-check/README.md
@kraten
kraten Update README.md
Latest commit d830b17 on Jun 1, 2022
 History
 2 contributors
@karansthr@kraten
61 lines (40 sloc)  2.45 KB

Vehicle Speed Detection
This repo is no longer maintained.


Technologies used :

Python
opencv
dlib

Tasks breakdown

Vehicle Detection
We are using Haarcascade classifier to identify vehicles.
Vehicle Tracking - ( assigning IDs to vehicles )
We have used corelation tracker from dlib library.
Speed Calculation
We are calculating the distance moved by the tracked vehicle in a second, in terms of pixels, so we need pixel per meter to calculate the distance travelled in meters.
With distance travelled per second in meters, we will get the speed of the vehicle.
How to run project?
Follow steps:

Clone repo : git clone https://github.com/2110030326/Speed-Detection

cd (change directory) into vehicle-speed-check cd vehicle-speed-check

Create virtual environment python -m venv venv

Activate virtual environment ./venv/bin/activate

Install requirements pip install  -r requirements.txt

run speed_check.py script python speed_check.py

Note:
A lot of you were raising the same issue about code understanding. I know that I haven't properly commented out the code. So, here is the brief summary of what the code does and how-

We have estimated these values manually for the current road to calculate pixels per metre(ppm). Therefore, the value will vary from road to road and have to be adjusted to be used on any other video.

If I talk about the part how we estimated ppm, we need to know the actual width in metres of the road(you can use google to find the approximate width of the road in your country). Also, we have taken the video frame and calculated the width of the road in pixels digitally. Now, we have the width of the road in metres from the real world and in pixels from our video frame. To map the distances between these two worlds, we have calculated pixels per metre by dividing distance of road in pixels to metres.

d_pixels gives the pixel distance travelled by the vehicle in one frame of our video processing. To estimate speed in any standard unit first, we need to convert d_pixels to d_metres.

Now, we can calculate the speed(speed = d_meters * fps * 3.6). d_meters is the distance travelled in one frame. We have already calculated the average fps during video processing. So, to get the speed in m/s, just (d_metres * fps) will do. We have multiplied that estimated speed with 3.6 to convert it into km/hr.

Pull requests are welcome
Footer
© 2023 GitHub, Inc.
Footer navigation
Terms
Privacy
Security
Status
Docs
Contact GitHub
Pricing
API
Training
Blog
About
