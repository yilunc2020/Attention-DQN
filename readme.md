# Deep Recurrent Attention Reinforcement Learning

10703 course project.
See this file for details. https://cl.ly/1h3b2k3f3H3X/10703_Course_Project_Proposal.pdf

## There are two types of attention to implement:
- Temporal attention (already implemented; enable with the `--a_t' flag. See this report http://cs229.stanford.edu/proj2016/report/ChenYingLaird-DeepQLearningWithRecurrentNeuralNetwords-report.pdf or this post https://github.com/fchollet/keras/issues/1629

- Spatial attention (implemented in TF). See this paper: https://arxiv.org/abs/1512.01693

## How to run in recurrent DQN mode **without** temporal attention
``python dqn_atari.py --env=Assault-v0 --train --net_mode=duel --num_episodes_at_test=20 --task_name 'RNN_keras' --num_frames 10 --recurrent --replay_memory_size=500000``

## How to run in recurrent DQN mode **with** spatial attention
``python dqn_atari.py --env=Seaquest-v0 --train --net_mode=dqn --num_episodes_at_test=20 --task_name 'RNN_dqn_tf_a-tSpatial_selectorON' --num_frames 10 --recurrent --replay_memory_size=500000 --a_t --selector``

## Important note
In Line 11 of ``den_atari.py``:
- ``from deeprl_prj.dqn import DQNAgent`` if you are using **Keras**

- ``from deeprl_prj.dqn_tf import DQNAgent`` if you are using **TF** 

- ``from deeprl_prj.dqn_tf_spatialAt import DQNAgent`` if you are using **TF** with spatial **attention**
