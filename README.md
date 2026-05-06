# Smart Traffic Light Controller with Pedestrian & Emergency Control (Verilog)

## Overview
This project implements an advanced traffic light control system using a Finite State Machine (FSM) in Verilog. The system manages two roads (Road A and Road B) and includes pedestrian crossing and emergency override features.

The design demonstrates real-world traffic control logic with priority handling and timed state transitions.

---

## System Operation

###  Normal Traffic Cycle
1. Road A → Green, Road B → Red  
2. Road A → Yellow, Road B → Red  
3. Road A → Red, Road B → Green  
4. Road A → Red, Road B → Yellow  

---

### Pedestrian Mode
- Triggered by `ped_request`  
- Both roads turn RED (safe crossing)  
- Controlled using a dedicated pedestrian timer  
- Returns automatically to normal operation  

---

###  Emergency Mode
- Triggered by `emergency` signal  
- Immediate override to safe state (Road A Green priority)  
- Highest priority in the system  

---

## Features
- Moore FSM-based design  
- Two-road traffic control  
- Pedestrian crossing support  
- Emergency override with priority handling  
- Dual-timer system (traffic + pedestrian)  
- Clock-driven and event-driven transitions  
- Fully verified using testbench  

---

## How It Works

### State Encoding
| State | Description |
|------|------------|
| 00 | Road A Green, Road B Red |
| 01 | Road A Yellow, Road B Red |
| 10 | Road A Red, Road B Green |
| 11 | Pedestrian / All Red |

---

### Priority Logic
1. Emergency → highest priority  
2. Pedestrian request → next priority  
3. Normal FSM sequence → default  

---

###  Timing System
- `count` → controls traffic light duration  
- `ped_count` → controls pedestrian crossing time  
- Transitions occur based on timer completion  

---

### Output Encoding
| Value | Meaning |
|------|--------|
| 2'b10 | Green |
| 2'b01 | Yellow |
| 2'b00 | Red |

---

## Tools & Technologies
- Verilog HDL  
- Xilinx Vivado  
- FSM Design, Counters, Priority Logic  

---

##  Project Structure
- `smart_traffic_advanced.v` → Main design  
- `tb_smart_traffic_advanced.v` → Testbench  

---

##  Simulation
1. Open project in Vivado  
2. Add design and testbench files  
3. Run behavioral simulation  
4. Verify:
   - Normal traffic cycle  
   - Pedestrian activation  
   - Emergency override  

---

## Key Concepts Demonstrated
- FSM with priority-based control  
- Multi-event handling in digital systems  
- Counter-based timing design  
- Real-world system modeling  

---

## What I Learned
- Designing complex FSMs with multiple conditions  
- Implementing priority logic (emergency vs normal flow)  
- Managing multiple timers in Verilog  
- Writing structured and scalable HDL code  

---

## Future Improvements
- Add sensor-based adaptive traffic control  
- Implement FPGA hardware deployment  
- Introduce configurable timing parameters  
- Expand to multi-intersection system  

---

## Author
Linga
