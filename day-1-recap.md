---
author: Alexandre Strube // Sabrina Benassou // Ismail Khalfaoui
title: Bringing Deep Learning Workloads to JSC supercomputers
subtitle: Recap of Day 1
date: December 9th, 2025
---

https://indico3-jsc.fz-juelich.de/event/240/

# Summary of Day 1

---

##  Quick recap

Quick recap

Alexandre led a comprehensive training session on supercomputer usage, covering job submission, resource management, and essential configurations including SSH key setup and software module management. The session included hands-on guidance for participants to configure their environments, troubleshoot connection issues, and properly use the supercomputer's resources through various tools and commands. The training concluded with demonstrations on running machine learning tasks and neural network training, including discussions on data preprocessing and file transfer methods between different computing systems.

Next steps

All participants: Complete the survey when sent after the course ends
Cristina: Create a new SSH key and repeat all configuration steps to fix connection issues
All participants: Join the TRAINING2556 project if not already done to ensure compute time access
All participants: Install Visual Studio Code and required plugins if not already installed
All participants: Configure SSH keys and add them to Jureca and JUDAC systems via the JuDoor website
All participants: Set up IP address restrictions on JuDoor for secure access from their locations
All participants: Create virtual environment using the provided template and install required packages
All participants: Download the pets dataset on login nodes before running training jobs on compute nodes
Francesco: Be aware that after December 31st, files can still be accessed via JUDAC for 3 months for data transfer
Antonio : Review the slides and catch up on missed content from the beginning of the course
Summary

## Supercomputer Training and Best Practices

Alexandre conducted a training session on using supercomputers, focusing on job submission, resource management, and best practices. He explained the architecture of supercomputers, distinguishing between login nodes and compute nodes, and emphasized the importance of efficient resource use due to limited access time. Participants were instructed to join a project for access to compute time and were guided through configuring their machines for secure SSH connections to the supercomputer. Alexandre highlighted the need for batch jobs over interactive sessions for optimal use of the machine and encouraged questions throughout the session.

## Technical Setup and Security Guidance

Alexandre led a technical session to help participants set up necessary tools and configurations for their work. He addressed issues such as plugin installations, SSH key setup, and Visual Studio Code configurations, providing step-by-step guidance and troubleshooting support to participants like Meral and Emil. Participants were reminded to avoid reusing SSH keys across different systems for security reasons. By the end of the session, Alexandre confirmed that most participants had successfully completed the required setup, with a few still working through issues.

## SSH Configuration and Troubleshooting Guide

The team discussed SSH configuration issues and provided guidance on setting up SSH keys and config files for different operating systems. Alexandre helped several team members troubleshoot their configurations, particularly focusing on Windows Subsystem for Linux (WSL) users who needed to adjust their paths and file locations. The team confirmed that the config file should be empty unless users are working with it, and emphasized that WSL creates two home directories which can cause confusion with SSH searches.

## SSH Key Setup for Jureca

Alexandre guided participants through the process of setting up SSH key access to Jureca, a supercomputer. He explained how to generate and configure SSH keys, including restrictions by IP address, and demonstrated the process using his own IP address. Participants were instructed to copy their public keys into the Jureca system's SSH key management interface. Mohammad experienced some difficulties but was able to complete the process with Alexandre's help. The session concluded with Alexandre explaining the purpose of JUDAC, a separate machine that provides access to file systems but not compute nodes, allowing users to save their files after project completion.

## SSH Configuration and Troubleshooting

Alexandre guided the team through SSH key configuration and troubleshooting, helping Robert and Cristina connect to the Jureca machine. He discovered that Robert was using the wrong username and fixed it by showing him the correct configuration. Cristina had issues with permission denied errors, which Alexandre helped resolve by showing her the correct SSH configuration lines to add to her file. Meral also faced permission issues, and Ismail helped troubleshoot her connection problems, discovering that her private key file was in a non-standard location (MNT) on her Windows machine.

## SSH Setup and Troubleshooting Session

Alexandre guided Meral through the process of setting up SSH access to a supercomputer, resolving file permission issues on Windows by adjusting security settings. He helped other participants troubleshoot similar issues, including Patrick who was using a Mac and Fabian who needed to configure two-factor authentication. By the end of the session, all participants were able to successfully connect to the remote machine through Visual Studio Code.

## Supercomputer Environment Setup Tutorial

Alexandre guided participants through the process of accessing and setting up their environment on a supercomputer, emphasizing the importance of using project directories to avoid filling the home directory. He explained the use of the module system, which allows users to access different versions of software, and demonstrated how to search for and load specific software modules. The session aimed to prepare participants for the upcoming course by ensuring they had the necessary software and configurations in place.

## Supercomputer Module Management Tutorial

Alexandre provided a tutorial on using modules in the supercomputer environment, explaining how to load different software versions without conflicting with each other. He demonstrated how to manage modules with specific versions, compilers, and MPI configurations, and showed how to purge modules when needed. Florianscheidl asked about using modules with Python package managers like UV, and Alexandre explained how to combine system modules with virtual environments using scripts and commands like uvip. The session concluded with Alexandre demonstrating how to easily transfer and edit files on the supercomputer using a web interface, rather than requiring commands like SCP or SFTP.

## Supercomputer Code Execution Guidance

Alexandre helped Patrick and Mohammad resolve issues with running code on a supercomputer using Visual Studio Code. He guided them through connecting to the supercomputer, opening and running a Python script for matrix multiplication, and explained the importance of running code on the login node rather than the compute nodes. Both Patrick and Mohammad successfully executed the code after following Alexandre's instructions.

## Supercomputer Training for Matrix Multiplication

The meeting focused on teaching participants how to use a supercomputer for running matrix multiplication and neural network training. Alexandre explained the importance of using compute nodes instead of login nodes and introduced SLURM, a resource management system, for submitting jobs. He demonstrated how to create and submit a batch script, manage jobs using the sbatch command, and monitor job status with the squeue command. The group also discussed how to set up virtual environments and install additional software packages using a template script. Participants were encouraged to experiment with the process and ask questions.

## Virtual Environment Setup for ML

Alexandre demonstrated how to set up a virtual environment with necessary libraries for machine learning tasks and explained the process of running a simple cat/dog classifier using FastAI. He highlighted that the compute nodes lack internet access, causing the dataset download to fail, and showed a workaround by modifying the script to run the data preprocessing steps on the login node while commenting out the training code. Patrick confirmed experiencing the same issue, and Alexandre clarified that the solution involves running the modified script on the login node to download and preprocess data.

## Neural Network Training and SSH

The meeting focused on training a neural network using SSH port forwarding and Visual Studio Code. Alexandre demonstrated how to download and train a neural network model, achieving 99% accuracy. He also explained how to use TensorBoard for monitoring the training process and how to access the supercomputer's web server through SSH port forwarding. The group discussed file transfer methods, with Alexandre recommending rsync for large files and UFTP for very large datasets. Questions were answered about accessing different computing systems (JUDAC, Jules Booster) and the availability of course materials. The session concluded with a reminder that a survey would be sent after the course ends.