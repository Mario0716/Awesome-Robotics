# Awesome-Robotics

| Title📖 | Conference & Journal📅 | Understanding🧠 |Question🤔|
|:---------|:---------|:---------|:---------|
|Data Scaling Laws in Imitation Learning For Robotic Manipulation | ICLR 2025 & CoRL 2024 Best Paper | 在机器人的单任务上，研究数据规模和泛化性的关系，研究发现数据多样性（包括环境，目标物以及两者的样本对）对提升机器人模型泛化性上大致符合幂律法则，有着很重要的影响，然而内容描述数据的规模在超过一定阈值后对训练不再产生影响。 |power-law relationship应该广泛适用于RL,IRL等领域;<br>正如作者所讲的目前限于single-task，还没有完成task-generlization，workload应该是很巨大的，如果推广到稍微复杂一些的任务，数据多样性应该是很庞大的，包括但不限于环境和目标物等因素;|
|Diffusing States and Matching Scores: A New Framework for Imitation Learning| ICLR 2025 | 该篇文章提出了一个新的模仿学习结构，通过 Diffusing States 和 Matching Scores 来增强的学习效果。||
|Adaptive Compliance Policy:Learning Approximate Compliance for Diffusion Guided Control| ICRA2025 |由于较难找到完美的合规性策略，作者使用了近似学习来完成最优合规性策略的估计，然后通过Q函数的学习和更新，不断调整智能体的行为，达到近似最优合规的目标||
|Look Before You Leap: Unveiling the Power of GPT-4V in Robotic Vision-Language Planning|arxiv2023| GPT4V to Robotic Vision-Language Planning|大模型的龙卷风到了Robotic|
|Explaining and Harnessing Adversarial Examples|ICLR2015|首次提出了对抗样本问题，并提出了通过对抗训练来提高模型鲁棒性的思路，以及模型可以通过对抗训练，正则化，梯度裁剪和数据增强等方法消除noise的影响|经典👍，伟大无需多言|
|Dream to Manipulate: Compositional World Models Empowering Robot Imitation Learning with Imagination|ICLR2025|文章的主要工作包括：<br>使用高斯泼溅 object-centric Gaussian Splatting 生成3D目标物的表征; <br>从相机中获取的视频处理成帧后，进行图像分割操作; <br>利用物理引擎PyBullet预测模型在真实环境中的后续动作; <br> 对demonstration进行等变变换（Equivariant Transformations）来帮助机器人生成imagination;  |说实话，给我看的云里雾里的。文章后面的等变变换不就是数据增强吗？经过高斯泼溅生成的object representation已经有点抽象了，真的有用吗？作者的motivation可以理解，无非是针对IL的短板去丰富样本集。|
|Diffusion Policy: Visuomotor Policy Learning via Action Diffusion| RSS2023|在视觉-运动控制任务中，文章基于强化学习的框架使用扩散模型生成robot动作序列，逐步优化生成的动作轨迹以获得连续、平滑的动作轨迹，对于策略优化部分采用了逆强化学习（Inverse Reinforcement Learning）的思想；图像特征提取就是传统的CNN-Based和Transformer-Based；|Diffusion结合Action，这个方法确实是获得连续且平滑动作序列的不错方式|
|Efficient Reductions for Imitation Learning|arxiv|为了简化模仿学习任务，文章提出了几种简化方法，<br>将学习任务拆分成两部分，第一部分在低维度空间内进行预训练，第二部分在高维度状态和动作空间进行优化 <br>探索和优化结合 <br>减少奖励函数 <br>结合转移学习，减少学习所需的专家演示数量，让IL学习之前任务已经学到的知识||

## Waiting List
|Title📖    |Year🧓 |Status🪣  |
|:---------|:---------|:---------|
|RLBench: The Robot Learning Benchmark & Learning Environment|ICRA2020|⌛️|
|Rvt-2: Learning precise manipulation from few demonstrations|2024|🙏|
|3d gaussian splat- ting for real-time radiance field rendering|2023|🙏|
|Robodreamer: Learning compositional world models for robot imagination|2024|🙏|
|Instant Policy: In-Context Imitation Learning via Graph Diffusion|ICLR2025 Oral|⌛️|
|Open X-Embodiment: Robotic Learning Datasets and RT-X Models|2023|⌛️|
