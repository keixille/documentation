# Scenario
Initially, we have 3 job tier. The lowest tier is Engineer and the highest tier is Manager. Below is the representation of the scenario: 
```mermaid
graph TD
A[Manager 1] --> B[Senior Engineer 1]
A --> C[Senior Engineer 2]
B --> D[Engineer 1]
B --> E[Engineer 2]
C --> F[Engineer 3]
C --> G[Engineer 4]
```

# Problem
The problem which we want to handle are:
1. Handle new job tier insertion in the top, bottom, and middle of the hierarchy
```mermaid
graph TD
Top(Senior Manager 1) --> A
A[Manager 1] --> B[Senior Engineer 1]
A --> C[Senior Engineer 2]
B --> Middle(Middle Engineer 1)
Middle --> D[Engineer 1]
Middle --> E[Engineer 2]
C --> F[Engineer 3]
C --> G[Engineer 4]
D --> Bottom(Intern 1)

subgraph Top Insertion
Top 
end

subgraph Middle Insertion
Middle
end

subgraph Bottom Insertion
Bottom
end
```
2. Query to get all member below certain tier 
(ex: All member below Senior Engineer 1)
```mermaid
graph TD
A[Manager 1] --> B[Senior Engineer 1]
A --> C[Senior Engineer 2]
B --> D[Engineer 1]
B --> E[Engineer 2]
C --> F[Engineer 3]
C --> G[Engineer 4]

subgraph Query
D
E
end
```

# Solution

The assumption is, every tier will have maximum slot equals to 10.
|Tier Name                      |Tier Code                  |
|-------------------------------|---------------------------|
|Manager 1			            |1 0 0            			|
|Senior Engineer 1           	|1 1 0						|
|Senior Engineer 2           	|1 2 0						|
|Engineer 1						|1 1 1						|
|Engineer 2						|1 1 2						|
|Engineer 3						|1 2 1						|
|Engineer 4						|1 2 2						|
