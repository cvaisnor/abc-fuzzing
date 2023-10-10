# Approximate Bayesian Computation As An Informed Fuzzing Technique

*Chris Vaisnor*

*Johns Hopkins University*

*Baltimore, MD*

# Abstract
# Introduction

Using Approximate Bayesian Computation, can we guess the probability of the boolean output of a black box machine, given a binary input sequence? 

- Useful in cyber-security fuzzing applications where the user attempts to determine the right input for a given output. 

What type of data will be used?
- Synthetic data will be generated as an array consisting of binary values.
	- Could be fixed size, variable, or have a minimum length requirement
- Output will be boolean
	- Could be changed to ternary or integers defined by a specific range

Simulations will be conducted that produce a probability distribution that can inform the prior probability guesses of a pattern matching sequence. 

- Questions arise such as:
	- How many times do you pass in an input sequence before coming to a conclusion about its output?
	- If you only get a fixed number of input attempts, how do you update your priors most efficiently?

Goal: Find the input array / pattern that generates a True output value. For black box machines that require a sufficiently long input, it becomes computationally intractable to brute force all possible combinations of an input sequence. 
# Literature Review

- Paper - Overview of recent developments in Approximate Bayesian Computation
	- https://academic.oup.com/sysbio/article/66/1/e66/2420817
- Paper - Analysis of Three Bayesian Network Inference Algorithms by Liu and Soetjipto
	- https://citeseerx.ist.psu.edu/document?repid=rep1&type=pdf&doi=ac14e6bf50d1491043baf1d854727a68f5f3f51d
- Paper - Fuzzing: Challenges and Reflections
	- https://www.comp.nus.edu.sg/~abhik/pdf/IEEE-SW-Fuzzing.pdf
- Paper - Fuzzing-based hard-label black-box attacks against machine learning models
	- https://www.sciencedirect.com/science/article/abs/pii/S016740482200092X?via%3Dihub
# Methodology

- Build a fixed-length array generator using one of the below implementations
	- Python
		- List
		- NumPy Array
		- PyTorch Tensor

- Use Python libraries for analysis and/or simulation
	- Control number of simulations
	- Save probability distributions of output
	- Could implement thresholding on similarity of inputs, execution time, distribution spread, etc

- Update priors given simulation outputs

# Discussion

- What was learned
- Comparisons among prior -> posterior updating methods
- Other techniques that could have been used

# Conclusion

### References
- Turing Machine implementation: https://python-course.eu/applications-python/turing-machine.php

- Python Library for Approximate Bayesian Inference: https://github.com/dflemin3/approxposterior

- Paper - Features of Similarity by Amos Tversky: http://www.ai.mit.edu/projects/dm/Tversky-features.pdf

- Alternate Python Library: https://github.com/Pat-Laub/approxbayescomp
	- Has built in data generating process simulation

- Book - Artificial Intelligence by Russell and Norvig 
	- Chapters: 13, 14, 15, 16

- Book - Probabilistic Graphical Models by Koller and Friedman
	- Chapters: 7, 12, 13, 14, 17, 18, 19