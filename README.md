# Awesome-Robotics

Hi~👋 Welcome Everyone interested in robotics to Follow, to Suggest and to Push my project!😈

- [Awesome-Robotics](#awesome-robotics)
  - [Papers📝](#papers) 
  - [Waiting List⛑️](#waiting-list️)
  - [ROS🤖](#ros)
  - [Simulator💻](#simulator)
  - [Machine Learning \& Deep Learning 🏰](#machine-learning--deep-learning-)
  - [Robotics💼](#robotics)
  - [Control🎳](#control)
  - [Code🧑‍💻](#code)
  - [Equipment Setting🧪](#equipment-setting)

## Papers📝

| Title📖 | Conference & Journal📅 | Understanding🧠 |Question🤔|
|:---------|:---------|:---------|:---------|
|Data Scaling Laws in Imitation Learning For Robotic Manipulation<br>[pdf](https://arxiv.org/abs/2410.18647) [project page](https://data-scaling-laws.github.io/) [code](https://github.com/Fanqi-Lin/Data-Scaling-Laws) | ICLR 2025 & CoRL 2024 Workshop Best Paper | 在机器人的单任务上，研究数据规模和泛化性的关系，研究发现数据多样性（包括环境，目标物以及两者的样本对）对提升机器人模型泛化性上大致符合幂律法则，有着很重要的影响，然而内容描述数据的规模在超过一定阈值后对训练不再产生影响。 |power-law relationship应该广泛适用于RL,IRL等领域;<br>正如作者所讲的目前限于single-task，还没有完成task-generlization，workload应该是很巨大的，如果推广到稍微复杂一些的任务，数据多样性应该是很庞大的，包括但不限于环境和目标物等因素;|
|Diffusing States and Matching Scores: A New Framework for Imitation Learning<br>[pdf](https://openreview.net/forum?id=kWRKNDU6uN) [code](https://github.com/ziqian2000/SMILING)| ICLR 2025 | 该篇文章提出了一个新的模仿学习结构，通过 Diffusing States 和 Matching Scores 来增强的学习效果。||
|Adaptive Compliance Policy:Learning Approximate Compliance for Diffusion Guided Control<br>[pdf](https://arxiv.org/abs/2410.09309) [project page](https://adaptive-compliance.github.io/) [code](https://github.com/yifan-hou/adaptive_compliance_policy)| ICRA2025 |由于较难找到完美的合规性策略，作者使用了近似学习来完成最优合规性策略的估计，然后通过Q函数的学习和更新，不断调整智能体的行为，达到近似最优合规的目标||
|Look Before You Leap: Unveiling the Power of GPT-4V in Robotic Vision-Language Planning<br>[pdf](https://arxiv.org/abs/2311.17842) [project page](https://robot-vila.github.io/)|arxiv2023| GPT4V to Robotic Vision-Language Planning|大模型的龙卷风到了Robotic|
|Explaining and Harnessing Adversarial Examples<br>[pdf](https://arxiv.org/abs/1412.6572)|ICLR2015|首次提出了对抗样本问题，并提出了通过对抗训练来提高模型鲁棒性的思路，以及模型可以通过对抗训练，正则化，梯度裁剪和数据增强等方法消除noise的影响|经典👍，伟大无需多言|
|Dream to Manipulate: Compositional World Models Empowering Robot Imitation Learning with Imagination<br>[pdf](https://openreview.net/forum?id=3RSLW9YSgk) [project page](https://dreamtomanipulate.github.io/) [code](https://github.com/leobarcellona/drema_code)|ICLR2025|文章的主要工作包括：<br>使用高斯泼溅 object-centric Gaussian Splatting 生成3D目标物的表征; <br>从相机中获取的视频处理成帧后，进行图像分割操作; <br>利用物理引擎PyBullet预测模型在真实环境中的后续动作; <br> 对demonstration进行等变变换（Equivariant Transformations）来帮助机器人生成imagination;  |说实话，给我看的云里雾里的。文章后面的等变变换不就是数据增强吗？经过高斯泼溅生成的object representation已经有点抽象了，真的有用吗？作者的motivation可以理解，无非是针对IL的短板去丰富样本集。|
|Diffusion Policy: Visuomotor Policy Learning via Action Diffusion<br>[pdf](https://arxiv.org/abs/2303.04137) [code](https://github.com/real-stanford/diffusion_policy) [zhihu](https://zhuanlan.zhihu.com/p/670555655) [bilibili](https://www.bilibili.com/video/BV1ZaeAe7EMu/?share_source=copy_web&vd_source=8f61948ca06d95eaa429d48386c8e460)| RSS2023|在视觉-运动控制任务中，文章基于模仿学习的框架使用扩散模型生成robot动作序列，逐步优化生成的动作轨迹以获得连续、平滑的动作轨迹;图像特征提取就是传统的CNN-Based和Transformer-Based，文章中给出的performance都是基于Transformer的；此外还结合了控制理论来帮助理解在简单任务下的局限性；|Diffusion结合Action，这个方法确实是获得连续且平滑动作序列的不错方式，但是推理速度和计算成本应该是有局限性的;（这篇文章看了蛮久...），代码也需要认真解读一下|
|Supervised Policy Learning for Real Robots<br>[project page](https://supervised-robot-learning.github.io/)|RSS 2024 Tutorial|Start Simple.|1✅,2⌛️,3⌛️,4✅|
|Hierachical Diffusion Policy: manipulation trajectory generation via contact guidance<br>[pdf](https://arxiv.org/abs/2411.12982) [code](https://github.com/dexin-wang/Hierarchical-Diffusion-Policy)|arxiv|文章提出了一个分层扩撒策略，一共两个层次：高层负责接触规划，底层负责轨迹生成;按照这个思想，文章设计了三个模块，分别为Guider，Critic和Actor，前两个分别负责提供robot接触位置和判断当前动作序列的Q值，动作执行模型则负责生成T时间段内的动作序列并传递给Critic，由Crtic筛选出短期步长内的动作执行动作，从而避免“很久以前的动作”对后续动作产生的影响；对于数据处理，文章将感知输入编码为点云形式，作为robot当前的状态输入。|逐步train three networks是不是有点难顶；文章在设计目标物接触位置/路线的时候使用人工标定的方式作为prompt|
|VQ-BeT: Behavior generation with latent actions<br>[pdf](https://arxiv.org/abs/2403.03181) [project page](https://sjlee.cc/vq-bet/) [code](https://github.com/jayLEE0301/vq_bet_official)|ICML2024(SOTA)|文章针对Behavior Transformer（BeT）关于k值选取和对高维或长序列所导致的梯度缺失问题，在第一阶段沿用了VQ-VAE中的量化向量编码-解码思想，完成动作序列编码-解码的任务；此外，在第二阶段引入了MiniGPT来进行编码预测（Code Prediction head）和偏离纠正（Offset head），来帮助重构采样动作序列。VQ-BeT在实验效果和执行效率上都有着不错的表现。|在实验部分，为什么Goal-Conditional behavior generation效果还要更差一些呢？反而是Unconditional behavior generation的效果在 5 of 6 tasks表现的都很好。文章中未给出模型参数量的比较，但是可以推测到：VQ-BeT的参数量应该是（远）大于Diffusion Policy等算法的，空间换时间的经典操作|
|RVT-2: Learning precise manipulation from few demonstrations<br>[pdf](https://arxiv.org/abs/2406.08545) [project page](https://robotic-view-transformer-2.github.io/) [code](https://github.com/nvlabs/rvt)|RSS2024|文章相比于RVT主要表现在可以完成高精度任务以及提升了推断和执行效率，模型采用了多阶段设计，第一层将输入RGB-D图像重构为点云后，由多视角Transformer粗略完成热力点的预测（夹爪的触点）；在第二阶段，由三个虚拟机位放大预测位置4倍，再交由多视角Transformer进行细粒度热力点预测，输出给机械臂完成抓取工作（MVT提供抓取位置，热力点的图像输入MLP后得到夹爪方向，开关和是否碰撞等信息）|RVT2将RVT中的5个虚拟摄像机位减少到了3个，此外手搓了新的点云渲染补丁并基于GPU加速方式调整了像素点索引值和深度值的精度，也算是针对执行效率提升做了针对性的工作🫡|
|Instant Policy: In-Context Imitation Learning via Graph Diffusion<br>[pdf](https://openreview.net/forum?id=je3GZissZc) [project page](https://www.robot-learning.uk/instant-policy) [code](https://github.com/vv19/instant_policy)|ICLR2025|作者以图神经为结构，可以简单的理解为GNN+Diffusion Policy，对于得到每个节点的特征部分（不同的节点作用是不同的，分别代表着动作，机器人状态->基本就是夹爪的开关状态，目标物的信息），都要先融合上一个节点的特征，然后再进行K（加噪声）+K（去噪声）步的扩散生成，最后注意力融合周围edge和邻节点特征信息到当前节点；在测试过程中，对其预测夹爪状态（开/关）与Ground Turth，又引入了SVD损失为模型执行动作时加一层保障|先说这个模型的训练过程...这个过程...挺好🙂...可能这样的操作才保证了每个节点特征信息丰富以及模型的zero-shot transfer，(当复习Graph Neural Networks🥱)；用图神经网络去解释上下文学习是有说服力的，毕竟图网络的结构优势在那里摆着|
|RLBench: The Robot Learning Benchmark & Learning Environment<br>[pdf](https://arxiv.org/abs/1909.12271)|ICRA2020 & RA-L2020|提供了一个标准的robotic learning benchmark，包括强化学习，模仿学习和元学习|直接上手搞，别废话😾|
|Open X-Embodiment: Robotic Learning Datasets and RT-X Models<br>[pdf](https://arxiv.org/abs/2310.08864) [project page](https://robotics-transformer-x.github.io/)|arxiv2023-dataset|这篇文章会不会成为未来最大规模的多任务，多机器人的学习数据集我不确定？但应该会是计算机上合作者最众多的一次。|引用张巍老师在课堂上的一句话“未来的趋势是什么？是开源，是派森”🤣|
|Safe Controller Optimization for Quadrotors with Gaussian Processes<br> [pdf](https://arxiv.org/abs/1509.01066) [video](https://www.youtube.com/watch?v=GiqNQdzc5TI)|ICRA2016-Controller|文章是通过数据驱动的方式(GP + SafeOpt)来优化控制器参数，在保障安全的前提下提升控制器的稳定性，适应实时的环境变化|感觉如何初始化Safe Set 应该是非常重要的‼️|
|DroneDiffusion: Robust Quadrotor Dynamics Learning with Diffusion Models<br>[pdf](https://arxiv.org/abs/2409.11292)|ICRA2025-Dynamics Learning|作者使用条件扩散模型来捕捉环境中的多模态干扰（确定性干扰如风速，负载等，不确定性干扰如未知障碍物，环境突然变化等），并引入滑模变量构建混合控制器，融合预测与实时应变能力，帮助无人机在多变的环境中保持飞行和负载稳定；扩散模型以传感器数据（位置，速度）和控制输入为input，训练拟合多模态残差 $\mathcal{H}$|首先这个模型强依赖于传感器数据，如果传感器不能及时获取准确有效的参数，DM预测值应该会有较大偏差；其次，DM模型的计算成本问题，将会给实际部署带来主要的约束🧶|
|Safe Bayesian Optimization for the Control of High-Dimensional Embodied Systems<br>[pdf](https://proceedings.mlr.press/v270/wei25b.html) [project page](https://lnsgroup.cc/research/hdsafebo) [code](https://github.com/yunyuewei/HdSafeBO)|CoRL2024-Controller & Bayesian|针对高维采样和优化问题，采用局部乐观安全策略来优化目标函数并扩大安全区域，具有概率安全保证和设定了累计安全违规界限，此外为了优化几千个变量的高纬输入，引入了等距嵌入（一种降维方法，字面意思应该是对高维特征输入进行等距截断）实现特征变换，并完成了临床实验中通过刺激神经成功优化人体运动控制|这篇论文对具深智能系统控制提供了理论支持，尤其是对高维度信息优化。但是由于作者对安全性的乐观预计和高斯过程的 $\mathcal{O}^3$ 复杂度，限制了该算法在未探索领域实现安全决策和影响了计算效率。|
|"Missing Is Useful": Missing Values in Cost-Sensitive Decision Trees<br>[pdf](https://sci2s.ugr.es/keel/pdf/specific/articulo/Zhang_Qin05.pdf)|TKDE2005-ML|作者提出了“missing is useful”处理缺失数据角度，此外综合和评估了之前四种对缺失数据的处理方法，分别是KV策略（known-value），空策略，内部节点策略和C4.5策略，使用“平均综合成本”（Average Total Cost）作为分类任务的评价指标，得出了内部节点策略是最有效的策略。|为什么我会突然想起来看这篇时间这么久的比较传统的ML文章？首先这是我导师以前的研究工作😂，在很久很久很久以前的与他一年一次的meeting时听他提起过，一直没有看，突然想起来就看一下🙈；站在现在RL+DL的角度去看这篇paper，“missing is useful”仍能给我了一些启发（说明），如果处理“missing”的成本过于高且收益甚微，也许skip是一个不错的思路。|
|Gaussian Process Optimization in the Bandit Setting: No Regret and Experimental Design<br>[pdf](https://icml.cc/Conferences/2010/papers/422.pdf)|ICML2010-GP Optimization|作者提出并从理论上验证了GP-UCB优化算法的有效性，获取函数即算法核心是 $x(t) = \arg\max \mu_{t-1}(x) + \beta\sigma_{t-1}(x)$ ，证明我还没看完，等我肝完...|ICML时间检验奖，喷不了一点，经典👍（就是看起来费脑子💥）|
|DemoGen:Synthetic Demonstration Generation for Data-Efficient Visuomotor Policy Learning<br>[pdf](https://demo-generation.github.io/paper.pdf) [project page](https://demo-generation.github.io/)|arxiv2025-Visumotor Policy|模仿学习的视觉移动任务中存在着有限的空间泛化性，作者通过将演示动作轨迹生成在不同的空间位置，也就是只需要一次示范和采集工作，就可以生成多条演示样例，降低了采样和演示成本的同时提升了推理策略的空间泛化性；此外针对“对于单个任务，为什么有限数量的demonstration会导致模型做出有限或者错误的决策？”这一问题，作者给出了解释：有限数量的示范对于模型在空间位置的影响是局限性的（一条demo只能影响近距离范围的策略学习，不足以覆盖整个平面），所以尽量多的demo可以帮助模型学习整个平面的决策。|[Prof.Xiaocong Li](https://www.xiaocongli.top/)分享了我一个Prof.huazhe xu关于具身智能入门的直播，该篇工作当时出现在了直播内容中，在这里再给聪哥点一个气球🎈:)；这篇工作的局限性如作者所说，本质上并没有在算法层面解决泛化性的问题，而且丰富的样本生成也不能保证robot在平面每一个位置都完成任务，这是由于视觉不匹配问题导致的|
|Stem-OB: Generalizable Visual Imitation Learning with Stem-Like Convergent Observation through Diffusion Inversion<br>[pdf](https://arxiv.org/abs/2411.04919v2) [project page](https://hukz18.github.io/Stem-Ob/)|ICLR2025-Imitation Learning|为了解决imitation learning应用到真实世界中存在的泛化性问题，机器人可能在受到光线，目标纹理改变，位置改变等干扰后而不能成功完成task，这篇文章使用反向扩散模型从视觉信息中逐步去除低级表征信息（纹理，光线，颜色等），从而获取高级语义信息（杯子，桌子，碗等具体内容），成功提高了不同IL在现实世界中不同task成功率|角度是很不错的，从生物学干细胞的角度切入讲了一个挺好的故事，讲故事能力和切入问题能力都值得我学习⛽️|
|Reactive Diffusion Policy:Slow-Fast Visual-Tactile Policy Learning for Contact-Rich Manipulation <br>[pdf](https://arxiv.org/pdf/2503.02881)|arxiv2025-Manipulation|对于以往遥控方法没有触感反馈的问题，本文基于VR头显提出了一个带实时触觉反馈的遥控方法，并将学习方法分为slow policy 和 fast policy两个层次，slow policy用于处理复杂视觉线索生成高级策略修正（指导）fast policy，对于fast policy，通过高频信号（电感信号、力反馈信号）采样反馈给模型和遥控系统，完成closed-loop control。|老师建议参考，还有一篇...多读总是没什么坏处🫨|
|3D Diffusion Policy: Generalizable Visuomotor Policy Learning via Simple 3D Representations<br>[pdf](https://arxiv.org/pdf/2403.03954) [project page](https://3d-diffusion-policy.github.io/) [code](https://github.com/YanjieZe/3D-Diffusion-Policy)|RSS2025|文章针对二维表征对空间泛化的局限性提出了3D表征方式，通过简单的编码器（三层MLP+一层Max Pooling）将点云图像输入映射为64维的紧凑表征，并作为条件输入（3d visual feature & robot pose，后者就是机器人的当前状态）帮助DDIM决策下一次的动作；此外，为了优化模型的推理速度，作者设计了simple DP3通过去除U-Net结构中冗余的部分，将推理速度提升了两倍（牺牲了7%的准确率）|文章不难理解，角度也还行🫢|
|SpatialLM: Large Language Model for Spatial Understanding<br>[project page](https://manycore-research.github.io/SpatialLM/) [code](https://github.com/manycore-research/SpatialLM)|OpenSource2025-LLM|目前开源的一个空间LLM模型，输入3D point cloud数据可以对空间中的物体进行准确的标注和划分，从演示主页的视频中可以看到分割精度和标注准确，可以应用到实际的机器人任务中|精准的空间定位可以作为任务的指导信息，等到公布论文之后可以看一下具体的理论支持，从视频效果看还是很不错的🫣|
|Uni3D: Exploring Unified 3D Representation at Scale<br>[pdf](https://openreview.net/forum?id=wcaE4Dfgt8) [code](https://github.com/baaivision/Uni3D)|ICLR2024-Representation Learning|文章提出了一个3D表征学习框架，使用预训练的CLIP（冻结）处理文本数据，Image ViT（装载预训练模型并冻结）提取图像特征，Uni3D ViT（初始化可以通过装载预训练的2D ViT模型）提取点云特征，训练过程中还需要Uni3D ViT蒸馏学习CLIP Teacher，然后使用对比学习损失完成特征对齐，将三个模态的数据特征映射到一个空间，通过计算两两间的余弦相似度完成多模态检索|有点这方面的想法但是被做掉了😓，那就学习人家是怎么做的吧😮‍💨 从Zero-shot classification的结果看，模型尺寸的变化对结果的影响没有很大，在3%左右，所以在使用的时候可以权衡一下参数量和准确率|
|Objaverse: A Universe of Annotated 3D Objects<br>[pdf](https://openaccess.thecvf.com/content/CVPR2023/papers/Deitke_Objaverse_A_Universe_of_Annotated_3D_Objects_CVPR_2023_paper.pdf) [project page](https://objaverse.allenai.org/)|CVPR2023-dataset|文章提出了一个包含800K+个带标注信息的3D模型数据集，可以应用在生成3D模型(generate 3D models)，改善三维图像分割(image segmentation)和训练目标导航(object navigation)等任务中|公开的一个3D dataset，先码一波|
|Will Scaling Solve Robotics?: Perspectives From CoRL 2023<br>[Youtube](https://www.youtube.com/watch?v=pGjzxdD2Sa4&list=PLtF7v_W_CG5oG_lhI9tA1g4dPJKBOWDsA&index=15) [WeiChat](https://mp.weixin.qq.com/s?__biz=MzkwNDMxMzg1NA==&mid=2247484454&idx=1&sn=33959e198900aeb042cf52fa7bb6e998&chksm=c089aab7f7fe23a19940a624e44123ef67e6d1624cc0dcdc0139542cc736925f727fc94cc75e&scene=21#wechat_redirect)|Talk2023-Robotic Direction|文章和油管的视频主要在讲大数据是否会带领机器人走向通用智能，一方Sergey等三位大佬比较赞同这个研究方向，他们认为LLM和大规模数据训练可以在CV/NLP取得不错的效果，同样的方案策略在机器人学也应该是行得通；另一方Scott等三位控制学巨佬不太看好纯Learning的思路，并给出了Tesla自动驾驶的例子，依赖于data scaling的纯Learning方向会有计算训练成本高、收集数据成本高和不同环境或移动状态下泛化性差等问题|作为番外篇，学习一下大佬们对机器人方向的研究思路和看法，听人劝吃饱饭|
|SafeDiffuser: Safe Planning with Diffusion Probabilistic Models<br>[pdf](https://openreview.net/pdf?id=ig2wk7kK9J#page=0.90) [project page](https://safediffuser.github.io/safediffuser/) [code](https://github.com/Weixy21/SafeDiffuser)|ICLR2025-Planning|文章首先将扩散生成策略与安全限制结合，在满足安全限定条件的前提下，生成起始点到目标状态的连续planning;在引入CBF（Control Barrier Function）限制后，文章提出了三种约束方式，分别是RoS，RES和TVS，根绝环境要求的严格程度选择性使用（迷宫规划，机器人移动，机器人操作）；此外，文章总结了模型容易陷入局部陷阱（e.g. local minial），通过降低约束标准和约束标准随时间变化两种策略减少了问题的发生概率|尽管作者通过改进约束方法，降低了local trap的发生概率，但是发生的概率依旧很高（TRAP RATE1: RES - 39%， TVS - 48 %），也就是说这种问题依旧很容易出现；此外，扩散模型的计算效率依旧堪忧，即使文章将时间优化到了0.040 s/step，total 256step = 10.24s，这也是一个可以有很大优化的角度|
|CL-DiffPhyCon: Closed-Loop Diffusion Control of Complex Physical Systems<br>[pdf](https://arxiv.org/pdf/2408.03124) [code](https://github.com/AI4Science-WestlakeU/CL_DiffPhyCon?tab=readme-ov-file)|ICLR2025 - Control|由于扩散模型在高维度、长时间窗口的显著优势，很多研究工作将扩散控制方法应用到闭环控制上，但是在每一次获得窗口内所有时间步的控制信号和状态都需要经过完整的去噪过程，导致效率很低；文章针对这个问题，提出了闭环控制方法，构建了同步去噪模型和异步去噪模型两个独立模型；首先获取当前物理时刻系统状态和异步联合隐变量，再利用异步扩散模型去噪，将采样到的控制信号应用到系统来获取系统反馈的最新状态和更新后的异步联合隐变量，依次推进；|经观察可以发现，两个扩散模型分别对应着两个分布，即同步扩散模型是从 $p(z_{1:H}(\frac{1}{H}T)\|u_0)$ 中采样，而异步扩散模型的作用是从 $p(z_{\tau : \tau + H -1}(0)\| u_{\tau -1}(0), z_{\tau:\tau +H-1}(\frac{1}{H}T))$ 中采样，所以同步异步相结合即可完成从轨迹数据分布中的无间隔采样，再通过在采样过程中加入控制信号完成优化控制的目标 |
|Visual Autoregressive Modeling: Scalable Image Generation via Next-Scale Prediction<br>[pdf](https://arxiv.org/pdf/2404.02905) [code](https://github.com/FoundationVision/VAR)|NIPS2024-Generative Model|||
|UniGS:Unified Language-Image-3D Pretraining with Gaussian Splatting<br>[pdf](https://arxiv.org/pdf/2502.17860) [code](https://github.com/Li-Hao-yuan/UniGS)|ICLR2025 - 3D Representation|作者做了一个多模态对齐工作，将文本，2D图像，3D高斯泼溅经编码器后映射到同一公共子空间，分别对 文本-3D高斯泼溅 ，2D图像-3D高斯泼溅组合 进行对比学习，从而得到对齐后的统一特征。统一特征可以用在跨模态检索，图像分类，单模态检索等领域。作者还把Trannsformer的self-attention雕一雕花构建了一个CA，也当做了一个创新点，从论文实验的文字描述上看上去是有效的，能提升三个点|个人认为，这篇工作在novelty最多算是tiny change，至于它为什么能被iclr接收就...（大家头脑风暴吧）；关于文章中的Cross-Attention，大家去看一下就估计也会是这个表情😂，不吐槽太多了，希望作者和他的老师做一些真的work的东西吧...|
|Scaling Proprioceptive-Visual Learning with Heterogeneous Pre-trained Transformers<br>[pdf](https://openreview.net/pdf?id=Pf7kdIjHRf) [Project Page](https://liruiw.github.io/hpt/)|NIPS2024 - Embodiment||我是从b站看到一个up主在讲这篇work，我也找来看了看。据说是Kaiming He的第一篇具身智能工作💼|
|Elastic Motion Policy: An Adaptive Dynamical System for Robust and Efficient One-Shot Imitation Learning<br>[pdf](https://arxiv.org/abs/2503.08029)|arxiv2025 - Policy Learning|||

## Waiting List⛑️
|Title📖    |Year🧓 |Status🪣  |
|:---------|:---------|:---------|
|RLBench: The Robot Learning Benchmark & Learning Environment|ICRA2020|⌛️Robo Benchmark(Next One...)➡️03.07✅|
|Rvt-2: Learning precise manipulation from few demonstrations|RSS2024|🙏Manipulation➡️03.05✅|
|3d gaussian splatting for real-time radiance field rendering|2023|🙏Generation|
|Robodreamer: Learning compositional world models for robot imagination|2024|🙏World Model|
|Instant Policy: In-Context Imitation Learning via Graph Diffusion|ICLR2025 Oral|⌛️Imitation Learning➡️03.07✅|
|Open X-Embodiment: Robotic Learning Datasets and RT-X Models|Dataset2023|⌛Multi-Task Multi-Robot Datasets➡️03.07✅|
|VQ-BeT: Behavior generation with latent actions|ICML2024|⌛️Policy Leaning➡️03.05✅|
|UMI: Universal Manipulation Interface: In-The-Wild Robot Teaching Without In-The-Wild Robots|RSS2024|⌛️Data Collection|
|ALOHA: Learning Fine Grained Bimanual Manipulation with Low-Cost Hardware|RSS2023|⌛️Policy Learning & Data Collecyion|
|Humanoid Locamotion as Next Prediction🌟|NIPS2024 Spotlight|⌛️humanoid Contorl|
|Safe Bayesian Optimization for the Control of High-Dimensional Embodied Systems|CoRL2024|⌛️Controller & Bayesian➡️03.10✅|
|On safety in safe bayesian optimization|TMLR2024|⌛️Bayesian Optimization|
|Adaptive and safe bayesian optimization in high dimensions via one-dimensional subspace|ICML2019|⌛️Bayesian Optimization|
|Meta-learning priors for safe bayesian optimization|CoRL2022|⌛️Bayesian Optimization|
|Relaxing the additivity constraints in decentralized no-regret high-dimensional bayesian optimization|ICLR2024|⌛️Bayesian Optimization|
|RL-based adaptive controller for high precision reaching in a soft robot arm|T-RO2024|⌛️Controller➡️03.12 video✅|
|Reaching the limit in autonomous racing: Optimal control versus reinforcement learning|Science Robotics 2023|⌛️Control & Optimization|
|CL-DiffPhyCon: Closed-Loop Diffusion Control of Complex Physical Systems|ICLR2025|⌛️Control➡️✅|
|OpenShape: Scaling Up 3D Shape Representation Towards Open-World Understanding|NIPS2023|⌛️3D Representation Learning|
|Score-based generative modeling through stochastic differential equations|ICLR2021|⌛️Diffusion Model|
|Differentiable Collision Detection for a Set of Convex Primitives|arxiv|⌛️CBF|


## ROS🤖
I am learning about Robot Operating System(ROS) from [AJie](https://www.bilibili.com/video/BV1BP4y1o7pw) on Bilibili website.

Completion: 10/77 ⌛️

ros2 installation(Recomendation: Ubuntu22.04 + ROS2 Humble). [link](https://docs.ros.org/en/humble/Installation/Alternatives/Ubuntu-Development-Setup.html)

ros1 installation(Recomendation: Ubuntu20.04 + ROS Noetic). [link](https://wiki.ros.org/cn/noetic/Installation/Ubuntu) ( I install ros1 just for that stupid Galaxea A1 Robot Arm because it only supports ros1... )

## Simulator💻
*"Try Anything in a Desperate Plight"*

Considering the complexity of differnt simulators, choose [MUJOCO](https://github.com/google-deepmind/mujoco) as the first step to help me train/test robot(Galaxea A1 and Franka Research 3). Maybe, [Nvidia Issac Sim for C++/Python](https://docs.isaacsim.omniverse.nvidia.com/4.5.0/introduction/quickstart_index.html) and [Drake for C++/Python](https://drake.mit.edu/) are also good choice. Besides, we can learn about introduction and basic knowledge about MUJOCO from [Prof.Wei Zhang, SUSTech](https://www.bilibili.com/video/BV1wPyfYHEmE).

I have learned the total series of IsaacSim [Courses in bilibili](https://www.bilibili.com/video/BV1xZ421s7ih/?spm_id_from=333.1387.0.0&vd_source=51baee34b45b10ae33bf59e4047cb767) and [Documentation](https://docs.isaacsim.omniverse.nvidia.com/latest/index.html).🌟✅🌟

## Machine Learning & Deep Learning 🏰
Personally thinking, [Prof.Hung-Yi Lee's ML courses](https://speech.ee.ntu.edu.tw/~hylee/ml/2016-fall.php) are the most outstanding around all of Internet courses✊. There are many interesting Pokémon examples😁 (Now if you are in China Mainland, maybe scientic surfing is all you need.🛝) To Deep Learning, recommand to read *[Deep Learning, written by Ian Goodfellow and Yoshua Bengio and Aaron Courville, MIT Press](https://www.deeplearningbook.org/front_matter.pdf)*, called "花书" in Chinese and practice code skills following *[Deep Learning with Pytorch, written by Eli Stevens and Luca Antiga and Thomas Viehmann](https://isip.piconepress.com/courses/temple/ece_4822/resources/books/Deep-Learning-with-PyTorch.pdf)*.

## Robotics💼
 I am learning about basic knowledge of Robotics on [bilibili website](https://www.bilibili.com/video/BV1oa4y1v7TY) *(PS: This is not the offical version)* following [Prof.Pei-Chun Lin, NTU](http://peichunlin.me.ntu.edu.tw/Homepage/greeting.htm).

Introduction✅ $\rightarrow$ Rotation Matrix✅ $\rightarrow$ Transformation Matrix✅ $\rightarrow$ RobotArm Geometry & DH Representation

## Control🎳
Basic control algorithm list:

PID✅<br>
MPC✅（[DR_CAN, bilibili📺](https://www.bilibili.com/video/BV1cL411n7KV)）

## Code🧑‍💻
About debug, follow this. [link](https://github.com/Mario0716/Awesome-Robotics/blob/main/equipment/debug.md)

## Equipment Setting🧪
In this section, I will record some settings that I have ever made mistakes and validated.

Server:  Nvidia RTX 5080 + AMD R9 7950x, and list of computer component details is here. [link](https://github.com/Mario0716/Awesome-Robotics/blob/main/equipment/server_details.md)<br>
Vision:  Intel RealSense Depth Camera D435i [Installation on Ubuntu](https://github.com/Mario0716/Awesome-Robotics/blob/main/equipment/d435i.md) & iPhone 12Pro(or higher version) with LiDAR <br>
Robot:   Galaxea A1 (only support ROS1, Not Recomandation) and Franka Research 3 (coming soon...)<br>
Data Collection: UMI(3D Print + GoPro) [Document](https://docs.google.com/document/d/1TPYwV9sNVPAi0ZlAupDMkXZ4CA1hsZx7YDMSmcEy6EU/edit?tab=t.0#heading=h.5k5vwx2iqjqg) is here. Very Excellent Job!!!🎈
