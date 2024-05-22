# **Code for JATRS 2024: Aircraft Routing using Dynamic Programming and Reinforcement Learning: A Customer-Centric Approach**
This github repository consists of all the codes and data files required for the paper accepted and published in JATRS 2024 titled "Aircraft Routing using Dynamic Programming and Reinforcement Learning: A Customer-Centric Approach". Authors - Dhawal Thakkar, Balamurugan Palaniappan. Link to access the paper https://www.sciencedirect.com/science/article/pii/S2941198X24000290

# **Abstract**

Over the past few decades, the airline industry has evolved into a sophisticated business, with conventional objectives such as operational efficiency, effective fleet assignment, flight punctuality, and equitable crew scheduling being the primary focus. Nevertheless, given the growing accessibility to customer feedback (either through public forums or private data), it is crucial to make business decisions that cater to the customers’ requirements in addition to conventional goals. Within aircraft operations, there is a series of decisions to be made, such as flight scheduling, fleet assignment, aircraft routing, and crew scheduling. After designating a fleet type to each flight leg, airlines ascertain the sequence of flight legs, or strings, to be operated by individual aircrafts, while complying with obligatory maintenance checks. This constitutes the aircraft routing problem.

We introduce a novel approach to aircraft routing problem, by infusing traditional methodologies with insightful customer feedback to create a more responsive and customer-centric model. Unlike conventional techniques of constructing routes, in our work, we construct maintenance feasible strings. Traditional aircraft routing methodologies typically concentrate on minimizing propagated delay. However, by integrating customer feedback, more effective prioritization to minimize delays for flight legs with higher customer dissatisfaction can be achieved. We propose an optimization model that strives to minimize propagated delay while prioritizing flights based on customer feedback, thus resulting in customer-aware routes. To solve the proposed optimization model, we design an iterative alternating optimization scheme where feasible strings are first constructed from the pool of available flight legs using a string generation procedure, followed by solving an integer linear optimization problem over only the feasible set of strings obtained in the first stage. To construct feasible strings of flights at each iteration, we use two different methods. The first method is based on a dynamic programming approach which is useful for mean delay information. To handle practical cases where delays are uncertain, we propose a reinforcement learning (RL) approach to construct the strings. We provide experiments of our proposed methods on synthetic and real data sets and demonstrate the effectiveness of our RL model in comparison to dynamic programming based model. Our experiments affirm that routing decisions informed by customer feedback prioritize minimizing delays for specific flight legs, resulting in routes that are inherently customer-friendly.


# **About Code**

All the codes are written in a Python notebook. The packages requirements are minimal and majorly standard packages are only used. Psuedo codes for the implementation can be found in the supplementary material of the paper; link https://ars.els-cdn.com/content/image/1-s2.0-S2941198X24000290-mmc1.pdf.

**Data Folder**
Folder Data contains all the data set required to test the models.

**DP_aircraft_routing.ipnyb**
The file "DP_aircraft_routing.ipnyb" contains the implementation of the dynamic programming implementation mentioned in the paper. 

**RL_aircraft_routing.ipnyb**
The file "RL_aircraft_routing.ipnyb" contains the implementation of the Reinforcement Learning framework mentioned in the paper.

**stringEnumerator.ipynb**
 "stringEnumerator.ipynb" enumerates all the strings possible and then selects the best strings based on the objective (minimization of propagated delays or incorporating importance assignemnts as well). "stringEnumerator.ipynb" is primarily designed for smaller test cases (Test Case1,2,3,4 whose excel files can be found in Data Folder) as enumerating for large scale data is not be computationally feasible.

 **dataGenerationDelays.ipynb**
 Other files are for data cleaning purposes which can be based on requirements or you may need to write different codes for file cleaning based on the data format of the original file. The requirements list can be seen in the file named "requirements.txt". To install the required dependencies, run the following command:
```
pip install -r requirements.txt
```

# **Contact**
For further queries please get in touch at dhawalthakkar.199020@gmail.com
