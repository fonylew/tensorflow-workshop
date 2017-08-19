1. Content-based approach
- cold start
- no discovery

2. Similarity
"แนะนำของเหมือนๆกัน"
- Uclidian distance
- Jaccard นับ similarity:  จำนวน A intersect B / A union B
- Cosine Similariry: represent with Vector

3. Collaborative Filtering
- **use other users preference**
- derive unknown ratings from those of 'similar' users

How-to
- K-NN
- estimated rating with weighted

4. Matrix Factorization
เขียนให้อยู่ในรูป product of two long,thin matices
map users and items with **latent factor** d dimensions (eg. actors, directors)

users x factors (dot) factors x items = Matrix M

*don't treat null value as 0*. It's just unknown data.
- UV Decomposition
ปรับยังไงให้ประมาณได้ถูกต้องที่สุด

5. Autoencoder
- A neural network ทำให้ได้ target เท่ากับ input

ไม่อยากให้ hidden unit เยอะเกิน
'dimensionally reduction' ประมาณค่าออกมาใกล้เคียงของเก่า

