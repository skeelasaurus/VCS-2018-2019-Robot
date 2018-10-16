# VCS-2018-2019-Robot
int main() {
    
    
    Brain.Screen.print("Tank Control Program Started");
    
    
    int armSpeedPCT = 50;
    int clawSpeedPCT = 50;
    
    
    while(1) {
        
       
        LeftMotor.spin(vex::directionType::fwd, Controller1.Axis3.value(), vex::velocityUnits::pct);
       
        RightMotor.spin(vex::directionType::fwd, Controller1.Axis2.value(), vex::velocityUnits::pct);
        
        
        if(Controller1.ButtonUp.pressing()) { 
      
            ArmMotor.spin(vex::directionType::fwd, armSpeedPCT, vex::velocityUnits::pct);
        }
        else if(Controller1.ButtonDown.pressing()) {
           
            ArmMotor.spin(vex::directionType::rev, armSpeedPCT, vex::velocityUnits::pct);
        }
        else {
          
            ArmMotor.stop(vex::brakeType::brake);
        }
        
       
        if(Controller1.ButtonA.pressing()) { 
           
            ClawMotor.spin(vex::directionType::fwd, clawSpeedPCT, vex::velocityUnits::pct);
        }
        else if(Controller1.ButtonY.pressing()) { 
           
            ClawMotor.spin(vex::directionType::rev, clawSpeedPCT, vex::velocityUnits::pct);
        }
        else { 
            
            ClawMotor.stop(vex::brakeType::brake);       
        }
        
		vex::task::sleep(20); 
    }

}
