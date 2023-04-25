# HockeyGym: Massive Parallel Training on the Air Hockey Game with Hierarchical RL

Mike Liu xl142

## Install and Run

1. Install IsaacGym Release 4 (https://developer.nvidia.com/isaac-gym). Docker install is recommended. The docker files I use for cloud server training  is (https://github.com/LXYYY/rlgpu_docker). Or please use the script from IsaacGym to generate a conda environment. Manually install the IsaacGym is not recommended.

2. Follow the installation instructions in https://github.com/LXYYY/legged_gym. If you successfully install the docker or the generated conda environment by IsaacGym, you will only need to:
   ```
   cd air_hockey_challenge && pip install -e .
   cd rsl_rl && pip install -e .
   cd legged_gym && pip install -e .
   pip install mushroom-rl mujoco
   ```

3. Train the model:
   ```
   python legged_gym/legged_gym/scripts/train.py --task=air_hockey_planar
   ```
   add `--headless` to run without visualization. And remember to set the number of robots here https://github.com/LXYYY/legged_gym/blob/0eaa2e1ee13aa46965cec82990b7670ed9f95c25/legged_gym/envs/air_hockey/air_hockey_config.py#L11. For a laptop 3070, recommend 300 with rendering, 1000 without. 

4. Play:
    ```
   python legged_gym/legged_gym/scripts/play.py --task=air_hockey_planar
   ```