# Stage 8 — Behavioural AI

## Reinforcement Learning: Complete Beginner's Module (V1.1)

From definition and the agent–environment loop, through Markov Decision Processes, the Bellman equation, dynamic programming, value and policy iteration, the model-free algorithms (Q-learning, SARSA, DQN, REINFORCE, actor–critic), on- and off-policy learning, and real-world applications.

> **Very important note:** don't look at the equations first — understand the explanation that is provided after the equation to properly understand it.

- **Module:** Stage 8 — Behavioural AI
- **Scope:** The 18 listed topics, reordered so no term is used before it is taught
- **Audience:** Beginners — no prior reinforcement-learning background
- **Learning path:** Notation box → Learning Outcomes → 18 topics → Glossary → References

## Contents

1. Definition
2. Basic Process & Example
3. Reinforcement Learning
4. Markov Decision Process — States, Actions, Rewards
5. Markov Decision Process — Probabilities, Policy, Value Function
6. Model Based vs Model Free
7. Bellman Equation
8. Dynamic Programming (1) — Policy Evaluation
9. Dynamic Programming (2) — Policy Improvement
10. Value Iteration
11. Policy Iteration
12. On-Policy & Off-Policy: The Core Distinction
13. Reinforcement Learning Algorithms — Overview
14. Value Based — Q-Learning
15. Value Based — Deep Q-Network, SARSA
16. Policy Based — REINFORCE, Policy Gradient
17. Actor–Critic Algorithms
18. Examples of Applications in the Real World
19. Master Glossary
20. References and Status

**Reading order:** Read the "Reading the Notation" box first, then the Module Overview and Learning Outcomes, then Section 1 onward.

---

## Module Overview and Learning Outcomes

### Overview

This module develops a beginner's understanding of Behavioural AI in the reinforcement-learning sense: AI that learns what to do through interaction with an environment and reward feedback. It moves from the definition and the agent–environment loop, through Markov Decision Processes and the Bellman equation, through dynamic programming and the two classical iteration algorithms, into the on-policy / off-policy distinction, and then into the model-free algorithm families (Q-learning, SARSA, DQN, REINFORCE, actor–critic). It closes with real-world applications. By the end, a learner should be able to explain the concepts, trace the algorithms by hand, and critique the reward functions that drive real systems.

### Learning Outcomes

By the end of this module, a learner should be able to:

| # | Outcome | Assessed in |
|---|---------|-------------|
| LO1 | Explain what Behavioural AI is, and distinguish it from supervised and unsupervised learning using the three-family frame. | Section 1; Section 1 Activity; Section 1 Q&A |
| LO2 | Describe the agent–environment loop and identify its five components in a concrete scenario, using correct notation (S<sub>t</sub>, A<sub>t</sub>, R<sub>t+1</sub>, S<sub>t+1</sub>). | Section 2; Section 2 Worked Example; Section 2 Activity |
| LO3 | Write down a small Markov Decision Process — states, actions, rewards, transition probabilities — and explain what the Markov property requires and why an insufficient state definition matters. | Section 4, Section 5; Section 4 Activity; Section 4 Q&A |
| LO4 | State the Bellman equation in both its expectation and optimality forms, and apply it to compute a one-step value update by hand. | Section 7; Section 7 Worked Example; Section 7 Activity |
| LO5 | Distinguish model-based from model-free learning, and trace value iteration and policy iteration on a small grid, extracting the greedy policy from converged values and comparing the two algorithms. | Section 6, Section 8–Section 11; Section 8, Section 10, Section 11 Activities |
| LO6 | Describe the three model-free algorithm families (value-based, policy-based, actor–critic) in terms of what each stores, what it updates, and what learning signal it uses; explain the on-policy / off-policy distinction and predict the behavioural consequence in the cliff-walk scenario. | Section 12–Section 17; Section 15 Activity; Section 12 Q&A |
| LO7 | Design a reward function for a stated application and critique it, identifying at least one unintended behaviour it might produce and one ethical consequence. | Section 18; Section 18 Activities |

### How these outcomes are assessed

Each outcome has at least one **worked example** (a skill demonstrated), one **activity** (a skill performed, with an answer), and one **check-your-understanding question** (a quick confirmation). The mapping above is the traceability check.

---

## Reading the Notation — Read This First

Every symbol is defined here once. You do not need to memorise this box; it is here so you can always flip back.

| Symbol | Meaning |
|--------|---------|
| S<sub>t</sub>, A<sub>t</sub>, R<sub>t+1</sub> | The state, action, and reward at time step t. The subscript *t* means "at this step"; *t+1* means "at the next step". |
| Σ (sigma) | Sum over all values. Σ<sub>a</sub> means "sum over all actions a"; Σ<sub>s′</sub> means "sum over all next states s′". |
| π(a \| s) | The probability of choosing action a when in state s. The vertical bar "\|" means "given". |
| P(s′ \| s, a) | The probability of landing in state s′ after taking action a in state s. |
| E[·] | Expected value — the long-run average if the process were repeated many times. |
| max<sub>a</sub> | The largest value over all choices of a. |
| argmax<sub>a</sub> | The action a that makes the following expression largest (the *action*, not its value). Example: if Q(Left) = 2 and Q(Right) = 5, then argmax<sub>a</sub> Q(a) = Right. |
| ← | "Update to." The left side is replaced by the right side. Example: x ← x + 1 means "increase x by 1". |
| ∇ (nabla) | Gradient — the direction in which a quantity increases fastest. |
| γ (gamma) | Discount factor — how much future rewards count compared to immediate ones. |
| α (alpha) | Learning rate — how far each update moves the estimate. |
| δ (delta) | TD error — the "surprise" (target minus current estimate). |
| θ (theta) | Policy parameters — the adjustable numbers that define the policy. |
| w | Critic parameters — the adjustable numbers that define the value function in actor–critic methods. |

---

## 1. Definition

### 1.1 What Behavioural AI Means Here

Behavioural AI in this module means AI that learns **what to do** by interacting with an environment and receiving reward feedback. It is not given the correct answer for each situation, and it is not asked to find hidden structure in unlabelled data. It is told, *after the fact*, how good the outcome was — and it adjusts its behaviour to get more reward.

The name comes from **behaviourism**, the psychology tradition of Pavlov, Thorndike, and Skinner. The core behaviourist claim is that behaviour is shaped by its consequences: actions followed by reward become more frequent; actions followed by punishment become less frequent. **Reinforcement Learning (RL)** is the computational version of that idea.

> **Three families of machine learning — one line each**
>
> - **Supervised learning** is given labelled examples: "this input should produce this output."
> - **Unsupervised learning** is given unlabelled data and looks for structure.
> - **Reinforcement learning** is given neither labels nor structure — only a reward signal after acting. That is the family this module is about.

### 1.2 Key Terms

| Term | Definition |
|------|------------|
| Agent | The learner or decision-maker (a robot, a program, a game character). |
| Environment | Everything outside the agent that the agent interacts with. |
| State (s) | A description of the current situation, sufficient to decide what to do next. |
| Action (a) | A choice the agent can make. |
| Reward (r) | A number the environment gives after an action; higher is better. |
| Policy (π) | The agent's rule for choosing actions in each state. |
| Value function | A prediction of how much total future reward to expect (formal definition in Section 5.4). |
| Episode | A run of interaction from a start state to a terminal state (e.g., one game). |

> **Q1.1.** A chess program is given millions of positions with the "correct" move. Is that behavioural AI?
>
> **A.** No — that is supervised learning. A behavioural AI chess program would play games and receive only win/loss/draw as feedback, then figure out which moves contributed to the outcome.

> **Activity 1.1 — Identify the components**
>
> A robot vacuum learns to clean a room. It can move forward, turn left, turn right, or stop. It receives +1 when it covers a dirty patch, −5 when it bumps into furniture, and 0 otherwise. Identify the agent, environment, actions, rewards, and one possible state.
>
> **Answer.** Agent = the vacuum's control program. Environment = the room, furniture, dirt. Actions = forward, left, right, stop. Rewards = +1 for dirt covered, −5 for collision, 0 otherwise. One possible state = "current position, heading, and dirt-sensor reading."

