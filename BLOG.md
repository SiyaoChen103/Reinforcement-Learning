
# Reinforcement Learning -- ML For Decision Making

## A. Introduction to Reinforcement Learning

Reinforcement is the field of machine learning concerning an agent learning how to behave in an environment, through performing actions and learning based upon the outcomes of these actions.  Reinforcement learning is one of the three basic machine learning paradigms, alongside supervised learning and unsupervised learning. 

Preliminaries:
1. An agent
2. Environment
3. A set of actions applied by agent to the environment
4. A set of observations and reinforcement returned from the environment

After applying actions, the agent receives a reward indicating how good the action was through a scalar reward function. The agent aims to maximize the reward, in order to obtain the required goal set by the system to accomplish. 

![agent_environment_image](https://github.com/SiyaoChen103/Reinforcement-Learning/blob/main/RL-image.jpg?raw=true)

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
A policy is a selection model used by an agent to pursue its goals, and dictates the actions as a function of the agent’s state and the environment.

#### Terminology
We define a policy $\pi$ in terms of the Markov Decision Process, which is a framework borrowed from the problem of optimal control.
A policy is basically a neural network that takes an observation $o_{t}$, or state $s_{t}$ as input, and generate action $a_{t}$ as output. 
- A policy that takes an observation as input is called an **observational policy**, written as **$\pi(a_{t}|o_{t})$**
- A policy that takes a state as input is called a **state-based policy**, written as **$\pi(a_{t}|s_{t})$**

*(Note: an observation is a 2-Dimensional complete description of the environment, while a state is a lower-dimensional information that determine particular parts of the environment.)*

The architecture of the policy is dependent on the input. For example, if the input is an image, then we could use CNN; if the input is a state, then we could use deep neural network; if the input is graph like data,then we could use graph network.


#### Steps
1. Once an observation $o_{t}$ is provided as input to the policy $\pi(a_{t}|o_{t})$, the network generates an output action $a_{t}$.
2. Immediately after the action is applied, agent receives a new observation, $o_{t+1}$.
3. $o_{t+1}$ then goes into the same policy $\pi(a_{t+1}|o_{t+1})$, and the network generates a new output $a_{t+1}$, which then creates a new observation $o_{t+2}$...
...


![Policy_image](https://github.com/SiyaoChen103/Reinforcement-Learning/blob/main/RL-image2.jpg?raw=true)

In summary, an agent' behavior in an environment is specified by a policy that maps the current state to a set of probabilities for taking each action. 

      
### **2. Value function**
Value function is a reward signal observed by the agent upon taking action, indicating the quality of the action. A policy is called optimal if it achieves the best-expected return from any initial state.

### **State-value Function** 
A **state-value function** is the expected return from a given state. Taking state as an input, the function predicts the expected reward for each possible action the agent could take. If the action is good, the state-value function will be high.

We define the value of a policy $\pi$ by **$V_{\pi}(s)=E_{\pi}[R_{t}|S_{t} = s]$**, where R is the return associated with following $\pi$ from the initial state s.  


### **Action-value Function**
Another helpful function is **action-value function**: **$Q_{\pi}(s,a)=E_{\pi}[R_{t}|S_{t} = s, A_{t} = a]$**.
The action-value function describes the expected return if the agent selects an action with the respect to policy and current state.


### **Optimal Policy**
To recall, the goal in reinforcement learning is to find the policy that obtains the most reward possible over the long run, which is the optimal policy. An optimal policy is defined as the policy with the highest possible value function in all states.

We can find the optimal policy using optimal value function, such as the Bellman equation, which defines a relationship between the value of a state, or state-action pair, and its possible successors. Upon solving the optimal value function, we can evaluate our policies to find theoptimal policy.


In summary, value functions estimate future return under a certain policy, and an optimal policy is the policy that achieves the highest value possible in each state. 

