This repository contains my Lab 4 - Continuous Integration with Jenkins solution for the Introduction to DevOps module in the third year of the Computer Science course at TU Dublin. 

# Overview  

This lab focuses on setting up Jenkins to implement a Continuous Integration (CI) pipeline for automating software builds. The pipeline is designed to build Git from source every 10 minutes, simulating real-world CI/CD practices.

# Key Features & Steps

- **Setting up Jenkins** on a Virtual Machine (VM) using Vagrant.
- **Installing Jenkins** and granting it root privileges for automation.
- **Configuring Jenkins** with an admin account and accessing it via `http://localhost:8082`.
- **Creating a Jenkins Pipeline** named `Build_Git` with the following stages:
  - **Cloning the Git repository** (`https://github.com/git/git`).
  - **Preparing the build** (Configuring and setting up dependencies).
  - **Compiling Git** using `make`.
  - **Installing the final program** (`sudo make install`).
- **Automating the build to run every 10 minutes** using Jenkins' cron syntax:  
  ```  
  TZ=Europe/Dublin  
  H/10 * * * *  
  ```
- **Verifying successful execution**, including multiple builds and ensuring the compiled Git version works with:  
  ```  
  ~/git-latest/bin/git --version  
  ```
  
## Technologies Used

- **Jenkins**
- **Git**
- **Linux (Debian-based VM)**
- **Bash & Shell Scripting**
- **Vagrant**
- **Makefile & Build Tools**

This project demonstrates a fully automated CI pipeline using Jenkins, essential for modern software development workflows.