---

## 2. Basic Process & Example

### 2.1 The Agent–Environment Loop

Every RL system follows the same five-step cycle. Read the subscripts using the notation box above.

1. **Observe** — the agent receives the current state S<sub>t</sub>.
2. **Act** — it selects an action A<sub>t</sub> according to its current policy.
3. **Transition** — the environment moves to a new state S<sub>t+1</sub>.
4. **Reward** — the environment emits a reward R<sub>t+1</sub>.
5. **Learn** — the agent updates its policy or value estimates from the experience.

```
        ACTION A_t
   ┌──────────────────────►
┌──┴──────────┐        ┌───┴─────────────┐
│    AGENT    │        │   ENVIRONMENT   │
│ (the learner)│       │   (the world)   │
└──▲──────────┘        └───┬─────────────┘
   └──────────────────────┘
     STATE S_t+1 + REWARD R_t+1
```
*Diagram 2.1 — The agent–environment loop.*

### 2.2 Worked Example: The 2×2 Grid World

We will use this tiny environment throughout the module so every later concept can be checked against the same picture.

```
        x = 0          x = 1
      ┌───────────┬───────────────┐
y = 1 │   (0,1)   │     (1,1)     │
      │   empty   │  GOAL (+1)    │
      │           │  terminal     │
      ├───────────┼───────────────┤
y = 0 │   (0,0)   │     (1,0)     │
      │   START   │     empty     │
      └───────────┴───────────────┘
```
*Diagram 2.2 — The 2×2 grid world used throughout the module.*

| Component | Definition in this world |
|-----------|--------------------------|
| States | Four cells: (0,0), (1,0), (0,1), (1,1). |
| Actions | `Right` (x+1) and `Up` (y+1). A move off the grid leaves the agent in place. |
| Rewards | +1 on entering (1,1); 0 otherwise. |
| Terminal state | (1,1) — the episode ends on arrival. |
| Discount | γ = 0.9. |

> **Worked example: one episode**
>
> Start (0,0). Action `Right` → state (1,0), reward 0. Action `Up` → state (1,1), reward +1. Episode ends.
>
> The transition tuple for each step is (S<sub>t</sub>, A<sub>t</sub>, R<sub>t+1</sub>, S<sub>t+1</sub>):
>
> - Step 1: ((0,0), Right, 0, (1,0))
> - Step 2: ((1,0), Up, +1, (1,1))

> **Q2.1.** The agent is at (1,0) and chooses `Up`. What is the next state and reward?
>
> **A.** Next state (1,1); reward +1; episode ends.

> **Activity 2.1 — Trace an episode**
>
> Starting at (0,0), the agent follows: `Right`, `Right`, `Up`.
>
> (a) List the state after each action. (b) List the reward after each action. (c) What is the total undiscounted reward?
>
> **Answer.** (a) Start (0,0) → Right → (1,0) → Right → (1,0) (blocked, stays) → Up → (1,1). (b) Rewards: 0, 0, +1. (c) Total = 1. The second `Right` was wasted — this is exactly why learning is needed.

---

## 3. Reinforcement Learning

### 3.1 What Makes RL Different

1. **Trial and error.** The agent is not told the correct action. It must try actions and observe consequences.
2. **Delayed reward.** The reward for a good action may arrive many steps later. The agent must solve the **credit assignment problem**: which earlier actions deserve credit for the final outcome?
3. **The environment responds to the agent.** The agent's own choices change future states, so the data it collects depends on its behaviour.

> **Common misconception**
>
> "RL is supervised learning with rewards as labels." No. In supervised learning, the label tells you the correct output for this input. In RL, the reward tells you how good the outcome was — not which action was correct. If a chess agent wins, every move gets some credit, even the bad ones.

### 3.2 Exploration vs Exploitation

The agent faces a constant trade-off:

- **Exploitation** — choose the action currently believed to be best (that is, the one with the highest estimated value).
- **Exploration** — try other actions, because one of them might be better.

The standard solution is **ε-greedy**: with probability ε (e.g., 0.1), choose a random action; otherwise choose the best-known action. ε is often reduced over time so the agent explores early and exploits later.

> **Q3.1.** Why is pure exploitation dangerous?
>
> **A.** The agent may never discover a better action. If it always takes the first action that looked good, it can get stuck in a mediocre policy forever.

> **Activity 3.1 — Predict the outcome** *(type: prediction)*
>
> A learner sets ε = 0 in the ε-greedy rule from the very start. Predict what happens to the agent's learning. Then propose one fix.
>
> **Answer.** With ε = 0 the agent never explores: it always picks the currently best-known action. If the initial value estimates are all equal (e.g., zero), the agent picks one arbitrary action forever. If that first action happens to be bad, the agent never discovers the good one, and the learned policy depends entirely on initial tie-breaking and the first reward signal. **Fix:** keep ε > 0 for some period, or use *optimistic initialisation* (start value estimates high so unexplored actions look attractive).

---

## 4. Markov Decision Process — States, Actions, Rewards

### 4.1 Why a Formal Framework?

The grid world is easy to describe in words, but to compute values and policies we need a precise mathematical object. The **Markov Decision Process (MDP)** is that object. Every algorithm in this module operates on an MDP.

### 4.2 The Components

| Symbol | Meaning |
|--------|---------|
| S | The set of all states the agent can be in. |
| A | The set of all actions available. |
| R(s, a, s′) | The reward for moving from s to s′ via a. |

In the 2×2 grid:

- S = {(0,0), (1,0), (0,1), (1,1)}
- A = {Right, Up}
- R = +1 for any transition into (1,1); 0 otherwise.

### 4.3 The Markov Property

The **Markov property** says: the current state contains all the information needed to predict the future. The past adds nothing beyond the present state.

> **Why this matters for beginners**
>
> Choosing the right state representation is a design decision. In the grid world, the coordinate is a perfect state. In a robot with only a forward camera, one image may not satisfy the Markov property, because the robot cannot see behind it. If the state is insufficient, learning becomes much harder.

> **Q4.1.** In a card game, is "the cards in my hand" a sufficient state?
>
> **A.** Not by itself — you also need to know which cards have already been played, because that affects what can still be drawn. A sufficient state must include that history or a summary of it.

> **Activity 4.1 — Write down an MDP**
>
> A 1×3 corridor has cells 1, 2, 3. Cell 3 is the goal (+1, terminal). Actions: `Left`, `Right`. Moving into a wall leaves you in place (reward 0).
>
> (a) State set. (b) Action set. (c) Two transition probabilities: one successful move, one blocked move. (d) Reward for moving from cell 2 to cell 3 via `Right`.
>
> **Answer.** (a) S = {1, 2, 3}. (b) A = {Left, Right}. (c) P(2 | 1, Right) = 1 (successful); P(1 | 1, Left) = 1 (blocked, stays). (d) R(2, Right, 3) = +1.

---

## 5. Markov Decision Process — Probabilities, Policy, Value Function

### 5.1 Transition Probabilities

Real environments are rarely deterministic — the outcome is not certain. A robot's wheels may slip; a user may click or not. Uncertainty is captured by **transition probabilities** P(s′ | s, a), which give the probability of landing in s′ after action a in state s.

> **Worked example**
>
> Modify the grid so `Right` succeeds with probability 0.8, and with probability 0.2 the agent slips and stays in place. Then:
>
> P((1,0) | (0,0), Right) = 0.8 and P((0,0) | (0,0), Right) = 0.2.

### 5.2 Policy

A **policy** π(a | s) is a probability distribution over actions given a state. A *deterministic* policy always picks the same action in a given state; a *stochastic* policy assigns probabilities. An **optimal policy** π\* maximises expected return from every state.

### 5.3 Discount Factor γ

