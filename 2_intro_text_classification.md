

Google
- phase base : unnatural
- Machine Translation 
neural
- tl;dr => summarization
- smart reply in Gmail: personalize
- smart reply in Allo => generate text from chat and image

(LSTMs)[http://colah.github.io/posts/2015-08-Understanding-LSTMs]

# Sequence Models
can be apply in sequence data
- word order matter : can't be done easily be word counting [must detect word order and context]
- statistical invariance [CNN] : same meaning regarding position
- long-term dependencies : information from the far past matters --> Hidden Markov model : next stage depends on previous state
- Recurrent Neural Networks (RNN)
`input -> neural net -> output -> self loop to neural net again` : time-dependent, share parameters and capture past information

### Training an RNN : Ba
backpropagation through time!
u and w are shared parameters
1. finding gradient 
2. update value

### Losses

### Backpropagation
chain rules

###  Vanishing Gradients
- baias to short term dependency
จำประโยคไกลๆไม่ได้ จะจำคำไม่ได้

# Long Short Term Memory
avoid the long-term dependency problem
- cell state (ข้อมูลที่อยากจำ) : predict คำถัดไปของประโยต
- gates : the singmoid layer outputs (0/1)
- 3 types of gates:
1. forget : forget past subject
2. input
3. output (h) decided by sigmoid layer(gate)
- updating cell state

### LSTM Variants
- Peephold connection แอบดูได้ 
- Gated Recurrent Unit (GRU) เอา cell state รวมกับ hidden state , รวม input กับ forget gate


# RNN Architectures
INPUT -> NN -> Output
- 1-1| no RNN
- 1-N| image captioning : มี input 1 แล้ว gen หลายๆอัน
- N-1| Sentiment Analysis
- M-N| Machine translation
- M-N| video classification (sync)

# NLP in Thai
by Pratya Boonkwan (Arm)
NLP 
1. use natural language (ภาษาที่เราไม่ได้ประดิษฐ์)
2. think semantically

## Process
User Interface -> 1. ถอดรากศัพท์ morphology -> 2. หาโครงสร้างไวยกรณ์ syntax (grammar) -> 3. หาความหมาย semantics -> inference engine หาความหมาย เปลี่ยนรูปแทนความหมาย แล้วทำย้อนกลับออกมาเป็นประโยต
1. Morphology: รากศัพท์ รูปคำ part of speech
2. Syntax การแบ่งประโยค
3. Semantics อรรถศาสตร์ ดูรูปกรรม ใครกรรมตรงกรรมรอง
4. Discourse ปริเฉฟ
5. pragmatics วัจนปฏิบัติ การตีความ common sense

## Introduction
- ภาษาไทยเป็นภาษาคำโดด : Subject Verb Object | head-initial (English is head-final)
- Thai is Simplex : use number and classifier to pluralize | adverbials 
- semantically  minimalist : เติมคำไปเรื่อยๆ เพื่อสร้างคำใหม่

grammarticallization กลายเป็นคำได้หลาย part of speech

# Lv1 Morphology
- Hidden Markov Model (n-gram)

How to segment word
1. ตัดตามคำมูล
2. ตัดตามความพี่ที่พบเห็น
3. ตัดตามคำประสม <=== ใช้เกณฑ์ของคน BEST Corpus (eg. |แมวน้ำ|)
4. ตัดตามคำแปลภาษาอื่น

ชื่อเฉพาะ - ตัวรวมเป็นก้อนเดียว
- organization name
- technical term

## POS tagging : part of speech ๋๋(JJ: adjective) -- use n-gram model (hidden markov model)

LV1.5 grammaticalization คำเป็นได้หลาย POS
# LV2 Syntax
CKY Algorithm (Chart parsing)
ดึงต้นไม้ออกมาจาก chart
โครงสร้างต้นไม้ไวยกรณ์
ดูว่าต้นไหน probability มากที่สุด

NVN : eg. หม้อหุงข้าว | หม้อหุงข้าวซ้อมมือ | คนขับรถบรรทุก
pro-dropping ละ (ละกรรม) ไม่รู้ว่า part of speech ที่หายไปคืออะไร

# LV3 Semantics
ตีความตามความหมาย : เอาคำมาติดกันเป็นประโยชน์
- word sense: เก็บคำไหน (มีหลายความหมาย)
- instantiation: ใครคนไหน
- quantifier : หาจำนวน
e.g. แม่วานน้องเก็บผ้า

# LV4 Discourse
### Sentence Segmentation
กำกับขอบเขตของประโยต
- ไวยกรณ์ ดู syntax (หา sub-ordinate clause) -> ประโยคยาวมากกก
- discourse unit : ตัดได้ EDU(Elementally Discourse Unit) ตัดง่าย แต่จะไม่เห็นความสัมพันธ์ของแต่ละ sub-ordinate ของแต่ละประโยค <== ์Nectec แล้วทำ discourse parser
- topic shift : ดูว่าเปลี่ยนเรื่องเมื่อไรตัดตรงไหน

### Discourse Parsing
ตัดเป็น EDU แล้วทำ parsing
ทำ automatic summarization ได้

ข้อความเลี่ยงที่จะพูดไม่จบความ (เลี่ยง main point)

# LV5 Pragmatics การตีความตามบริบท Speech vs Speech act
*Intent* การตีความ common sense  eg. May I have your name, please? --> Yes .... (should answer your name instead) 

# ภาษา social network
- simplification ชิมิ มะรุ
- events เสียงสูง (ตามข่าวดารา)
- typos เมพ ครัช คนับ ลาก่อย
- onomatopoeia คำเลียนเสียงธรรมชาติ แว้น
- assimilation การกลืนเสียง แวร๊ง อัลไล ตัลหลอด
- peculiarities นก (มาจากเหตุการณ์)
- คำยืมภาษาอื่น
- sarcasm ดีออก
- repetition ค่าาาาาาา

# Trends of Thai NLP
- **Deep Learning**
- CRF (random field) เร็ว
- Bayesian ห่วย โมเดลไบแอสตามแดต้า --> gravitational bayes
- Reinforcement learning /
- Q learning /
- multi task learning /
- semi-supervised /
- almost unsupervised /
- unsuperviesd ไม่ค่อยดีเสมอไป

## Resource
- word segmentation and POS tagging
- Treebanks แบ่งต้นไม้ไวยกรณ์ and EDU
- Ontologies and knowledge graphs เอาข้อมูลมาทำให้คอมเข้าใจ

## Deep Word Segmentation
easy to implement
1. character embedding
2. LSTM bidirectional state transition
3. ใส่ไปหลายๆ ชั้นได้ 1-2 วน ประมาณ 5 ชม. (3ชั้นอาจจะสองวัน)
4. Hidden state ใส่ dropout ใส่เพื่อ simulate noise (brain damage)
5. ใส่ tanh
6. ทำ prediction

### Evaluation
Gold standard
Prediction
- Precision
- Recall
- F1 

วัด precision จาก boundary อันไหนถูกบ้าง
จะไม่วัดจาก character

# Deep NLP @Nectec
เรียนรู้การสะกด
- sentence segmentation
- syntactic parsing
- shallow discourse 

- NLP Research Community in Thailand
aiat.in.th

- Conference : isai-nlp.org

- (BKK Machine Learning)[http://facebook.com/bkkml]
kaamanita@gmail.com

Q: Reinforcement Learning with NLP
+ reward , - penalty
การตัดคำ ใส่ gold standard
ค่อยๆสอนไปเรื่อยๆ
หาพยางค์ หาคำ
เครื่องแปลภาษา : แล้วให้คนมานั่งอ่าน ว่าดี/ไม่ดี
แต่คนจะเหนื่อย
ยกเว้น **chat robot**

Q: LSTM จะ learn จาก gold standard แล้วใช้ back propagation ย้อนกลับ วัด losses (non-linear,..) :keras

Dynamic network จะใช้ keras ไม่ได้ ต้องใช้ tensorflow

