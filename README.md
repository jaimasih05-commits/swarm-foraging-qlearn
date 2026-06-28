![preview](https://raw.githubusercontent.com/jaimasih05-commits/swarm-foraging-qlearn/main/preview.svg)

# 🧠 Synaptic Harmony: Multi-Agent Cognitive Foraging with Adaptive Q-Learning

Embark on a journey into emergent intelligence, where autonomous agents learn to collaborate, compete, and coexist in a living, breathing digital ecosystem. **Synaptic Harmony** reimagines the classic foraging problem as a symphony of decentralized decision-making, where each agent—a note in the collective score—discovers optimal strategies through trial, error, and memory. This repository explores how simple reinforcement learning rules can give rise to complex, adaptive group behaviors in environments that shift like seasons and present obstacles like uncharted reefs.

Unlike traditional multi-agent systems that rely on centralized control or static policies, Synaptic Harmony implements a **distributed Q-learning architecture** where each forager maintains its own state-action value table. Agents learn to navigate renewable resource patches, evade static and dynamic obstacles, and even negotiate resource competition through implicit signaling. The environment is not a sterile grid—it breathes, resource nodes regenerate, obstacles reconfigure, and the collective energy of the swarm ebbs and flows.

This project is a sandbox for understanding emergent cooperation, the economics of shared resources, and the resilience of decentralized intelligence. Whether you are a researcher prototyping multi-agent coordination, a developer exploring reinforcement learning in Python, or a hobbyist curious about artificial life, Synaptic Harmony offers a configurable, extensible, and visually animated foundation to build upon.

---

## [![Download](https://raw.githubusercontent.com/jaimasih05-commits/swarm-foraging-qlearn/main/button.svg)](https://jaimasih05-commits.github.io/swarm-foraging-qlearn/)

---

## 🌟 Key Features

- **🧬 Multi-Agent Q-Learning from Scratch**  
  No external RL libraries; agents learn using pure NumPy-based Q-tables, epsilon-greedy exploration, and decaying learning rates. Each agent's brain is a lightweight, state-discretized lookup table.

- **🌿 Dynamic Renewable Resource System**  
  Food sources regrow over time based on configurable regeneration rates. Agents must learn not to deplete a patch entirely—strategic harvesting emerges naturally from the reward structure.

- **🗺️ Adaptive Obstacle Navigation**  
  Walls, pits, and moving barriers appear and disappear across episodes. Agents generalize avoidance behaviors without explicit mapping, embodying a primitive form of spatial memory.

- **📊 Real-Time Performance Dashboard**  
  Animated grid renderer displays agent positions, resource levels, and collision events. A separate metrics panel tracks cumulative reward, exploration rate decay, and inter-agent proximity over time.

- **🧩 Modular Reward Engineering**  
  Tune rewards for consumption, collision, goal achievement, and even altruistic behaviors (e.g., sharing resource location via proximity signaling). Experiment with competitive vs. cooperative reward shaping.

- **🌐 Configuration-Driven Simulation**  
  All parameters—grid size, number of agents, resource spawn rate, obstacle density, Q-learning hyperparameters—are controlled via a human-readable YAML config file. No code changes needed for rapid experimentation.

- **🔬 Reproducible Experiment Logging**  
  Every simulation run outputs a timestamped log of Q-table snapshots, reward curves, and environmental state sequences. Load and replay past experiments for analysis.

- **📈 Multilingual Agent Observation Encoding**  
  Agents perceive their surroundings using a symbolic observation language (e.g., "wall ahead," "food left," "agent behind") that can be mapped to any natural language interface for human-in-the-loop experiments.

- **🛡️ 24/7 Continuous Learning Mode**  
  Run headless simulations for thousands of episodes without interruption. The system automatically saves checkpoints every 100 episodes and resumes from the latest state on restart.

---

## 🚀 Getting Started

Synaptic Harmony runs wherever Python 3.9+ and NumPy are available. The simulation engine is purely computational—no GPU required, no cloud dependency. A typical foraging episode takes under 200 milliseconds on a modern laptop.

### Prerequisites

- Python 3.9 or newer
- NumPy (>=1.21)
- Matplotlib (for live rendering, optional)
- PyYAML (for configuration parsing)

### Launch Your First Swarm

1. **Clone or download** this repository (using your preferred method—no specific tool required).
2. **Edit the configuration** file `config/default.yaml` to set your grid size (e.g., 20x20), number of foragers (try 8), resource density (0.3), and obstacle probability (0.15).
3. **Run the main entry point**:
   ```
   python run_simulation.py
   ```
4. Watch the agents explore, learn, and converge toward optimal foraging paths. Use the slider in the GUI to adjust simulation speed in real time.

---

## 📘 How It Works: A Gentle Explanation

Imagine a colony of tiny robots dropped into an unknown terrain with scattered fruit patches. At first, they wander randomly, bump into walls, and occasionally stumble upon food. Slowly, each robot builds a mental map: "If I move left when there is a wall ahead, I get stuck. If I move toward the green glow, I find berries." This is Q-learning in action.

**Synaptic Harmony** abstracts this process into a discrete grid where each cell can be empty, contain food, hold an obstacle, or house another agent. Every agent observes a local window of 5x5 cells (configurable). Its brain converts that window into a state ID, looks up its Q-table for the best action (up, down, left, right, stay), and executes it. The environment returns a reward: +10 for consuming food, -1 for hitting a wall, -0.1 for each timestep to encourage efficiency, and +5 for being near another agent when a food source is discovered (cooperative bonus).

Over hundreds of episodes, agents transition from chaotic exploration to purposeful navigation. They learn to avoid areas that are consistently barren, to cluster around regenerating resource patches, and to spread out when competition is high. The emergent pattern is not programmed—it is discovered.

---

## 🧪 Experiments & Use Cases

| Experiment | Description | What to Observe |
|------------|-------------|-----------------|
| **Baseline Foraging** | Static resources, no obstacles | Learning curve convergence, average steps to food |
| **Resource Scarcity** | Reduce regeneration rate to 0.1 | Agents develop territorial behaviors; some starve |
| **Moving Obstacles** | Barriers shift every 50 episodes | Adaptability of Q-tables; memory retention |
| **Cooperative Bonus Tuning** | Increase altruism reward from +2 to +15 | Emergence of leader-follower dynamics |
| **Scalability Stress Test** | 50 agents on a 100x100 grid | Computational bottlenecks, collision avoidance emergence |

Each experiment can be automated via the `experiments/` directory, which contains YAML presets and a runner script that aggregates results into a single CSV.

---

## 🧩 Repository Structure

```
synaptic-harmony/
├── agents/              # Agent class definitions, Q-learning logic
├── environment/         # Grid world, resource dynamics, obstacle manager
├── config/              # Default and experiment-specific YAML files
├── experiments/         # Automated experiment runner and result aggregator
├── visualization/       # Matplotlib-based renderer and metric dashboard
├── utils/               # Logging, checkpointing, state encoding helpers
├── run_simulation.py    # Main entry point
├── LICENSE              # MIT License
└── README.md            # This file
```

---

## 🤝 Contributing

Synaptic Harmony thrives on community intelligence. Whether you discover a novel emergent behavior, optimize the Q-learning speed, or add a new environmental hazard (fire, flooding, predators), your contribution is welcome.

Please review our contributing guidelines (in `CONTRIBUTING.md`) before submitting pull requests. We follow a lightweight fork-and-pull model. All discussions happen in GitHub Issues—no external forums.

---

## 🧾 License

This project is released under the MIT License. You are free to use, modify, distribute, and learn from it—even for commercial purposes—provided the original copyright notice is included.

See the [LICENSE](LICENSE) file for full terms.

---

## ❗ Disclaimer

Synaptic Harmony is a research and educational simulation. It is **not** intended for real-world autonomous navigation, robotics control, or safety-critical decision-making. The emergent behaviors observed in simulation may not transfer to physical environments without significant adaptation. The authors assume no liability for any outcomes resulting from the use of this software in live systems.

All experiments and metrics reported are from simulated environments with idealized physics. Real-world deployment requires robust sensor calibration, fail-safe mechanisms, and regulatory compliance.

---

## 📅 Year of Release

This project was conceived and released in 2026, building on decades of reinforcement learning research and multi-agent systems theory. It represents a snapshot of ongoing exploration into decentralized intelligence.

---

## 💬 Final Thoughts

In a world increasingly shaped by autonomous systems, understanding how individual learning rules aggregate into collective wisdom is not just academic—it is essential. Synaptic Harmony offers a window into that process, a toolkit for curiosity, and a foundation for tomorrow's cooperative AI.

Thank you for exploring these ideas. May your foragers always find the ripest fruit.

---

## [![Download](https://raw.githubusercontent.com/jaimasih05-commits/swarm-foraging-qlearn/main/button.svg)](https://jaimasih05-commits.github.io/swarm-foraging-qlearn/)