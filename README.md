#include "robot-config.h"
/*+++++++++++++++++++++++++++++++++++++++++++++| Notes |++++++++++++++++++++++++++++++++++++++++++++++
Arcade Control 
This program instructs your robot to use remote control values to move the robot. 

Robot Configuration:
[Smart Port]    [Name]        [Type]           [Description]       [Reversed]
Motor Port 1    LeftMotor     V5 Smart Motor    Left side motor     false
Motor Port 10   RightMotor    V5 Smart Motor    Right side motor    true
Motor Port 3    ArmMotor      V5 Smart Motor    Arm motor          false
Motor Port 8    clawMotor     V5 Smart Motor    Claw motor         false

----------------------------------------------------------------------------------------------------*/     
int main() {
    
    
    Brain.Screen.print("Tank Control Program Started");
    
    
    int armSpeedPCT = 50;
    int clawSpeedPCT = 50;
    
    
    while(1) {
        
       
        LeftMotor.spin(vex::directionType::fwd, Controller1.Axis3.value(), vex::velocityUnits::pct);
       
        RightMotor.spin(vex::directionType::fwd, Controller1.Axis2.value(), vex::velocityUnits::pct);
        
    }
      
