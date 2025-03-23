# Stream Data Resource Allocation with RL

## Overview

This project is focused on:

1. **Understanding** the paper ["Allocating Resources for Stream Data Using RL"](https://arxiv.org/abs/1911.08517) and its official Python code implementation.
2. **Running and potentially improving** the authors’ code (a Deep Reinforcement Learning model) that optimizes resource allocation in stream data processing.
3. **Investigating Apache Flink's** scheduling framework to see how we can **replace Flink’s built-in scheduler** with the RL model from the paper.

---

![Apache Flink & RL Integeration](images/img1.png)

---

## Project Structure

project/<br>
├── paper/<br>
│ └── 1911.08517.pdf # The research paper<br>
├── model/<br>
│ └── code/ # DRL implementation<br>
├── flink/ <br>
│ └── ... # understanding how flink works (creating and running some flink files - flink Basics)<br>
│ └── ... # a prototype integration between Flink and the learned resource allocation strategy<br>
├── images/ # images for the README.md file<br>
└── README.md<br>
