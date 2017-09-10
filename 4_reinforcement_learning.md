# Reinforcement Learning [RL]
==> Triall and Error with delayed evaluative feedback (reward)
==> Realistic
e.g. learning to ride a bicycle, playing chase

# Components

Agent -(control)-> Environment
  ^			|
  ----------------------

Agent learner + Decision Maker
Environment (stochastic -> nondeterministic ทำหลายครั้งได้ผลไม่เหมือนเดิม)

## Characteristics
- Generalization:  
- Explore ลองทำ ดี/ไม่ดี
- Delayed Consequences อาจจะได้รับผลในอนาคต

## Key

- Exploit ได้ reward เยอะ อาจจะ miopic (สายตาสั้น)
- Explore ดูว่ามี action อื่นที่ดีกว่าเปล่า

## Elements
### Policy
** ดูว่าจะ intereactยังไง **
==> mapping จาก state นึงไปอีกอันนึง
อาจจะเป็น function, look up table
stochastic มีหลายความน่าจะเป็นที่ทำได้หลาย action

### RewardSignal (0/1)

** Maximized long term reward **

### Value Function
** บอกว่าอะไรดีใน long term **
S :ถ้าเริ่ม state นี้จะได้ reward ยังไง
หาวิธีไป state ที่ value เยอะสุด ไ่ม่ใช่ reward เยอะสุด

## Example
- playing Atari games
- News recommender: ้hot news - contextเอาข่าวที่คิดว่าคนนั้นจะสนใจมาอยู่ข้างบน

# Markov Decision Processes (MDPs)
(Introduction to reinforcement learning , MIT pub - Sutton)

St, Rt, At เป็น random variable ทั้งหมด

เขียนออกมาเป็น state machine

## A finite Markov Decision Process
`St, At, Rt+1, St+1, At+1, Rt+2 ...`

## Markov Property
environment ที่ time t+1 เกี่ยวเนื่องกับ time t เท่านั้น

s' คือ state ถัดไป

Pr = p(s1,r|s,a)

จัด state ให้เป็น markov property
(แตก state เป็น state ย่อยๆได้)

## Policies
(** deterministic **/ strochastic)
a determistic policy:		a = Pi(ss)
an agent following policy:	

### return
return (value) miximize the cumulative reward

T : Final time step
(ต้องมี T  ใหญ่ ที่เป็นที่สิ้นสุด "episode")

return อาจเยอะเป็น infinity
มี discount rate (r in [0,1])


### Value Function
[Bellman equation]
