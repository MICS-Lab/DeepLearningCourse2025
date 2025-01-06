# Deep Learning Course
Ressources for Deep Learning Course (VSE).

## GitHub Repository:

## Grade breakdown:

## Drive folder with datasets:
https://drive.google.com/drive/folders/14QmpxUPmpeRtUxnDiCIaNLlsx9KIv8AK?usp=sharing

## Linux operations to install Python on the server at your disposal for GPUs
```
#!/bin/bash

#SBATCH --job-name=condaEnvSetup
#SBATCH --nodes=1
#SBATCH --partition=gpu_prod_long
#SBATCH --time=1:00:00

# Ensure module is visible
source /etc/profile

# Load the conda module
module load anaconda3/2022.10/gcc-13.1.0

conda remove -n DLNLP2025 --all

# Create conda environment
# and prevent the use of system site-package
# that will interfer with the conda env
export PYTHONNOUSERSITE=1

# Create the environment using python 3.13
conda create --name DLNLP2025 python=3.13 --force

# Activate the environment
source activate DLNLP2025

pip install torch torchvision torchaudio matplotlib numpy pandas seaborn scipy scikit-learn
```