The **discount factor** γ ∈ [0, 1) makes future rewards worth less than immediate ones. There are three reasons:

- **Uncertainty.** A reward far in the future is less certain than one now.
- **Mathematical convenience.** With γ < 1, the infinite sum of rewards is finite.
- **Preference for sooner.** In many applications, reaching the goal sooner is genuinely better.

With γ = 0.9, a reward of +1 received two steps in the future is worth 0.9² = 0.81 now.

### 5.4 Value Functions

A **value function** predicts how much total future reward to expect.

```
State value:   Vπ(s)   = Eπ[ Rt+1 + γ·Rt+2 + γ²·Rt+3 + ⋯ | St = s ]
Action value:  Qπ(s,a) = Eπ[ Rt+1 + γ·Rt+2 + γ²·Rt+3 + ⋯ | St = s, At = a ]
```

**Symbols.** E<sub>π</sub> = expected value (average) when following π. γ = discount factor, defined in Section 5.3. The subscript t indexes time steps. The vertical bar "|" means "given".

**Plain English.** V(s) is the average total discounted reward the agent expects starting from s under π. Q(s, a) is the average total discounted reward from taking a in s and *then* following π.

> **Worked example: computing a value by hand**
>
> In the deterministic 2×2 grid, policy: "in (0,0), go `Right`; in (1,0), go `Up`." Path: (0,0) → (1,0) → (1,1), rewards 0 then +1.
>
> - V<sup>π</sup>((0,0)) = 0 + 0.9 × 1 = **0.9**.
> - Also: V<sup>π</sup>((1,0)) = **1** (the next move enters the goal and earns +1 immediately).
> - V<sup>π</sup>((1,1)) = **0** (terminal — no further reward is collected).
>
> **Teaching note:** the reward for entering the goal is counted in the value of the *previous* state, not the goal state. This is the most common beginner trap in this chapter.

> **Q5.1.** Under the same policy, what is V<sup>π</sup>((0,1))?
>
> **A.** From (0,1), the policy says `Right`, which enters (1,1) and earns +1. So V<sup>π</sup>((0,1)) = 1 + 0.9 × 0 = 1.

> **Activity 5.1 — Change the discount**
>
> With the same policy, what is V<sup>π</sup>((0,0)) if γ = 0.5? Explain the change in one sentence.
>
> **Answer.** V<sup>π</sup>((0,0)) = 0 + 0.5 × 1 = 0.5. The reward is one step in the future, so a smaller γ shrinks its present value more heavily.

> **Activity 5.2 — Find the error** *(type: find the error)*
>
> A student defines an MDP for a card game. The state is "the cards in the player's hand." A second student says: "This violates the Markov property." Find the error and fix the state definition.
>
> **Answer.** The state is insufficient — the player's hand does not include which cards have already been played, the discard pile, or the opponent's visible cards. Two situations with identical hands but different play histories would require different optimal actions. **Fix:** extend the state to include played cards, the discard pile, and the opponent's visible information.

---

## 6. Model Based vs Model Free

### 6.1 The Distinction

A **model** is the agent's estimate of how the environment behaves: "if I am in state s and take action a, I will probably end up in s′ and get reward r." Formally, this is the pair of transition probabilities P(s′ | s, a) and rewards R(s, a, s′) — both defined in Section 4.2 and Section 5.1.

- **Model-based learning:** the agent learns this model, then uses it to *plan* — simulating ahead.
- **Model-free learning:** the agent learns values or a policy directly, without an explicit model.

| | MODEL-BASED | MODEL-FREE |
|---|---|---|
| Idea | learns how the world responds; can simulate ahead | learns values or policy directly; no simulation |
| Pro | data-efficient once learned | no model errors |
| Con | model errors compound | needs more interaction |
| Examples | value iteration, policy iteration | Q-learning, SARSA, DQN, REINFORCE |

*Diagram 6.1 — The two families and their trade-offs.*

### 6.2 An Analogy

A **model-based** learner is like someone who builds a mental map of a new city: "this street connects to that one." Once the map is good, new routes can be planned without walking them. A **model-free** learner is like someone who learns by repetition: "when I leave home and turn left, I get to work." No map, but the habit works — until a road closes, and then it must discover the detour by trial.

> **Q6.1.** A robot vacuum has a stored floor plan and computes a route from it. Model-based or model-free?
>
> **A.** Model-based. The floor plan is an explicit model, and the route is planned over it.

> **Activity 6.1 — Compare approaches** *(type: comparison)*
>
> Robot A works in a fixed warehouse with a stored, accurate floor plan. Robot B works in a new building every week with no map. For each robot, decide whether model-based or model-free learning is more appropriate. Justify both choices in one sentence each.
>
> **Answer.** **Robot A: model-based.** The model (the floor plan) is already available, so planning over it is efficient; a model-free method would waste the plan. **Robot B: model-free.** No model is available, and learning one from scratch every week is expensive; the robot must learn values or a policy from experience. The decision is driven by whether a reliable model exists.

---

## 7. Bellman Equation

### 7.1 The Idea in One Sentence

**The value of where you are now equals the reward you get for the next step plus the discounted value of where you land.** Everything else is notation.

```
   V(s)     =     R(s, a, s′)      +      γ · V(s′)
 value of      immediate reward        discounted next value
 state s

 Value now = reward next step + discounted value of where you land
 γ ∈ [0,1): how much the future counts
```
*Diagram 7.1 — The Bellman equation decomposed into its three parts.*

### 7.2 The Expectation Form (fixed policy)

```
Vπ(s) = Σa π(a | s) Σs′ P(s′ | s, a) [ R(s, a, s′) + γ Vπ(s′) ]
```

**Read it left to right.** The value of s under π = average over actions the policy might take (weighted by π(a|s)) of the average over next states (weighted by P) of [immediate reward + discounted value of the next state].

### 7.3 The Optimality Form

```
V*(s) = maxa Σs′ P(s′ | s, a) [ R(s, a, s′) + γ V*(s′) ]
```

The only change: max<sub>a</sub> instead of averaging over actions. The agent picks the *best* action rather than following a fixed policy.

### 7.4 Worked Example

> **One Bellman update**
>
> In the 2×2 grid, suppose V\*((1,0)) = 1 and V\*((0,1)) = 1. What is V\*((0,0))?
>
> From (0,0): `Right` gives Q = 0 + 0.9 × 1 = 0.9. `Up` gives Q = 0 + 0.9 × 1 = 0.9. V\*((0,0)) = max(0.9, 0.9) = **0.9**.
>
> Both actions are optimal — optimal policies need not be unique.

### 7.5 Why It Is Powerful

The Bellman equation turns an infinite-horizon problem ("maximise reward over all future steps") into a recursive one-step problem ("what is the best immediate action, given the value of the next state?"). Every algorithm in this module is a way of solving or approximating this recursion.

> **Q7.1.** Suppose V\*((1,0)) = 1 but V\*((0,1)) = 0. What is the optimal action from (0,0), and what is V\*((0,0))?
>
> **A.** `Right` gives 0 + 0.9 × 1 = 0.9. `Up` gives 0 + 0.9 × 0 = 0. So `Right` is optimal and V\*((0,0)) = 0.9.

> **Activity 7.1 — Break the equation** *(type: find the error)*
>
> A classmate writes: `V(s) = R(s,a,s′) + V(s′)`. Identify three things wrong or missing compared with the correct Bellman equation.
>
> **Answer.** (1) No expectation over actions (or no max<sub>a</sub>) — the equation must account for the action choice. (2) No expectation over next states — must sum over s′ weighted by P(s′|s,a). (3) No discount factor γ on the future value.

---

## 8. Dynamic Programming (1) — Policy Evaluation

### 8.1 What Dynamic Programming Means Here

**Dynamic programming (DP)** solves problems by breaking them into overlapping subproblems and reusing solutions. In RL, DP computes value functions by iterating the Bellman equation over the whole state space until values stop changing. This requires knowing the model (P and R), so DP is **model-based**.

