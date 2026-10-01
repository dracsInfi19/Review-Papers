# Paper P01 — Design and Analysis of Approximate Compressors for Multiplication

## Publication Information

- **Title:** Design and Analysis of Approximate Compressors for Multiplication
- **Authors:** Amir Momeni, Jie Han, Paolo Montuschi, Fabrizio Lombardi
- **Year:** 2015
- **Journal:** IEEE Transactions on Computers
- **Volume:** 64
- **Issue:** 4
- **Pages:** 984–994
- **DOI:** 10.1109/TC.2014.2308214
- **Publisher:** IEEE
- **Paper Link:** https://doi.org/10.1109/TC.2014.2308214

---

## Abstract

This paper presents an analysis and design of two new approximate 4–2 compressors in multipliers. The proposed designs depend on several characteristics and features of the compressor architecture.

Approximate computing provides advantages in terms of transistor count, delay, power consumption, and overall performance, while the tradeoff is evaluated using error rate and normalized error distance.

A 4–2 compressor is a small arithmetic circuit used inside fast binary multipliers to reduce the number of partial product bits. The paper includes simulations and demonstrates approximate multiplication for image processing applications.

The authors show that the newly designed approximate 4–2 compressors provide reductions in power dissipation, delay, and transistor count. In addition, the resulting multipliers show improved ANED (Average Normalized Error Distance) and SNR (Signal-to-Noise Ratio).

---

## All About 4–2 Compressors

These are small arithmetic circuits used in fast binary multiplication to reduce the number of partial products.

### 4–2 Compressor
(fig3)

A 4–2 compressor has four input bits and two output bits, usually represented as:

- Inputs: `X₁, X₂, X₃, X₄, Cᵢₙ`
- Outputs: `Sum, Carry, Cₒᵤₜ`

---

## Introduction – Main Concept

In this paper, two new approximate 4–2 compressors are proposed and analyzed. The aim is to determine which compressor design provides better delay and power consumption than the exact 4–2 compressor.

The work also compares their performance in terms of accuracy and hardware efficiency.

---

## Part A – Exact Compressor

This section discusses the exact 4–2 compressor structure and its operation.
The common implementation of 4-2 compressor is usually made of two full adder cell. where as different designs using same constraints are proposed for 4-2 compressor 
fig(4) shows an example of exact 4-2 compressor made up of XOR and XNOR gates .
as the design consists of 3 XOR and XNOR gates, 1 individual XOR and 2 2-1 MUX .
Because of these constraints the net delay in overall circuit is 3(del).,where as (del) represents the unit delay measure through gates in the circuit design. 
Following equations gives output of 4-2 compressor.

$$
Sum = x_1 \oplus x_2 \oplus x_3 \oplus x_4 \oplus C_{in}
$$

$$
C_{out} = (x_1 \oplus x_2)x_3 + (x_1 \oplus x_2)x_1
$$

$$
Carry = \overline{(x_1 \oplus x_2 \oplus x_3 \oplus x_4)}C_{in} + (x_1 \oplus x_2 \oplus x_3 \oplus x_4)x_4
$$


---

## Part B - Approximate Compressor
### Design 1
By comparing the output table of exact 4-2 compressor in (fig1t1) you find carry output and Cin in many i/o are majorly same, 25 out of 32 states are same. this clearly shows that in 75% of states both carry and Cin are same. so this can be the key point in approximate design.

---

### Phase 1

Here, the author made a quite manupilation in the other unmatched states. so author changed equation to [Carry′=Cin]- eqn(1). this changes we can observe in output of design1 approximate 4-2 compressor in (fig2t2). In (fig2t2) we can see carry′= Cin in all the cases.
because of Carry output has the higher weight of a binary bit. there is an error difference observed of 2 because of this change. to explain this author gave an example, in the row 10 of (fig1t1) input pattern is 01001  and the output is 010 this is output of exact 4-2 compressor.
 when author altered eqn(1) here as we can observe in (fig2t2) we can see row 10 has input 01001 but in output case we have 000 this change occured because of the instruction of eqn(1). and here we need to observe the difference between output value of exact compressor and approximate compressor. 

 we can see:  error= difference(exact output- approximate output)
               010 - 000   ,in terms of decimal is 2

               ---
               
### Phase 2
as we see this distance of error is not accepted . here comes phase 2 of design manuplation ,to reduce or to compensate this distance ,author proposes one more manuplation in equation by simplifing Cout and sum data. in the second half of (fig2t2) author simplified value of sum to 0 in all states of second half, which eventually reduces the difference between the approximate and the exact outputs which is also called as error distance.

Its all because of equation (fig5).
here Cin is the game changer ,because if Cin=1 (as Cin′=0) .
Then the sum′=0.
Because of this difference in sum we can achieve reduction in overall delay of design.

---


### Phase 3

The final phase of manuplation which make an apsolutely new design of approximate 4-2 compressor design 1.
after alteration of sum and carry here comes final manuplation of Cout.
which holds highest weight among all 3 parameters.
Author proposed a equation that is (fig6).
here in this equation after simplifing it using "De Morgan's law".

   we get: C′out= (x1+x2)(x3+x4)

   so we can analyse
   if (x1+x2)=1
      (x3+x4)=1 then , C′out=1
      to make C′out=1 we need to make sure at least one of x1,x2 must be 1, AND at least one of x3,x4 must be 1.

The reason to make C′out=1 is to compansate or reduce the most of error distance occured by manuplation of sum and carry. 
we remember we made an error distance of 2 before intentionally to reduce delay. 
how? the answer is 
for example if we take row 6 of (fig2t2) we see
inputs are 00101  , the exact output is 2
and *approximate value is 0 before conversion of C′out=1
so error distance is 2 . to compensate this we keep 1 to C′out only which reduces the error distance ie: approximate value = C′out=1, Carry′=0 and sum′=0. buy this as weight of C′out is 2 
2(1)+2(0)+1(0)= 2
so new approximate value is also 2. 
now both exact and approximate values .This concludes error distance=0. 

Cout    Carry    Sum
  2       2       1

After analysing all 3 phases ,although making changes in carry and sum increase error rate but delay, complexity and power consumption is reduced. and for compensation for error rate cout takes action to reduce error rate but 1 point to note not all errors are compansated only some are compansated although cout handled to reduce a bit of error rate. 
one this we need to observe is as of now from table (fig2t2) we see that 12 out of 32 outputs are incorrect.
so yield error rate is 37.5%. but one thing still makes this design positive because this error rate is less than the best approximate compressors compared to all the references made by author.

Here comes an end to the DESIGN 1.

---

### Result
The Overall output we got in design 1 is 
* Reduction in overall delay of design
* Reduction in complexity
* Reduction in power consumption


 





## Summary

This study highlights the tradeoff between accuracy and efficiency in approximate arithmetic circuits. The proposed approximate compressors are useful in multiplier design where minor computational controlled errors are acceptable in exchange for reduced hardware cost and faster operation.
