# Awesome-Robotics

| Title📖 | Conference & Journal📅 | Understanding🧠 |Question🤔|
|:---------|:---------|:---------|:---------|
|Data Scaling Laws in Imitation Learning For Robotic Manipulation | ICLR 2025 & CoRL 2024 Best Paper | 在机器人的单任务上，研究数据规模和泛化性的关系，研究发现数据多样性（包括环境，目标物以及两者的样本对）对提升机器人模型泛化性上大致符合幂律法则，有着很重要的影响，然而内容描述数据的规模在超过一定阈值后对训练不再产生影响。 |power-law relationship应该广泛适用于RL,IRL等领域;<br>正如作者所讲的目前限于single-task，还没有完成task-generlization，workload应该是很巨大的，如果推广到稍微复杂一些的任务，数据多样性应该是很庞大的，包括但不限于环境和目标物等因素;|
|Diffusing States and Matching Scores: A New Framework for Imitation Learning| ICLR 2025 | 该篇文章提出了一个新的模仿学习结构，通过 Diffusing States 和 Matching Scores 来增强的学习效果。||
|Adaptive Compliance Policy:Learning Approximate Compliance for Diffusion Guided Control| ICRA2025 |由于较难找到完美的合规性策略，作者使用了近似学习来完成最优合规性策略的估计，然后通过Q函数的学习和更新，不断调整智能体的行为，达到近似最优合规的目标||
|Look Before You Leap: Unveiling the Power of GPT-4V in Robotic Vision-Language Planning|arxiv2023| GPT4V to Robotic Vision-Language Planning|大模型的龙卷风到了Robotic|
|Explaining and Harnessing Adversarial Examples|ICLR2015|首次提出了对抗样本问题，并提出了通过对抗训练来提高模型鲁棒性的思路，以及模型可以通过对抗训练，正则化，梯度裁剪和数据增强等方法消除noise的影响|经典👍，伟大无需多言|
|Dream to Manipulate: Compositional World Models Empowering Robot Imitation Learning with Imagination|ICLR2025|文章的主要工作包括：<br>使用高斯泼溅 object-centric Gaussian Splatting 生成3D目标物的表征; <br>从相机中获取的视频处理成帧后，进行图像分割操作; <br>利用物理引擎PyBullet预测模型在真实环境中的后续动作; <br> 对demonstration进行等变变换（Equivariant Transformations）来帮助机器人生成imagination;  |说实话，给我看的云里雾里的。文章后面的等变变换不就是数据增强吗？经过高斯泼溅生成的object representation已经有点抽象了，真的有用吗？作者的motivation可以理解，无非是针对IL的短板去丰富样本集。|
|Diffusion Policy: Visuomotor Policy Learning via Action Diffusion| RSS2023|在视觉-运动控制任务中，文章基于强化学习的框架使用扩散模型生成robot动作序列，逐步优化生成的动作轨迹以获得连续、平滑的动作轨迹;图像特征提取就是传统的CNN-Based和Transformer-Based，文章中给出的performance都是基于Transformer的；此外还结合了控制理论来帮助理解在简单任务下的局限性；|Diffusion结合Action，这个方法确实是获得连续且平滑动作序列的不错方式，但是推理速度和计算成本应该是有局限性的;（这篇文章看了蛮久...），代码也需要认真解读一下|
|Supervised Policy Learning for Real Robots|RSS 2024 Tutorial|Start Simple.|1✅,2⌛️,3⌛️,4✅|
|Hierachical Diffusion Policy: manipulation trajectory generation via contact guidance|arxiv|文章提出了一个分层扩撒策略，一共两个层次：高层负责接触规划，底层负责轨迹生成;按照这个思想，文章设计了三个模块，分别为Guider，Critic和Actor，前两个分别负责提供robot接触位置和判断当前动作序列的Q值，动作执行模型则负责生成T时间段内的动作序列并传递给Critic，由Crtic筛选出短期步长内的动作执行动作，从而避免“很久以前的动作”对后续动作产生的影响；对于数据处理，文章将感知输入编码为点云形式，作为robot当前的状态输入。|逐步train three networks是不是有点难顶；文章在设计目标物接触位置/路线的时候使用人工标定的方式作为prompt|
|VQ-BeT: Behavior generation with latent actions|ICML2024|||

## Waiting List
|Title📖    |Year🧓 |Status🪣  |
|:---------|:---------|:---------|
|RLBench: The Robot Learning Benchmark & Learning Environment|ICRA2020|⌛️Robo Benchmark|
|Rvt-2: Learning precise manipulation from few demonstrations|2024|🙏|
|3d gaussian splatting for real-time radiance field rendering|2023|🙏Generation|
|Robodreamer: Learning compositional world models for robot imagination|2024|🙏World Model|
|Instant Policy: In-Context Imitation Learning via Graph Diffusion|ICLR2025 Oral|⌛️Imitation Learning|
|Open X-Embodiment: Robotic Learning Datasets and RT-X Models|Dataset2023|⌛️|
|VQ-BeT: Behavior generation with latent actions|ICML2024|⌛️Policy Leaning|
|UMI: Universal Manipulation Interface: In-The-Wild Robot Teaching Without In-The-Wild Robots|RSS2024|⌛️Data Collection|
|ALOHA: Learning Fine Grained Bimanual Manipulation with Low-Cost Hardware|RSS2023|⌛️Policy Learning & Data Collecyion|


## ROS🤖
I am learning about Robot Operating System(ROS) from [AJie](https://www.bilibili.com/video/BV1BP4y1o7pw) on Bilibili website.

Completion: 10/77 ⌛️

## Simulator💻
Considering the complexity of differnt simulators, choose [MUJOCO](https://github.com/google-deepmind/mujoco) as the first step to help me test robot(Galaxea A1 and Franka Research 3). Maybe, [Nvidia Issac Gym for C++/Python](https://developer.nvidia.com/isaac-gym) and [Drake for C++/Python](https://drake.mit.edu/) are also good choice. Besides, we can learn about introduction and basic knowledge about MUJOCO from [Prof.Wei Zhang, SUSTech](https://www.bilibili.com/video/BV1wPyfYHEmE).
