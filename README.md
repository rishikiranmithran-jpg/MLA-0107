###Depth first search

    CREATE empty set Visited

    CALL DFS_Visit(StartNode)

    DFS_Visit(Node)
        ADD Node to Visited
        VISIT Node

        FOR each Neighbor of Node in Graph DO
            IF Neighbor not in Visited THEN
                CALL DFS_Visit(Neighbor)
            END IF
        END FOR
    END DFS_Visit
Mini-max
Minimax(Node, Depth, IsMax)

    IF Depth = 0 OR Node is leaf THEN
        RETURN value
    END IF

    IF IsMax THEN
        RETURN max(Minimax(children))
    ELSE
        RETURN min(Minimax(children))
    END IF
Uniform cost search
    CREATE priority queue PQ
    CREATE set Visited

    INSERT (0, Start) into PQ      // (cost, node)

    WHILE PQ not empty DO
        (Cost, Node) ← REMOVE node with minimum cost from PQ

        IF Node = Goal THEN
            PRINT "Goal Reached with cost", Cost
            EXIT
        END IF

        IF Node not in Visited THEN
            ADD Node to Visited

            FOR each Neighbor of Node DO
                INSERT (Cost + EdgeCost, Neighbor) into PQ
            END FOR
        END IF
    END WHILE

Greedy Best First search

GreedySearch(Graph, Start, Goal)

    CREATE priority queue PQ
    INSERT Start using heuristic

    WHILE PQ not empty DO
        Node ← REMOVE lowest heuristic node
        PRINT Node
        IF Node = Goal THEN EXIT
        INSERT neighbors into PQ
    END WHILE

Breadth First search
BFS(Graph, StartNode)

    CREATE empty queue Q
    CREATE empty set Visited

    ADD StartNode to Visited
    ENQUEUE StartNode into Q

    WHILE Q is not empty DO
        CurrentNode ← DEQUEUE Q
        VISIT CurrentNode

        FOR each Neighbor of CurrentNode in Graph DO
            IF Neighbor not in Visited THEN
                ADD Neighbor to Visited
                ENQUEUE Neighbor into Q
            END IF
        END FOR
    END WHILE




Alpha beta pruning
AlphaBeta(Node, Depth, α, β, IsMax)

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


A *search
AStar(Graph, Start, Goal)

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



Water Jug problem

WaterJug(Jug1, Jug2, Target)

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

 DecisionTree(Dataset, Target)

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


CryptArithmetic()

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




NeuralNetwork(Inputs, Weights, Bias)

    INITIALIZE weights and bias
    FOR each training example DO
        CALCULATE weighted sum
        APPLY activation function
        COMPARE output with target
        UPDATE weights if error exists
    END FOR

    RETURN trained model

END NeuralNetwork




