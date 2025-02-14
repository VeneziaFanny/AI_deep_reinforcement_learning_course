#### UNIT 1 : Introduction to Deep Reinforcement Learning

##### 1. What is Reinforcement Learning?

Reinforcement learning is a framework for solving control tasks (also called decision problems) by building agents that learn from the environment by interacting with it through trial and error and receiving rewards (positive or negative) as unique feedback.

##### 2. The Reinforcement Learning Framework

* The RL Process

This RL loop outputs a sequence of state, action, reward and next state.
The agent’s goal is to maximize its cumulative reward, called the expected return.

In papers, you’ll see that the RL process is called a Markov Decision Process (MDP).
The Markov Property implies that our agent needs only the current state to decide what action to take and not the history of all the states and actions they took before.

* Observations/States Space

State s: is a complete description of the state of the world (there is no hidden information). In a fully observed environment.

Observation o: is a partial description of the state. In a partially observed environment.

* Action Space

The Action space is the set of all possible actions in an environment.

Discrete space: the number of possible actions is finite.
Continuous space: the number of possible actions is infinite.

* Rewards and the discounting

The reward is fundamental in RL because it’s the only feedback for the agent. Thanks to it, our agent knows if the action taken was good or not.

##### 3. Type of tasks

* Episodic task/Continuing tasks

A task is an instance of a Reinforcement Learning problem. We can have two types of tasks: episodic and continuing.

In this case, we have a starting point and an ending point (a terminal state). This creates an episode: a list of States, Actions, Rewards, and new States.

These are tasks that continue forever (no terminal state). In this case, the agent must learn how to choose the best actions and simultaneously interact with the environment.

##### 4. The Exploration/Exploitation trade-off

Exploration is exploring the environment by trying random actions in order to find more information about the environment.
Exploitation is exploiting known information to maximize the reward.

Remember, the goal of our RL agent is to maximize the expected cumulative reward. However, we can fall into a common trap.

We need to balance how much we explore the environment and how much we exploit what we know about the environment.

##### 5. Two main approaches for solving RL problems

* The Policy π: the agent’s brain

The Policy π is the brain of our Agent, it’s the function that tells us what action to take given the state we are in. So it defines the agent’s behavior at a given time.

* Policy-Based Methods
In Policy-Based methods, we learn a policy function directly.
This function will define a mapping from each state to the best corresponding action. Alternatively, it could define a probability distribution over the set of possible actions at that state.

We have two types of policies:

Deterministic: a policy at a given state will always return the same action.
Stochastic: outputs a probability distribution over actions.

* Value-based methods
Our value function defined values for each possible state.

Thanks to our value function, at each step our policy will select the state with the biggest value defined by the value function: -7, then -6, then -5 (and so on) to attain the goal.

##### 6. The “Deep” in Reinforcement Learning

Deep Reinforcement Learning introduces deep neural networks to solve Reinforcement Learning problems — hence the name “deep”.

You’ll see the difference is that, in the first approach, we use a traditional algorithm to create a Q table that helps us find what action to take for each state.

In the second approach, we will use a Neural Network (to approximate the Q value).

##### 7. Summary

That was a lot of information! Let’s summarize:

Reinforcement Learning is a computational approach of learning from actions. We build an agent that learns from the environment by interacting with it through trial and error and receiving rewards (negative or positive) as feedback.

The goal of any RL agent is to maximize its expected cumulative reward (also called expected return) because RL is based on the reward hypothesis, which is that all goals can be described as the maximization of the expected cumulative reward.

The RL process is a loop that outputs a sequence of state, action, reward and next state.

To calculate the expected cumulative reward (expected return), we discount the rewards: the rewards that come sooner (at the beginning of the game) are more probable to happen since they are more predictable than the long term future reward.

To solve an RL problem, you want to find an optimal policy. The policy is the “brain” of your agent, which will tell us what action to take given a state. The optimal policy is the one which gives you the actions that maximize the expected return.

There are two ways to find your optimal policy:

By training your policy directly: policy-based methods.
By training a value function that tells us the expected return the agent will get at each state and use this function to define our policy: value-based methods.

Finally, we speak about Deep RL because we introduce deep neural networks to estimate the action to take (policy-based) or to estimate the value of a state (value-based) hence the name “deep”.

##### 8. Exercices

LunarLander : https://huggingface.co/queenVdu13/ppo-LunarLander-v2

Train Huggy : https://huggingface.co/queenVdu13/ppo-Huggy