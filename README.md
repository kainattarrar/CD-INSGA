CD-INSGA: Dynamic Community Detection Problem Solver
CD-INSGA (Community Detection using an Improved NSGA) is a genetic algorithm designed to tackle the community detection problem in dynamic networks. Implemented in Python, this algorithm takes a list of Networkx Graph class instances as input and produces a list of final community partitions as output.

Inspired by the transfer learning mechanism of TMOGA, CD-INSGA employs a feature transfer mechanism to enhance its results. By retaining useful information from previous network snapshots, it aids in optimizing the community structures of the current network. This unique mechanism significantly improves algorithm stability and accuracy. Although feature transfer adds some runtime, its impact on overall performance is negligible compared to the genetic algorithm portion.

For further details on the algorithm and its applications, please refer to the following paper:

Tarrar, K. A., & Atay, Y. (2023). International Antalya Scientific Research and Innovative Studies Congress-V, p 545-556.

Installation
You can install CD-INSGA from pip using the following command:

pip install tmoga

Requirements
Python >= 3.7
networkx >= 2.5
argparse >= 1.1
python-louvain >= 0.15
joblib >= 0.17.0
tqdm >= 4.50.2
numpy >= 1.19.2
matplotlib >= 3.3.2
sklearn >= 0.23.2
pandas >= 1.1.3
Datasets
This project includes several classic datasets for dynamic community detection problems. The sources are as follows:

Dataset	Source
SYN-FIX (Z = 3)	Kim, M. S., & Han, J. (2009). Proceedings of the VLDB Endowment, 2(1), 622-633.
SYN-FIX (Z = 6)	Kim, M. S., & Han, J. (2009). Proceedings of the VLDB Endowment, 2(1), 622-633.
SYN-VAR (Z = 3)	Kim, M. S., & Han, J. (2009). Proceedings of the VLDB Endowment, 2(1), 622-633.
SYN-VAR (Z = 6)	Kim, M. S., & Han, J. (2009). Proceedings of the VLDB Endowment, 2(1), 622-633.
SYN-EVENT (Various types)	Greene, D., Doyle, D., & Cunningham, P. (2010, August). IEEE.
Mobile Phone Communication Network	http://visualdata.wustl.edu/varepository
The generating tool for SYN-EVENT datasets can be found at http://mlg.ucd.ie/dynamic/. Parameters for each dataset can be found at ./dataset/SYNEVENT/*/generation_parameters.txt.

Usage
Command Line
To run CD-INSGA from the command line, navigate to the root directory and execute the following command:

css
Copy code
python3 ./main.py output -d dataset -g generation -p population  --CID cid  --Md md --Tp tp --Cp cp --Mp mp
Parameters:

output: Directory to save community files (required).
-d: Dataset to use (synfix3, synfix6, etc.). Default is synfix3.
-g: Number of generations. Default is 100.
-p: Population size. Default is 200.
--CID: CID threshold (default 0.8).
--Md: Max depth of search tree (default 5).
--Tp: Transfer probability (default 0.5).
--Cp: Crossover probability (default 0.8).
--Mp: Mutation probability (default 0.2).
Example:

css
Copy code
python3 ./main.py ./ -d synfix6 -g 20 -p 20  --CID 0.5  --Md 5 --Tp 0.5 --Cp 0.5 --Mp 0.2
Python Library
After installation, import the TMOGA algorithm and evaluation functions in Python shell:

python
Copy code
from tmoga import TMOGA, evaluation
The TMOGA class is the main component of CD-INSGA, with various parameters to customize its behavior.

For detailed usage instructions, please refer to the documentation.

Disclaimer
If you encounter any bugs or issues, please contact me at kaina.tarar@gmail.com. Your feedback is valuable.