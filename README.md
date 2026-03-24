## 📘 Project Overview

This repository contains the implementation of fundamental Artificial Intelligence search and decision-making algorithms.
The objective of this laboratory work is to analyse how intelligent systems explore problem spaces, compute optimal solutions, and support automated reasoning.

## ✨ Unique Contributions

✔ Implemented algorithms using interactive user-defined inputs  
✔ Displayed traversal sequence and optimal solution path  
✔ Included computational complexity understanding  
✔ Added execution output screenshots for clarity  
✔ Structured programs using modular functions    
✔ Performed conceptual comparison between search strategies  

## ⚙️ Algorithms Implemented

 🔹 Breadth First Search (BFS)  
 🔹 Depth First Search (DFS)  
 🔹 Uniform Cost Search  
 🔹 Greedy Best First Search  
 🔹 A* Search Algorithm  
 🔹 Minimax Algorithm  
 🔹 Alpha–Beta Pruning  
 🔹 Water Jug Problem  
 🔹 Decision Tree Construction  
 🔹 CryptArithmetic Problem  
 🔹 Basic Neural Network Training Model  

### 🔎 Depth First Search

    CREATE empty set Visited
    DFS(Node)
       ADD Node to Visited
       VISIT Node
       FOR each unvisited Neighbor
          CALL DFS(Neighbor)
    END
    CALL DFS(StartNode)
    
### 🎮 Minimax

    IF depth = 0 → RETURN node value
      IF Max player
        RETURN max(left subtree, right subtree)
      ELSE
        RETURN min(left subtree, right subtree)
    END
        
### 💰 Uniform cost search
    CREATE priority queue PQ
    INSERT Start with cost 0
    
    WHILE PQ not empty
      REMOVE node with minimum cost
      IF node is Goal → STOP
      ADD node to Visited
      INSERT neighbours with updated cost
    END WHILE
    
### 🚀 Greedy Best First search

    INSERT Start into priority queue (based on heuristic)
    
    WHILE queue not empty
      REMOVE node with lowest heuristic
      IF node is Goal → STOP
      INSERT neighbours into queue
    END WHILE

### 📡 Breadth First search

    CREATE queue and Visited set
    INSERT Start into queue
    
    WHILE queue not empty
      REMOVE front node
      IF not visited
          VISIT node
          ADD to Visited
          INSERT neighbours into queue
     END WHILE

### 🎯 Alpha beta pruning

    IF Depth = 0 THEN RETURN value

    IF IsMax THEN
        FOR each child DO
            α ← max(α, AlphaBeta(child))
            IF β ≤ α THEN BREAK
        END FOR
    ELSE
        FOR each child DO
            β ← min(β, AlphaBeta(child))
            IF β ≤ α THEN BREAK
        END FOR
    END IF


### 🌟 A *search

    CREATE priority queue PQ
    INSERT (f=0, Start)

    WHILE PQ not empty DO
        Node ← REMOVE node with lowest f
        IF Node = Goal THEN
            PRINT "Goal Reached"
            EXIT
        END IF
        FOR each Neighbor DO
            g ← path cost
            f ← g + heuristic
            INSERT Neighbor into PQ
        END FOR
    END WHILE



### 🧩 Water Jug problem

    CREATE queue Q
    CREATE set Visited

    ENQUEUE (0,0)
    ADD (0,0) to Visited

    WHILE Q not empty DO
        (x,y) ← DEQUEUE Q

        IF x = Target OR y = Target THEN
            PRINT "Target Reached"
            EXIT
        END IF

        GENERATE possible states
        ADD unvisited states to Q
    END WHILE

    PRINT "Target Not Possible"  

 ### 🌳 DecisionTree(Dataset, Target)

    IF all records belong to same class THEN
        RETURN that class
    END IF

    IF no attributes left THEN
        RETURN majority class
    END IF

    SELECT best attribute using Information Gain
    CREATE decision node for that attribute

    FOR each value of selected attribute DO
        SPLIT dataset
        RECURSIVELY build subtree
    END FOR

RETURN Decision Tree


### 🔐 CryptArithmetic()

    FOR all possible digits S,E,N,D,M,O,R,Y from 0 to 9 DO
        ENSURE all digits are different
        ENSURE S and M are not zero

        FORM numbers SEND, MORE, MONEY

        IF SEND + MORE = MONEY THEN
            PRINT solution
            STOP
        END IF
    END FOR

END CryptArithmetic

### 🧠 Neural Network

    INITIALIZE weights and bias
    FOR each training example DO
        CALCULATE weighted sum
        APPLY activation function
        COMPARE output with target
        UPDATE weights if error exists
    END FOR

    RETURN trained model

END NeuralNetwork




