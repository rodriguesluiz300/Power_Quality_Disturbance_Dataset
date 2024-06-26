This repository has a folder for .mat files and another for .csv files. Both contain the same data. Inside each folder, there is a folder called Signal_Feature and another called Dataset_Train.

Signal_Feature

    Contains the "signal_class" files, which are the synthetic signals used to train the model, and the "Dataset_feature_class" files, which are the extracted features.

    The PQDs were generated following the recommendations of IEEE 1159-2019. The dataset used to train the model contains 100 signals with SNRs of 40, 50 and 60 dB, 34, 33 and 33 signals for each SNR value, respectively. A fundamental frequency of 60 Hz, a sampling frequency of 15,360 Hz, corresponding to 256 samples per cycle, and 10 cycles were considered. The start of each PQD was randomly varied within the first two cycles.

    The feature matrix of the "Dataset_feature_class" files contains the features according to Table 1 of the paper for each sample of the signal: indices 1 to 22 are the estimated features and index 23 is the number of the sample that starts the disturbance.

    The estimated features are composed of a three-dimensional matrix: Dataset_feature_class (23 x 2560 x 100). Where 23 means the number of features (row), 2560 means the number of samples (column), and 100 means the number of signals (depth).

Dataset_Train

    The data in this folder includes only the samples of the signals after the start of the disturbance, to ensure that the observation sets can be characterized by their respective behaviours where the disturbance occurs. To do this, 256 samples were selected after the start of the disturbance and considered 4 cycles (1024 samples) ahead. After this, the Fisher selection step generates a new data set ready to be used to train the model. The new dataset can be found in the "Dataset_train_class" files and the indices used to select the 14 most discriminating features in the "index_total" file.

Note: "class" has been used in the file names here in this README and this represents the generic name for each disturbance. In addition, "capc" means the class of the Transient Oscillatory disturbance.

