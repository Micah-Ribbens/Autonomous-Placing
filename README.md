Finished Development: 04/05/2023

# Getting the code (not published yet)
Wrist: NA

Claw: NA

GrabAndGo: NA

# Summary
The main automation of the placing sequence was in a subsystem called GrabAndGo. It controlled the interactions among the other subsystems to automate the task of placing a game piece.
This subsystem can be thought of like an orchestrator with each other subsystem being an instrument. 
The individual subsystems do not know about how their actions affect the entire process. They follow the orchestrator who knows what the entire process is. 
Let's run through a quick, simplified example of how a piece went from being on the ground to being placed:

- The driver presses the pick button, so the GrabAndGo tells the picker to come down, which will put the game piece into the chamber.
- Once the chamber senses the game piece, the GrabAndGo tells the arm to go into a position that grabs the game piece. The claw will also be told to open and close at the right time to grab the game piece.
- The GrabAndGo tells the arm to go into the "transport" position. The transport position is the position that allowed the robot to drive and have the game piece secured.
- When the driver presses the place button, the GrabAndGo will tell the arm to go to the placing position. GrabAndGo then waits for the driver to press the release game piece button.
- Once the driver presses the release game piece button, the GrabAndGo tells the claw to drop the game piece onto the target. Then the GrabAndGo tells the arm to go back to the home position.


## State Diagram
For diagram simplicity we split the diagram into two parts: one for cube and one for cone. The states that share the same 
name are identical. The reason we did this was because of how many different arrows there would be within the diagram making 
it more confusing to look at.
![GrabAndGoStateDiagram](documentation/GrabAndGoStateDiagram.png?raw=true)

## Simplified Arm Positions Diagram
![ArmPositionsDiagram](documentation/SimplifiedArmPositions.png?raw=true)