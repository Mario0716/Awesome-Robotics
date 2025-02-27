# Awesome-Robotics

| Title | Conference & Journal | Understanding |Q|
|:---------:|:---------:|:---------:|:---------:|
|Data Scaling Laws in Imitation Learning For Robotic Manipulation | ICLR 2025 & CoRL 2024 Best Paper | 在机器人的单任务上，研究数据规模和泛化性的关系，研究发现数据多样性（包括环境，目标物以及两者的样本对）对提升机器人模型泛化性上大致符合幂律法则，有着很重要的影响，然而内容描述数据的规模在超过一定阈值后对训练不再产生影响。 |power-law relationship应该广泛适用于RL,IRL等领域；<br>如果推广到稍微复杂一些的任务，数据多样性应该是很庞大的，包括但不限于环境和目标物等因素|
|Diffusing States and Matching Scores: A New Framework for Imitation Learning| ICLR 2025 | 该篇文章提出了一个新的模仿学习结构，通过 Diffusing States 和 Matching Scores 来增强的学习效果。||
|Adaptive Compliance Policy:Learning Approximate Compliance for Diffusion Guided Control| ICRA2025 |由于较难找到完美的合规性策略，作者使用了近似学习来完成最优合规性策略的估计，然后通过Q函数的学习和更新，不断调整智能体的行为，达到近似最优合规的目标||
