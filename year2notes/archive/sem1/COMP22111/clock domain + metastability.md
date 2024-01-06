[[COMP22111]]
[[COMP32211]]

**a clock domain** is a specific area of a system which uses one clock signal. Complex systems can be made up of multiple clock domains, as different devices e.g. CPU and RAM may need different clock frequencies

When crossing clock domains, **resynchronisation** is required in order to resolve **metastability** - if metastability is not resolved, signals entering a flip flop from a different clock domain will put the flip flop into an **unknown state**

# metastability
- metastability is typically entered when set-up/hold conditions of a DFF are violated
- over time, the probability of remaining metastable decreases exponentially but it is feasible for a flip-flop to remain metastable indefinitely
- metastability in relation to flip-flops basically means an unstable state between 1 and 0 has been entered
- ==the metastable state can be interpreted as 1 or 0 by different inputs== - this can ultimately be dangerous, causing faulty/unpredictable behaviour