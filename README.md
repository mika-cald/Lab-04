# Lab 04 - SOP/POS and KMaps 
### Team 4 - Mika Calderon + Tim Palacios

In this lab, you’ve learned how to apply KMaps, Sum Of Products and Products of
sums to simplify digital logic equations. Then, you’ve proven out that they work
using an implemented design on your Basys3 boards.

## Rubric

| Item | Description | Value |
| ---- | ----------- | ----- |
| Summary Answers | Your writings about what you learned in this lab. | 25% |
| Question 1 | Your answers to the question | 25% |
| Question 2 | Your answers to the question | 25% |
| Question 3 | Your answers to the question | 25% |

## Lab Summary

In this lab, we learned how to simplify Boolean logic equations using KMaps. We 
started by adding an equation to our naive file to represent all of the 1 values 
in our truth table. Our next step was turning our truth table into a KMap to easily 
find our Sum of Products and Product of Sums. These two equations were added to 
the minterm and maxterm files, respectively which allowed us to run a simulation 
in Vivado to check if all three files produced the same result. When the simulation 
worked, we could be sure that we simplified the original truth table correctly. 
This lab showed that Boolean expressions can be simplified or written in different 
ways that may be more efficient for the type of code we are trying to write.

## Lab Questions

### Why are the groups of 1’s (or 0’s) that we select in the KMap able to go across edges?

Groups of 1's or 0's are able to go across edges because the cells differ by one 
variable. Logically, they would be considered next to each other and can be grouped 
together to further simplify a Boolean expression.

### Why are the names Sum of Products and Products of Sums?

The AND operation acts like multiplication, and the OR operation acts like 
addition. 

For Sum of Products, we start by putting values in AND operations (products) and 
then OR all of those AND operations together (the sum of those products). 
EX. `(A & B) | (C & D)`

For Products of Sum, we do the opposite and start by putting values in OR 
operations (sum). Those sums are then all put in AND operations with each other 
(the product of the sums).
EX. `(A | B) & (C | D)`

### Open the test.v file – how are we able to check that the signals match using XOR?

We are able to check if signals match with XOR, as it outputs 1 when the inputs are 
different and 0 when they are the same. In the test file, when the XOR does not 
equal 0, that means that the signals are different and that our test failed. If all 
outputs are 0, then all of our implementations had the same result.