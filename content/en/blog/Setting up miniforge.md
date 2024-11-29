---
title: "Setting up a python environment using miniforge"
weight: 2
resources:
params:
date: 2024-11-11T18:00:53-05:00
showDate: false
draft: false
tags: ["blog","howto"]
---
## Why Use Miniforge?

The default Python version installed on most systems is often outdated and not recommended for development. Miniforge provides a minimal installer for Conda, allowing you to create isolated Python environments with the latest versions and necessary packages.

## Step-by-Step Guide

### 1. Check Your Current Python Installation

First, let's check if you have Python installed and where it's located:


which python

This should return either empty or point to /usr/bin/python.
### 2. Download Miniforge
Download the latest Miniforge installer:
bash
wget https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-Linux-x86_64.sh

### 3. Install Miniforge
Run the installer:
bash
bash Miniforge3-Linux-x86_64.sh

Follow the prompts to complete the installation.
### 4. Verify Installation
After installation, check your Python location again:
bash
which python

It should now point to something like <path_to_home>/miniforge3/bin/python.
### 5. Activate Miniforge Environment
Activate the base Miniforge environment:
bash
mamba activate

To deactivate when needed:
bash
mamba deactivate
