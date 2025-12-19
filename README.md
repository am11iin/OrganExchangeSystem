# Organes Transplant Simulation

A C program simulating organ requests and donations among **critical** and **non-critical** patients using **shared memory**, **semaphores**, **message queues**, and **pipes**.

---

## Features

- 🏥 **Patient Types**
  - Critical Patients (M1 = 4 requests)  
  - Non-Critical Patients (M2 = 6 requests)

- 🔄 **Interprocess Communication**
  - Message queues for organ requests and responses  
  - Shared memory as a circular buffer for organs  
  - Semaphores for synchronization  
  - Pipes for intermediate communication between processes

- ⚙️ **Processes**
  - **Critical Patient Process**: Sends requests for critical organs  
  - **Non-Critical Patient Process**: Sends requests for non-critical organs  
  - **Surgeon Process**: Collects requests and provides organs  
  - **Donor Process**: Fills the shared buffer with available organs

- 🎯 **Synchronization**
  - Mutual exclusion with semaphores  
  - Non-blocking communication using pipes and message queues

---

## Requirements

- Linux / Unix system  
- C compiler (gcc)  
- Basic understanding of IPC (Interprocess Communication)

---

## Compilation

```bash
gcc organes.c -o organes -lrt
```

---

## Usage

```bash
./organes
```

- The program will spawn four processes automatically:  
  1. Critical patients  
  2. Non-critical patients  
  3. Surgeon  
  4. Donor  

- Observe organ requests and successful transplants printed on the terminal.

---

## How It Works

1. Critical and non-critical patients generate random organ requests.  
2. Surgeon reads requests from message queues and transfers them via a pipe.  
3. Donor process randomly provides organs to fulfill patient requests.  
4. Shared memory is used as a circular buffer with semaphore-based synchronization to ensure thread-safe access.  
5. Program terminates when all organ requests are fulfilled.

---

## Clean-up

The program automatically removes:  

- Semaphores  
- Shared memory  
- Message queues  
- Pipes  

---

## Author

© 2025 — sellami mohamed amine 
