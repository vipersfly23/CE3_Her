CE3_Her
=======
##Rules to Follow:
•	It has two external inputs, Up_Down and Stop.
•	When Up_Down is active and Stop is inactive, the elevator will move up until it reaches the top floor (one floor per clock, of course).
•	When Up_Down is inactive and Stop is inactive, the elevator will move down until it reaches the bottom floor (one floor per clock).
•	When Stop is active, the system stops at the current floor.  
•	When the elevator is at the top floor, it will stay there until Up_Down goes inactive while Stop is inactive.  Likewise, it will remain at the bottom until told to go up and Stop is inactive.  
•	The system should output the floor it is on (1 – 4) as a four-bit binary number.

===================================
##Moore Elevator Controller:


![alt text](https://github.com/vipersfly23/CE3_Her/blob/master/Moore_Simulation.GIF?raw=true "simulation result")

##  Explanation:
  I believe my design is functional based on my simulation because the elevator only moves when up_down = 1, and stop is inactive. It also meets the requirement of  stopping at least 2 clk period on each level. Whenever stop is active, the elevator stops on that floor until stop is inactive, up_down active again. once the elevator hits the fourth floor as displayed in the simulation diagram, the simulation stops on the four floor for at least two clock cycles then moves down to the first floor, floor by floor when both stop and up_down is inactive.
  
  [Moore Module](https://github.com/vipersfly23/CE3_Her/blob/master/MooreElevatorController_Shell.vhd)
  
  [Moore TestBench](https://github.com/vipersfly23/CE3_Her/blob/master/MooreElevatorTB.vhd_)

  
  


===================================
##Mealy Elevator Controller:

![alt text](https://github.com/vipersfly23/CE3_Her/blob/master/Mealy_Simulation.GIF?raw=true "Simulation Result")

## Answers: 
*Question: Will it be different from your Moore Machine?*
The only difference between the mealy machine and the moore machine is that the mealy machine takes in the input, and outputs the next move, and the current move based on the inputs, while the moore just takes in the input and performs the task, and outputs the current move.

##  Explanation:

  I believe this is correct because it does exactly as expected with the exception of the unreliability of the mealy machine. Since it has to remember the next state in-between cycles when the stop goes from active to inactive and the floor has not changed, the mealy system auto assumes next floor is 1, until the next floor is approached. I believe this is a flaw in the mealy machine and not my implementation. The jump can be observed by the yellow line.
  
  [Mealy Module](https://github.com/vipersfly23/CE3_Her/blob/master/MealyElevatorController_Shell.vhd)
  
  [Mealy TestBench](https://github.com/vipersfly23/CE3_Her/blob/master/Mealy_testbench_Her.vhd)



===================================
## Documentation: 

No other receieved.




