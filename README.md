# VCS-2018-2019-Robot
#include "robot-config.h"
/*+++++++++++++++++++++++++++++++++++++++++++++| Notes |++++++++++++++++++++++++++++++++++++++++++++++

Robot Configuration:
[Smart Port]    [Name]        [Type]           [Description]       [Reversed]
Motor Port 1    LeftMotor     V5 Smart Motor    Left side motor     false
Motor Port 10   RightMotor    V5 Smart Motor    Right side motor    true
Motor Port 12    ArmMotor1      V5 Smart Motor    Arm motor          false
Motor Port 11    ArmMotor2     V5 Smart Motor    Claw motor         false
Motor Port 20    ArmMotor3     V5 Smart Motor    Claw motor         false  

----------------------------------------------------------------------------------------------------*/     

    void pre_auton( void ) {
            

    }
    
void autonomous( void ){
    
         
}

void usercontrol(void){
    
    int armSpeedPCTUp = 100;
    int clawSpeedPCTUp = 100;
    int downPCT = 30;
    
    while(true) {
        
       
        LeftMotor.spin(vex::directionType::fwd, Controller1.Axis2.value(), vex::velocityUnits::pct);
       
        RightMotor.spin(vex::directionType::fwd, Controller1.Axis3.value(), vex::velocityUnits::pct);
        
    
        if(Controller1.ButtonR1.pressing()) { 
      
            ArmMotor1.spin(vex::directionType::fwd, clawSpeedPCTUp, vex::velocityUnits::pct);
            
        }
        else if(Controller1.ButtonR2.pressing()) {
           
            ArmMotor1.spin(vex::directionType::rev, downPCT, vex::velocityUnits::pct);
            
        }
        else if (Controller1.ButtonL1.pressing()){
        ArmMotor2.spin(vex::directionType::rev,armSpeedPCTUp, vex::velocityUnits::pct);
           ArmMotor3.spin(vex::directionType::fwd,armSpeedPCTUp, vex::velocityUnits::pct);
    }
    
        else if (Controller1.ButtonL2.pressing()){
          
        ArmMotor2.spin(vex::directionType::fwd,downPCT, vex::velocityUnits::pct);
        ArmMotor3.spin(vex::directionType::rev,downPCT, vex::velocityUnits::pct);
    }
    
        else {
          
            ArmMotor1.stop(vex::brakeType::brake);
        
            ArmMotor2.stop(vex::brakeType::brake);
            
            ArmMotor3.stop(vex::brakeType::brake);
             }
        }
}
    
int main() {
    

    
    Competition.autonomous( autonomous );
    
    Competition.drivercontrol( usercontrol );

}
