# Team 4 - Team3_deathwing

## Lab 4:

### Final project- TurtleBot Path-finding and Automatic Parking

# Code structure

## 1. Wall follower & finding goal 
 The [wall follower](https://github.com/THD-autonomous-system/team3_deathwing/blob/main/Lab4_final/Code/wall_following.py) class will navigate through its surroundings using a wall follower algorithm. The process consists of the following steps: 
 - First robot will save the starting position coordinate and start moving towards closest wall. 
 - The robot will locate the closest wall and save the cordinates. 
 - It will then follow the wall while avoiding any obstacles.
 - Once the robot has completed a full lap of the environment, it will come to a halt and store the all possible parking spot.

## 2.Mapping 
The [mapping](https://github.com/THD-autonomous-system/team3_deathwing/blob/main/Lab4_final/Code/mapping.py) class will operate simultaneously with the wall follower function, using LIDAR values to gather information about the environment and its positions. 
 - It will store data about all detected obstacles in the form of coordinates and keep a record of this information in a file called "ranges.txt".


## Methodology

##### Wall follower:
We built a wall following algorithm where our bot would forward until it finds a point and turn right as soon as it reaches a first nearest wall.

##### Mapping:
A SLAM method is used by the robot to map out its surroundings. Data from the LIDAR is used to built a map and saved in a range.txt file. The LIDAR gives the intensity values in the map and black-tap value is shown in black or blue color.

##### Localization:
The robot uses information from its sensors to pinpoint where the desired point is in the map which would we later used for parking.

##### Returning to Original Position:
After completing the wall follow and mapping, subtask is to reach the starting position. These were achieved by navigating towards the starting position using PI controller and A* algorithm.

##### Path Planning:
The robot plans a path to the assigned parking space using the navigation stack. To accomplish this, one can use the environment's various characteristics or park according to the marked lines.

##### Locating the nearest parking spot:  
Using the information gathered during mapping and all possible parking spots, calculate the distance respect to all parking spots and find nearest parking spot.
plan a path for nearest parking spot and start moving towards it.
