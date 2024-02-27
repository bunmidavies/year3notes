[[COMP34312]]

- bootstrapping allows one to generate a new dataset, through sampling $N$ items with replacement from the original $M$ items in a dataset
- also known as ==bootstrap aggregating==

"Bagging" algorithm (Breiman, 1996):


- some models are almost completely unaffected by bootstrapping - they become very similar to each other on test data
- these are known as ==low variance models== - i.e. models which aren't as sensitive depending on the data you provide it, which aren't as suitable for [[parallel ensemble construction]]