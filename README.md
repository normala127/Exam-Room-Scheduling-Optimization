# Optimized Exam Room Assignment Using Mixed Integer Programming

This repository contains an optimization model for assigning university exams to available rooms while minimizing unused seating capacity and respecting real-world operational constraints.

The project was originally developed as part of **IE303 – Operations Research I (Spring 2025)** and is based on **real examination scheduling data** from the International University of Sarajevo.

> **Important note on privacy:**  
> The full implementation, and report have been **partially redacted and slightly modified** before publication to protect institutional and student privacy.
> The original dataset was not uploaded due to same reasoning. 
> The modeling logic, structure, and optimization approach remain representative of the original solution.

---

## Problem Overview

During examination periods, universities must allocate students to rooms in a way that:
- respects room capacity limits,
- avoids schedule conflicts,
- minimizes unnecessary fragmentation of exams,
- and efficiently utilizes available infrastructure.

The objective of this project is to **minimize the total number of unused seats** across all exam sessions while satisfying academic, logistical, and comfort-related constraints.

---

## Modeling Approach

The problem is formulated as a **Mixed Integer Programming (MIP)** model.

### Key Features
- Assigns students from each exam to one or more rooms
- Enforces strict room capacity constraints (no overbooking)
- Prevents small exams from being split across multiple rooms
- Ensures consistency between room assignments and buildings
- Handles overlapping exams across shared infrastructure

The model was implemented in **Python using PuLP**.

---

## Mathematical Model (Summary)

### Decision Variables
- Number of students assigned from each exam to each room
- Binary indicators for room usage
- Binary indicators for building assignment

### Objective
- Minimize total unused room capacity across all exam sessions

### Constraints
- All registered students must be assigned seating
- No room may exceed capacity during overlapping exams
- Exams must be assigned to a single building
- Minimum group sizes enforced when splitting large exams
- Exams with fewer than 50 students cannot be split

A detailed formulation is provided in the accompanying (censored) report.

---

## Results

The optimization model:
- Found an **optimal solution**
- Assigned all students without violating capacity or scheduling constraints
- Reduced unnecessary room usage and exam fragmentation
- Improved operational feasibility compared to the original schedule

---

## Sensitivity Analysis & Validation

The model was tested under:
- student enrollment scaling scenarios,
- building availability constraints,
- simulated room failures.

Key findings:
- Short-term enrollment growth can be accommodated with minimal efficiency loss
- The current infrastructure supports substantial population growth
- The model correctly identifies infeasible scenarios when resources are insufficient
- Individual room failures are generally tolerable, with expected critical dependencies

---

## Repository Notes (Important)

- **Data files are not included** due to privacy and institutional restrictions.
- **Code and report have been slightly modified** to remove identifying details.
- Variable names, identifiers, and values may be abstracted.

Despite these modifications, this repository demonstrates:
- practical optimization modeling,
- real-world constraint handling,
- and applied operations research techniques.

---

## Technologies Used
- Python
- PuLP (Linear & Integer Programming)
- Optimization modeling
- Sensitivity analysis

---

## Possible Extensions
- Integration with a university student information system
- Real-time room availability checks
- Dynamic rescheduling under disruptions
- Performance optimization for larger-scale instances

