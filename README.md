# 4-Bit Wallace Tree Multiplier in Verilog

## Overview
This project implements a **4-bit Wallace Tree Multiplier** using **Verilog HDL**. The design multiplies two 4-bit binary numbers and produces an **8-bit product output**.

The Wallace Tree multiplication technique reduces partial products in parallel using **Half Adders (HA)** and **Full Adders (FA)**, making multiplication faster compared to conventional array multipliers.

---

## Features
- 4-bit × 4-bit multiplication
- 8-bit output product
- Wallace Tree reduction technique
- Uses:
  - **Half Adders**
  - **Full Adders**
- Parallel partial product generation
- Faster multiplication due to reduced propagation delay

---

## Module Description

### Top Module
**Module Name:** `wallic_Tree_multiplier`

### Inputs
| Signal | Size | Description |
|---------|------|-------------|
| `a` | 4-bit | First input operand |
| `b` | 4-bit | Second input operand |

### Output
| Signal | Size | Description |
|---------|------|-------------|
| `prod` | 8-bit | Product of `a × b` |

---

## Working Principle

### 1. Partial Product Generation
The multiplier first generates partial products using **AND gates**.

Each bit of input `a` is ANDed with each bit of input `b`.

Formula:

```text
p[i][j] = a[j] & b[i]
