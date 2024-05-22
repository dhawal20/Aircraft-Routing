# **Code for JATRS 2024 paper: Aircraft Routing using Dynamic Programming and Reinforcement Learning: A Customer-Centric Approach**
This github repository consists of all the codes and data files required for the paper accepted and published in JATRS 2024 titled "Aircraft Routing using Dynamic Programming and Reinforcement Learning: A Customer-Centric Approach". Authors - Dhawal Thakkar, Balamurugan Palaniappan. Link to access the paper https://www.sciencedirect.com/science/article/pii/S2941198X24000290

# **Abstract**

Over the past few decades, the airline industry has evolved into a sophisticated business, with conventional objectives such as operational efficiency, effective fleet assignment, flight punctuality, and equitable crew scheduling being the primary focus. Nevertheless, given the growing accessibility to customer feedback (either through public forums or private data), it is crucial to make business decisions that cater to the customers’ requirements in addition to conventional goals. Within aircraft operations, there is a series of decisions to be made, such as flight scheduling, fleet assignment, aircraft routing, and crew scheduling. After designating a fleet type to each flight leg, airlines ascertain the sequence of flight legs, or strings, to be operated by individual aircrafts, while complying with obligatory maintenance checks. This constitutes the aircraft routing problem.

We introduce a novel approach to aircraft routing problem, by infusing traditional methodologies with insightful customer feedback to create a more responsive and customer-centric model. Unlike conventional techniques of constructing routes, in our work, we construct maintenance feasible strings. Traditional aircraft routing methodologies typically concentrate on minimizing propagated delay. However, by integrating customer feedback, more effective prioritization to minimize delays for flight legs with higher customer dissatisfaction can be achieved. We propose an optimization model that strives to minimize propagated delay while prioritizing flights based on customer feedback, thus resulting in customer-aware routes. To solve the proposed optimization model, we design an iterative alternating optimization scheme where feasible strings are first constructed from the pool of available flight legs using a string generation procedure, followed by solving an integer linear optimization problem over only the feasible set of strings obtained in the first stage. To construct feasible strings of flights at each iteration, we use two different methods. The first method is based on a dynamic programming approach which is useful for mean delay information. To handle practical cases where delays are uncertain, we propose a reinforcement learning (RL) approach to construct the strings. We provide experiments of our proposed methods on synthetic and real data sets and demonstrate the effectiveness of our RL model in comparison to dynamic programming based model. Our experiments affirm that routing decisions informed by customer feedback prioritize minimizing delays for specific flight legs, resulting in routes that are inherently customer-friendly.


# **About Code**

All the codes are written in Python notebook files (.ipynb format). The package requirements are minimal and majorly standard packages are only used. Psuedo codes for the implementation can be found in the supplementary material of the paper.

**Data Folder**

Data Folder contains the excel files for the input data. In the paper we have talked about Test Case 1, 2, 3, 4 and Indigo_Fleet test cases which are present in this folder.

We propose an optimization model that strives to minimize propagated delay while prioritizing flights based on customer feedback, thus resulting in customer-aware routes. To solve the proposed optimization model, we design an iterative alternating optimization scheme where feasible strings are first constructed from the pool of available flight legs using a string generation procedure, followed by solving an integer linear optimization problem over only the feasible set of strings obtained in the first stage. To construct feasible strings of flights at each iteration, we use two different methods: Dynamic Programming (DP) and Reinforcement Learning (RL) approaches.

**DP_aircraft_routing.ipnyb**

The file "DP_aircraft_routing.ipnyb" contains the implementation of the DP approach mentioned in the paper. DP approach is useful when mean delay information is available. Optimization model discussed in Section 4 of the paper is implemented in this approach using pyomo. Discussion of the DP approach can be found in Section 5 of the paper and the pseudocodes can be found in the supplementary material of the paper.

**RL_aircraft_routing.ipnyb**

The file "RL_aircraft_routing.ipnyb" contains the implementation of the RL Framework approach mentioned in the paper. The objective of RL framework is to capture the uncertainties in delays the flight legs might face in real life situations. Optimization model discussed in Section 4 of the paper is implemented in this approach using pyomo. Discussion of the RL approach can be found in Section 6 of the paper and the pseudocodes can be found in the supplementary material of the paper.

**stringEnumerator.ipynb**

"stringEnumerator.ipynb" enumerates all possible flight sequence strings, which are then used for selection based on the objective (minimization of propagated delays with the option of incorporating importance assignments as well). It is primarily designed for smaller test cases (Test Case1,2,3,4 whose excel files can be found in Data Folder) as enumerating for large scale data is not computationally feasible. Optimization model discussed in Section 4 is implemented to achieve the objective.

 **dataGenerationDelays.ipynb**

The file dataGenerationDelays.ipynb is used to generate delays which is used in the DP approach and the distribution defined for the flight legs belonging to each cluster is then used in RL approach to capture the uncertainties in delay. Detailed discussion on the delay generation scheme can be found in Section 7.2.2 of the paper.

**fileRefiner.ipynb, dataCleaner_IndigoData.ipynb**

These files are used to clean the data from the excel file obtained from the Indigo website to suit our implementation purposes. "fileRefiner.ipynb" particularly removes the flight legs that do not have both incoming and outgoing connections. "dataCleaner_IndigoData.ipynb" formats the date and time of the original Indigo data file into the format that will be suited for our implementation purposes.

**stringVisualizer.ipynb**

The file "stringVisualizer.ipynb" is used to create Gantt Chart like visualisations of the strings (e.g. the ones found in Figures 10 and 11 in the paper). In the file all the strings obtained from Test cases 1, 2, 3 and 4 can be found with and without $\xi$ value assignments of the flight legs. 
 
The requirements list can be seen in the file named "requirements.txt". To install the required dependencies, run the following command:
```
pip install -r requirements.txt
```

# **Citation**

Citation is yet to be announced and will be soon updated.

# **Contact**
For further queries please get in touch primarily at  dhawalthakkar.199020@gmail.com or alternatively at balamurugan.palaniappan@iitb.ac.in 
