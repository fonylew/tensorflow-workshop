# Reinforcement Learning in a Nutshell
## Markov Decision Process (MDP)
S - States
A - Actions
P - Policies (State Transitions)
R - Reward function
r(grammar) - discount factor

### MDP Policy
Policy (PI) : Optimal Policy

#### Example
- Video Gaming (Deep Q Network)
[imperfect system (can't see what's happened inside)

ยิ่ง discount ยื่งเยอะ คือให้ความสำคัญกับ state ในอนาคต

- Board Game : perfect information
(finite)
	- tic-tac-toe : 3^9
	- Chess : 10^40
	- Go : 3^(19x19) - 1.74x10^172
(Alphago)
SL Policy network  ==> Rollout Policy
มีเน็ตเวิร์คแยกกันสองตัว : คำนวณ value และ policy

## Montecarlo
(Alphago)
selection > Expansion > Evaluation > Backup
ต้อง update table

# Example
-  Finance & Trading
RL in Trading
sell / Buy / Hold

- Robot Navigation
	- Maze escape

- Conversational Dialogue
	- forward-looking and interactive

	Rewards
	- Ease of answering
	  (ติดลบบทสนทนาที่ไม่มีประโยชน์)
	- Information Flow : ไม่ควรพูดเรื่องซ้ำๆ
	  (ติดลบบทสนทนาซ้ำๆ)
	- Semantic Coherence : มีความหมายเกี่ยวเนื่องกัน

- Computer Vision
Visual Attention (จุดที่ควร pay attention)
ต้องโฟกัสที่ไหน (Object Detection)

- Personalized Ad Recommendation System

- Neural Architecture Search
Generating CNN architecture with skip connection

