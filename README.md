# Initial-Code----Basic-Navigation-Variables-and-Functions
Robotics Assignment
#include <kipr/botball.h>
//Michael Goldberg

int l_motor = 0;
int r_motor = 3;
int speed = 400;
int pause = 750;
int low_speed = 100;  

int main()
{
    while(1){	 //stuff I want to loop 
        forward();	//look for a collision event
	
        if(digital(0)){//if a collision is detected...
				backward();
				 left();
            }
            if(digital(4)){
                backward();
                right();
            }
    }
    printf("I like class\n");
    return 0;
}
//FUNCTION DEFINITIONS//
void forward(){
    motor(l_motor,speed);//go foward 
    motor(r_motor,speed);   
}
void backward(){
	 motor(l_motor,-low_speed); //go backward
	 motor(r_motor,-low_speed);
	 msleep(750);
     ao();
}
	void right(){
    motor(l_motor,speed); // try to turn right
    motor(r_motor,-speed);
    msleep(1000);
	ao();
}
void left(){
    motor(r_motor,speed); //try to turn left
    motor(l_motor,-speed);
    msleep(1000);
	ao();
}
