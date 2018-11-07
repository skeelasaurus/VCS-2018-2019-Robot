 if(Controller1.ButtonR1.pressing()) { 
      
            ArmMotor1.spin(vex::directionType::fwd, armSpeedPCT, vex::velocityUnits::pct);
            
        }
        else if(Controller1.ButtonL1.pressing()) {
           
            ArmMotor1.spin(vex::directionType::fwd, armSpeedPCT, vex::velocityUnits::pct);
            
        }
        else if (Controller1.ButtonR2.pressing()){
        ArmMotor1.spin(vex::directionType::rev,armSpeedPCT, vex::velocityUnits::pct);
    }
    
      else if (Controller1.ButtonL2.pressing()){
          
        ArmMotor2.spin(vex::directionType::rev,armSpeedPCT, vex::velocityUnits::pct);
    }
    
    else {
          
            ArmMotor1.stop(vex::brakeType::brake);
            ArmMotor2.stop(vex::brakeType::brake);
        }
    }     
       
