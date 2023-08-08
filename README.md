# LunarLander-DL-NMA23

Project on Reinforcement Learning done during [Deep Learning Neuromatch Academy 2023](https://deeplearning.neuromatch.io).

## Environment ##
LunarLander environment from Gymnasium package developed by OpenAI
* [Gymnasium documentation](https://gymnasium.farama.org/environments/box2d/lunar_lander/)
* [Gymnasium code](https://github.com/Farama-Foundation/Gymnasium)

## Task ##
<img src="https://github.com/pdzialecka/LunarLander-DLNeuromatch23/blob/main/Figures/cLunarLanderCp_env.png"  height="50%" width="50%">

1. Train the agent to land safely (+100 points) -> **cLunarLander** environment
2. Train the agent to visit a checkpoint (+100 points) before landing (+100 points) -> modified **cLunarLanderCp** environment

## RL algorithm ##
Deep Q Network [(DQN](https://stable-baselines3.readthedocs.io/en/master/modules/dqn.html); stable_baselines3)

## Models ##
1. **Pretrained**: Pretrained model in basic cLunarLander environment, iterations = 75k
2. **FreshL_r**: Fresh model trained in modified cLunarLanderCp environment, iterations = 75k
3. **FreshL**: Fresh model trained in modified cLunarLanderCp environment, iterations = 150k
4. **TL**: Transfer learning approach: pretrained model in basic cLunarLander environment (1) + further training in modified cLunarLanderCp, iterations = 75k + 75k

All tested in modified cLunarLanderCp environment

## Results ##
<img src=https://github.com/pdzialecka/LunarLander-DLNeuromatch23/blob/main/Figures/reward_results.png  height="50%" width="50%">

**% of trials landed**
Model  | Accuracy (%)
------------- | -------------
Pretrained (1)  | 99.0
FreshL_r (2) | 20.2
FreshL (3) | 0.0
TL (4) | 53.4



***% of trials with checkpoint visited**
Model  | Accuracy (%)
------------- | -------------
Pretrained (1) | 0.6
FreshL_r (2) | 48.8
FreshL (3) | 0.0
TL (4) | 10.6

## Model performance ##
1. Learns how to land well but does not know about the checkpoint
2. Learns to visit the checkpoint in ~50% of cases, lands only in 20% of cases 
3. Worst performance: learns neither to land nor to visit the checkpoint
4. Learns to land in ~50% of cases, visits checkpoint ~10% of cases

### Potential further improvements for the TL model ###
* Longer training time
* Improved reward function
* Different RL algorithm, e.g. PPO

## Starting point ##
[Performance Analysis of DQN Algorithm on the Lunar Lander task](https://github.com/pdzialecka/course-content-dl/blob/main/projects/ReinforcementLearning/lunar_lander.ipynb)
