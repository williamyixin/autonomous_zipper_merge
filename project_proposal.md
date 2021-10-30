# Project Proposal 

## Goals
We will implement merging and disengaging on two platoons of robots. In particular, when two platoons meet at a merge, we want the two platoons to merge into a single platoon using zipper merge. We will also implement platoon disengaging where robots can split into two platoons.

## Approach
In the beginning, we would have platoons traveling along a black tape. We will maintain this as a Doubly Linked List, where each robot would be able to know the robot before and after it. The robots would be able to communicate any speeding decisions to robots in front and after it. Each robots would also have a radar or ultrasonic sensor so that it can detect the physical distance between each robot. We can also use accelerometer, gyroscope, and encoder readings to position the robot kinetically, and compare it to robots before and after it. 

### Merging
Two platoons travelling independently would encounter a merge. We will denote entering the merge with a peice of colored tape. Once a platoon encounters the merge, it would send out a signal such that other platoons would be aware of a merge taking place, and it would actively listen to similar signals. The platoon would send a signal when the last robot of the platoon exits the junction, denoted by another peice of colored tape at the exit. If the platoon received a signal during the process that another platoon is trying to merge, it would clear the junction such that any cars that haven't entered would stop. Once the junction has cleared, the platoon would give a signal and yield the right of way. The other platoon is then allowed to let one car go through, send a signal once it's done, and yield the right of way. This would continue until one platoon runs out of cars, and the rest of the platoon would be stacked. Afterwards, one of the platoons would be eliminated, and the entire platoon linked list would be reorganized to contain robots from both platoons.

### Disengaging
When given the signal to separate, which should contain which cars would separate, the cars that separates would watch for exits to the right. Once the exit has been spotted, they would remove themselves from the original platoon and form a new platoon. Then, robots in each platoon would close the gap. 

## Resources

## Risks

## Github Link
https://github.com/williamyixin/autonomous_zipper_merge
