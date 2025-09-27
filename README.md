# Design and Implementation of 2-Way Set-Associative Cache Memory on Basys3 FPGA Board

## 📌 Introduction
In modern computer systems, memory access speed is a crucial factor that directly impacts overall system performance. Since accessing **main memory (DRAM)** is relatively slow compared to the processor speed, a **cache memory** is introduced to bridge the gap.  

A **cache memory** is a small, high-speed memory placed between the CPU and main memory that stores frequently accessed data.  
- **Direct-Mapped Cache** provides simple mapping but suffers from conflicts.  
- **Fully Associative Cache** gives flexibility but is costly.  
- **Set-Associative Cache** strikes a balance between the two by dividing the cache into sets and allowing multiple blocks per set.  

In this project, we focus on a **2-Way Set-Associative Cache Memory**, which allows two blocks to reside in a set, reducing cache conflicts while maintaining efficiency.  

---

## 🚀 Benefits of Cache Memory
- **Reduced Memory Latency**: Faster data access compared to main memory.  
- **Improved CPU Utilization**: Processor spends less time waiting for memory.  
- **Efficient Bandwidth Usage**: Minimizes repeated memory fetches.  
- **Scalability**: Works across different applications like processors, DSPs, and embedded systems.  

---

## 🎯 Project Objective
The main objective of this project is to:  
1. **Design and implement a 2-Way Set-Associative Cache** on the Basys3 FPGA board.  
2. **Simulate cache behavior** (read hit, write hit, read miss, write miss) using Verilog HDL.  
3. **Integrate using IP block design** in Vivado for real-time FPGA testing.  
4. **Validate functionality** through simulation waveforms, FPGA output LEDs, and debugging using ILA/VIO cores.  

---

## 📊 Simulation Results
Below is the simulation waveform showcasing cache behavior:  

![Simulation Waveform]()

- **Hit/Miss signals** indicate cache lookup status.  
- Initial cache misses are seen when new data is loaded.  
- Subsequent accesses show hits, validating correct cache operation.  

---

## 🏗️ High-Level Block Diagram
The high-level block diagram of the cache memory system is as follows:  

![High-Level Block Diagram](images/highlevel_block.png)  

- **CPU Interface**: Handles requests and responses.  
- **Tag & Index Decoder**: Determines the cache line location.  
- **Cache Memory (2-Way)**: Stores data with tags and valid bits.  
- **Main Memory**: Accessed during cache misses.  

---

## ⚙️ Internal Architecture
The internal design of the **2-Way Set-Associative Cache** consists of:  

![Internal Architecture](images/internal_architecture.png)  

- **Tag Array**  
- **Data Array (2 Ways)**  
- **LRU (Least Recently Used) Replacement Policy**  
- **Comparator & Control Logic**  

---

## 🧩 IP Block Design in Vivado
The cache module was integrated using the **IP Integrator flow** in Vivado.  

![IP Block Design](images/ip_block.png)  

- Custom cache module wrapped as an IP.  
- Connected with clocking wizard, reset, and debugging cores.  

---

## 💡 FPGA Implementation
The design was deployed on the **Basys3 FPGA Board (Xilinx Artix-7)**.  
Output verification was performed using onboard LEDs, switches, and UART.  

![FPGA Board Output](images/fpga_output.png)  

---

## 🔍 Debugging using ILA & VIO
The design was validated and debugged using **Integrated Logic Analyzer (ILA)** and **Virtual Input/Output (VIO)** cores.  

- **ILA captures real-time cache signals**  
![ILA Debug](images/ila.png)  

- **VIO allows interactive testing of cache inputs/outputs**  
![VIO Debug](images/vio.png)  

---

## ✅ Conclusion
- Successfully implemented a **2-Way Set-Associative Cache Memory** on Basys3 FPGA.  
- Achieved functional validation through **simulation, IP block integration, FPGA testing, and debugging**.  
- Demonstrated the efficiency of set-associative mapping in reducing cache misses compared to direct-mapped caches.  

---

## 🛠️ Tools & Technologies Used
- **Hardware**: Basys3 FPGA (Xilinx Artix-7)  
- **Software**: Xilinx Vivado (IP Integrator, ILA, VIO)  
- **Language**: Verilog HDL  
- **Simulation**: Vivado Simulator  

---

## 👨‍💻 Author
**Gaurav Dhak**  
B.Tech Electronics System Engineering | NIELIT Aurangabad  
Specialization in **RTL Design & Verification, FPGA Prototyping, and Computer Architecture**  

---

