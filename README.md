# DSC212 — Assignment 1  
**Author:** Yash Jitendra Mhatre  
**Student ID:** IMS24140  

---

##  Overview  
This repository contains the solution to **Assignment 1** of the DSC212 course.

---

##  Context: The Karate Club Story  

In the early 1970s, **Wayne W. Zachary**, a graduate student in anthropology, conducted a study on social interactions within a university **karate club**.  
Over two years, he observed **34 members**, recording their friendships and interactions — such as training together, attending events, and socializing outside class.  

From these observations, Zachary constructed a **social network** where:
- Each member is a **node**  
- An **edge** connects two members if they frequently interacted  

This network, now known as the **Zachary’s Karate Club Graph**, has become one of the most iconic examples in **network science**.

###  The Split  
During Zachary’s research, a dispute arose between:
- The **instructor** (“Mr. Hi”), and  
- The **club administrator** (the **club president**)  

The disagreement — over how to spend club funds — eventually **split the club into two factions**.  
Zachary later observed that **friendship patterns** strongly predicted this division: members tended to follow their close friends.  

---

##  Research Question  
Given the network **before** the split, can a **community detection algorithm** recover the same division purely from the graph structure?  

This makes the Karate Club network a perfect “**Hello World**” of community detection — small, interpretable, and historically significant.

---

##  Process  

The algorithm implemented in this assignment follows the **spectral method of modularity maximization**.  

1. **Compute the Modularity Matrix (B)** for the network  
2. **Find the leading eigenvector** of \( B \)  
3. **Split nodes** into communities based on the **sign** of their eigenvector components  
4. **Repeat recursively** on each resulting community  
   - Continue until no split yields a **positive modularity gain (ΔQ > 0)**  

*(In this case, the process stops after the first iteration.)*

---

##  Conclusions  

- The algorithm identifies **multiple communities** through recursive splitting  
- **Nodes 0 and 33** (the two leaders) remain **most central** across splits  
- **Betweenness centrality** changes significantly between iterations  
  - Nodes that bridge communities lose importance once the split occurs  
- **Degree centrality** remains constant  
  - It depends only on the number of direct connections  
- The **first split** closely matches the **actual historical division** of the club  

---

##  Key Takeaway  
The Karate Club network elegantly demonstrates how **mathematical structures in graphs** can reveal the **social dynamics** that shape real-world communities.
