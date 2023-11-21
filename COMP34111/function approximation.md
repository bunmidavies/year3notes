[[COMP34111]]

- typically, q-learning/v-learning requires visiting a large number of states/state-action pairs requires everything to be visited a bunch of times in order to gain a good estimate - in a lot of cases, the actual time required to learn these functions just isn't feasible
- function approximation is the attempt at using ==supervised learning== to approximate a Q/V function
- our desired output is the expected reward given a state/action pair or state i.e. our regular Q/V-function - this is a ==regression problem==
- this can be achieved through typical supervised learning methods e.g. MLP regressor, SVM regressor, linear/polynomial regression 