# MDP REPRESENTATION
## NAME : Mahesh Raj Purohit J
## REG.NO.:212222240058
## AIM:
To represent the Drone Navigation System in Markov Decision Process (MDP) form and implement it in Python for simulation.

## PROBLEM STATEMENT:
Autonomous drones must navigate complex environments efficiently while avoiding collisions, managing battery life, and optimizing energy use.

### Problem Description
The drone is tasked with navigating a predefined environment containing obstacles (trees and buildings) while minimizing travel time and energy consumption. The drone must find the optimal path from the Start (Base) to the Goal (Arrival point) using Reinforcement Learning (RL) principles.

### State Space
- I – Start (Base)
- II – Intermediate State (No Obstacles)
- III – Terminal State (Building)
- IV – Terminal State (Tree)
- V – Intermediate State (No Obstacles)
- VI – Goal (Arrival point)

### Sample State
```Start (I) -> Intermediate (II) -> Intermediate (V) -> Goal (VI)```

### Action Space
The drone can perform four main types of movements:
- P (0) – Pitch: Move Forward (a) or Backward (b)
- R (1) – Roll: Rotate Right (a) or Left (b)
- Y (2) – Yaw: Turn Right (a) or Left (b)
- T (3) – Thrust: Move Up (a) or Down (b)

### Sample Action
2a >> 0a >> 1a >> 0a
Start (I) -> Intermediate (II) -> Intermediate (V) -> Goal (VI)

### Reward Function
Reward Function = { +1, if reaching the Goal (VI)
                   0, Otherwise }

### Graphical Representation
![image](https://github.com/user-attachments/assets/1f73dab7-8952-47e7-a411-a7b31d5dd44a)


## PYTHON REPRESENTATION:
mdp = {
    'I': {0: [('IV', 0.05, 0), ('II', 0.95, 0)], 1: [('I', 0, 0)], 2: [('I', 0, 0)], 3: [('I', 0, 0)]},
    'II': {0: [('V', 0.99, 0)], 1: [('III', 0.05, 0)], 2: [('II', 0, 0)], 3: [('II', 0, 0)]},
    'III': {0: [('III', 0, 0)], 1: [('III', 0, 0)], 2: [('III', 0, 0)], 3: [('III', 0, 0)]},
    'IV': {0: [('IV', 0, 0)], 1: [('IV', 0, 0)], 2: [('IV', 0, 0)], 3: [('IV', 0, 0)]},
    'V': {0: [('V', 0, 0)], 1: [('VI', 0.99, 1)], 2: [('V', 0, 0)], 3: [('V', 0, 0)]},
    'VI': {0: [('VI', 1, 0)], 1: [('VI', 1, 0)], 2: [('VI', 1, 0)], 3: [('VI', 1, 0)]}
}

## OUTPUT:
```c
{0: {0: [(1.0, 0, 0.0, False)],
     1: [(1.0, 4, 0.0, False)],
     2: [(1.0, 1, 0.0, False)],
     3: [(1.0, 0, 0.0, False)]},
 1: {0: [(1.0, 0, 0.0, False)],
     1: [(1.0, 5, 0.0, True)],
     2: [(1.0, 2, 0.0, False)],
     3: [(1.0, 1, 0.0, False)]},
 2: {0: [(1.0, 1, 0.0, False)],
     1: [(1.0, 6, 0.0, False)],
     2: [(1.0, 3, 0.0, False)],
     3: [(1.0, 2, 0.0, False)]},
 3: {0: [(1.0, 2, 0.0, False)],
     1: [(1.0, 7, 0.0, True)],
     2: [(1.0, 3, 0.0, False)],
     3: [(1.0, 3, 0.0, False)]},
 4: {0: [(1.0, 4, 0.0, False)],
     1: [(1.0, 8, 0.0, False)],
     2: [(1.0, 5, 0.0, True)],
     3: [(1.0, 0, 0.0, False)]},
 5: {0: [(1.0, 5, 0, True)],
     1: [(1.0, 5, 0, True)],
     2: [(1.0, 5, 0, True)],
     3: [(1.0, 5, 0, True)]},
 6: {0: [(1.0, 5, 0.0, True)],
     1: [(1.0, 10, 0.0, False)],
     2: [(1.0, 7, 0.0, True)],
     3: [(1.0, 2, 0.0, False)]},
 7: {0: [(1.0, 7, 0, True)],
     1: [(1.0, 7, 0, True)],
     2: [(1.0, 7, 0, True)],
     3: [(1.0, 7, 0, True)]},
 8: {0: [(1.0, 8, 0.0, False)],
     1: [(1.0, 12, 0.0, True)],
     2: [(1.0, 9, 0.0, False)],
     3: [(1.0, 4, 0.0, False)]},
 9: {0: [(1.0, 8, 0.0, False)],
     1: [(1.0, 13, 0.0, False)],
     2: [(1.0, 10, 0.0, False)],
     3: [(1.0, 5, 0.0, True)]},
 10: {0: [(1.0, 9, 0.0, False)],
      1: [(1.0, 14, 0.0, False)],
      2: [(1.0, 11, 0.0, True)],
      3: [(1.0, 6, 0.0, False)]},
 11: {0: [(1.0, 11, 0, True)],
      1: [(1.0, 11, 0, True)],
      2: [(1.0, 11, 0, True)],
      3: [(1.0, 11, 0, True)]},
 12: {0: [(1.0, 12, 0, True)],
      1: [(1.0, 12, 0, True)],
      2: [(1.0, 12, 0, True)],
      3: [(1.0, 12, 0, True)]},
 13: {0: [(1.0, 12, 0.0, True)],
      1: [(1.0, 13, 0.0, False)],
      2: [(1.0, 14, 0.0, False)],
      3: [(1.0, 9, 0.0, False)]},
 14: {0: [(1.0, 13, 0.0, False)],
      1: [(1.0, 14, 0.0, False)],
      2: [(1.0, 15, 1.0, True)],
      3: [(1.0, 10, 0.0, False)]},
 15: {0: [(1.0, 15, 0, True)],
      1: [(1.0, 15, 0, True)],
      2: [(1.0, 15, 0, True)],
      3: [(1.0, 15, 0, True)]}}
```

## RESULT:
Thus, the MDP representation of the Drone Navigation System has been successfully implemented and represented in Python.

