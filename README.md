# Rule30-Pseudo-Random-Number-Generator
A (pseudo)random number generator that uses the central column values of Wolfram's Rule30. <br />

Given the string central_column, which stores the values of Wolfram's Rule30's central column values for around $90,000$ generations, we generate a pseudorandom number in the following manner: <br />

1. Generate a seed using the computer's internal clock in nanoseconds, say $s$. <br />
2. Skip $s$ generations, and read the first $b$ bits from generation $s+1$ onwards ($b$ is determined by the desired upperbound on the desired random number $n$). <br />
3. Interpret such a string as a binary number and return it ($=n$). <br />

Interesetingly enough, the outputs seem to be heavily biased towards low numbers (close to the lower bound) even when using Julia's $rand(1:length(central_column))$ function as a seed generator. We believe this might lead to interesting inisghts into Rule30's structure. 
