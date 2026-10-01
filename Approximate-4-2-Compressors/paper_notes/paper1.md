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
Carry = (x_1 \oplus x_2 \oplus x_3 \oplus x_4)C_{in} + (x_1 \oplus x_2 \oplus x_3 \oplus x_4)x_4
$$


---

## Part B - Approximate Compressor
# Design 1
By comparing the output table of exact 4-2 compressor in (fig1t1) you find carry output and Cin in many i/o are majorly same, 25 out of 32 states are same. this clearly shows that in 75% of states both carry and Cin are same. so this can be the key point in approximate design.

Here, the author made a quite manupilation in the other unmatched states. so author changed equation to [Carry′=Cin]. this changes we can observe in output of design1 approximate 4-2 compressor in (fig2t2)





## Summary

This study highlights the tradeoff between accuracy and efficiency in approximate arithmetic circuits. The proposed approximate compressors are useful in multiplier design where minor computational controlled errors are acceptable in exchange for reduced hardware cost and faster operation.
