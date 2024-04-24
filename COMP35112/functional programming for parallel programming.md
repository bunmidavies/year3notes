[[COMP35112]]

- due to functional programming languages being able to exhibit the [[church-rosser property]], as well as functions exhibiting [[referential transparency]], the composition of operations is all that matters, and ordering of operations doesn't have to be accounted for (which is of importance in imperative programming)
- this means that singular operations can be evaluated in any order, as well as in parallel, and the general analysis of programs becomes easier

- operations are effectively independent, though it can still be difficult to tell whether they are fully independent at runtime - [[dataflow architectures]] can help to alleviate these issues