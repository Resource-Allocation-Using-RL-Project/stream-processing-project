# Stream Data Resource Allocation with RL

## Overview

This project is focused on:
1. **Understanding** the paper ["Allocating Resources for Stream Data Using RL"](https://arxiv.org/abs/1911.08517) and its official Python code implementation.
2. **Running and potentially improving** the authors’ code (a Deep Reinforcement Learning model) that optimizes resource allocation in stream data processing.
3. **Investigating Apache Flink's** scheduling framework to see how we can **replace Flink’s built-in scheduler** with the RL model from the paper.

---

## Images Placeholder

> Here is a spot where you can include images (like the Apache Flink logo) in your markdown.  
> For example, if you put the Flink logo in `./images/flink_logo.png`, you can reference it like this:


---

## Project Structure
project/ 
├── paper/
│ └── 1911.08517.pdf # The research paper 
├── model/
│ └── code/ # DRL implementation 
├── flink/ 
│ └── ... # understanding how flink works (creating and running some flink files - flink Basics)
│ └── ... # a prototype integration between Flink and the learned resource allocation strategy
├── images/ # images for the README.md file
└── README.md
