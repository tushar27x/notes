![[Pasted image 20241110114745.png]]

- **Equivalence Partitioning** -> Divides inputs into valid and invalid groups (partitions). Tests a representative value from each group, reducing the number of test cases needed.

- **Boundary Value Analysis** -> Focuses on the boundaries of input ranges. Testing boundary values helps identify errors at the edge of input domains (e.g., minimum and maximum values).

- **Decision Table Testing** -> Creates a table of possible inputs and their expected outputs, helpful for applications with complex business logic.![[Pasted image 20241110114321.png]]
1. **Condition Stubs :** The conditions are listed in this first upper left part of the decision table that is used to determine a particular action or set of actions.
2. **Action Stubs :** All the possible actions are given in the first lower left portion (i.e, below condition stub) of the decision table.
3. **Condition Entries :** In the condition entry, the values are inputted in the upper right portion of the decision table. In the condition entries part of the table, there are multiple rows and columns which are known as Rule.
4. **Action Entries :**  In the action entry, every entry has some associated action or set of actions in the lower right portion of the decision table and these values are called outputs.


 - **State Transition Testing** ->Tests the application’s behavior under various states, focusing on how it transitions from one state to another.![[Pasted image 20241110114615.png]]

- **Error Guessing** -> Relies on the tester’s experience to predict areas where defects are likely, such as fields that may accept invalid input or functions that may be prone to edge cases.
 