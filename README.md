
Real-Time Task Scheduling Project
Introduction

This repository contains the assignments, reports, and source code developed for the final examination project of the Embedded Systems course. The project focuses on analyzing, designing, and implementing real-time scheduling mechanisms (RTOS Scheduling) on an STM32 microcontroller.

The system includes the following scheduling models:

Single-task Models

Time-Triggered (TT)

Event-Triggered (ET)

Multi-task Models

Time-Slice with Priority Scheduling

Rate Monotonic Scheduling (RMS)

Earliest Deadline First (EDF)

This project demonstrates the full workflow of building a real-time embedded system:
task analysis, timing constraint definition, scheduler implementation, and verification on actual hardware.

Requirements
Functional Requirements

Read temperature data from a sensor at a specified sampling period.

Measure real-time clock (RTC) values and provide accurate time updates.

Display temperature, humidity, and real-time data on an LCD.

Transmit system data to a computer via UART.

Receive control commands from the computer to adjust operational parameters.

Scheduling Requirements

Configure task timing: periods, priorities, deadlines.

Implement time-triggered and event-triggered single-task schedulers.

Implement RMS, EDF, and priority-based scheduling for multi-task execution.

Ensure deterministic behavior and validate task schedulability.

Task Set and Timing Requirements
1. Temperature Measurement Task

Function: Reads temperature sensor values.

Timing: Temperature changes slowly → period 2–3 seconds.

Type: Periodic.

2. Real-Time Clock (RTC) Task

Function: Retrieves current time and sends it to the display task.

Timing: Must show correct time → period ≤ 1 second.

Type: Periodic, high priority.

3. Temperature Display Task

Function: Displays temperature on LCD/UART.

Timing: Depends on measurement task → period ≥ 2–3 seconds.

Type: Periodic.

4. Real-Time Display Task

Function: Updates the time display on LCD/UART.

Timing: Must be precise → fixed 1-second period.

Type: High-priority periodic task.

5. Humidity Measurement Task

Function: Reads humidity sensor data.

Timing: Humidity changes slowly → period 2–3 seconds.

Type: Periodic.

6. Humidity Display Task

Function: Displays humidity on LCD/UART.

Timing: Does not require frequent updates → period 4–5 seconds.

Type: Periodic.

Implemented Scheduling Models
Time-Triggered Scheduling

Simple Periodic TT Scheduler

Non-Preemptive Event-Triggered Scheduler

Multi-Task Real-Time Scheduling

Rate Monotonic Scheduling (RMS)

Fixed-priority scheduling based on task frequency

Designed and implemented schedulable periodic tasks

Earliest Deadline First (EDF)

Dynamic priority assignment based on deadlines

Fully implemented EDF task dispatcher

Priority-Based Scheduling

Priority with Time-Slice

Execution analysis and configuration

Preemptive scheduling behavior

Author

Phạm Huy Tuyên — 20213031
Responsible for single-task scheduling models (Time-Triggered and Event-Triggered).

Lưu Đình Tú — 20213016
Responsible for multi-task scheduling models, including Time-Slice with Priority, RMS, and EDF. (This is me.)
Overview

This project focuses on the analysis, design, and implementation of real-time scheduling algorithms (RTOS Scheduling) for an embedded system. The goal is to ensure that all tasks meet their timing constraints while maintaining system stability and efficient resource utilization.

Several scheduling models are explored and implemented, including:

Time-Triggered (TT) Scheduling

Event-Triggered (ET) Scheduling

Rate Monotonic Scheduling (RMS)

Earliest Deadline First (EDF)

Priority-Based Scheduling

The system performs sensing, processing, and display operations for temperature, humidity, and real-time clock data.

Task Set and Timing Requirements
1. Temperature Measurement Task

Function: Reads temperature sensor data.

Timing Requirements: Temperature changes slowly over time.

Period: 2–3 seconds.

Type: Periodic task.

2. Real-Time Clock (RTC) Task

Function: Obtains the current timestamp and forwards it to the display task.

Timing Requirements: Must maintain accurate real-time information.

Period: ≤ 1 second.

Type: High-priority periodic task.

3. Temperature Display Task

Function: Receives temperature data and displays it via LCD/UART.

Timing Requirements: Depends on the temperature measurement task.

Period: ≥ temperature measurement period (2–3 seconds or higher).

Type: Periodic task.

4. Real-Time Clock Display Task

Function: Updates the time display via LCD/UART.

Timing Requirements: Must refresh the displayed time at a fixed rate to ensure accuracy.

Period: 1 second (fixed).

Type: High-priority periodic task.

5. Humidity Measurement Task

Function: Measures humidity sensor data.

Timing Requirements: Humidity also changes slowly.

Period: 2–3 seconds.

Type: Periodic task.

6. Humidity Display Task

Function: Displays humidity information via LCD/UART.

Timing Requirements: Does not require rapid updates.

Period: 4–5 seconds.

Type: Periodic task.

Implemented Scheduling Models
🔹 Time-Triggered Scheduling

Simple Periodic Time-Triggered Scheduler

Non-Preemptive Event-Triggered Scheduler

🔹 Multi-Task Real-Time Scheduling

Rate Monotonic Scheduling (RMS)

System modeling based on RMS

Task implementation following frequency-based priorities

Earliest Deadline First (EDF)

System modeling based on deadlines

Task implementation using EDF dynamic prioritization

🔹 Priority-Based Scheduling

Time slicing techniques

Priority assignment and execution analysis

Full implementation demonstrating preemptive scheduling behavior
