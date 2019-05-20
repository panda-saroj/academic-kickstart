+++
title = "Obstacle Tower" 
date = 2019-05-17T00:00:00

# Authors. Comma separated list, e.g. `["Bob Smith", "David Jones"]`.
authors = ["Saroj Panda"]

#List format.
#0 = Simple
#1 = Detailed
#2 = Stream
list_format = 2

# Tags (optional).
#   Set `tags = []` for no tags, or use the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = ["Abstract"]

# Step to follow.
Obstacle_Tower="1) Obstacle Tower."
advancemenuimg=""


#Optional featured image (relative to static/img/ folder).
[header] 
image = "" 
caption = "" 
+++

Video games have increasingly been used as AI benchmarks. In contrast to classic board games, video games require more frequent decision making, often in real-time settings, and additionally define more complex state spaces. They may also have some combination of hidden information, stochasticity, complex interaction rules, and large branching factors. Modern video game-based AI benchmarks do not provide agents with processed representations of the environment. The agents have to act based on the raw pixels, i.e. the screen output that they receive from the environment. The advancement of reinforcement learning using deep neural networks as function approximators, so called deep reinforcement learning, are now capable of processing high-dimensional input such as screen images. 

The agents trained using such deep reinforcement learning(Deep RL) algorithms are now able to play many Atari 2600 video games at a human-competitive level.  But, one of the game Montezuma’s Revenge was very hard for reinforcement learning algorithms because of the sparse rewards and partial observability. This challenge promoted development of several novel approaches to Deep RL algorithms including methods which focus on providing intrinsic reward signals based on state visitation, to methods for hierarchical agent control to learning from demonstrations. Some of these research results started to claim that they have solved the game, but those algorithm results don’t seem to apply to many problems outside of that one game. The Obstacle Tower project was conceived to create a new challenge that was both difficult in the traditional ways people think of reinforcement learning problems as being difficult, namely in visual complexity, the need for dexterity, and the need for planning. Most importantly the project requires generalization in the agents learning. 

The Obstacle Tower is a procedurally generated 3D video game consisting of multiple floors to be solved by a learning agent. It is designed to test learning agent’s abilities in computer vision, locomotion skills, high-level planning, and most importantly generalization. It combines platforming-style gameplay with puzzles and planning problems, and critically, increases in difficulty as the agent progresses. Within each floor, the goal of the agent is to arrive at the set of stairs leading to the next level of the tower. These floors are composed of multiple rooms, each which can contain their own unique challenges. Each floor contains several procedurally generated elements, such as visual appearance, puzzle configuration, and floor layout. This ensures that for an agent to be successful at the Obstacle Tower task, they must be able to generalize to new and unseen combinations of conditions.

Agents trained using the current state of the art Deep RL algorithms such as OpenAI Baseline implementation of Proximal Policy Optimization (PPO) and implementation of Rainbow provided by Google Brain’s Dopamine library have suboptimal performance compared to human players. These trained agents could achieve average floor completion score of 6 compared to human players who could achieve average floor completion score of more than 15. The reason for that seems to be these trained agents get stuck at the introduction of locked doors and keys on floor 5 or introduction of puzzle rooms on some floors. These state of the art Deep RL algorithms seem to have difficulty adapting to drastically new tasks.
    
To solve the Obstacle Tower, the agent must both learn a complex set of behaviors under varying visual circumstances and scene configurations and to learn good abstract representations and generalize that can easily be re-used under very different circumstances.

<h5> References: </h5>
1.	https://arxiv.org/pdf/1902.01378.pdf
2.	https://medium.com/@cxbxmxcx/an-interview-with-dr-arthur-juliani-from-unity-on-the-otc-and-more-7d866381e1b2

