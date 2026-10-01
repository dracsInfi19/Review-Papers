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

---

## Summary

This study highlights the tradeoff between accuracy and efficiency in approximate arithmetic circuits. The proposed approximate compressors are useful in multiplier design where minor computational errors are acceptable in exchange for reduced hardware cost and faster operation.
