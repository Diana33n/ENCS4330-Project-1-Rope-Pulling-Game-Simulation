

# 🪢 Rope Pulling Game Simulation

A multi-process Linux simulation of a **rope pulling game** where two teams compete in rounds. Built using **C**, **POSIX signals**, **pipes**, and **OpenGL**, this project demonstrates real-time process coordination, inter-process communication, and graphical visualization.

---

## 📖 Overview

This project was developed as part of:

> 🏫 **Birzeit University – ENCS4330**
> 🖥 *Real-Time Applications & Embedded Systems*
> 📅 **2nd Semester 2024/2025**
> 👨‍🏫 Instructor: Dr. Hanna Bullata

It simulates two teams pulling a rope, with a **referee** coordinating player actions and a **visualizer** displaying the game in real time.

---

## 🎯 Objectives

✅ Demonstrate multi-process programming in Linux.
✅ Use **signals** and **pipes** for inter-process communication.
✅ Implement random events like player falls and recoveries.
✅ Provide a **graphical visualization** of player states, rope movement, and scores using OpenGL.
✅ Allow configurable game parameters (team size, energy, thresholds, etc.) via text file.

---

## 🏗 Architecture

* 🕹 **Referee (main.c)**: Parent process controlling game flow, rounds, and player coordination.
* 👨‍👩‍👦‍👦 **Players (player.c)**: Child processes managing energy, effort, and responding to referee signals.
* 🎨 **Visualizer (visualizer.c)**: OpenGL-based display showing players, rope position, and scores.
* 📁 **Shared Definitions (common.h)**: Constants and data structures for cross-process use.
* 📝 **Game State File (game\_state.txt)**: Intermediary between referee and visualizer.

---

## 📂 Project Structure

| File             | Description                                       |
| ---------------- | ------------------------------------------------- |
| `main.c`         | Referee process managing players and game rounds. |
| `player.c`       | Player logic: energy, effort, random falls.       |
| `visualizer.c`   | OpenGL visualizer of the game state.              |
| `common.h`       | Shared constants and structures.                  |
| `Makefile`       | Build instructions for all components.            |
| `game_state.txt` | Intermediate file for visualization updates.      |

---

## ⚡ Features

### 🏃‍♂️ Multi-Process Simulation

* Each player runs as a separate process.
* Referee manages signals (`SIGUSR1`, `SIGUSR2`) to coordinate rounds.

### 📡 Inter-Process Communication

* **Pipes**: Data exchange between referee and players.
* **Signals**: Start pulling, report energy, notify round winners.

### 🎨 Real-Time Visualization

* Player positions and effort visualized.
* Rope dynamically moves based on team effort.
* Scores and round results displayed.

### 🎲 Random Events

* Players may fall randomly, setting effort to zero temporarily.
* Recovery time is randomized within user-defined limits.

### 🛠 Configurable Parameters

* Energy limits, round thresholds, and timeouts set via a text file.

---

## 🚀 Getting Started

### 📦 Prerequisites

* Linux OS
* GCC Compiler
* OpenGL and GLUT libraries

### 🔨 Build

```bash
make
```

### ▶ Run

```bash
./main config.txt
```

This starts the referee, spawns players, and launches the visualizer.

---

## 🖥 Example Gameplay

* Players aligned by energy level: stronger players at rope ends.
* Rope moves dynamically based on team effort.
* Rounds end when a team exceeds the effort threshold.
* Visualization shows:

  * Player energy bars
  * Falling and recovering players
  * Winning team flashes

---

## 👥 Team Members

| Name           | Student ID |
| -------------- | ---------- |
| Diana Muzahem  | 1210363    |
| Shahd Abdallah | 1212840    |
| Masa Shaheen   | 1210635    |


---

## 📚 References

* **POSIX Signals & Pipes**: Linux Programming Interface by Michael Kerrisk
* **OpenGL (GLUT)**: [OpenGL Documentation](https://www.opengl.org/documentation/)
* ENCS4330 Lecture Notes

---


