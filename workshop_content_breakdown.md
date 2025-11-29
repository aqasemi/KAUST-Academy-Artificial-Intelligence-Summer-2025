# Workshop Content Breakdown (Storyboard)

This file details the content for each slide in the Beamer presentation. Target: ~50 slides.

---

## Section 1: Introduction (Slides 1-7)

**Slide 1: Title Slide**
- Title: Introduction to Reinforcement Learning
- Subtitle: From Fundamentals to Flappy Bird
- Authors: [Your Names]
- Date: CPCS-331 Workshop
- Theme: Red/Clean

**Slide 2: The Hook**
- Title: What if machines could learn like us?
- Content:
    - Image/Placeholder: A baby taking first steps vs A robot falling.
    - Text: "No manual, no map, just trial and error."

**Slide 3: What is Reinforcement Learning?**
- Title: Defining RL
- Content:
    - RL is a computational approach to learning from interaction.
    - Goal: Maximize a numerical reward signal.
    - Unlike other AI, the agent is *not* told which action to take.

**Slide 4: The Agent-Environment Loop (Visual)**
- Title: The Core Loop
- Content:
    - Diagram (TikZ): Agent <-> Environment.
    - Arrows: Action ($A_t$), State ($S_t$), Reward ($R_t$), Next State ($S_{t+1}$).

**Slide 5: Key Terminology**
- Title: The Language of RL
- Bullets:
    - **Agent:** The learner/decision maker.
    - **Environment:** Everything outside the agent.
    - **Action ($A$):** What the agent does.
    - **State ($S$):** The current situation.
    - **Reward ($R$):** Immediate feedback (Scalar).

**Slide 6: The Reward Hypothesis**
- Title: The Reward Hypothesis
- Content:
    - "All goals can be described by the maximization of expected cumulative reward."
    - Example:
        - Win Chess game = +1
        - Lose = -1
        - Moves in between = 0

**Slide 7: Question Time!**
- Title: Question?
- Content:
    - "Consider a Dog Training scenario."
    - Q: What is the Agent? (Dog)
    - Q: What is the Reward? (Treat / "Good Boy")
    - Q: What is the Action? (Sit / Bark)

---

## Section 2: Context - RL vs The World (Slides 8-13)

**Slide 8: Where does RL fit?**
- Title: The AI Landscape
- Content:
    - Venn Diagram or List:
    - Supervised Learning (Labels provided).
    - Unsupervised Learning (Finding structure).
    - Reinforcement Learning (Reward maximization).

**Slide 9: RL vs Supervised Learning**
- Title: RL vs Supervised Learning
- Split Screen:
    - **Supervised:** Teacher says "This is a cat". Error is immediate.
    - **RL:** Agent acts. Environment says "+10" later. No "Correct Answer" given.

**Slide 10: RL vs Search Algorithms (Our Course)**
- Title: RL vs Search (A*, BFS)
- Content:
    - We studied Search (A*, DFS).
    - **Search:** Requires a model (Rules of the game, Map) to plan *offline*.
    - **RL:** Can work *without* a model. Learns *online* by trying.

**Slide 11: Comparison Table**
- Title: Comparison
- Table:
    - Feature | Search (A*) | RL
    - Planning? | Offline | Online (mostly)
    - Model? | Required | Not Required
    - Data source? | Given Rules | Interaction

**Slide 12: Bonus Section: Planning in RL**
- Title: BONUS: Can RL Plan?
- Content:
    - Yes! Model-Based RL.
    - AlphaZero uses Monte Carlo Tree Search (MCTS) + RL.

**Slide 13: Question Time!**
- Title: Question?
- Content:
    - "Is A* an RL algorithm?"
    - Answer: No. It solves a known pathfinding problem using a heuristic. It doesn't "learn" a policy from scratch via rewards.

---

## Section 3: Fundamentals (Sutton & Barto) (Slides 14-25)

**Slide 14: Starting Simple - The Bandit**
- Title: The k-Armed Bandit Problem
- Content:
    - You are in a casino.
    - $k$ slot machines (bandits).
    - Each pays out differently (unknown probability).
    - Goal: Maximize money.

