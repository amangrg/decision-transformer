
# Fork of Decision Transformer of the course CSE 8803 at Georgia Tech

Lili Chen\*, Kevin Lu\*, Aravind Rajeswaran, Kimin Lee, Aditya Grover, Michael Laskin, Pieter Abbeel, Aravind Srinivas†, and Igor Mordatch†

# 1) Create & activate
conda env create -f conda_env.yml
conda activate decision-transformer-gym

# 2) Install MuJoCo 2.1 runtime (headless-safe)
mkdir -p ~/.mujoco && cd ~/.mujoco
wget https://mujoco.org/download/mujoco210-linux-x86_64.tar.gz
tar -xf mujoco210-linux-x86_64.tar.gz
echo 'export MUJOCO_PY_MUJOCO_PATH=$HOME/.mujoco/mujoco210' >> ~/.bashrc
echo 'export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$HOME/.mujoco/mujoco210/bin' >> ~/.bashrc
echo 'export MUJOCO_GL=egl' >> ~/.bashrc
source ~/.bashrc

# 3) Quick sanity checks
python -c "import torch; print('torch', torch.__version__, 'cuda?', torch.cuda.is_available())"
python -c "import gym; import mujoco_py; print('gym', gym.__version__, 'mujoco-py', mujoco_py.__version__)"
python -c "import transformers, tokenizers; print('hf', transformers.__version__, 'tok', tokenizers.__version__)"

## License

MIT
