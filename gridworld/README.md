# GridWorld — Value Iteration vs. Q-Learning

A 5×5 GridWorld with a goal, a hazard, and a step cost, solved two ways and compared directly:

- **Value Iteration** — has full access to the reward function and transition dynamics, and computes
  the optimal policy directly via the Bellman optimality backup, with no need to actually act in the
  environment
- **Q-Learning** — model-free, off-policy TD control: learns purely from (state, action, reward,
  next-state) experience via ε-greedy exploration, with no access to the model at all

## Results

Value Iteration converges in 9 sweeps. After 500 episodes of ε-greedy exploration, Q-Learning's
learned policy agrees with the exact optimal policy on 21/23 non-terminal states (91%) — a solid
result given it never saw the reward function or transition model directly.

## Getting started

```bash
pip install -r requirements.txt
jupyter notebook gridworld.ipynb
```

No external data — the environment is defined in the notebook itself.
