# Vending Machine Controller (Verilog)

## Project Overview
This project implements a **Vending Machine Controller** using **Verilog** and **Finite State Machine (FSM)** concepts.  
It simulates a vending machine that accepts ₹5 and ₹10 coins and dispenses a product when the total amount reaches or exceeds ₹15.

### Key Learning Outcomes
- Designing **FSMs** in Verilog
- Counting money and handling conditional outputs
- Simulating hardware with **EDA Playground** and **EPWave**
- Understanding **input debouncing** (simplified version)

---

## Functionality
- Accepts **₹5** and **₹10** coins
- Product price = ₹15
- Dispenses product automatically when the total inserted amount ≥ ₹15
- Supports **reset** to return to idle state

---

## FSM States

| State | Amount Inserted | Description        |
|-------|----------------|------------------|
| S0    | ₹0             | Idle state        |
| S5    | ₹5             | ₹5 inserted       |
| S10   | ₹10            | ₹10 inserted      |
| S15   | ≥₹15           | Product dispensed |

---

## Files
- `vending_machine.v` → Verilog design (DUT)  
- `tb_vending_machine.v` → Testbench for simulation  

---

## Testbench Console Output Example

| Time (ns) | Reset | Coin5 | Coin10 | Dispense |
|-----------|-------|-------|--------|----------|
| 0         | 1     | 0     | 0      | 0        |
| 10        | 0     | 0     | 0      | 0        |
| 20        | 0     | 1     | 0      | 0        |
| 30        | 0     | 0     | 0      | 0        |
| 40        | 0     | 0     | 1      | 1        |
| 70        | 0     | 0     | 1      | 1        |
| 100       | 0     | 1     | 0      | 0        |
| 180       | 0     | 1     | 0      | 0        |
| 210       | 0     | 1     | 0      | 1        |

> **Note:** `$monitor` in the testbench prints these values during simulation. Waveforms can also be viewed in **EPWave**.

---

## How to Run on EDA Playground
1. Copy `code and testbench` into **EDA Playground**.  
2. Select **Icarus Verilog** as the simulator.  
3. Click **Run**.   
4. Observe console output for the tabular simulation data.  

---

## Future Enhancements
- Return **change** if amount > product price  
- Support **multiple products** with selection buttons  
- Implement **debouncing logic** for physical coin inputs
