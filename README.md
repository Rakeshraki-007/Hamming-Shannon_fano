# Huffman-Shannon_fano
## NAME: Rakesh R
## Reg No: 212222060191
## Consider a discrete memoryless source with symbols and statistics {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25} for its output. 
 - Apply the Huffman and Shannon-Fano to this source. 
Show that draw the tree diagram, the average code word length, Entropy, Variance, Redundancy, Efficiency.
## Aim:
 - To compute the Average Codeword Length, Entropy, Efficiency, Redundancy, and Variance for a discrete memoryless source using Huffman and Shannon-Fano coding based on the given probabilities and codeword lengths.

## Tools Required:
 - python IDE with Numpy and Scipy.
   
## Program:
~~~~
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

for k in range (n):
    Avg1 = p[k] * lk[k]
    L = L + Avg1

for k in range (n):
    e = p[k] * math.log(1 / p[k], 2)
    hs = hs + e
hs = round(hs,3)

eff = hs / L
eff = round(eff,3)

red =  round(1 - eff,3) 

var = 0
for k in range(n):
    var1 = p[k] * (lk[k]-L)**2
    var = var + var1
var = round(var,3)
print()
print(f"Average Codeword Length is : {L}")
print(f"Entropy is : {hs}")
print(f"Efficiency is : {eff*100} %")
print(f"Redudancy is : {red}")
print(f"Variance is : {var}")
~~~~
## Calculation:
![Screenshot 2025-03-30 201551](https://github.com/user-attachments/assets/38db08e2-554a-450a-93f4-c8ac09f66d91)
<img width="1200" height="1600" alt="image" src="https://github.com/user-attachments/assets/e65f05c3-db94-47c3-b0d9-41c27de91ad9" />

<img width="1200" height="1600" alt="image" src="https://github.com/user-attachments/assets/7b31886b-9a87-4425-ad69-6ac6ea420bca" />
<img width="1200" height="1600" alt="image" src="https://github.com/user-attachments/assets/0bb51a5d-4250-440b-84ef-ab21f28775bf" />


## Results:
For the given probabilities 0.125,0.0625,0.25,0.0625,0.125,0.125,0.25

i)Average Codeword Length is : 2.625.
ii)Entropy is : 2.625.
iii)Efficiency is : 100.0 %.
iv)Redudancy is : 0.0.
v)Variance is : 0.484.



