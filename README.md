# traffic-anomaly-detection
📄
This project takes inspiration from the paper "Profiling the End Host: Thomas Karagiannis, Konstantina Papagiannaki,
Nina Taft, and Michalis Faloutsos" to implement an anomaly detection tool based on SVMs and Graph kernels.

🎯
The final goal is to create a classification with two labels: "NORMAL" and "ANOMALOUS" given the single transactions found in the /Dataset folder.

➡️
The approach presented here uses the following steps:
- Create graph representations (profile) for all users in the transaction list
- Simplify these representation to include only most relevant (and stable) features, these profiles will be the baseline for behaviour of each user therefore they don't
include anomalous behaviour
- For each transaction in the dataset take the union of the transaction graph and the user profile (user starting the transaction)
- Compute the Gram matrix using a Random Walk Kernel between all graphs created in the previous step (1 for each transaction)
- Train an SVM model using the RWK to detect anomalous behaviour

ℹ️
For more informations regarding the dataset or the problem the pdf file contains in detail specs.
