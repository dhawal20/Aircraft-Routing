# **Code for JATRS 2024: Aircraft Routing using Dynamic Programming and Reinforcement Learning: A Customer-Centric Approach**
This github repository consists of all the codes and data files required for the paper submitted to JATRS 2024 titled "Aircraft Routing using Dynamic Programming and Reinforcement Learning: A Customer-Centric Approach"

# **Abstract**

Over the past few decades, the airline industry has evolved into a sophisticated business, with conventional objectives such as operational efficiency, effective fleet assignment, flight punctuality, and equitable crew scheduling being the primary focus. Nevertheless, given the growing accessibility to customer feedback (either through public forums or private data), it is crucial to make business decisions that cater to the customers' requirements in addition to conventional goals. Within aircraft operations, there is a series of decisions to be made, such as flight scheduling, fleet assignment, aircraft routing, and crew scheduling. After designating a fleet type to each flight leg, airlines ascertain the sequence of flight legs, or strings, to be operated by individual aircraft, while complying with obligatory maintenance checks. This constitutes the aircraft routing problem.

We introduce a novel approach to a particular version of the aircraft routing problem, namely flight leg sequence scheduling, infusing traditional scheduling methodologies with insightful customer feedback to forge a more responsive and customer-centric operational model. Traditional flight sequence scheduling methodologies typically concentrate on minimizing propagated delay. However, by integrating customer feedback to inform scheduling decisions, more effective prioritization of flight legs can be achieved. We propose an optimization model that strives to minimize propagated delay while prioritizing flights based on customer feedback, thus resulting in customer-aware flight leg sequence schedules. To solve the proposed optimization model, we propose an alternating optimization scheme where feasible flight leg sequences are selected from the pool of available flight leg sequences using a string generation procedure, followed by solving an integer linear optimization problem over only the feasible set of flight leg sequences. To construct feasible strings of flights at each iteration, we use two different methods. The first method is based on a dynamic programming approach, which is useful for deterministic delay information. To handle practical cases where delays are uncertain, we propose a reinforcement learning (RL) approach to construct the strings. We provide experiments of our proposed methods on synthetic and real datasets and demonstrate the effectiveness of our RL model in comparison to the dynamic programming-based model.

# **About Code**

The code is written in a Python notebook. The packages requirements are minimal and majorly standard packages are only used. The file "DP_aircraft_routing.ipnyb" contains the implementation of the dynamic programming implementation mentioned in the paper. The file "RL_aircraft_routing.ipnyb" contains the implementation of the Reinforcement Learning framework mentioned in the paper. Folder Data contains all the data set required to test the models. "stringEnumerator.ipynb" enumerates all the strings possible and then selects the best strings based on the objective (minimization of propagated delays or incorporating importance assignemnts as well). "stringEnumerator.ipynb" is primarily designed for smaller test cases (Test Case1,2,3,4 whose excel files can be found in Data Folder) as enumerating for large scale data is not be computationally feasible. Other files are for data cleaning purposes which can be based on requirements or you may need to write different codes for file cleaning based on the data format of the original file. The requirements list can be seen in the file named "requirements.txt". To install the required dependencies, run the following command:
```
pip install -r requirements.txt
```

# **Contact**
For further queries please get in touch at dhawalthakkar.199020@gmail.com
