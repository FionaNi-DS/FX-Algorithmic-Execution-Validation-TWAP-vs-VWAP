# FX Algorithmic Execution Validation (TWAP vs VWAP)

## Overview

This project develops a quantitative validation framework for evaluating algorithmic execution strategies in Foreign Exchange (FX) markets. The focus is on comparing **Time-Weighted Average Price (TWAP)** and **Volume-Weighted Average Price (VWAP)** strategies against a naive benchmark.

The framework simulates realistic market conditions and evaluates execution performance using key metrics such as **slippage**, **implementation shortfall**, and **market VWAP comparison**.

---

## Motivation

As financial markets become increasingly automated, execution algorithms play a critical role in minimizing trading costs and market impact. However, these models introduce risks that require independent validation.

This project demonstrates:

- Quantitative model validation
- Benchmark vs challenger model comparison
- Sensitivity to market conditions and order size
- Identification of execution inefficiencies

---

## Methodology

### 1. Market Simulation

Synthetic FX market data is generated using:

- **Geometric Brownian Motion (GBM)** for price dynamics
- **U-shaped intraday volume profile** to reflect realistic liquidity patterns
- **Bid-ask spread modeling** to incorporate transaction costs

---

### 2. Execution Strategies

We compare three execution approaches:

- **TWAP (Time-Weighted Average Price)**  
  Executes trades evenly over time.

- **VWAP (Volume-Weighted Average Price)**  
  Allocates trades based on market volume.

- **Naive Benchmark**  
  Executes the entire order immediately at arrival.

---

### 3. Performance Metrics

Execution quality is evaluated using:

- **Slippage (bps)**  
  Difference between execution price and arrival price

- **Implementation Shortfall**  
  Total cost relative to arrival benchmark

- **VWAP Benchmark Comparison**  
  Measures performance relative to market average price

---

## Results

### Base Case (Downward Market Scenario)

- **VWAP achieves the best performance**, with the lowest slippage
- **TWAP performs well**, but slightly worse than VWAP
- **Naive execution performs worst**, due to immediate execution at higher prices

---

## Key Insights

- In a **declining market**, delayed execution (TWAP/VWAP) leads to better prices  
- In an **increasing market**, immediate execution may be preferable  
- **Order size amplifies execution cost differences**  
- There is **no universally optimal strategy** — performance depends on market conditions  

---

## Model Validation Perspective

This project adopts a **benchmark vs challenger framework**:

- Naive execution serves as the **baseline model**
- TWAP and VWAP act as **challenger models**

The goal is not only to rank strategies, but also to identify:

- When execution performance deteriorates
- How sensitive strategies are to market conditions
- Potential limitations of execution models

---

## Technologies Used

- Python
- NumPy
- Pandas
- Matplotlib

---

## Project Structure
FX-Algorithmic-Execution-Validation/
│
├── FX_Algo_Execution_Validation.ipynb
├── README.md

## Conclusion

This project demonstrates a structured approach to validating execution algorithms in FX markets. It highlights the importance of:

- Market dynamics
- Order size
- Benchmark comparison

in determining optimal execution strategies.



