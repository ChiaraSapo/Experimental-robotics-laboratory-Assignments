Experimental robotics laboratory Assignments
dialog_manager 
It has an internal function that simulates the raw data coming from a microphone driver. Commands can be 
- "go to n1 n2", where n1 and n2 can be any 2 integer numbers,
- "hey buddy"
- "play"
and they are generated randomly and at 50% of the time.
In the first case the dialog manager sends the entire string. In the second two cases it sends the string request_to_play.

image_manager
It has an internal function that simulates the person's position and a gesture position computed from an image from a camera. In practice it generates 4 random numbers to represent two sets of coordinates. 
It sends  the two desired coordinates.

geometry_grounding
It analyzes the command in input: 
- if it is a "go to" command, it estrapolates from it the coordinates 
- if it is a "go_home" command, it sets the home coordinates 
- if it is a "go_rand" command, it computes random coordinates
It sends the coordinates in output.

planner
It computes a simple trajectory to get from the current position to the target position. Then it saves as current position the target position (Hypothesis: robot can always manage to reach the point, maybe remove this hypothesis later). It sends the trajectory.

robot_motion_controller
It should control the robots actuators in order to make it move. In practice it waits 2 seconds and then sends signal goto_finished and current pos

state manager
work in progress

