# 🧠 Decision Transformer

Fork of [Kostrikov et al.](https://github.com/kzl/decision-transformer) for **CSE 8803 DRL Gatech Project**.  

## ⚙️ Environment Setup

```bash
# 1. Create and activate environment
conda env create -f conda_env.yml
conda activate decision-transformer-gym

# 2. Install MuJoCo 2.1 (no license required)
mkdir -p ~/.mujoco && cd ~/.mujoco
wget https://mujoco.org/download/mujoco210-linux-x86_64.tar.gz
tar -xf mujoco210-linux-x86_64.tar.gz
echo 'export MUJOCO_PY_MUJOCO_PATH=$HOME/.mujoco/mujoco210' >> ~/.bashrc
echo 'export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$HOME/.mujoco/mujoco210/bin' >> ~/.bashrc
echo 'export MUJOCO_GL=egl' >> ~/.bashrc
source ~/.bashrc

# 3. Verify setup
python -c "import torch; print('Torch', torch.__version__, 'CUDA?', torch.cuda.is_available())"
python -c "import mujoco_py, gym; print('Gym', gym.__version__, 'MuJoCo', mujoco_py.__version__)"

## Downloading datasets Datasets are stored in the data directory. Install the [D4RL repo](https://github.com/rail-berkeley/d4rl), following the instructions there. Then, run the following script in order to download the datasets and save them in our format:
python download_d4rl_datasets.py
## Example usage Experiments can be reproduced with the following:
python experiment.py --env hopper --dataset medium --model_type dt
Adding -w True will log results to Weights and Biases.
