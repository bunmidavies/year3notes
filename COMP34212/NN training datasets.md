[[COMP34212]]

- all data is typically divided into 3 sets for neural networks

- ==training dataset==: data used repeatedly during the training
- an ==epoch== consists of using all stimuli (data) once. If you have 100 samples in your training set, your epoch consists of all 100 samples

- ==validation dataset==: data used to monitor performance during training - a separate set used at the end of each epoch
- can be thought of as a mini test set - just something to intermediately test the model with something other than training data

- ==test dataset (generalisation dataset)==: unique data to assess model performance
- this will determine how well your model has generalised based on the resulting accuracy