### 8.2 The Question Policy Evaluation Answers

Given a fixed policy π, what is V<sup>π</sup>? It measures how good the current policy is; it does not try to improve it.

### 8.3 The Algorithm

Recall from the notation box that ← means "update to".

1. Initialise V(s) = 0 for all states.
2. Repeat: for each state s, update

   ```
   V(s) ← Σa π(a | s) Σs′ P(s′ | s, a) [ R(s, a, s′) + γ V(s′) ]
   ```
3. Stop when the largest change across all states is below a small threshold (e.g., 0.001).

### 8.4 Worked Example: Two Sweeps on the 2×2 Grid

Policy: "always go `Right` if possible; otherwise `Up`." γ = 0.9. Initialise V = 0.

| Sweep | V((1,1)) | V((1,0)) | V((0,1)) | V((0,0)) |
|-------|----------|----------|----------|----------|
| 0 (init) | 0 | 0 | 0 | 0 |
| 1 | 0 | 1 | 1 | 0 |
| 2 | 0 | 1 | 1 | 0.9 |
| 3 | 0 | 1 | 1 | 0.9 (converged) |

**How sweep 1 was computed.** V((1,0)): the policy takes `Up`, entering (1,1) with reward +1, so V = 1 + 0.9 × 0 = 1. V((0,1)): the policy takes `Right`, same result. V((0,0)): the policy takes `Right`, entering (1,0) with reward 0, so V = 0 + 0.9 × V<sub>old</sub>((1,0)) = 0.9 × 0 = 0.

**How sweep 2 was computed.** Only V((0,0)) changes: 0 + 0.9 × 1 = 0.9. Further sweeps do not change the values.

> **Q8.1.** Why does V((1,0)) become 1 in sweep 1, not 0?
>
> **A.** Because the reward for entering the goal is earned on the transition from (1,0) to (1,1). The value of (1,0) includes that +1 immediately; it is the terminal state (1,1) that has value 0.

> **Activity 8.1 — One more sweep**
>
> Starting from the converged values above, suppose γ changes to 0.5. Perform one sweep of policy evaluation. What are the new values?
>
> **Answer.** V((1,1)) = 0; V((1,0)) = 1; V((0,1)) = 1; V((0,0)) = 0 + 0.5 × 1 = 0.5. The goal-adjacent states keep value 1; the start state's value shrinks because its reward is delayed and now discounted more heavily.

> **Activity 8.2 — Find the error** *(type: find the error)*
>
> A student reports the following sweep-2 values for the 2×2 grid with γ = 0.9, given that sweep-1 produced V<sub>old</sub>((1,0)) = 1:
>
> V((1,0)) = 0, V((0,1)) = 1, V((0,0)) = 0.5
>
> Find the arithmetic error and give the corrected sweep-2 values.
>
> **Answer.** V((1,0)) = 0 is wrong. From (1,0), the policy takes `Up`, which enters the goal (1,1) and earns +1 immediately: V((1,0)) = 1 + 0.9 × V((1,1)) = 1 + 0 = 1, not 0. With V((1,0)) = 1, V((0,0)) = 0 + 0.9 × 1 = 0.9, not 0.5. **Corrected sweep 2:** V((1,1)) = 0, V((1,0)) = 1, V((0,1)) = 1, V((0,0)) = 0.9.

---

## 9. Dynamic Programming (2) — Policy Improvement

### 9.1 The Idea

Once V<sup>π</sup> is known, ask at each state: if I take action a now, and then follow π, is that better or worse than what π would do? If some action looks better, switch to it.

### 9.2 The Update Rule

```
π′(s) = argmaxa Σs′ P(s′ | s, a) [ R(s, a, s′) + γ Vπ(s′) ]
```

**Plain English.** In each state, choose the action that maximises one-step reward plus discounted value of the next state. Remember from the notation box that argmax<sub>a</sub> returns the *action*, not the value.

### 9.3 The Policy Improvement Theorem

The theorem guarantees that the new policy π′ is *at least as good as* π from every state. It cannot be worse. If it is exactly as good, then π was already optimal. This is the mathematical justification for the whole evaluate–improve cycle.

> **Worked example**
>
> Using the converged values from Section 8.4: V((0,0)) = 0.9, V((1,0)) = 1, V((0,1)) = 1, V((1,1)) = 0, γ = 0.9.
>
> - At (0,0): Q(Right) = 0 + 0.9 × 1 = 0.9; Q(Up) = 0 + 0.9 × 1 = 0.9. Both actions tie — the policy is already optimal at (0,0).
> - At (1,0): Q(Up) = 1 + 0.9 × 0 = 1; Q(Right) is blocked. So `Up` is optimal.
> - At (0,1): Q(Right) = 1; Q(Up) is blocked. So `Right` is optimal.

> **Q9.1.** Suppose V((0,1)) were 0.5 instead of 1. Which action would policy improvement choose at (0,0)?
>
> **A.** `Right`: 0 + 0.9 × 1 = 0.9, versus `Up`: 0 + 0.9 × 0.5 = 0.45. `Right` wins.

---

## 10. Value Iteration

### 10.1 The Idea

Policy iteration does two full phases: evaluate the policy completely, then improve it. **Value iteration** merges them: at every state, immediately take the best action (using current value estimates) and update the value. There is no separate evaluation phase.

### 10.2 The Update

```
Vk+1(s) ← maxa Σs′ P(s′ | s, a) [ R(s, a, s′) + γ Vk(s′) ]
```

Each sweep updates every state using the best one-step lookahead. Repeat until the maximum change is below a threshold. Then extract the policy **greedily** from V\* — *greedy* means: at each state, choose the action with the highest current value estimate.

### 10.3 Worked Example: Sweeps on the 2×2 Grid

γ = 0.9. Initialise all V = 0. Terminal (1,1) stays 0.

| Sweep | V((1,1)) | V((1,0)) | V((0,1)) | V((0,0)) |
|-------|----------|----------|----------|----------|
| 0 (init) | 0 | 0 | 0 | 0 |
| 1 | 0 | 1 | 1 | 0 |
| 2 | 0 | 1 | 1 | 0.9 |
| 3 | 0 | 1 | 1 | 0.9 (converged) |

**Extract the policy.** At (0,0), both actions give 0.9, so either is optimal. At (1,0), `Up` is optimal. At (0,1), `Right` is optimal.

### 10.4 Why It Converges

For γ < 1, the Bellman optimality operator is a **contraction** — a mapping that brings any two points closer together. Repeated application therefore converges to a unique **fixed point** — a value function that no longer changes when the update is applied. This is the mathematical guarantee that value iteration works.

> **Q10.1.** Why does V((0,0)) stay 0 in sweep 1?
>
> **A.** Because the update uses the *old* values for the next states, and V<sub>old</sub>((1,0)) and V<sub>old</sub>((0,1)) were both 0 at the start of sweep 1. The value propagates backward one step per sweep.

> **Activity 10.1 — Change the discount**
>
> Re-run value iteration with γ = 0.5. What is V\*((0,0)) after convergence? Explain in one sentence why it changed.
>
> **Answer.** V\*((1,0)) = 1, V\*((0,1)) = 1, V\*((0,0)) = 0 + 0.5 × 1 = 0.5. The start state's value is lower because the reward is one step in the future and is discounted more heavily when γ is smaller.

