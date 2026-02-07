# HUFFMAN AND SHANNON-FANO CODING
### AIM
Consider a discrete memoryless source with symbols and statistics {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25} for its output. 
Apply the Huffman and Shannon-Fano to this source. 
Show that by drawing the tree diagram, and Calculate the average code word length, entropy, variance, redundancy, and efficiency.
  
### TOOLS REQUIRED
Python IDE with Numpy and Scipy libraries or Colab

### PROGRAM

```
#Huffman and Shannon-Fano coding
import numpy as np
import math
L  = 0
hs = 0
p = []
lk = []
n = int(input("Enter the number of Samples : "))
for i in range (n):
    pr = float(input(f"Enter the probability of sample values {i + 1}: "))
    p.append(pr)
for j in range (n):
    l = float(input(f"Enter the length of the sample values {j + 1}: "))
    lk.append(l)
# Avg length of the code word
for k in range (n):
    Avg1 = p[k] * lk[k]
    L = L + Avg1
# Entropy
for k in range (n):
    e = p[k] * math.log(1 / p[k], 2)
    hs = hs + e
hs = round(hs,3)
# Efficiency
eff =  hs / L
eff = round(eff,3)
# Redundancy
red =  round(1 - eff,3)
# Variance
var = 0
for k in range(n):
    var1 = p[k] * (lk[k]-L)**2
    var = var + var1
var = round(var,3)
print(f"Average Codeword Length is : {L}")
print(f"Entropy is : {hs}")
print(f"Efficiency is : {eff}")
print(f"Redudancy is : {red}")
print(f"Variance is : {var}")
```

### CALCULATION
<img width="973" height="1381" alt="image" src="https://github.com/user-attachments/assets/afc2d9e9-9533-4d84-a58b-5b527d765a6b" />
<img width="900" height="500" alt="image" src="https://github.com/user-attachments/assets/de7d6f22-c350-4096-a8c7-3c63c0cd1bb9" />


### OUTPUT
<img width="639" height="469" alt="image" src="https://github.com/user-attachments/assets/591953ae-a2d7-4eca-b043-cc25ba73a5c3" />

### RESULT
Huffman and Shannon-Fano coding methods were implemented on the provided source. Calculations for average codeword length, entropy, variance, redundancy, and coding efficiency have been carried out successfully and verified.
