School Infection Simulation Model
This project implements a school infection simulation using the Mesa framework to model the spread of diseases among students in a school environment. It tracks various interactions such as dorm contacts, class contacts, and random contacts to simulate the spread of infection. The model runs using a multi-agent system where each student is represented by an agent.

Repository Structure
TB-ABM/
├── TB_ABM/                  # Core simulation notebooks
│   ├── A_100.ipynb          # school A outbreak scenario
│   ├── B_100.ipynb          # school B outbreak scenario
│   ├── C_100.ipynb          # school C outbreak scenario
│   └── D_100.ipynb          # school D outbreak scenario
│
├── requirements.txt         # Python dependencies
└── README.md


Overview
The model simulates the spread of a disease among students in a school, considering interactions among students in classrooms, dormitories, and random contacts. The infection dynamics are governed by state transitions between Susceptible (S), Exposed (E), Infected (I), and Recovered (R) states.

The simulation also leverages parallel computing (using Joblib) to run multiple iterations in parallel and record the results for analysis.

Key Features:
Student Agent: Each student is an agent with attributes such as class ID, dorm ID, and infection status.
Contact Patterns: Includes class, dorm, and random contacts to simulate disease transmission.
Parallel Simulation: Multiple simulations are run in parallel using Joblib to gather results quickly.
Profiling: The code uses cProfile to profile and analyze the simulation's performance.
Requirements
Python 3.x
Required libraries (listed in requirements.txt):
mesa
pandas
joblib
numpy
cProfile
Installation
Clone the repository:

git clone https://github.com/heyueyueyue/TB-ABM.git
cd school-infection-simulation
Install the required dependencies:

pip install -r requirements.txt
Usage
To run the simulation:

Initialize and run the model:

python simulation_model.py
This will run the school infection simulation model with 11099 students and an initial infected count of 1, running the simulation for 200 iterations.

To profile the performance of the simulation, you can use:

python simulation_model.py
It will generate a heyue_A_hzc_joblib.prof file containing profiling data, which can be analyzed later.

After running the simulation, you will get an output CSV file (A_200.csv) containing the results of the simulation, including the number of new infections on each day.

Code Description
Classes and Functions
StudentAgent: Represents each student in the model with attributes like status, roommates, and class_id. The agent interacts with other agents based on its infection status.

SchoolModel: This is the main model class where agents are created and interactions are simulated over multiple time steps. The model includes functions to handle agent interactions in dorms, classes, and randomly.

run_single_model: Runs a single simulation instance of the school infection model over 20 time steps.

run_model: Executes the run_single_model function multiple times in parallel, collecting results for analysis.

cProfile: Used to profile the performance of the model and record how much time is spent in each function.

Example Output
The simulation will produce a CSV file (A_200.csv) with the following columns:

Date: The date of the simulation (time step).
New Infections: The number of new infections on that day.
The output DataFrame is organized as follows:

Date	Run 1	Run 2	...	Run N
1	5	3	...	...
2	10	7	...	...
...	...	...	...	...
Profiling Results
After running the profiling using cProfile, you can analyze the performance of the simulation using the pstats library. Example:

import pstats
p = pstats.Stats('heyue_A_hzc.prof')
p.strip_dirs()
p.sort_stats('tottime').print_stats(10)
This will print the top 10 functions consuming the most time during the simulation.

Notes
Time Step: Each time step represents a day in the simulation.
Infection Probability: The probability of an infection occurring during a contact is set to 0.0057254 (adjustable).
Simulation Length: The model runs for 20 days, and the simulation results are saved after running all iterations.
License
This project is licensed under the MIT License.

Contributing
Feel free to fork the repository and submit pull requests. If you find any bugs or have suggestions for improvements, please open an issue.

Acknowledgments
The Mesa framework for agent-based modeling.
Joblib for parallel computing.
Pandas for data handling and analysis.
