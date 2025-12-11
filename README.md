## Real-Time Task Scheduling Project

## Introduction
This repository contains the assignments, reports, and source code developed for the final examination project of the *Embedded Systems* course.  
The project focuses on analyzing, designing, and implementing **real-time scheduling algorithms (RTOS Scheduling)** on an **STM32 microcontroller**.

The system supports several scheduling models:

### Single-Task Scheduling
- Time-Triggered (TT)  
- Event-Triggered (ET)

### Multi-Task Scheduling
- Time-Slice with Priority Scheduling  
- Rate Monotonic Scheduling (RMS)  
- Earliest Deadline First (EDF)

This project demonstrates the complete workflow of designing a real-time embedded system: task modeling, timing constraints analysis, scheduler implementation, and verification on hardware.

---

## Requirements

### Functional Requirements
- Read temperature and humidity sensor data periodically.  
- Retrieve real-time clock (RTC) data accurately.  
- Display sensor data and time on an LCD.  
- Transmit system data to a computer via UART.  
- Receive control commands from the PC to adjust runtime parameters.

### Scheduling Requirements
- Configure task periods, deadlines, and priorities.  
- Implement TT and ET scheduling in single-task mode.  
- Implement RMS, EDF, and priority scheduling in multi-task mode.  
- Guarantee deterministic, schedulable real-time behavior.

---

## Task Set and Timing Specifications

### Temperature Measurement Task
- **Function:** Read temperature sensor values.  
- **Period:** 2–3 seconds (slow-changing signal).  
- **Type:** Periodic.

### Real-Time Clock (RTC) Task
- **Function:** Obtain current timestamp and forward to display task.  
- **Period:** ≤ 1 second.  
- **Type:** High-priority periodic.

### Temperature Display Task
- **Function:** Display temperature data on LCD/UART.  
- **Period:** ≥ 2–3 seconds (depends on measurement task).  
- **Type:** Periodic.

### Real-Time Clock Display Task
- **Function:** Update time display on LCD/UART.  
- **Period:** 1 second (fixed).  
- **Type:** High-priority periodic.

### Humidity Measurement Task
- **Function:** Read humidity sensor data.  
- **Period:** 2–3 seconds.  
- **Type:** Periodic.

### Humidity Display Task
- **Function:** Display humidity on LCD/UART.  
- **Period:** 4–5 seconds.  
- **Type:** Periodic.

---

## Implemented Scheduling Models

### Time-Triggered Scheduling
- Simple periodic TT scheduler  
- Non-preemptive event-triggered scheduler  

### Multi-Task Real-Time Scheduling

#### Rate Monotonic Scheduling (RMS)
- Frequency-based fixed priorities  
- Schedulable periodic task implementation  

#### Earliest Deadline First (EDF)
- Dynamic priority based on deadlines  
- Fully implemented EDF dispatcher  

### Priority-Based Scheduling
- Time-slicing  
- Static priority configuration  
- Demonstration of preemptive execution  

---

## Overview
This project explores and implements various real-time scheduling algorithms to ensure that all tasks meet their timing constraints while maintaining efficiency and system stability.

The implemented system performs sensing, processing, communication, and display operations for:
- Temperature  
- Humidity  
- Real-Time Clock (RTC)  

Each scheduling model is analyzed, designed, implemented, and tested on STM32 hardware to ensure correct real-time behavior.

---

## Authors
- **Phạm Huy Tuyên — 20213031**  
  Responsible for *single-task scheduling models* (Time-Triggered & Event-Triggered).

- **Lưu Đình Tú — 20213016**  
  Responsible for *multi-task scheduling models* (Time-Slice Priority, RMS, EDF). *(This is me.)*

---

## Project Structure (suggested)
```txt
├── src/
│   ├── scheduler_tt/
│   ├── scheduler_rms/
│   ├── scheduler_edf/
│   └── priority_scheduler/
├── docs/
│   ├── analysis/
│   └── diagrams/
├── include/
├── README.md
└── LICENSE
