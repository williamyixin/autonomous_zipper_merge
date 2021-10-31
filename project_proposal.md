# Project Proposal 

## Goals
We will implement merging and disengaging on two platoons of robots. In particular, when two platoons meet at a merge, we want the two platoons to merge into a single platoon using zipper merge. We will also implement platoon disengaging where robots can split into two platoons.

## Approach
In the beginning, we would have platoons traveling along a black tape. We will maintain this as a Doubly Linked List, where each robot would be able to know the robot before and after it. The robots would be able to communicate any speeding decisions to robots in front and after it. Each robots would also have a radar or ultrasonic sensor so that it can detect the physical distance between each robot. We can also use accelerometer, gyroscope, and encoder readings to position the robot kinetically, and compare it to robots before and after it. 

### Video of Concept

https://www.youtube.com/watch?v=Hon3XX8OO88

### Merging
Two platoons travelling independently would encounter a merge. Let these two platoons be platoon A and B, with platoon B merging into platoon A. We will denote entering the merge with a piece of colored tape in each lane. Once the platoons receive the signal of a merge occurring, it would send out a signal such that the other platoon would be aware of a merge taking place. Platoon would create additional space between their cars so that the cars in platoon B can insert themselves into the space, much like a zipper. Cars in platoon B would pull up to the end of their lane, and insert themselves in the appropriate times. The cars in platoon B will know when to insert themselves based on signals sent by platoon A when checkpoints are passed. If no more cars in platoon A remain, all cars in platoon B will merge automatically. The platoon would send a signal when the last robot of the platoon B exits the junction, denoted by another piece of colored tape at the exit. Finally, all gaps within the now unified platoon (AB) will be closed.

note from will: idk if we need this b elow part, because I think we're only trying to merge 2 platoons? merging more platoons might result in overcomplicating the problem for ourselves
If the platoon received a signal during the process that another platoon is trying to merge, it would clear the junction such that any cars that haven't entered would stop. Once the junction has cleared, the platoon would give a signal and yield the right of way. The other platoon is then allowed to let one car go through, send a signal once it's done, and yield the right of way. This would continue until one platoon runs out of cars, and the rest of the platoon would be stacked. Afterwards, one of the platoons would be eliminated, and the entire platoon linked list would be reorganized to contain robots from both platoons.


### Disengaging
When given the signal to separate, which should contain which cars would separate, the cars that separates would watch for exits to the right. Once the exit has been spotted, they would remove themselves from the original platoon and form a new platoon. Then, robots in each platoon would close the gap. 

## Resources

3 Distance sensors per romi 
4-5 romi's 


## Schedule

October 31: Finish Project Proposal 
November 7: Have FSM drawn out, order neccessary parts, start figuring out/exploring Romi code, construct skeleton code needed for project
November 14: Figure out how to attach and use distance sensors on cars, and find how to use colored tape to detect checkpoints. Find how to send signals from one robot to another. 
November 21: Figure out how to create set distance gaps between cars within one platoon, and how to have all cars in a platoon to drive up to a certain checkpoint denoted by a piece of colored tape. 
November 28: Write merging code, start testing
December 5: Continue testing
December 12: Conclude testing, write final report, make video


## Risks and Feasibility 

One risk is that we have no guarantee that the romi's will drive straight. This project is fully dependent on the fact that the romi's will exhibit consistent movement throughout the demo. 

## Github Link
https://github.com/williamyixin/autonomous_zipper_merge