> **Activity 10.2 — Compare approaches** *(type: comparison)*
>
> A grid world has 10,000 states. Compare value iteration and policy iteration for this case. Which would you try first, and why?
>
> **Answer.** Value iteration has many cheap sweeps; policy iteration has fewer outer iterations, each more expensive because the evaluation phase runs to convergence. For a large state space, try value iteration first because of its lower per-iteration cost. Fall back to policy iteration if convergence is too slow, or if a good initial policy is available (in which case policy iteration's outer loop terminates in very few iterations).

---

## 11. Policy Iteration

### 11.1 The Algorithm

1. Initialise a policy π (e.g., always `Right`).
2. **Policy evaluation:** compute V<sup>π</sup> by iterating the Bellman expectation equation until convergence.
3. **Policy improvement:** set π′(s) = argmax<sub>a</sub> Q<sup>π</sup>(s, a) for every state.
4. If π′ = π, stop. Otherwise set π ← π′ and return to step 2.

### 11.2 Value Iteration vs Policy Iteration

| | Value iteration | Policy iteration |
|---|---|---|
| What is iterated | The value function directly | The policy, with full value evaluation inside each iteration |
| Policy extraction | After convergence (or greedily during) | At every improvement step |
| Typical behaviour | Many cheap sweeps | Fewer outer iterations, each more expensive |
| Conceptual focus | Fixed-point iteration of the optimality operator | Alternation of evaluation and improvement |
| When to prefer | Large state spaces where full evaluation is costly | When a good policy is found quickly and evaluation is affordable |

Both converge to the same optimal policy. The choice is an engineering trade-off, not a correctness issue.

> **Worked example**
>
> Start with policy "always `Right`." Policy evaluation gives the values from Section 8.4. Policy improvement: at (0,0) both actions tie; at (1,0), `Up` is best; at (0,1), `Right` is best.
>
> The new policy differs from the old at (1,0) (old policy said `Right`, which is blocked). Re-evaluate with the new policy — it is already optimal — and the next improvement step changes nothing. Policy iteration terminates after two outer iterations.

> **Q11.1.** Why does policy iteration stop when the policy stops changing, while value iteration stops when the value changes become small?
>
> **A.** Policy iteration has an explicit policy to compare; a discrete "no action changed" is a clean stopping condition. Value iteration has no explicit policy during the loop, so it uses the magnitude of value changes as a proxy — small changes imply the greedy policy is (nearly) stable.

---

## 12. On-Policy & Off-Policy: The Core Distinction

> **Why this section comes before the algorithms**
>
> The next three sections describe algorithms that are classified as on-policy or off-policy. Those two terms are defined here, so that when the algorithms reference them, they have already been taught.

### 12.1 The Definitions

Every RL agent has two policies:

- **Behaviour policy:** the policy the agent actually uses to select actions during learning (e.g., ε-greedy, which sometimes picks a random action).
- **Target policy:** the policy the agent is trying to learn or improve.

These may be the same policy or different ones. That gives the two families:

- **On-policy:** the behaviour policy and the target policy are the *same*. The update target uses the action actually taken next (a′). Examples: SARSA, REINFORCE.
- **Off-policy:** the behaviour policy and the target policy are *different*. The update target uses the best possible next action (max<sub>a′</sub>). Examples: Q-learning, DQN.

### 12.2 Comparison Table

| | On-policy | Off-policy |
|---|---|---|
| Behaviour policy | Same as target policy | Different from target policy |
| Update target | Uses actual next action a′ | Uses best next action max<sub>a′</sub> |
| Examples | SARSA, REINFORCE | Q-learning, DQN |
| Data reuse | Each update must be based on the current policy's actions | Can learn from old or exploratory data |
| Behavioural consequence | Learns the value of the policy it actually follows, including exploratory mistakes | Learns the optimal policy even while exploring suboptimally |

### 12.3 A Beginner-Friendly Summary

**On-policy** learning is like learning the value of the strategy you are actually playing. **Off-policy** learning is like learning the value of the *best* strategy, even while you are experimenting with worse ones.

Neither is universally better. Off-policy is more data-efficient and can learn from old experience; on-policy is often more stable and naturally accounts for the exploration the agent will actually do.

> **Q12.1.** A robot uses ε-greedy exploration and Q-learning. Is the policy it follows the same as the policy it is learning? Explain.
>
> **A.** No. It follows an ε-greedy behaviour policy (sometimes random), but it learns the greedy optimal policy via the max in the update. This is off-policy learning.

> **Activity 12.1 — Classify the algorithm**
>
> For each algorithm, state whether it is on-policy or off-policy, and give the update target in one line.
>
> (a) SARSA. (b) Q-learning. (c) REINFORCE. (d) DQN.
>
> **Answer.** (a) On-policy; target = r + γ Q(s′, a′) using the action actually taken. (b) Off-policy; target = r + γ max<sub>a′</sub> Q(s′, a′). (c) On-policy; target = the return G<sub>t</sub> from the episode, using the actions actually taken. (d) Off-policy; target = r + γ max<sub>a′</sub> Q(s′, a′; θ⁻) using the target network.

---

## 13. Reinforcement Learning Algorithms — Overview

> **This section is a map, not a lesson**
>
> The three families below are explained in detail in Section 14–Section 17. Reading this section first gives you the landscape; do not expect to fully understand the algorithms yet. Every term used here is defined in the section that teaches the relevant algorithm.

### 13.1 From Model-Based to Model-Free

Everything up to Section 11 assumed the model (P and R) was known. From here on, the agent learns from **sampled experience**: it does not know P or R in advance. Model-free RL splits into three families.

```
                  MODEL-FREE RL
          ┌──────────────┼──────────────┐
          ▼              ▼              ▼
    VALUE-BASED     POLICY-BASED    ACTOR–CRITIC
    learns V or Q   learns π        learns both
    Q-learning      directly        A2C, PPO
    SARSA, DQN      REINFORCE
                    policy gradient
```
*Diagram 13.1 — The model-free RL family tree.*

### 13.2 What Each Family Stores, Updates, and Uses as Its Learning Signal

| Family | Stores | Updates | Learning signal |
|--------|--------|---------|-----------------|
| Value-based | A table or network of values V(s) or Q(s,a) | The values | TD error (target − current estimate) |
| Policy-based | The policy parameters θ | The policy directly | Return G<sub>t</sub> (or advantage) |
| Actor–critic | Policy parameters θ *and* a value function | Both, together | Advantage estimate (often the TD error) |

> **Q13.1.** Which family would you choose for a continuous action space (e.g., steering angle), and why?
>
> **A.** Policy-based (or actor–critic). Value-based methods require a max over actions, which is awkward in continuous spaces; a policy can output a continuous action directly.

---

## 14. Value Based — Q-Learning

### 14.1 The Idea

**Q-learning** learns the optimal action-value function Q\*(s, a) directly from sampled transitions (s, a, r, s′). Once Q\* is known, the optimal policy is simple: in each state, pick the action with the highest Q-value.

It needs no model. It learns from experience as it happens.

### 14.2 The Update Rule

```
Q(s, a) ← Q(s, a) + α [ r + γ maxa′ Q(s′, a′) − Q(s, a) ]
```

**Symbols.** α = learning rate (small positive number, e.g., 0.1); r = reward just received; s′ = next state; max<sub>a′</sub> Q(s′, a′) = value of the best action in the next state.

**Read it as:**

- **Old estimate:** Q(s, a).
- **Target:** r + γ max<sub>a′</sub> Q(s′, a′) — reward just received plus discounted value of the best action in the next state.
- **TD error** (temporal-difference error): target − old estimate. This is the "surprise": how much better or worse the outcome was than expected.
- **Update:** move the old estimate a fraction α of the way toward the target.

```
Q-learning update, step by step  (α = 0.5 in this example)

  Old estimate   Q(s,a) = 0.2
  Target         r + γ·max Q(s′,a′) = 1
  TD error       target − old = 0.8
  New Q          0.2 + 0.5 × 0.8 = 0.6
```
*Diagram 14.1 — The four parts of the Q-learning update.*

> **Worked example: one Q-learning update**
>
> Q(s, a) = 0.2, r = 1, γ = 0.9, max Q(s′, a′) = 0 (terminal next state), α = 0.5.
>
> - Target = 1 + 0.9 × 0 = 1.
> - TD error = 1 − 0.2 = 0.8.
> - New Q = 0.2 + 0.5 × 0.8 = **0.6**.

### 14.3 Exploration with ε-Greedy

If the agent always picks the highest Q-value, it may never discover a better action. The standard solution is **ε-greedy**: with probability ε choose a random action; otherwise choose the greedy action. ε is often decreased over time.

### 14.4 Q-Learning Is Off-Policy

Q-learning's update target is r + γ max<sub>a′</sub> Q(s′, a′) — the value of the *best possible* next action. It learns the optimal policy even while following an exploratory behaviour policy. That is the **off-policy** distinction, defined in Section 12.

> **Common misconception**
>
> "Q-learning always follows the greedy action." No. Q-learning *learns about* the optimal policy, but the agent *behaves* using an exploratory policy (e.g., ε-greedy). The separation between behaviour policy and target policy is the essence of off-policy learning.

> **Q14.1.** Why is Q-learning called "off-policy"?
>
> **A.** Its update target uses max<sub>a′</sub> Q(s′, a′) — the best possible next action — regardless of the action the agent will actually take. It learns the optimal policy while behaving exploratorily.

> **Activity 14.1 — Trace a Q-learning update**
>
> With Q(s, a) = 1.5, r = 0, γ = 0.9, max Q(s′, a′) = 2, α = 0.1: compute the TD error and the new Q value.
>
> **Answer.** Target = 0 + 0.9 × 2 = 1.8. TD error = 1.8 − 1.5 = 0.3. New Q = 1.5 + 0.1 × 0.3 = 1.53.

> **Activity 14.2 — Explain a decision** *(type: explain a decision)*
>
> An engineer building a robot vacuum wants to learn from historical data collected by other vacuums in the same building. She chooses Q-learning over SARSA. Explain her decision.
>
> **Answer.** Q-learning is off-policy, so it can learn from historical data collected under a different behaviour policy (the other vacuums' policies). SARSA is on-policy and its updates assume the robot's own actions; it cannot reuse old-policy data without correction. Since she wants to reuse existing data, Q-learning is the right choice.

---

## 15. Value Based — Deep Q-Network, SARSA

### 15.1 SARSA

**SARSA** updates using the action the agent *actually takes* next, not the best possible action:

```
Q(s, a) ← Q(s, a) + α [ r + γ Q(s′, a′) − Q(s, a) ]
```

The name comes from the quintuple (s, a, r, s′, a′). Because the update uses the action the agent actually takes, SARSA is **on-policy** (defined in Section 12).

> **Worked contrast: Q-learning vs SARSA**
>
> State (0,0), action `Up` → state (0,1), reward 0. Q((0,0), Up) = 0.5, α = 0.1, γ = 0.9. In (0,1), Q(Right) = 1 and Q(Left) = 0. The behaviour policy (exploring) chooses `Left` this time.
>
> - **Q-learning target:** 0 + 0.9 × max(1, 0) = 0.9. New Q = 0.5 + 0.1 × (0.9 − 0.5) = **0.54**.
> - **SARSA target:** 0 + 0.9 × Q((0,1), Left) = 0. New Q = 0.5 + 0.1 × (0 − 0.5) = **0.45**.
>
> Q-learning is optimistic: it updates as if the agent will act optimally next. SARSA is realistic: it updates based on what the agent actually did, including exploratory mistakes.

### 15.2 The Cliff-Walk Intuition

A grid has a cliff along the bottom. The shortest path hugs the cliff; the safe path is one row away.

- **Q-learning** learns the cliff-edge path, because its target assumes optimal future actions. This is *optimal* if exploration stops at deployment.
- **SARSA** learns the safer path, because its target accounts for the exploratory actions the agent actually takes — including the occasional fall.

```
START ───────────────────────────────────► GOAL
        SARSA: safer path (solid blue, upper row)
                                              ▲
  - - - - - - - - - - - - - - - - - - - - - - ┘
  Q-learning: optimal but risky (dashed red, along the cliff edge)
┌──────────────────────────────────────────────┐
│              CLIFF (fall = −100)              │
└──────────────────────────────────────────────┘
```
*Diagram 15.1 — The behavioural consequence of on-policy vs off-policy learning. Q-learning (off-policy) takes the cliff-edge route; SARSA (on-policy) takes the safer route.*

### 15.3 Deep Q-Network (DQN)

A Q-table is impossible when states are images with millions of pixels. **DQN** replaces the table with a **neural network** — a model made of layers of simple units connected by adjustable weights. It takes a state as input and outputs one Q-value per action. The network is trained to minimise the squared TD error.

Two stabilising innovations are standard:

- **Experience replay:** store transitions in a buffer and sample random **minibatches** (small random samples of stored transitions). This breaks the correlation between consecutive samples.
- **Target network:** use a separate, slowly updated copy of the network to compute the TD target, so the target does not move every time the main network updates.

```
INPUT            HIDDEN LAYERS      OUTPUT           STABILITY TRICKS
state (pixels) ─ learned features ─ one Q per action ─ experience replay
                                                       target network
                                                       squared TD loss
```
*Diagram 15.2 — DQN architecture and its two stability tricks.*

> **Q15.1.** In the cliff-walk, which algorithm would a safety engineer prefer if the robot continues to explore during deployment?
>
> **A.** SARSA. Its on-policy updates account for the exploratory actions the robot actually takes, so it learns a policy that is safe *given that exploration continues*. Q-learning's optimal cliff-edge path is only optimal if exploration stops.

> **Activity 15.1 — DQN vs Q-table**
>
> Why can a DQN be used where a Q-table cannot? Give one example domain.
>
> **Answer.** A Q-table needs one entry per state–action pair, which is impossible when states are high-dimensional (e.g., raw pixel images with millions of possible inputs). A DQN generalises across states using a neural network. Example: Atari game playing from screen pixels.

> **Activity 15.2 — Compare approaches** *(type: comparison)*
>
> A robot's state is a 512-dimensional continuous sensor reading. Compare a Q-table and a DQN for this case. Which is feasible, and why?
>
> **Answer.** A Q-table would need one entry per (state, action) pair; with 512-dimensional continuous states there are infinitely many entries, so the table is not feasible. A DQN approximates Q with a neural network and generalises across similar states. The DQN is the only feasible choice; the trade-off is that it is harder to train and debug than a table.

---

## 16. Policy Based — REINFORCE, Policy Gradient

### 16.1 Why Learn the Policy Directly?

- When the action space is continuous (e.g., steering angle), taking a max over actions is awkward.
- When the optimal policy is stochastic (e.g., games with mixed strategies).
- When small changes in action values should produce small changes in behaviour (smooth policies).

### 16.2 The Core Idea

Parameterise the policy π<sub>θ</sub>(a | s) by parameters θ (e.g., the weights of a neural network). Adjust θ so that actions that led to high return become more likely.

The **policy gradient** for an episode is:

```
∇θ J(θ) = E[ Σt γ^t · Gt · ∇θ ln πθ(At | St) ]
```

**Symbols.** ∇<sub>θ</sub> = gradient with respect to θ — the direction in which the quantity increases fastest. J(θ) = expected return. G<sub>t</sub> = the return from time t, defined in Section 5.4 as the total discounted future reward. ln = the natural logarithm (a standard mathematical function; the algorithm computes it — you do not need to by hand). E[·] = expected value.

**Plain English.** The gradient points toward making the taken action more likely; multiplying by G<sub>t</sub> scales the push by how good the outcome was.

### 16.3 REINFORCE

**REINFORCE** is the simplest policy-gradient algorithm. It runs a complete episode, computes the return G<sub>t</sub> for each step, and updates:

```
θ ← θ + α Σt γ^t · Gt · ∇θ ln πθ(At | St)
```

> **Worked example: computing returns**
>
> An episode has three actions a<sub>0</sub>, a<sub>1</sub>, a<sub>2</sub>, with rewards r<sub>1</sub> = 0, r<sub>2</sub> = 0, r<sub>3</sub> = 1. γ = 0.9.
>
> - G<sub>2</sub> = r<sub>3</sub> = 1.
> - G<sub>1</sub> = r<sub>2</sub> + γ r<sub>3</sub> = 0 + 0.9 = 0.9.
> - G<sub>0</sub> = r<sub>1</sub> + γ r<sub>2</sub> + γ² r<sub>3</sub> = 0 + 0 + 0.81 = 0.81.
>
> All three actions are reinforced, but the later actions (closer to the reward) get stronger reinforcement. REINFORCE assigns credit to *all* actions in the episode, including bad ones.

### 16.4 The Variance Problem

REINFORCE is **unbiased** — its estimate is correct on average across many episodes — but **high variance**: the estimate fluctuates a lot from one episode to another, which makes learning noisy. Two standard remedies:

- **Baseline subtraction:** subtract a baseline b(s) (often an estimate of V(s)) from G<sub>t</sub>. This does not change the expected gradient but reduces variance. The quantity G<sub>t</sub> − b(s) is an estimate of the **advantage**.
- **Actor–critic:** use a learned value function as the baseline (next section).

> **Q16.1.** In the worked example, why does a<sub>0</sub> get less credit than a<sub>2</sub>?
>
> **A.** Because the reward is further in the future from a<sub>0</sub>, so it is discounted more heavily. a<sub>2</sub> is immediately before the reward and gets full credit.

> **Activity 16.1 — Compute a return**
>
> Rewards: 0, 2, 0, 1. γ = 0.5. Compute G<sub>0</sub>, G<sub>1</sub>, G<sub>2</sub>, G<sub>3</sub>.
>
> **Answer.** G<sub>3</sub> = 1. G<sub>2</sub> = 0 + 0.5 × 1 = 0.5. G<sub>1</sub> = 2 + 0.5 × 0 + 0.25 × 1 = 2.25. G<sub>0</sub> = 0 + 0.5 × 2 + 0.25 × 0 + 0.125 × 1 = 1.125.

> **Activity 16.2 — Predict the outcome** *(type: prediction)*
>
> A learner uses a baseline b(s) that is always 100, when typical returns are between 0 and 10. Predict what happens to the learning. Explain.
>
> **Answer.** The expected gradient is unchanged (because the expected gradient of ln π with respect to θ is zero for any policy, so adding a constant to the baseline does not bias the estimate). But the variance increases dramatically: every update has magnitude around 100 − (0 to 10) ≈ 90–100 instead of the natural 0–10 scale. With a fixed learning rate, the updates become noisy and can cause unstable or divergent learning. **Fix:** learn the baseline alongside the policy so it tracks typical returns.

---

## 17. Actor–Critic Algorithms

### 17.1 The Idea

**Actor–critic** combines policy-based and value-based learning. Two components learn together:

- **Actor:** the policy π<sub>θ</sub>(a | s), updated by policy gradients.
- **Critic:** a value function V<sub>w</sub>(s) or Q<sub>w</sub>(s, a), which evaluates the actor's choices and provides a lower-variance signal.

```
 ┌──────────────────┐      action       ┌───────────────────┐
 │      ACTOR       │ ────────────────► │    ENVIRONMENT    │
 │ policy πθ(a|s)   │                   │  state, reward,   │
 │ chooses actions  │                   │  next state       │
 └───────▲──────────┘                   └─────────┬─────────┘
         │ TD error / advantage                   │
 ┌───────┴──────────┐   reward + next state       │
 │      CRITIC      │ ◄───────────────────────────┘
 │  value Vw(s)     │
 └──────────────────┘
```
*Diagram 17.1 — Actor–critic: the critic's TD error updates both the critic and the actor.*

### 17.2 The Advantage Function

```
Aπ(s, a) = Qπ(s, a) − Vπ(s)
```

It measures how much better action a is than the **average** action under the policy in state s. Positive advantage means "better than usual"; negative means "worse than usual."

A practical estimate uses the **TD error** (defined in the notation box):

```
δ = r + γ Vw(s′) − Vw(s)
```

If δ > 0, the outcome was better than the critic expected, so the actor should increase the probability of that action. If δ < 0, decrease it.

> **Worked example: one actor–critic update**
>
> V<sub>w</sub>(s) = 0.5, action a, reward r = 1, next state value V<sub>w</sub>(s′) = 0.4, γ = 0.9.
>
> δ = 1 + 0.9 × 0.4 − 0.5 = 1 + 0.36 − 0.5 = **0.86**.
>
> δ is positive, so the actor increases the probability of action a in state s. The critic then updates V<sub>w</sub>(s) toward the target r + γ V<sub>w</sub>(s′) = 1.36, reducing future error.

### 17.3 Why This Helps

The critic gives the actor a **dense** learning signal (every step produces a TD error), whereas REINFORCE only learns at the end of an episode. This reduces variance and speeds learning. Modern algorithms such as A2C and PPO are actor–critic methods.

> **Q17.1.** If δ = −0.3, what should the actor do to the probability of the taken action? Why?
>
> **A.** Decrease it. A negative TD error means the outcome was worse than the critic expected, so the action was worse than average.

> **Activity 17.1 — Compute a TD error**
>
> V(s) = 2.0, r = 1, V(s′) = 1.5, γ = 0.9. Compute δ. Should the actor increase or decrease the action's probability?
>
> **Answer.** δ = 1 + 0.9 × 1.5 − 2.0 = 1 + 1.35 − 2.0 = 0.35. Positive δ → increase the probability.

> **Activity 17.2 — Explain a decision** *(type: explain a decision)*
>
> In your own words, explain why actor–critic typically learns faster than REINFORCE. Do not use the word "variance" without explaining what you mean by it.
>
> **Model answer.** REINFORCE only learns at the end of an episode: the agent acts, collects a return, and then updates the policy. Actor–critic learns at every step: the critic produces a TD error at each step, telling the actor "this action was better or worse than expected right now." Because feedback is available at every step, the actor makes many more updates from the same amount of experience. The "variance" here is the amount by which a single return fluctuates from one episode to another; REINFORCE's per-episode return fluctuates a lot, so its updates are noisy. The critic's per-step TD error reflects only a one-step outcome, so it fluctuates less, and the actor's updates are more stable.

---

## 18. Examples of Applications in the Real World

For each application, identify **what is learned** and **what reward is being optimised** — that is the behavioural core of the system.

| Domain | Example | What is learned | Reward optimised |
|--------|---------|-----------------|------------------|
| Recommender systems | A content platform ranks items; the ranking policy is adjusted from user feedback | A ranking policy | Engagement signals (clicks, watch time) |
| Robotics | A robot arm learns to pour, assemble, or manipulate, trained in simulation and transferred to hardware | A control policy mapping sensor readings to motor commands | Task success, with penalties for dropping or colliding |
| Healthcare / rehabilitation | A prosthesis controller adapts its parameters to an individual patient; a rehabilitation robot adapts exercise difficulty | A personalisation policy | Clinical outcome measures |
| Game playing | Agents learn to play Atari, Go, or chess from pixels or board states | A policy and/or value function | Game score or win/loss |
| Energy management | A building's heating/cooling controller learns when to pre-heat or pre-cool | A control policy | Energy cost minus comfort penalty |
| Traffic signal control | Intersection signals learn timing that reduces waiting | A signalling policy | Negative average vehicle delay |

> **The ethical point, stated plainly**
>
> Every system in this table is a *behavioural* system in the literal sense: it shapes behaviour by optimising a reward. A recommender optimised for clicks will reinforce whatever increases clicks; a robot optimised for speed may learn unsafe shortcuts; a prosthesis optimised for one gait metric may produce a gait that is efficient by that metric but uncomfortable for the patient. The reward function is a design choice with ethical consequences. Beginners should leave this section able to ask: **"What is the reward, who chose it, and whose behaviour does it shape?"**

> **Q18.1.** For the energy-management example, why is a comfort penalty needed in the reward?
>
> **A.** Without it, the agent would learn to minimise energy by turning heating and cooling off entirely — optimal for the stated reward but unacceptable for the occupants. The penalty encodes the real trade-off.

> **Activity 18.1 — Design a reward, predict the behaviour**
>
> A delivery drone is trained with RL. Propose a reward function and predict one behaviour it will learn. Then identify one behaviour it might learn that you did not intend.
>
> **Model answer.** Reward: +10 for on-time delivery, −20 for crash, −1 per minute late, −0.1 per unit of energy. Intended behaviour: efficient, punctual delivery routes. Unintended behaviour: it may learn to fly aggressively fast (risking battery depletion) or to cut close to obstacles to save time, because the reward does not explicitly penalise near-misses. **Fix:** add a proximity-penalty term and test in simulation before deployment.

> **Activity 18.2 — Find the error** *(type: find the error)*
>
> A cleaning robot is trained with the reward: `+10 for cleaning a dirty patch, −5 for bumping into furniture, +1 per minute of operation`. The robot learns to walk in circles and keep "cleaning" the same patch. Find the flaw in the reward and fix it.
>
> **Answer.** The `+1 per minute` rewards the robot for staying on, and the `+10 for cleaning` can be triggered repeatedly if the "dirty" status is re-detected (e.g., after a time threshold). The robot has learned to *farm the reward* rather than clean the room. **Fix:** remove the `+1 per minute`, or replace it with a `−1 per minute` penalty for time spent; flag cleaned patches so they cannot be rewarded twice; add a completion bonus for cleaning all patches. The lesson is that the reward function encodes the intended behaviour, and any term that can be exploited will be.

---

## 19. Master Glossary

| Term | Definition |
|------|------------|
| Action (a) | A choice available to the agent. |
| Actor–critic | An RL method combining a policy (actor) and a value function (critic). |
| Advantage A(s,a) | Q(s,a) − V(s): how much better an action is than average. |
| Agent | The learner or decision-maker. |
| Bellman equation | Value = immediate reward + discounted next-state value. |
| Behaviour policy | The policy the agent actually uses to select actions during learning. |
| Contraction | A mapping that brings any two points closer; guarantees convergence of value iteration. |
| Credit assignment | The problem of deciding which earlier actions contributed to a later reward. |
| Discount factor (γ) | Weight of future rewards relative to immediate ones, in [0,1). |
| DQN | Deep Q-Network: a neural network replacing a Q-table. |
| Dynamic programming | Solving MDPs by iterating the Bellman equation over the full state space. |
| Environment | Everything the agent interacts with. |
| Episode | A run from a start state to a terminal state. |
| ε-greedy | With probability ε choose a random action; otherwise choose the best-known action. |
| Experience replay | Sampling random minibatches from a stored buffer of transitions. |
| Exploration / exploitation | Trying new actions / choosing the best-known action. |
| Fixed point | A value function that no longer changes when the update is applied. |
| Greedy policy | Always choosing the action with the highest current value estimate. |
| Learning rate (α) | How far each update moves the estimate. |
| Markov property | The current state is sufficient to predict the future. |
| MDP | Markov Decision Process: (S, A, P, R, γ). |
| Minibatch | A small random sample of stored transitions. |
| Model-based / model-free | Learning an environment model / learning values or policy directly. |
| Monte-Carlo method | An algorithm that learns from complete episodes rather than step by step. |
| Neural network | A model of layers of simple units connected by adjustable weights. |
| Off-policy / on-policy | Target policy differs from / equals the behaviour policy. |
| Policy (π) | A rule for choosing actions. |
| Policy evaluation | Computing V<sup>π</sup> for a fixed policy. |
| Policy improvement | Making a policy greedy with respect to its value function. |
| Policy iteration | Alternating policy evaluation and policy improvement. |
| Q-learning | Off-policy value-based RL algorithm learning Q\*. |
| Q-value Q(s,a) | Expected return from taking a in s and then following a policy. |
| REINFORCE | Policy-gradient algorithm that updates after each complete episode. |
| Return (G<sub>t</sub>) | Total discounted reward from time t. |
| Reward (r) | Feedback signal in RL. |
| SARSA | On-policy value-based RL algorithm. |
| State (s) | A description of the current situation. |
| State value V(s) | Expected return from state s under a policy. |
| Target network | A slowly updated copy of the Q-network used for stable TD targets. |
| Target policy | The policy the agent is trying to learn or improve. |
| TD error (δ) | Target minus current estimate: the "surprise". |
| Transition probability P(s′\|s,a) | Chance of landing in s′ after action a in s. |
| Unbiased | An estimate that is correct on average across many episodes. |
| Value function | Predicted total future reward (V or Q). |
| Value iteration | Iterating the Bellman optimality equation until convergence. |
| Variance | How much an estimate fluctuates from episode to episode. |

---

## 20. References and Status

### 20.1 References

1. Sutton, R. S., & Barto, A. G. (2018). *Reinforcement Learning: An Introduction* (2nd ed.). MIT Press.
2. Bellman, R. (1957). *Dynamic Programming*. Princeton University Press.
3. Watkins, C. J. C. H., & Dayan, P. (1992). Q-learning. *Machine Learning*, 8, 279–292.
4. Rummery, G. A., & Niranjan, M. (1994). On-line Q-learning using connectionist systems.
5. Williams, R. J. (1992). Simple statistical gradient-following algorithms for connectionist reinforcement learning. *Machine Learning*, 8, 229–256.
6. Konda, V. R., & Tsitsiklis, J. N. (2000). Actor-critic algorithms. *NeurIPS*, 12.
7. Mnih, V., et al. (2015). Human-level control through deep reinforcement learning. *Nature*, 518, 529–533.
8. Puterman, M. L. (1994). *Markov Decision Processes*. Wiley.
9. Skinner, B. F. (1938). *The Behavior of Organisms*.

### 20.2 Reordering and Fixes Applied

| Change | Where |
|--------|-------|
| MDP (States, Actions, Rewards) moved before Model-Based vs Model-Free | New Section 4 (was Section 5) |
| MDP (Probabilities, Policy, Value Function) moved before Model-Based vs Model-Free | New Section 5 (was Section 6) |
| Model-Based vs Model-Free moved after the MDP | New Section 6 (was Section 4) |
| On-Policy & Off-Policy moved before Q-Learning and SARSA | New Section 12 (was Section 17) |
| RL Algorithms Overview moved after On-Policy & Off-Policy | New Section 13 (was Section 12) |
| Discount Factor γ moved before Value Functions (because γ appears in the V and Q equations) | Section 5.3 before Section 5.4 |
| Worked Example moved before "Why It Is Powerful" in the Bellman section | Section 7.4 before Section 7.5 |
| Notation box added | Before Section 1 |
| P(s′\|s,a) removed from the Model-Based vs Model-Free diagram; plain-English label used instead | Section 6 diagram |
| "Greedy", "fixed point", "contraction", "neural network", "minibatch", "gradient", "ln", "unbiased", "variance" all defined at first use | Section 10.2, Section 10.4, Section 15.3, Section 16.2, Section 16.4 |
| Section 12 defines behaviour policy and target policy before they are used | Section 12.1 |
| Module Overview and Learning Outcomes added | Before Section 1 |
| Ten new activities added across four additional types (prediction, comparison, find-error, explain-decision) | Activities 3.1, 6.1, 5.2, 8.2, 10.2, 14.2, 15.2, 16.2, 17.2, 18.2 |
| "Monte-Carlo" glossary entry rewritten | Section 19 |
| "Without correction" cell replaced with plain English | Section 12.2 comparison table |

### Remaining gaps to address in a future version

- Exploration strategies beyond ε-greedy (softmax, optimistic initialisation, UCB) — mentioned only in passing.
- Convergence conditions and the deadly triad — not covered.
- PPO / TRPO — named in Section 13 but not developed.
- Offline RL and multi-agent RL — out of current scope.
- Learner testing — a teammate who did not write Section 14–Section 17 should complete the activities as a "beginner" and record any remaining confusion.

---

*End of module — Stage 8 Behavioural AI V1.1 (Reordered and Fixed)*

