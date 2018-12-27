# CarND-Controls-PID
Self-Driving Car Engineer Nanodegree Program - PID Control project

---
## Basic Build Instructions

1. Clone this repo.
2. Make a build directory: `mkdir build && cd build`
3. Compile: `cmake .. && make`
4. Run it: `./pid`. 

## Rubric points
### Describe the effect each of the P, I, D components had in your implementation.  
The P, or "proportional", component had the most directly observable effect on the car's behavior. It causes the car to steer proportional (and opposite) to the car's distance from the lane center (which is the CTE) - if the car is far to the right it steers hard to the left, if it's slightly to the left it steers slightly to the right.

The D, or "differential", component counteracts the P component's tendency to ring and overshoot the center line. A properly tuned D parameter will cause the car to approach the center line smoothly without ringing.

The I, or "integral", component counteracts a bias in the CTE which prevents the P-D controller from reaching the center line. This bias can take several forms, such as a steering drift (as in the Control unit lessons), but I believe that in this particular implementation the I component particularly serves to reduce the CTE around curves.

### Describe how the final hyperparameters were chosen.
The parameters were chosen manually in this project. First, make sure the car can drive straight with zero as parameters. Then add the proportional and the car start going on following the road but it starts overshooting go out of it. Then add the differential to try to overcome the overshooting. The integral part only moved the car out of the road; so, it stayed as zero. 

The final parameters where [P: 0.13, I: 0.0, D: 3.0].


This project was run in Udacity workspace, but I was not able to open the recording functionality... here just past a screenshot below.    
<img src="image/pid tuning.JPG" width="800">  
