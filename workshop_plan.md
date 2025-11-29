# Workshop Agenda: Introduction to Reinforcement Learning
**Duration:** 1 Hour
**Audience:** CPCS-331 Colleagues (Know AI fundamentals, Search Algos, NN/CNNs).
**Goal:** Intuitive understanding of RL, from fundamentals to Deep RL, connecting to known concepts (Search), with a focus on applications and a Flappy Bird demo.

## Agenda Overview

1.  **Introduction & Hook (0:00 - 0:05)**
    *   **Hook:** Video placeholder of Multi-Agent Hide and Seek or AlphaGo moment.
    *   **Definition:** What is RL? Learning by trial and error.
    *   **The Loop:** Agent, Environment, Action, State, Reward.
    *   *Question:* What everyday examples look like RL? (Dog training, Baby walking).

2.  **Context: RL vs The World (0:05 - 0:10)**
    *   **RL vs Search (BFS/A*):**
        *   Search: Model is known (we know the map), Offline planning.
        *   RL: Model unknown (must explore), Online learning.
    *   **RL vs Supervised Learning:**
        *   SL: Supervisor gives answers (labels).
        *   RL: Sparse feedback (rewards), temporal delay (credit assignment).

3.  **Fundamentals (Sutton & Barto Flow) (0:10 - 0:20)**
    *   **The Bandit Problem:**
        *   One state. Multiple arms.
        *   **Exploration vs Exploitation:** The core dilemma.
        *   *Bonus:* Epsilon-Greedy explained simply.
    *   **Markov Decision Processes (MDPs):**
        *   Adding "States" to the Bandit.
        *   Sequential decision making.
        *   The Goal: Maximize cumulative reward (Return).
    *   **Value Functions & Policies:**
        *   Policy: The Strategy (Brain).
        *   Value: How good is it to be here?

4.  **Transition to Deep RL (0:20 - 0:30)**
    *   **The Problem with Tables:**
        *   Tabular Q-learning works for small grids.
        *   Real world (Images, Atoms) has too many states.
    *   **Enter Neural Networks:**
        *   Replace the Table with a Neural Net (DQN).
        *   Input: State (Image/Vector). Output: Q-values for actions.
        *   *Connection:* You know CNNs! We feed game screens into CNNs to output actions.

5.  **Tools & History (0:30 - 0:35)**
    *   **History:** Atari 2600. The benchmark that started Deep RL.
    *   **Gymnasium (formerly OpenAI Gym):**
        *   The standard API (env.step(), env.reset()).
        *   Spaces (Box, Discrete).

6.  **Hands-on Session: Flappy Bird Agent (0:35 - 0:45)**
    *   **The Setup:**
        *   Env: Flappy Bird clone.
        *   State: Distance to next pipe (X, Y).
        *   Action: Flap (1) or Do Nothing (0).
        *   Reward: +0.1 every frame, +1 passing pipe, -100 collision.
    *   **The Agent:** A simple PPO or DQN model.
    *   **Demo Placeholder:** (Switch to live code run).
    *   **Results:** Watch it suck, then watch it become godlike.

7.  **Applications & Conclusion (0:45 - 0:55)**
    *   **Beyond Games:**
        *   Robotics (Boston Dynamics - though they use control theory too, RL is huge in sim-to-real).
        *   LLMs (RLHF): ChatGPT wasn't just trained on text; it was fine-tuned with feedback (RL!).
    *   **What we didn't cover:** The math (Bellman), advanced algorithms.

8.  **Q&A & Quiz (0:55 - 1:00)**
    *   Quick quiz for the audience (Bonus points!).

## Interaction Plan
- **Hooks:** Start of every section (e.g., "Why did the robot fall over?").
- **Questions:**
    - "If you play Chess, is the reward given at every move?" (No, sparse).
    - "Is A* RL?" (No, it has the map).
- **Bonus Slides:** "The Credit Assignment Problem", "AlphaGo's Move 37".
