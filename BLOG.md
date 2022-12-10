
# Reinforcement Learning -- ML For Decision Making

## A. Introduction to Reinforcement Learning

Reinforcement is the field of machine learning concerning an agent learning how to behave in an environment, through performing actions and learning based upon the outcomes of these actions.  Reinforcement learning is one of the three basic machine learning paradigms, alongside supervised learning and unsupervised learning. 

Preliminaries:
1. An agent
2. Environment
3. A set of actions applied by agent to the environment
4. A set of observations and reinforcement returned from the environment

After applying actions, the agent receives a reward indicating how good the action was through a scalar reward function. The agent aims to maximize the reward, in order to obtain the required goal set by the system to accomplish. 

![This is an image](https://github.com/SiyaoChen103/Reinforcement-Learning/blob/main/RL-image.jpg?raw=true)

#### Two Fundemental Challenges
##### 1. Data is not i.i.d. (independent and identically distributed)
Unlike supervised learning where the input data comes from a fixed source, the observation/data used in reinforcement learning is created by the agent on its own, and influenced by actions the agent did. Thus, the data is not independent and identically distributed.

##### 2. Ground truth actions are often not available
Reinforcement learning also differs from supervised learning in that there is no label provided. No instruction is given to the agent on how to perform actions, and the agent has to figure out on its own.

## B. Types of Reinforcement
  ### 1. Positive Reinforcement
Positive Reinforcement is when the resulted event from a particular behavior leads to an **increase** in strength and frequency of the behavior. In other words, the resulting event has a positive effect on the behavior.

**Advantages:**
 - The performance is maximized
 - The change is sustained for a long period of time.
 
**Disadvantages:**
 - Too much reinforcement can lead to n overload of states and diminished result

  ### 2. Negative Reinforcement
Negative Reinforcement is defined as the strengthening of behavior, as a result of some negative condition being stopped or avoided. 
  
**Advantages:**
 - The behavior is increased

**Disadvantages:**
 - Only the minimum behavior of the model can be reached

## C. How does agent decide which action to take?
### **1. Policy**
A policy is a selection model used by an agent to pursue its goals. The policy dictates the actions as a function of the agent’s state and the environment.

#### Mathematics 
We define a policy \pi in terms of the Markov Decision Process, which is a framework borrowed from the problem of optimal control.
      
### **2. Value function**
  - Value function is a reward signal received by the agent to indicate the quality of the action taken.
      `
