# Learning to Recovery with Natural Multimodal Assistance in Vision-based Navigation


#### Motivation
To accomplish tasks that are beyond their capabilities, intelligent agents must be able to actively seek for help from humans. Assistance from humans can come in a variety of human-friendly forms: written or spoken language, images, gestures, etc. These forms of communication are also rich and generalizable, allowing human assistants to specify complex goals concisely and accurately. In navigation
tasks, humans can assist agents to accomplish various tasks via verbal instructions or visual demonstrations (Se et al., 2001; Gaspar et al., 2000; DeSouza and Kak, 2002;Anderson et al., 2018; Bisk et al., 2016, 2017; Misra et al., 2014). Unfortunately, humans may not be available all the time to offer help. Moreover, they can be upset and distrust agents if help requests come too often. To reduce human effort in assisting agents, it is essential to design a system that (a) automatically supports agents in the absence of humans and (b) communicates with agents via human-intelligible media (e.g., words, images) so that learning to interact with the system enables agents to better leverage natural assistance from humans when it is available. 

In this work, we present the concept of Automatic Natural Navigation Assistance system (ANNA), which aids mobile agents in navigation tasks via natural multimedia instructions. ANNA manages a set of unidirectional language-assisted routes, each of
which is associated with natural language navigation instructions that guide the agent from the start point to the end point of the route. The agent has an option to signal ANNA requesting assistance when it is at the start point of a route. Upon requested, the
system responds with a multimedia message consisting of a language instruction corresponding to a route that starts from the agent’s location, and an image of a location on the route where the system wants it to stops following the instruction. To effectively leverage ANNA, the agent needs to learn to (a) determine when to enter or depart a route and (b) understand the multimedia messages.

ANNA can be pre-programmed and thus can function without human operation. However, by using natural forms of communication, the system can easily incorporate humans when they are willing to participate. Beside its practical purpose of reducing human assistance effort, ANNA provides a testbed for research on interactive grounded visionlanguage learning. Modeling multi-round natural interaction in photorealistic simulators remains a challenge, as interactions must adapt to the agent’s diverse situations and locations. A naive approach that crowd-sources an interaction for every location and situation does not scale to large environments.
Previous work on grounded vision-language learning via navigation tasks either follows a “one-timeinstruction-following” setup (Anderson et al., 2018; Bisk et al., 2016, 2017; Misra et al., 2014; Chen et al., 2018; Blukis et al., 2018), where the agent is given a natural language instruction only at the beginning and is not able to seek for additional help later, or model interaction with artificial languages.
ANNA, on the other hand, can effectively simulate multi-round interaction and can scale to large environments because we do not need to connect all locations but only major landmarks in the environment. 

Datasets for setting up ANNA in several photorealistic simulated environments are readily available in forms of one-time-instruction-following datasets.
(Anderson et al., 2018) to construct ANNA for object-finding tasks in the Matterport3D simulator
without any extra annotation effort. Using imitation learning, we train an agent to learn to request help
from ANNA and execute the multimedia subtasks to find objects in photorealistic environments.

### State-of-the-art 

The task is new so there is not state-of-the-art results
yet. But here is some related work.

**Language and robots** Learning to translate natural language commands to physical actions is wellstudied at the intersection of language and robotics. Proposals include a variety of grounded parsing models that are trained from data (Matuszek et al., 2012, 2013; Krishnamurthy and Mitchell, 2012) and models that interact with robots via natural language queries against a knowledge base (Saxena
et al., 2014) Most relevant to the present work are Misra et al. (2014) who ground natural language to robotic manipulator instructions using Learningfrom-Demonstration (LfD) and (Duvallet et al., 2013) who employ imitation learning of natural language instructions using humans following directions as demonstration data. Simulated environments Simple simulators as Puddle World Navigation (Janner et al., 2018) and Rich 3D Blocks World (Bisk et al., 2016, 2017) have facilitated understanding of fundamental representational and grounding issues by allowing for fast experimentation in easily-managed environments. Hermann et al. (2017) and Wu et al. (2018)
similarly use reinforcement learning in simulated 3D environments for successful execution of written instructions. Simulators that are more photorealistic, realistic-physics enabled simulators are beginning to be utilized to train real-world embodied agents (Kempka et al., 2016; Dosovitskiy et al., 2017; Shah et al., 2018). The Matterport3D dataset (Chang et al., 2017) comprising photo-realistic indoor models of 90 real homes underpins the Matterport3DSimulator and its associated RoomToRoom dataset (Anderson et al., 2018). We use this simulator and the RoomToRoom dataset in our experiments. This dataset is also used by Wang et al. (2018) to study the combination of model-based and model-free reinforcement learning for navigation from language. End-to-end learning in rich simulators: (Das
et al., 2018a) present the “Embodied Question Answering” (EmbodiedQA) task where an agent is put in a 3D environment and asked to answer questions like “What color is the car?”. They develop end-toend-trained agents trained via reinforcement learning and propose evaluation protocols. Hermann et al. (2017) and Wu et al. (2018) similarly use reinforcement learning in simulated 3D environments
for successful execution of written instructions. Das et al. (2018b) propose a hierarchical architecture where each level of the hierarchy is independently warmed up with imitation learning and further improved with reinforcement learning.

### Timeline:

March 15: finish implementation of baseline algorithms.

April 1: first set of experiments.

Apri 20: finish implementation of final algorthms.

May 5: final set of experiments.

May 10: collect results and write report. 

### Response to comments:

*How much background work have you done in this area?*
- I had a [CVPR 2019](https://arxiv.org/pdf/1812.04155.pdf) paper on this area. A [demo video](https://www.youtube.com/watch?v=Vp6C29qTKQ0&feature=youtu.be) is also available.

*How will you demonstrate your results? Please provide the details of your experiments?*
- We will try to answer these questions:
1. Does the natural assistance help with accomplishing tasks? (assistance vs. no asssitance)
2. How effective is verbal/visual assistance? (ablation study on type of assistance). 
3. What is the best help-requesting strategy? (comparison between our learned strategy and several baselines such as randomly ask, ask every k steps).

Experiments will be conducted on the [Matterport3D simulator](https://github.com/peteanderson80/Matterport3DSimulator)

For more details about the setup, please read [this document](https://drive.google.com/file/d/19Q0OBZBFeNv7t1Sl8ZCg6sdLDIbYrLLp/view?usp=sharing)


