Campus Infection Spread Simulation System

Project Overview

This project implements an infection transmission simulation system in campus environments using the Mesa framework. Through multi-agent modeling, the system simulates student contact behaviors in classrooms, dormitories, and random social scenarios while tracking disease propagation.

Core Features
Multi-scenario contact simulation: Precise modeling of three contact scenarios (classroom, dormitory, and random social)

SEIR transmission model: Complete disease cycle implementation (Susceptible-Exposed-Infected-Recovered)

Parallel computing optimization: Utilizes Joblib for accelerated multi-round simulations

Visualized analytics: Built-in data analysis and visualization capabilities

Quick Start
Clone repository:

git clone https://github.com/heyueyueyue/TB-ABM.git
cd TB-ABM

Install dependencies:

pip install -r requirements.txt

Launch and execute:

jupyter notebook

Open the corresponding scenario notebook (e.g. A_100.ipynb) and run all cells to execute complete simulation

Technical Architecture

Core Components
StudentAgent: Student agent containing:

Class/dormitory assignment

Health status (S/E/I/R)

Daily behavior patterns

SchoolModel: Campus environment model managing:

Time step progression

Multi-scenario contact events

Transmission calculations

Data Processing
Automatically generates CSV files containing multi-round simulation results

Built-in statistical analysis and visualization functions

Parameter Configuration
Parameter Default Description

Infection Probability 0.0057254 Transmission probability per effective contact
Simulation Duration 20 days Time span per simulation round
Initial Infections 1 Starting infected count

License

This project is licensed under MIT open-source license, allowing free usage and modification.

Contribution Guidelines

We welcome issue submissions for bug reports or feature suggestions, and accept code improvements via pull requests.

Acknowledgments

Special thanks to these open-source projects:
Mesa multi-agent modeling framework

Joblib parallel computing library

Pandas data processing toolkit
