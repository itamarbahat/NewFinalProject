# NewFinalProject – Development Workflow

## Project Overview

This repository contains experiments for the final deep learning project
based on THz-like image degradation and image classification.

Main model currently under investigation: **TransNeXt**.

---

# Repository Structure

src/
data/
runs/
artifacts/

---

# Code Changes So Far

## datasets.py
Added ImageNet normalization after degradation.

## runner.py
Added freeze_backbone option for linear probe experiments.

---

# How to Work on the Project

## Opening in VSCode

1. Open folder `NewFinalProject`
2. Select interpreter `.venv`

---

# Git Workflow

Before starting work:

git pull

After finishing work:

git add .
git commit -m "Describe changes"
git push