**Slide 15: Exploration vs Exploitation**
- Title: The Core Dilemma
- Content:
    - **Exploit:** Pull the arm you *think* is best (Maximize current reward).
    - **Explore:** Pull a random arm to learn more (Maybe it's better?).
    - You cannot do both simultaneously!

**Slide 16: Epsilon-Greedy**
- Title: A Simple Solution: $\epsilon$-Greedy
- Content:
    - Flip a coin (with probability $\epsilon$).
    - If Heads: Explore (Random Action).
    - If Tails: Exploit (Best known Action).

**Slide 17: Moving to MDPs**
- Title: From Bandits to Context
- Content:
    - Bandits have 1 state (The casino).
    - Life has *sequences* of states.
    - Enter: Markov Decision Processes (MDPs).

**Slide 18: The Markov Property**
- Title: The Markov Property
- Content:
    - "The future depends only on the present, not the past."
    - $P(S_{t+1} | S_t, A_t)$ covers everything we need.
    - Example: Board position in Chess (History of moves doesn't change the physics of the current board).

**Slide 19: Components of an MDP**
- Title: MDP Defined
- List:
    - Set of States $\mathcal{S}$
    - Set of Actions $\mathcal{A}$
    - Transition Probability $\mathcal{P}$ (Physics)
    - Reward Function $\mathcal{R}$
    - Discount Factor $\gamma$ (gamma)

**Slide 20: The Discount Factor**
- Title: Why Discount ($\gamma$)?
- Content:
    - $\gamma \in [0, 1]$.
    - A reward now is worth more than a reward later.
    - If $\gamma = 0$: Myopic (Only cares about now).
    - If $\gamma \to 1$: Far-sighted.
    - Math guarantees convergence (keeps sum finite).

**Slide 21: Policies and Value Functions**
- Title: The Goal of RL
- Content:
    - Find an optimal **Policy** ($\pi$).
    - $\pi(s)$: Mapping from state to action. "If I see X, I do Y".

**Slide 22: Value Function Intuition**
- Title: Value Functions $V(s)$
- Content:
    - "How good is it to be in this state?"
    - Example: In Tic-Tac-Toe, having two Xs in a row is a *high value* state.
    - Being about to lose is a *low value* state.

**Slide 23: Q-Value Intuition**
- Title: Action-Value Functions $Q(s, a)$
- Content:
    - "How good is it to take action $A$ in state $S$?"
    - This is what we usually learn.
    - If we know $Q^*(s, a)$ for all actions, we just pick the max!

**Slide 24: Tabular Learning**
- Title: Tabular Q-Learning
- Content:
    - Imagine a giant Excel sheet.
    - Rows = States. Columns = Actions.
    - Cells = Q-values.
    - We update the cells as we explore.

**Slide 25: Question Time!**
- Title: Question?
- Content:
    - "Why can't we use a table for a self-driving car?"
    - Answer: Too many states! (Continuous position, camera pixels...)

---

## Section 4: Deep RL (Slides 26-33)

**Slide 26: The Curse of Dimensionality**
- Title: The Problem with Tables
- Content:
    - Tic-Tac-Toe: ~5000 states. (Table is fine).
    - Chess: $10^{47}$ states. (Table is impossible).
    - Images: $256^{100x100}$ states. (Universe breaks).

**Slide 27: Function Approximation**
- Title: Solution: Approximation
- Content:
    - Don't memorize every state.
    - *Generalize* from seen states to unseen ones.
    - Use a function $f(s) \approx Q(s, a)$.

**Slide 28: Enter Neural Networks**
- Title: Deep Q-Networks (DQN)
- Content:
    - Use a Neural Network as the function approximator.
    - Input: State (e.g., Image).
    - Output: Q-values for each action.
    - Weights $\theta$ replace the table entries.

**Slide 29: You know CNNs!**
- Title: Connecting to CNNs
- Content:
    - For Atari games, the state is raw pixels.
    - We use Convolutional Neural Networks (CNNs) to extract features.
    - Features -> Dense Layers -> Q-Values.

**Slide 30: Deep RL Challenges**
- Title: It's Unstable!
- Content:
    - RL with NNs is notoriously unstable.
    - "Moving Target" problem.
    - Data is correlated (sequential frames).

**Slide 31: BONUS: Experience Replay**
- Title: BONUS: Experience Replay
- Content:
    - Trick: Save experiences $(S, A, R, S')$ in a memory buffer.
    - Train the network on *random batches* from memory.
    - Breaks correlation, stabilizes training.

**Slide 32: Policy Gradients (Brief)**
- Title: Alternative: Policy Gradients
- Content:
    - Instead of learning Q-values, learn the Policy $\pi$ directly.
    - Increase probability of actions that yield high reward.
    - Algorithms: REINFORCE, PPO (Proximal Policy Optimization).

**Slide 33: Summary of Methods**
- Title: Family Tree
- Content:
    - Value-Based (DQN).
    - Policy-Based (PPO, REINFORCE).
    - Model-Based (AlphaZero).

---

## Section 5: Tools & History (Slides 34-39)

**Slide 34: A Brief History**
- Title: History: Atari 2600
- Content:
    - 2013: DeepMind presents DQN.
    - First agent to play generic Atari games at human level directly from pixels.
    - Before this: RL needed hand-crafted features.

**Slide 35: The Environment Standard**
- Title: OpenAI Gym / Gymnasium
- Content:
    - To compare algorithms, we need standard environments.
    - `gym` (now `gymnasium`) provides this interface.

**Slide 36: The Gym API**
- Title: The Code Interface
- Code Block:
    ```python
    env = gym.make("CartPole-v1")
    observation, info = env.reset()
    action = env.action_space.sample()
    new_obs, reward, terminated, truncated, info = env.step(action)
    ```

**Slide 37: Standard Environments**
- Title: Common Benchmarks
- Content:
    - Classic Control (CartPole, Pendulum).
    - Atari (Breakout, Pong).
    - MuJoCo (Physics simulation for robots).

**Slide 38: Action Spaces**
- Title: Discrete vs Continuous
- Content:
    - **Discrete:** [Left, Right, Jump]. (Mario, Atari).
    - **Continuous:** [Steering Angle 23.4, Gas 0.8]. (Robotics, Driving).

**Slide 39: Question Time!**
- Title: Question?
- Content:
    - "In Flappy Bird, is the action space Discrete or Continuous?"
    - Answer: Discrete (Flap or Don't Flap).

---

## Section 6: Hands-on Flappy Bird (Slides 40-45)

**Slide 40: Let's Build an Agent!**
- Title: Project: Flappy Bird RL
- Content:
    - Objective: Teach an AI to play Flappy Bird.
    - We will use `flappy-bird-gymnasium`.

**Slide 41: State Representation**
- Title: What does the Agent See?
- Content:
    - We *could* use raw pixels (CNN).
    - For simplicity/speed: Use coordinates.
    - State: `[Horizontal Dist to Pipe, Vertical Dist to Top Pipe, Vertical Velocity]`.

**Slide 42: Reward Function**
- Title: Designing the Reward
- Content:
    - "Shape" the behavior.
    - +0.1 for every frame alive.
    - +1.0 for passing a pipe.
    - -100.0 for dying.

**Slide 43: The Algorithm**
- Title: Choosing the Algorithm
- Content:
    - We use PPO (Stable Baselines3).
    - It's robust and works well out of the box.

**Slide 44: Code Snippet**
- Title: Training Code
- Code Block (Python):
    ```python
    model = PPO("MlpPolicy", env, verbose=1)
    model.learn(total_timesteps=100000)
    model.save("flappy_bird_expert")
    ```

**Slide 45: DEMO TIME**
- Title: LIVE DEMO
- Content:
    - (Switching to Code)
    - 1. Watch untrained agent (Random flailing).
    - 2. Watch trained agent (Superhuman).

---

## Section 7: Applications & Conclusion (Slides 46-52)

**Slide 46: Real World Applications**
- Title: RL is Everywhere
- Content:
    - It's not just games anymore.

**Slide 47: Robotics**
- Title: Robotics
- Content:
    - Sim-to-Real transfer.
    - Training robots to walk, grasp objects, parkour (Boston Dynamics research).

**Slide 48: LLMs and RLHF**
- Title: RL in ChatGPT
- Content:
    - RL from Human Feedback (RLHF).
    - Step 1: Train on text (Predict next word).
    - Step 2: Use RL to align with human preference (Helpful, Honest, Harmless).
    - The "Reward Model" learns what humans like.

**Slide 49: Other Cool Apps**
- Title: Cooling Data Centers
- Content:
    - Google used DeepMind RL to reduce cooling energy by 40%.
    - Controls fans/windows based on sensors.

**Slide 50: Recap**
- Title: Summary
- Content:
    - RL = Learning by Interaction.
    - Agent, Env, State, Action, Reward.
    - Fundamentals: Bandits, MDPs, Q-Learning.
    - Deep RL: Using NNs to scale.

**Slide 51: References & Resources**
- Title: Want to learn more?
- Content:
    - **Book:** Sutton & Barto (The Bible of RL).
    - **Course:** Hugging Face Deep RL Course (Free).
    - **Library:** Stable Baselines3 (Python).

**Slide 52: Q&A**
- Title: Thank You!
- Content:
    - Questions?
    - Bonus: Who wants to see the code?
