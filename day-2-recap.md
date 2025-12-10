---
author: Alexandre Strube // Sabrina Benassou // Ismail Khalfaoui
title: Bringing Deep Learning Workloads to JSC supercomputers
subtitle: Recap of Day 2
date: December 10th, 2025
---

# Summary of Day 2

---

## Quick recap

The meeting focused on optimizing data loading and storage strategies for machine learning projects on supercomputers, with detailed explanations of file systems, data formats, and distributed training techniques. Participants learned about efficient data handling methods, including HDF5 storage and parallelized training approaches using transformer language models and distributed data parallelism. The session addressed technical challenges and troubleshooting issues during the implementation of distributed training jobs, concluding with discussions on various parallelization techniques and resources for further learning.

---

## Next steps

Alexandre: Post yesterday's recording on YouTube and share on Slack
Alexandre: Make meeting host available to Narimene for when he leaves
Participants: Clone the data loading repository from the link provided in Slack
Participants: Add 'datasets' to requirements.txt in SCVENF template and run setup
Participants: Download the WikiText dataset by running the training script on login node before submitting to compute nodes
Participants: Comment out lines 76 and 135 in the training script before downloading dataset
Participants: Install torch_run_jsc package
Participants: Follow TODO instructions in to_distributed_training.py and run_to_distributed_training.sbatch files
Participants: Increase number of nodes to 2 to test multi-node training with 8 GPUs
Participants: Update PyTorch to version 2.7 or 2.8 in requirements.txt for FSDP functionality
Participants: Remove PyTorch module loading from module.sh when upgrading to PyTorch 2.7+
Participants: Complete and submit the course feedback survey that will be sent after the session
Narimene: Consider adding coding examples for tensor parallelism and pipelining to future course offerings

---

# Summary

## Optimizing Data for Supercomputers

Alexandre introduced the session, noting that Sabrina would lead most of the course due to his prior commitment. He explained the importance of efficiently loading data onto supercomputers for machine learning, emphasizing the need to keep GPUs busy and the significance of data storage strategies. He highlighted the differences between classical and deep learning in terms of data usage and described the supercomputer's file system, including project folders, scratch space, and data directories. The session aimed to provide participants with insights into optimizing data loading and storage for their projects.

---

## Efficient Large Dataset Storage Strategies

Narimene explained how to efficiently load and store large datasets for training, focusing on strategies for datasets smaller than 500GB that can fit into RAM. She demonstrated methods for storing data in HDF files and Apache Arrow format, addressing the system's inode limitations by showing how to create these files to avoid running out of available inodes. The discussion included a practical example using the ImageNet dataset, where images were transformed into binary format to ensure compatibility with HDF and Arrow formats, and she provided instructions for running example scripts to save and load the data.

---

## HDF5 and Distributed Training Overview

The meeting focused on clarifying file formats and systems, with Narimene explaining that HDF5 is the preferred format due to its performance and widespread use in the scientific community. They discussed how to handle heterogeneous datasets using HDF5 groups and binary formats for variable-sized data. The group then moved on to parallelized training using a transformer language model with the Wikitext dataset, with Alexandre reminding participants to clone the necessary repository and install required datasets. The session concluded with a review of training.py and run_distributed_training.sbatch files, which participants were instructed to run using SLURM batch commands.

---

## Optimizing GPU Utilization in Training

The team discussed running distributed training jobs on the supercomputer, focusing on GPU utilization and communication between GPUs. Narimene explained that using only one GPU out of four available was inefficient and demonstrated how to modify the SBATCH file to use all GPUs. They discussed collective operations like all-reduce, all-gather, and reduce-scatter for efficient communication between GPUs. The team also addressed issues with data downloading and reservation times for running jobs on the supercomputer.

---

## Distributed Training Techniques Overview

The meeting covered the basics of distributed computing terminology and distributed training techniques, with a focus on DDP (Distributed Data Parallel). Narimene explained key concepts including word size, rank, and locker rank, followed by a detailed explanation of DDP implementation in PyTorch. The group discussed technical issues with Python code execution and setup, with Alexandre providing assistance to Agnieszka and others. The session concluded with a demonstration of distributed training using 4 GPUs, showing improved GPU utilization and reduced training time compared to single-GPU training.

---

The team discussed issues with running distributed training jobs and code errors. Narimene helped Florianscheidl troubleshoot errors related to torch run and environment setup, suggesting he clone the STV template again and install dependencies correctly. Agnieszka faced an issue with the sbatch file, which Narimene helped resolve by identifying and removing an extra hashtag and replacing file names. Peter had forgotten to remove "torch" before "safety room" in his code, which he fixed. The team also clarified how to access LLV, which requires the same password as Eudor.


---

The meeting covered several topics related to distributed training techniques in deep learning. Narimene explained the concepts of Data Parallelism (DDP) and Fully Sharded Data Parallelism (FSDP), including how they work and when to use them. She also discussed other parallelization techniques like tensor parallelism and pipelining. The participants encountered some issues with installing the required PyTorch version (2.6 or 2.7) for FSDP, but some were able to resolve them. Narimene provided useful resources for further learning and mentioned that a survey would be sent out to gather feedback on the course.