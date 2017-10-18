

Reconstruct the wiring between neurons from fluorescence imaging of neural activity




1) Loads the fluorescence file as a matrix F, neurons in columns; each line is a time sample.
2) Performs various steps to compute scores for neuron i -> neuron j [correlation only for "challengeFastBaseline" and a choice of methods for "challengeMain", including the GTE algorithm, from Stetter, O., Battaglia, D., Soriano, J. & Geisel, T. Model-free reconstruction of excitatory neuronal connectivity from calcium imaging signals. PLoS Comput Biol 8, e1002653 (2012). 
The resulting "scores" matrix is a matrix N x N, N being the number of neurons, each entry (i, j) indicating the "confidence" that neuron i -> neuron j.
3) Writes the scores in Kaggle submission format as a 2-column csv file
NET_neuronI_neuronJ Strength indicating the "confidence" that neuron i -> neuron j.
4) Computes AUC performance [if the network architecture is provided, i.e. for training networks only].


CODE TO TRAIN A PREDICTIVE MODEL
================================
To combine several scores used as "features" we provide sample code training a simple linear model: 
 
> challengeTrain;
