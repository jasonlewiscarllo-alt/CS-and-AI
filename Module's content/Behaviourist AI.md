# Behavioural AI

From the agent–environment loop and Markov Decision Processes, through the Bellman equation and dynamic programming,

to Q-learning, SARSA, DQN, REINFORCE, actor–critic and real-world applications.

Part of: Hardware, Networks and Behavioural AI

------------------------------------------------------------------------

# Contents

- Module overview and learning outcomes
- How to study this module
- Reading the notation (read first)
- 1\. Definition
- 2\. Basic process and example
- 3\. Reinforcement learning
- 4\. MDP: states, actions, rewards
- 5\. MDP: probabilities, policy, value function
- 6\. Model-based vs model-free
- 7\. Bellman equation
- 8\. Dynamic programming (1): policy evaluation
- 9\. Dynamic programming (2): policy improvement
- 10\. Value iteration
- 11\. Policy iteration
- 12\. On-policy and off-policy
- 13\. Algorithms overview
- 14\. Q-learning
- 15\. DQN and SARSA
- 16\. REINFORCE and policy gradient
- 17\. Actor–critic
- 18\. Real-world applications
- 19\. Mind map and summary
- 20\. Case studies
- 21\. Mixed practice
- 22\. End-of-module test
- 23\. Learning material list
- 24\. Master glossary
- 25\. References and revision notes

Learning path: Overview → Notation box → 18 topics in an order where no term is used before it is taught → mind map → case studies → mixed practice → test → learning materials → glossary.

# Module Overview and Learning Outcomes

This module develops a beginner’s understanding of Behavioural AI in the reinforcement-learning sense: AI that learns what to do by interacting with an environment and receiving reward feedback. It moves from the definition and the agent–environment loop, through Markov Decision Processes and the Bellman equation, through dynamic programming and the two classical iteration algorithms, into the on-/off-policy distinction, and then into the model-free families (Q-learning, SARSA, DQN, REINFORCE, actor–critic). It closes with real-world applications, a mind map, case studies and a test.

| \#  | Outcome: by the end of this module you can…                                                                                                                         | Assessed in                              |
|-----|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------|
| LO1 | Explain what Behavioural AI is and distinguish it from supervised and unsupervised learning.                                                                        | S1; Activity 1.1; Q1.1                   |
| LO2 | Describe the agent–environment loop and identify its five components, using correct notation (S<sub>t</sub>, A<sub>t</sub>, R<sub>t+1</sub>, S<sub>t+1</sub>).      | S2; Activity 2.1                         |
| LO3 | Write down a small Markov Decision Process (states, actions, rewards, transition probabilities) and explain the Markov property.                                    | S4–5; Activities 4.1, 5.2                |
| LO4 | State the Bellman equation in expectation and optimality forms and compute a one-step update by hand.                                                               | S7; Activity 7.1                         |
| LO5 | Distinguish model-based from model-free learning; trace policy evaluation, value iteration and policy iteration on a small grid.                                    | S6, S8–11; Activities 8.1, 10.1, 11.1    |
| LO6 | Describe the three model-free families in terms of what each stores, updates and learns from; explain on-/off-policy learning and predict the cliff-walk behaviour. | S12–17; Activities 12.1, 15.1            |
| LO7 | Design a reward function for an application and critique it, naming an unintended behaviour and an ethical consequence.                                             | S18; Activities 18.1, 18.2; case studies |

**Traceability.** Every outcome has at least one worked example (a skill demonstrated), one activity (a skill performed, with an answer) and one check question (a quick confirmation). The end-of-module test samples all seven.

**Prerequisites.** Basic arithmetic and the idea of an average. No programming and no prior machine-learning knowledge are needed.

## How to study this module

> **Important: read the explanation before the equation**
>
> Do not look at an equation first. Read the plain-English explanation that follows it, then come back to the symbols. Every symbol is defined in the notation box on the next page.

| Week | Sections | Focus                                           | Do this                                             |
|------|----------|-------------------------------------------------|-----------------------------------------------------|
| 1    | 1–3      | What RL is; the loop; exploration               | Do Activities 1.1–3.1; explain the loop to a friend |
| 2    | 4–6      | MDPs; policy and value; models                  | Write an MDP for a board game you know              |
| 3    | 7–9      | Bellman; policy evaluation and improvement      | Redo the 2×2 tables by hand without looking         |
| 4    | 10–12    | Value and policy iteration; on/off-policy       | Do the corridor exercise; classify four algorithms  |
| 5    | 13–17    | Q-learning, SARSA, DQN, REINFORCE, actor–critic | Trace one update of each by hand                    |
| 6    | 18–22    | Applications, case studies, test                | Take the test closed-book, then mark it             |

> **Learning suggestions**
>
> \(1\) Keep one 2×2 grid sketch on paper and re-use it for every section. (2) Always compute before you read the answer. (3) Teach each section to someone in two minutes: if you cannot, re-read it. (4) Reproduce the algorithm table in Section 13.2 from memory. (5) After Section 15, run a small Q-learning example in Gymnasium (see the learning material list) and watch the values change. (6) Keep a running list of every symbol you forget; the list is your personal glossary.

# Reading the Notation — Read This First

Every symbol is defined here once. You do not need to memorise this box; flip back whenever you need it.

| Symbol                                        | Meaning                                                                                                                    |
|-----------------------------------------------|----------------------------------------------------------------------------------------------------------------------------|
| S<sub>t</sub>, A<sub>t</sub>, R<sub>t+1</sub> | The state, action and reward at time step t. Subscript t means “at this step”; t+1 means “the next step”.                  |
| Σ (sigma)                                     | Sum over all values. Σ<sub>a</sub> sums over all actions; Σ<sub>s′</sub> over all next states.                             |
| π(a \| s)                                     | Probability of choosing action a in state s. The bar “\|” means “given”.                                                   |
| P(s′ \| s, a)                                 | Probability of landing in state s′ after taking action a in state s.                                                       |
| R(s, a, s′)                                   | The reward for moving from s to s′ by action a.                                                                            |
| G<sub>t</sub> (return)                        | Total discounted reward from step t onward: G<sub>t</sub> = R<sub>t+1</sub> + γR<sub>t+2</sub> + γ²R<sub>t+3</sub> + …     |
| E\[·\]                                        | Expected value: the long-run average if the process were repeated many times.                                              |
| max<sub>a</sub>                               | The largest value over all choices of a.                                                                                   |
| argmax<sub>a</sub>                            | The action a that makes the expression largest (the action, not its value). If Q(Left)=2 and Q(Right)=5, argmax Q = Right. |
| ←                                             | “Update to”: x ← x + 1 means increase x by 1.                                                                              |
| ∇ (nabla)                                     | Gradient: the direction in which a quantity increases fastest.                                                             |
| γ (gamma)                                     | Discount factor: how much future rewards count compared with immediate ones.                                               |
| α (alpha)                                     | Learning rate: how far each update moves the estimate.                                                                     |
| δ (delta)                                     | TD error: the “surprise” (target minus current estimate).                                                                  |
| θ (theta)                                     | Policy parameters: the adjustable numbers that define the policy.                                                          |
| w                                             | Critic parameters: the adjustable numbers that define the value function in actor–critic methods.                          |

# 1. Definition

## 1.1 What Behavioural AI means here

Behavioural AI in this module means AI that learns **what to do** by interacting with an environment and receiving reward feedback. It is not given the correct answer for each situation, and it is not asked to find hidden structure in unlabelled data. It is told, after the fact, how good the outcome was — and it adjusts its behaviour to get more reward.

The name comes from **behaviourism**, the psychology tradition of Pavlov, Thorndike and Skinner. Its core claim is that behaviour is shaped by its consequences: actions followed by reward become more frequent; actions followed by punishment become less frequent. **Reinforcement learning (RL)** is the computational version of that idea.

![Figure 1 — Three families of machine learning. This module is about the third.](figures/behavioural_ai/fig-01.svg)

*Figure 1 — Three families of machine learning. This module is about the third.*

> **Three families of machine learning — one line each**
>
> **Supervised** learning is given labelled examples. **Unsupervised** learning is given unlabelled data and looks for structure. **Reinforcement** learning is given neither labels nor structure — only a reward signal after acting.

## 1.2 Key terms

| Term           | Definition                                                                                 |
|----------------|--------------------------------------------------------------------------------------------|
| Agent          | The learner or decision-maker (a robot, a program, a game character).                      |
| Environment    | Everything outside the agent that it interacts with.                                       |
| State (s)      | A description of the current situation, sufficient to decide what to do next.              |
| Action (a)     | A choice the agent can make.                                                               |
| Reward (r)     | A number the environment gives after an action; higher is better.                          |
| Policy (π)     | The agent’s rule for choosing actions in each state.                                       |
| Value function | A prediction of how much total future reward to expect (formal definition in Section 5.4). |
| Episode        | A run of interaction from a start state to a terminal state (e.g. one game).               |

> **Check Q1.1. A chess program is given millions of positions with the “correct” move. Is that behavioural AI?**
>
> **Answer.** No — that is supervised learning. A behavioural-AI chess program would play games and receive only win/loss/draw as feedback, then work out which moves contributed to the outcome.

> **Activity 1.1 — Identify the components**
>
> A robot vacuum learns to clean a room. It can move forward, turn left, turn right or stop. It receives +1 when it covers a dirty patch, −5 when it bumps into furniture and 0 otherwise. Identify the agent, environment, actions, rewards and one possible state.

> **Answer**
>
> Agent = the vacuum’s control program. Environment = the room, furniture, dirt. Actions = forward, left, right, stop. Rewards = +1, −5, 0. One possible state = “current position, heading and dirt-sensor reading”.

# 2. Basic Process and Example

## 2.1 The agent–environment loop

Every RL system follows the same five-step cycle. Read the subscripts using the notation box.

![Figure 2 — The agent–environment loop.](figures/behavioural_ai/fig-02.svg)

*Figure 2 — The agent–environment loop.*

1.  **Observe** — the agent receives the current state S<sub>t</sub>.
2.  **Act** — it selects an action A<sub>t</sub> according to its current policy.
3.  **Transition** — the environment moves to a new state S<sub>t+1</sub>.
4.  **Reward** — the environment emits a reward R<sub>t+1</sub>.
5.  **Learn** — the agent updates its policy or value estimates from the experience.

## 2.2 Worked example: the 2×2 grid world

We use this tiny environment throughout the module so every later concept can be checked against the same picture.

![Figure 3 — The 2×2 grid world. The goal (1,1) is terminal.](figures/behavioural_ai/fig-03.svg)

*Figure 3 — The 2×2 grid world. The goal (1,1) is terminal.*

| Component      | Definition in this world                                                 |
|----------------|--------------------------------------------------------------------------|
| States         | Four cells: (0,0), (1,0), (0,1), (1,1).                                  |
| Actions        | Right (x+1) and Up (y+1). A move off the grid leaves the agent in place. |
| Rewards        | +1 on entering (1,1); 0 otherwise.                                       |
| Terminal state | (1,1): the episode ends on arrival.                                      |
| Discount       | γ = 0.9.                                                                 |

> **Worked example — one episode**
>
> Start (0,0). Action Right → state (1,0), reward 0. Action Up → state (1,1), reward +1. Episode ends. The transition tuple (S<sub>t</sub>, A<sub>t</sub>, R<sub>t+1</sub>, S<sub>t+1</sub>) for each step: Step 1: ((0,0), Right, 0, (1,0)). Step 2: ((1,0), Up, +1, (1,1)).

> **Check Q2.1. The agent is at (1,0) and chooses Up. What is the next state and reward?**
>
> **Answer.** Next state (1,1); reward +1; the episode ends.

> **Activity 2.1 — Trace an episode**
>
> Starting at (0,0), the agent follows Right, Right, Up. (a) List the state after each action. (b) List the reward after each action. (c) What is the total undiscounted reward?

> **Answer**
>
> \(a\) Start (0,0) → Right → (1,0) → Right → (1,0) (blocked, stays) → Up → (1,1). (b) Rewards 0, 0, +1. (c) Total = 1. The second Right was wasted — exactly why learning is needed.

# 3. Reinforcement Learning

## 3.1 What makes RL different

1.  **Trial and error.** The agent is not told the correct action; it must try actions and observe consequences.
2.  **Delayed reward.** The reward for a good action may arrive many steps later. The agent must solve the **credit assignment problem**: which earlier actions deserve credit for the final outcome?
3.  **The environment responds to the agent.** The agent’s choices change future states, so the data it collects depends on its own behaviour.

> **Common misconception**
>
> “RL is supervised learning with rewards as labels.” No. A supervised label tells you the correct output for this input. A reward tells you how good the outcome was, not which action was correct. If a chess agent wins, every move gets some credit, even the bad ones.

## 3.2 Exploration vs exploitation

**Exploitation** means choosing the action currently believed to be best (the highest estimated value). **Exploration** means trying other actions, because one might be better. The standard compromise is **ε-greedy**: with probability ε (e.g. 0.1) choose a random action; otherwise choose the best-known action. ε is often reduced over time so the agent explores early and exploits later.

> **Worked example — a two-slot-machine agent**
>
> Machine A paid out 1 on the first pull, so its estimate is 1. Machine B has never been tried (estimate 0). A purely greedy agent pulls A forever. Suppose B actually pays 5 on average. The greedy agent never finds out. With ε = 0.1, about one pull in ten is random, so B is tried, its estimate rises, and the agent switches.

> **Check Q3.1. Why is pure exploitation dangerous?**
>
> **Answer.** The agent may never discover a better action. If it always takes the first action that looked good, it can get stuck in a mediocre policy forever.

> **Activity 3.1 — Predict the outcome prediction**
>
> A learner sets ε = 0 from the very start. Predict what happens to learning, then propose one fix.

> **Answer**
>
> With ε = 0 the agent never explores. If all value estimates start equal (e.g. zero) it picks one arbitrary action forever; if that action happens to be poor it never finds the good one, so the learned policy depends on tie-breaking and the first reward. Fix: keep ε \> 0 for a period, or use optimistic initialisation (start estimates high so unexplored actions look attractive).

# 4. Markov Decision Process: States, Actions, Rewards

## 4.1 Why a formal framework?

The grid world is easy to describe in words, but to compute values and policies we need a precise mathematical object. The **Markov Decision Process (MDP)** is that object. Every algorithm in this module operates on an MDP (or learns without knowing it).

## 4.2 The components

| Symbol        | Meaning                                   |
|---------------|-------------------------------------------|
| S             | The set of all states.                    |
| A             | The set of all actions.                   |
| P(s′ \| s, a) | Transition probabilities (Section 5.1).   |
| R(s, a, s′)   | The reward for moving from s to s′ via a. |
| γ             | Discount factor (Section 5.3).            |

An MDP is therefore the tuple (S, A, P, R, γ). In the 2×2 grid: S = {(0,0), (1,0), (0,1), (1,1)}; A = {Right, Up}; R = +1 for any transition into (1,1) and 0 otherwise; P is deterministic (every move succeeds, or is blocked at the edge).

## 4.3 The Markov property

The **Markov property** says: the current state contains all the information needed to predict the future. The past adds nothing beyond the present state.

> **Why this matters**
>
> Choosing the state representation is a design decision. In the grid, the coordinate is a perfect state. For a robot with only a forward camera, one image may not satisfy the Markov property because the robot cannot see behind it. If the state is insufficient, learning becomes much harder.

> **Check Q4.1. In a card game, is “the cards in my hand” a sufficient state?**
>
> **Answer.** Not by itself — you also need to know which cards have been played, because that affects what can still be drawn. A sufficient state includes that history or a summary of it.

> **Activity 4.1 — Write down an MDP**
>
> A 1×3 corridor has cells 1, 2, 3. Cell 3 is the goal (+1, terminal). Actions: Left, Right. Moving into a wall leaves you in place (reward 0). (a) State set. (b) Action set. (c) Two transition probabilities: one successful move, one blocked move. (d) Reward for moving from cell 2 to cell 3 via Right.

> **Answer**
>
> \(a\) S = {1, 2, 3}. (b) A = {Left, Right}. (c) P(2 \| 1, Right) = 1 (successful); P(1 \| 1, Left) = 1 (blocked, stays). (d) R(2, Right, 3) = +1.

# 5. Markov Decision Process: Probabilities, Policy, Value Function

## 5.1 Transition probabilities

Real environments are rarely deterministic. A robot’s wheels may slip; a user may click or not. Uncertainty is captured by transition probabilities P(s′ \| s, a): the probability of landing in s′ after action a in state s.

> **Worked example — a slippery grid**
>
> Modify the grid so Right succeeds with probability 0.8, and with probability 0.2 the agent slips and stays in place. Then P((1,0) \| (0,0), Right) = 0.8 and P((0,0) \| (0,0), Right) = 0.2. The probabilities for one (state, action) pair always sum to 1.

## 5.2 Policy

A policy π(a \| s) is a probability distribution over actions given a state. A **deterministic** policy always picks the same action in a state; a **stochastic** policy assigns probabilities. An **optimal policy** π\* maximises expected return from every state.

## 5.3 Discount factor γ

The discount factor γ ∈ \[0, 1) makes future rewards worth less than immediate ones, for three reasons: **uncertainty** (a far-off reward is less certain), **mathematical convenience** (with γ \< 1 the infinite sum of rewards is finite) and **preference for sooner** (reaching the goal sooner is often genuinely better). With γ = 0.9, +1 received two steps in the future is worth 0.9² = 0.81 now.

## 5.4 Return and value functions

The **return** G<sub>t</sub> is the total discounted reward from time t onward:

> G<sub>t</sub> = R<sub>t+1</sub> + γR<sub>t+2</sub> + γ²R<sub>t+3</sub> + …

A **value function** is the expected return. Because the future is uncertain, we take an average:

> State value: V<sub>π</sub>(s) = E<sub>π</sub>\[ G<sub>t</sub> \| S<sub>t</sub> = s \]

> Action value: Q<sub>π</sub>(s, a) = E<sub>π</sub>\[ G<sub>t</sub> \| S<sub>t</sub> = s, A<sub>t</sub> = a \]

**Symbols.** E<sub>π</sub> = expected value when following π; G<sub>t</sub> as defined above. **Plain English.** V(s) is the average total discounted reward the agent expects starting from s under π. Q(s, a) is the average total discounted reward from taking a in s and then following π.

> **Worked example — computing a value by hand**
>
> In the deterministic 2×2 grid, policy: “in (0,0) go Right; in (1,0) go Up.” Path (0,0) → (1,0) → (1,1) with rewards 0 then +1. So V<sub>π</sub>((0,0)) = 0 + 0.9 × 1 = **0.9**. Also V<sub>π</sub>((1,0)) = 1 (the next move earns +1 immediately) and V<sub>π</sub>((1,1)) = 0 (terminal: nothing more is collected).
>
> **Teaching note:** the reward for entering the goal is counted in the value of the *previous* state, not the goal state. This is the most common beginner trap in this module.

> **Check Q5.1. Under a policy that goes Right from (0,1), what is V π ((0,1))?**
>
> **Answer.** Right enters (1,1) and earns +1, so V = 1 + 0.9 × 0 = 1.

> **Activity 5.1 — Change the discount**
>
> With the policy from the worked example, what is V<sub>π</sub>((0,0)) if γ = 0.5? Explain the change in one sentence.

> **Answer**
>
> V<sub>π</sub>((0,0)) = 0 + 0.5 × 1 = 0.5. The reward is one step in the future, so a smaller γ shrinks its present value more.

> **Activity 5.2 — Find the error find the error**
>
> A student defines an MDP for a card game. The state is “the cards in the player’s hand.” A second student says: “This violates the Markov property.” Find the error and fix the state definition.

> **Answer**
>
> The state is insufficient: the hand does not include which cards were played, the discard pile or the opponent’s visible cards. Two situations with identical hands but different histories need different optimal actions. Fix: extend the state to include played cards, the discard pile and the opponent’s visible information.

# 6. Model-Based vs Model-Free

## 6.1 The distinction

A **model** is the agent’s estimate of how the environment behaves: “if I am in state s and take action a, I will probably end up in s′ and get reward r.” Formally, it is the pair P(s′ \| s, a) and R(s, a, s′) from Sections 4.2 and 5.1.

![Figure 4 — Model-based versus model-free learning.](figures/behavioural_ai/fig-04.svg)

*Figure 4 — Model-based versus model-free learning.*

**Model-based** learning: the agent learns (or is given) this model, then uses it to plan by simulating ahead. **Model-free** learning: the agent learns values or a policy directly, without an explicit model.

## 6.2 An analogy

A model-based learner is like someone who builds a mental *map* of a new city: “this street connects to that one.” Once the map is good, new routes can be planned without walking them. A model-free learner learns by repetition: “when I leave home and turn left, I get to work.” No map, but the habit works — until a road closes, and then it must discover the detour by trial.

> **Check Q6.1. A robot vacuum has a stored floor plan and computes a route from it. Model-based or model-free?**
>
> **Answer.** Model-based. The floor plan is an explicit model and the route is planned over it.

> **Activity 6.1 — Compare approaches comparison**
>
> Robot A works in a fixed warehouse with a stored, accurate floor plan. Robot B works in a new building every week with no map. For each, decide model-based or model-free and justify in one sentence each.

> **Answer**
>
> Robot A: model-based; the model is already available, so planning over it is efficient. Robot B: model-free; no model exists and learning one from scratch every week is expensive, so it learns values or a policy from experience. The deciding question is whether a reliable model exists.

# 7. Bellman Equation

## 7.1 The idea in one sentence

> **Bellman, in words**
>
> The value of where you are now equals the reward you get for the next step plus the discounted value of where you land. Everything else is notation.

## 7.2 The expectation form (fixed policy)

> V<sub>π</sub>(s) = Σ<sub>a</sub> π(a \| s) Σ<sub>s′</sub> P(s′ \| s, a) \[ R(s, a, s′) + γ V<sub>π</sub>(s′) \]

Read it left to right. The value of s under π = the average over actions the policy might take (weighted by π(a \| s)) of the average over next states (weighted by P) of \[immediate reward + discounted value of the next state\]. For a terminal state, V = 0.

## 7.3 The optimality form

> V\*(s) = max<sub>a</sub> Σ<sub>s′</sub> P(s′ \| s, a) \[ R(s, a, s′) + γ V\*(s′) \]

The only change: max<sub>a</sub> instead of averaging over actions. The agent picks the best action rather than following a fixed policy. The same idea for action values is Q\*(s, a) = Σ<sub>s′</sub> P(s′ \| s, a)\[ R + γ max<sub>a′</sub> Q\*(s′, a′) \], which Q-learning (Section 14) approximates from samples.

## 7.4 Worked example

> **One Bellman update**
>
> In the 2×2 grid suppose V\*((1,0)) = 1 and V\*((0,1)) = 1. What is V\*((0,0))? Right gives Q = 0 + 0.9 × 1 = 0.9. Up gives Q = 0 + 0.9 × 1 = 0.9. So V\*((0,0)) = max(0.9, 0.9) = **0.9**. Both actions are optimal: optimal policies need not be unique.

## 7.5 Why it is powerful

The Bellman equation turns an infinite-horizon problem (“maximise reward over all future steps”) into a recursive one-step problem (“what is the best immediate action, given the value of the next state?”). Every algorithm in this module is a way of solving or approximating this recursion.

> **Check Q7.1. Suppose V\*((1,0)) = 1 but V\*((0,1)) = 0. What is the optimal action from (0,0) and V\*((0,0))?**
>
> **Answer.** Right gives 0 + 0.9 × 1 = 0.9; Up gives 0 + 0.9 × 0 = 0. Right is optimal and V\*((0,0)) = 0.9.

> **Activity 7.1 — Break the equation find the error**
>
> A classmate writes V(s) = R(s,a,s′) + V(s′). Identify three things wrong or missing compared with the correct Bellman equation.

> **Answer**
>
> \(1\) No average over actions (or no max<sub>a</sub>). (2) No average over next states, weighted by P(s′ \| s, a). (3) No discount factor γ on the future value.

# 8. Dynamic Programming (1): Policy Evaluation

## 8.1 What dynamic programming means here

**Dynamic programming (DP)** solves problems by breaking them into overlapping subproblems and reusing the solutions. In RL, DP computes value functions by iterating the Bellman equation over the whole state space until values stop changing. This requires knowing the model (P and R), so DP is model-based.

## 8.2 The question policy evaluation answers

Given a fixed policy π, what is V<sub>π</sub>? It measures how good the policy is; it does not try to improve it.

## 8.3 The algorithm

Recall that ← means “update to”.

1.  Initialise V(s) = 0 for all states.
2.  Repeat: for each state s, update

> V(s) ← Σ<sub>a</sub> π(a \| s) Σ<sub>s′</sub> P(s′ \| s, a) \[ R(s, a, s′) + γ V(s′) \]

3.  Stop when the largest change across all states is below a small threshold (e.g. 0.001).

In the tables below each sweep uses the *old* values from the previous sweep for the right-hand side (a “synchronous” sweep).

## 8.4 Worked example: sweeps on the 2×2 grid

Policy: “always go Right if possible; otherwise Up.” γ = 0.9. Initialise V = 0.

| Sweep    | V((1,1)) | V((1,0)) | V((0,1)) | V((0,0))        |
|----------|----------|----------|----------|-----------------|
| 0 (init) | 0        | 0        | 0        | 0               |
| 1        | 0        | 1        | 1        | 0               |
| 2        | 0        | 1        | 1        | 0.9             |
| 3        | 0        | 1        | 1        | 0.9 (converged) |

> **How the sweeps were computed**
>
> **Sweep 1.** V((1,0)): the policy takes Up, entering (1,1) with reward +1, so V = 1 + 0.9 × 0 = 1. V((0,1)): the policy takes Right, same result, 1. V((0,0)): the policy takes Right to (1,0) with reward 0, so V = 0 + 0.9 × V<sub>old</sub>((1,0)) = 0.9 × 0 = 0. **Sweep 2.** Only V((0,0)) changes: 0 + 0.9 × 1 = 0.9. Further sweeps change nothing. Note how value travels *backwards* from the goal, one step per sweep.

> **Check Q8.1. Why does V((1,0)) become 1 in sweep 1, not 0?**
>
> **Answer.** The reward for entering the goal is earned on the transition from (1,0) to (1,1). The value of (1,0) includes that +1 immediately; the terminal state (1,1) has value 0.

> **Activity 8.1 — One more sweep**
>
> Starting from the converged values above, suppose γ changes to 0.5. Perform one sweep. What are the new values?

> **Answer**
>
> V((1,1)) = 0; V((1,0)) = 1; V((0,1)) = 1; V((0,0)) = 0 + 0.5 × 1 = 0.5. The goal-adjacent states keep value 1; the start state’s value shrinks because its reward is delayed and discounted more.

> **Activity 8.2 — Find the error find the error**
>
> A student reports sweep-2 values for the 2×2 grid with γ = 0.9, given V<sub>old</sub>((1,0)) = 1: V((1,0)) = 0, V((0,1)) = 1, V((0,0)) = 0.5. Find the error and give the corrected values.

> **Answer**
>
> V((1,0)) = 0 is wrong: the policy takes Up into the goal, so V((1,0)) = 1 + 0.9 × 0 = 1. With that, V((0,0)) = 0 + 0.9 × 1 = 0.9, not 0.5. Corrected: V((1,1)) = 0, V((1,0)) = 1, V((0,1)) = 1, V((0,0)) = 0.9.

# 9. Dynamic Programming (2): Policy Improvement

## 9.1 The idea

Once V<sub>π</sub> is known, ask at each state: if I take action a now and then follow π, is that better or worse than what π would do? If some action looks better, switch to it.

## 9.2 The update rule

> π′(s) = argmax<sub>a</sub> Σ<sub>s′</sub> P(s′ \| s, a) \[ R(s, a, s′) + γ V<sub>π</sub>(s′) \]

**Plain English.** In each state choose the action that maximises one-step reward plus the discounted value of the next state. argmax returns the *action*, not the value.

## 9.3 The policy improvement theorem

The theorem guarantees that the new policy π′ is at least as good as π from every state. It cannot be worse. If it is exactly as good, π was already optimal. This is the mathematical justification for the whole evaluate–improve cycle.

> **Worked example**
>
> Using the converged values from Section 8.4: V((0,0)) = 0.9, V((1,0)) = 1, V((0,1)) = 1, V((1,1)) = 0, γ = 0.9.
>
> At (0,0): Q(Right) = 0 + 0.9 × 1 = 0.9; Q(Up) = 0 + 0.9 × 1 = 0.9. They tie, so the policy is already optimal there. At (1,0): Q(Up) = 1 + 0.9 × 0 = 1; Right is blocked, so the agent stays and Q(Right) = 0 + 0.9 × 1 = 0.9 \< 1. Up is optimal. At (0,1): Q(Right) = 1; Q(Up) (blocked) = 0 + 0.9 × 1 = 0.9. Right is optimal.

> **Check Q9.1. Suppose V((0,1)) were 0.5 instead of 1. Which action would policy improvement choose at (0,0)?**
>
> **Answer.** Right: 0 + 0.9 × 1 = 0.9, versus Up: 0 + 0.9 × 0.5 = 0.45. Right wins.

# 10. Value Iteration

## 10.1 The idea

Policy iteration (Section 11) does two full phases: evaluate a policy completely, then improve it. **Value iteration** merges them: at every state, immediately take the best action (using current value estimates) and update the value. There is no separate evaluation phase.

## 10.2 The update

> V<sub>k+1</sub>(s) ← max<sub>a</sub> Σ<sub>s′</sub> P(s′ \| s, a) \[ R(s, a, s′) + γ V<sub>k</sub>(s′) \]

Each sweep updates every state using the best one-step lookahead. Repeat until the maximum change is below a threshold. Then extract the policy **greedily** from V\*: at each state choose the action with the highest one-step lookahead value.

## 10.3 Worked example: sweeps on the 2×2 grid

γ = 0.9. Initialise all V = 0. The terminal (1,1) stays 0.

| Sweep    | V((1,1)) | V((1,0)) | V((0,1)) | V((0,0))        |
|----------|----------|----------|----------|-----------------|
| 0 (init) | 0        | 0        | 0        | 0               |
| 1        | 0        | 1        | 1        | 0               |
| 2        | 0        | 1        | 1        | 0.9             |
| 3        | 0        | 1        | 1        | 0.9 (converged) |

**Extract the policy.** At (0,0) both actions give 0.9, so either is optimal. At (1,0) Up is optimal. At (0,1) Right is optimal.

> **Worked example — value iteration on a 1×3 corridor**
>
> Cells 1, 2, 3; cell 3 is the terminal goal (+1 on entering); actions Left/Right; walls leave you in place; γ = 0.9. V(3) = 0 always.
>
> | Sweep | V(1) | V(2) | V(3)          |
> |-------|------|------|---------------|
> | 0     | 0    | 0    | 0             |
> | 1     | 0    | 1    | 0             |
> | 2     | 0.9  | 1    | 0             |
> | 3     | 0.9  | 1    | 0 (converged) |
>
> Sweep 1: V(2) = max(Right: 1 + 0.9×0 = 1, Left: 0 + 0.9×V<sub>old</sub>(1) = 0) = 1; V(1) = max(Right: 0.9×V<sub>old</sub>(2) = 0, Left: 0.9×V<sub>old</sub>(1) = 0) = 0. Sweep 2: V(1) = max(Right: 0.9×1 = 0.9, Left: 0) = 0.9. The greedy policy is Right in cells 1 and 2.

## 10.4 Why it converges

For γ \< 1, the Bellman optimality operator is a **contraction**: a mapping that brings any two points closer together. Repeated application therefore converges to a unique **fixed point**, a value function that no longer changes when the update is applied. This is the mathematical guarantee that value iteration works.

> **Check Q10.1. Why does V((0,0)) stay 0 in sweep 1?**
>
> **Answer.** The update uses the old values of the next states, and V<sub>old</sub>((1,0)) and V<sub>old</sub>((0,1)) were both 0 at the start of sweep 1. Value propagates backward one step per sweep.

> **Activity 10.1 — Change the discount**
>
> Re-run value iteration with γ = 0.5. What is V\*((0,0)) after convergence? Explain in one sentence why it changed.

> **Answer**
>
> V\*((1,0)) = 1, V\*((0,1)) = 1, V\*((0,0)) = 0 + 0.5 × 1 = 0.5. The start state’s value is lower because its reward is one step away and is discounted more heavily when γ is smaller.

> **Activity 10.2 — Compare approaches comparison**
>
> A grid world has 10,000 states. Compare value iteration and policy iteration. Which would you try first, and why?

> **Answer**
>
> Value iteration has many cheap sweeps; policy iteration has fewer outer iterations, each more expensive because evaluation runs to convergence. For a large state space try value iteration first for its lower per-iteration cost; fall back to policy iteration if convergence is slow or a good initial policy is available (then policy iteration finishes in very few iterations).

# 11. Policy Iteration

## 11.1 The algorithm

1.  Initialise a policy π (e.g. always Right).
2.  **Policy evaluation:** compute V<sub>π</sub> by iterating the Bellman expectation equation until convergence.
3.  **Policy improvement:** set π′(s) = argmax<sub>a</sub> Q<sub>π</sub>(s, a) for every state.
4.  If π′ = π, stop. Otherwise set π ← π′ and return to step 2.

![Figure 5 — Two routes to the same optimal policy.](figures/behavioural_ai/fig-05.svg)

*Figure 5 — Two routes to the same optimal policy.*

## 11.2 Value iteration vs policy iteration

|                   | Value iteration                                    | Policy iteration                                            |
|-------------------|----------------------------------------------------|-------------------------------------------------------------|
| What is iterated  | The value function directly                        | The policy, with full evaluation inside each iteration      |
| Policy extraction | After convergence                                  | At every improvement step                                   |
| Typical behaviour | Many cheap sweeps                                  | Fewer outer iterations, each more expensive                 |
| Conceptual focus  | Fixed-point iteration of the optimality operator   | Alternation of evaluation and improvement                   |
| When to prefer    | Large state spaces where full evaluation is costly | A good policy is found quickly and evaluation is affordable |

Both converge to the same optimal policy. The choice is an engineering trade-off, not a correctness issue.

> **Worked example — policy iteration on the 2×2 grid (γ = 0.9)**
>
> **Start:** policy π<sub>0</sub> = “always Right”.
>
> **Evaluate π<sub>0</sub>.** V(1,1) = 0. V(0,1): Right enters the goal, so V = 1. V(1,0): Right is blocked, so the agent stays forever and never earns anything: V = 0 + 0.9×V(1,0), which gives V(1,0) = 0. V(0,0): Right goes to (1,0): V = 0 + 0.9×0 = 0.
>
> **Improve.** At (1,0): Up gives 1 + 0.9×0 = 1 versus Right 0.9×0 = 0, so choose Up. At (0,1): Right gives 1, Up (blocked) gives 0.9×1 = 0.9, keep Right. At (0,0): Right gives 0.9×0 = 0, Up gives 0.9×1 = 0.9, so choose Up. New policy π<sub>1</sub>: (0,0) Up, (1,0) Up, (0,1) Right.
>
> **Evaluate π<sub>1</sub>:** V(1,0) = 1, V(0,1) = 1, V(0,0) = 0.9×1 = 0.9. **Improve:** at (0,0) Right = 0.9 and Up = 0.9 tie; keep Up. No action changes, so π<sub>1</sub> is optimal. Policy iteration stops after two improvement steps.

> **Check Q11.1. Why does policy iteration stop when the policy stops changing, while value iteration stops when value changes become small?**
>
> **Answer.** Policy iteration has an explicit policy to compare, so “no action changed” is a clean stopping condition. Value iteration has no explicit policy during the loop, so it uses the size of value changes as a proxy: small changes imply the greedy policy is (nearly) stable.

> **Activity 11.1 — Policy iteration on the corridor**
>
> On the 1×3 corridor (goal +1 on entering cell 3, γ = 0.9) start with policy “always Left”. Run policy iteration. (Break ties by keeping the current action.)

> **Answer**
>
> Evaluate: V(1) = V(2) = V(3) = 0 (the agent never reaches the goal). Improve: at 2, Right = 1 beats Left = 0, so Right; at 1, Right = 0.9×0 = 0 ties with Left, keep Left. Evaluate (1: Left, 2: Right): V(2) = 1, V(1) = 0.9×V(1) = 0. Improve: at 1, Right = 0.9×1 = 0.9 beats Left = 0, so Right. Evaluate (Right, Right): V(2) = 1, V(1) = 0.9. Improve: no change. Optimal policy: Right in both cells; V = (0.9, 1).

# 12. On-Policy and Off-Policy: The Core Distinction

> **Why this section comes before the algorithms**
>
> The next sections describe algorithms classified as on-policy or off-policy. The two terms are defined here so that they are already taught when the algorithms use them.

## 12.1 The definitions

Every RL agent has two policies. The **behaviour policy** is the policy the agent actually uses to select actions during learning (e.g. ε-greedy, which sometimes picks a random action). The **target policy** is the policy the agent is trying to learn or improve. They may be the same or different.

- **On-policy:** behaviour and target policy are the same. The update uses the action actually taken next (a′). Examples: SARSA, REINFORCE.
- **Off-policy:** behaviour and target policy differ. The update uses the best possible next action (max<sub>a′</sub>). Examples: Q-learning, DQN.

## 12.2 Comparison table

|                         | On-policy                                                                          | Off-policy                                                  |
|-------------------------|------------------------------------------------------------------------------------|-------------------------------------------------------------|
| Behaviour policy        | Same as target policy                                                              | Different from target policy                                |
| Update target           | Uses the actual next action a′                                                     | Uses the best next action max<sub>a′</sub>                  |
| Examples                | SARSA, REINFORCE                                                                   | Q-learning, DQN                                             |
| Data reuse              | Each update must be based on the current policy’s actions                          | Can learn from old or exploratory data                      |
| Behavioural consequence | Learns the value of the policy it actually follows, including exploratory mistakes | Learns the optimal policy even while exploring suboptimally |

## 12.3 A beginner-friendly summary

On-policy learning is like learning the value of the strategy you are actually playing. Off-policy learning is like learning the value of the *best* strategy even while you experiment with worse ones. Neither is universally better: off-policy is more data-efficient and can learn from old experience; on-policy is often more stable and naturally accounts for the exploration the agent will really do.

> **Check Q12.1. A robot uses ε-greedy exploration and Q-learning. Is the policy it follows the same as the policy it is learning?**
>
> **Answer.** No. It follows an ε-greedy behaviour policy (sometimes random) but learns the greedy optimal policy via the max in the update. This is off-policy learning.

> **Activity 12.1 — Classify the algorithm**
>
> For each algorithm state whether it is on-policy or off-policy and give the update target in one line: (a) SARSA, (b) Q-learning, (c) REINFORCE, (d) DQN.

> **Answer**
>
> \(a\) On-policy; target = r + γQ(s′, a′) with the action actually taken. (b) Off-policy; target = r + γ max<sub>a′</sub> Q(s′, a′). (c) On-policy; target = the return G<sub>t</sub> from the episode, using the actions actually taken. (d) Off-policy; target = r + γ max<sub>a′</sub> Q(s′, a′; θ<sup>−</sup>) using the target network.

# 13. Reinforcement Learning Algorithms: Overview

> **This section is a map, not a lesson**
>
> The three families below are explained in Sections 14–17. Reading this section first gives you the landscape; do not expect to understand the algorithms yet.

## 13.1 From model-based to model-free

Everything up to Section 11 assumed the model (P and R) was known. From here on the agent learns from **sampled experience** and does not know P or R in advance. Model-free RL splits into three families.

![Figure 6 — The three model-free families and example algorithms.](figures/behavioural_ai/fig-06.svg)

*Figure 6 — The three model-free families and example algorithms.*

## 13.2 What each family stores, updates and learns from

| Family       | Stores                                      | Updates             | Learning signal                         |
|--------------|---------------------------------------------|---------------------|-----------------------------------------|
| Value-based  | A table or network of values V(s) or Q(s,a) | The values          | TD error (target − current estimate)    |
| Policy-based | The policy parameters θ                     | The policy directly | Return G<sub>t</sub> (or advantage)     |
| Actor–critic | Policy parameters θ and a value function    | Both, together      | Advantage estimate (often the TD error) |

> **Check Q13.1. Which family would you choose for a continuous action space (e.g. a steering angle), and why?**
>
> **Answer.** Policy-based or actor–critic. Value-based methods need a max over actions, which is awkward in continuous spaces; a policy can output a continuous action directly.

# 14. Value Based: Q-Learning

## 14.1 The idea

Q-learning learns the optimal action-value function Q\*(s, a) directly from sampled transitions (s, a, r, s′). Once Q\* is known the optimal policy is simple: in each state pick the action with the highest Q-value. It needs no model and learns from experience as it happens.

## 14.2 The update rule

> Q(s, a) ← Q(s, a) + α \[ r + γ max<sub>a′</sub> Q(s′, a′) − Q(s, a) \]

**Symbols.** α = learning rate (e.g. 0.1); r = reward just received; s′ = next state; max<sub>a′</sub> Q(s′, a′) = value of the best action in the next state. **Read it as:** *old estimate* Q(s, a); *target* r + γ max Q(s′, a′) (reward plus discounted best next value); *TD error* (temporal-difference error) = target − old estimate, the “surprise”; *update*: move the old estimate a fraction α of the way toward the target. For a terminal next state, max Q(s′, ·) = 0.

> **Worked example — one Q-learning update**
>
> Q(s, a) = 0.2, r = 1, γ = 0.9, max Q(s′, a′) = 0 (terminal next state), α = 0.5. Target = 1 + 0.9 × 0 = 1. TD error = 1 − 0.2 = 0.8. New Q = 0.2 + 0.5 × 0.8 = **0.6**.

## 14.3 Exploration with ε-greedy

If the agent always picks the highest Q-value it may never discover a better action. With ε-greedy it picks a random action with probability ε, otherwise the greedy action; ε is usually reduced over time.

## 14.4 Q-learning is off-policy

The update target r + γ max<sub>a′</sub> Q(s′, a′) is the value of the best possible next action. Q-learning learns the optimal policy even while following an exploratory behaviour policy: that is the off-policy distinction of Section 12.

> **Common misconception**
>
> “Q-learning always follows the greedy action.” No. It *learns about* the optimal policy, but the agent *behaves* using an exploratory policy such as ε-greedy. The separation of behaviour and target policy is the essence of off-policy learning.

> **Check Q14.1. Why is Q-learning called “off-policy”?**
>
> **Answer.** Its target uses max<sub>a′</sub> Q(s′, a′), the best possible next action, regardless of what the agent will actually do next. It learns the optimal policy while behaving exploratorily.

> **Activity 14.1 — Trace a Q-learning update**
>
> With Q(s, a) = 1.5, r = 0, γ = 0.9, max Q(s′, a′) = 2 and α = 0.1, compute the TD error and the new Q value.

> **Answer**
>
> Target = 0 + 0.9 × 2 = 1.8. TD error = 1.8 − 1.5 = 0.3. New Q = 1.5 + 0.1 × 0.3 = 1.53.

> **Activity 14.2 — Explain a decision explain a decision**
>
> An engineer building a robot vacuum wants to learn from historical data collected by other vacuums in the building. She chooses Q-learning over SARSA. Explain her decision.

> **Answer**
>
> Q-learning is off-policy, so it can learn from data collected under a different behaviour policy (the other vacuums’). SARSA is on-policy: its updates assume the learner’s own actions and cannot reuse old-policy data without correction. Since she wants to reuse existing data, Q-learning is right.

# 15. Value Based: Deep Q-Network and SARSA

## 15.1 SARSA

SARSA updates using the action the agent actually takes next, not the best possible action:

> Q(s, a) ← Q(s, a) + α \[ r + γ Q(s′, a′) − Q(s, a) \]

The name comes from the quintuple (s, a, r, s′, a′). Because the update uses the action actually taken, SARSA is **on-policy**.

> **Worked contrast — Q-learning vs SARSA**
>
> In the 2×2 grid the agent is at (0,0) and takes Up to (0,1), reward 0. Q((0,0), Up) = 0.5, α = 0.1, γ = 0.9. In (0,1): Q(Right) = 1 and Q(Up) = 0 (Up is blocked there). The exploring behaviour policy chooses **Up** this time.
>
> Q-learning target: 0 + 0.9 × max(1, 0) = 0.9, so new Q = 0.5 + 0.1 × (0.9 − 0.5) = **0.54**. SARSA target: 0 + 0.9 × Q((0,1), Up) = 0, so new Q = 0.5 + 0.1 × (0 − 0.5) = **0.45**. Q-learning is optimistic: it updates as if the agent will act optimally next. SARSA is realistic: it updates from what the agent actually did, including exploratory mistakes.

## 15.2 The cliff-walk intuition

![Figure 7 — The cliff-walk. Falling into the cliff costs a large penalty and returns the agent to the start.](figures/behavioural_ai/fig-07.svg)

*Figure 7 — The cliff-walk. Falling into the cliff costs a large penalty and returns the agent to the start.*

A grid has a cliff along the bottom. The shortest path hugs the cliff; the safe path is further away. **Q-learning** learns the cliff-edge path, because its target assumes optimal future actions; this is optimal if exploration stops at deployment. **SARSA** learns the safer path, because its target accounts for the exploratory actions the agent really takes, including the occasional fall.

## 15.3 Deep Q-Network (DQN)

A Q-table is impossible when states are images with millions of pixels. DQN replaces the table with a **neural network**: a model made of layers of simple units connected by adjustable weights. It takes a state as input and outputs one Q-value per action, and is trained to minimise the squared TD error. Two stabilising innovations are standard:

- **Experience replay:** store transitions in a buffer and sample random **minibatches** (small random samples). This breaks the correlation between consecutive samples.
- **Target network:** use a separate, slowly updated copy of the network to compute the TD target, so the target does not move every time the main network updates.

> **Check Q15.1. In the cliff-walk, which algorithm would a safety engineer prefer if the robot keeps exploring during deployment?**
>
> **Answer.** SARSA. Its on-policy updates account for the exploratory actions the robot really takes, so it learns a policy that is safe given continued exploration. Q-learning’s cliff-edge path is only optimal if exploration stops.

> **Activity 15.1 — DQN vs Q-table**
>
> Why can a DQN be used where a Q-table cannot? Give one example domain.

> **Answer**
>
> A Q-table needs one entry per state–action pair, impossible for high-dimensional states such as raw pixels. A DQN generalises across similar states using a neural network. Example: Atari games played from screen pixels.

> **Activity 15.2 — Compare approaches comparison**
>
> A robot’s state is a 512-dimensional continuous sensor reading. Compare a Q-table and a DQN. Which is feasible?

> **Answer**
>
> A Q-table needs an entry per (state, action) pair; with continuous 512-dimensional states there are infinitely many, so it is not feasible. A DQN approximates Q with a neural network and generalises across similar states, so it is the feasible choice, at the cost of being harder to train and debug.

# 16. Policy Based: REINFORCE and Policy Gradient

## 16.1 Why learn the policy directly?

- When the action space is continuous (e.g. a steering angle), taking a max over actions is awkward.
- When the best policy is stochastic (e.g. games with mixed strategies).
- When small changes in values should produce small changes in behaviour (smooth policies).

## 16.2 The core idea

Parameterise the policy π<sub>θ</sub>(a \| s) by parameters θ (e.g. the weights of a neural network) and adjust θ so that actions that led to high return become more likely. The **policy gradient** has the form

> ∇<sub>θ</sub>J(θ) = E\[ G<sub>t</sub> ∇<sub>θ</sub> ln π<sub>θ</sub>(A<sub>t</sub> \| S<sub>t</sub>) \]

**Symbols.** ∇<sub>θ</sub> = gradient with respect to θ, the direction in which the quantity increases fastest; J(θ) = expected return; G<sub>t</sub> = the return from step t (Section 5.4); ln = the natural logarithm (the computer evaluates it; you need not by hand); E\[·\] = expected value. (Some textbooks also include a factor γ<sup>t</sup>; practical implementations usually drop it.) **Plain English.** ∇ ln π points in the direction that makes the taken action more likely; multiplying by G<sub>t</sub> scales the push by how good the outcome was.

## 16.3 REINFORCE

REINFORCE is the simplest policy-gradient algorithm and a **Monte-Carlo method**: it learns from complete episodes rather than step by step. It runs an episode, computes the return G<sub>t</sub> for each step, and updates

> θ ← θ + α G<sub>t</sub> ∇<sub>θ</sub> ln π<sub>θ</sub>(A<sub>t</sub> \| S<sub>t</sub>) for each step t

> **Worked example — computing returns**
>
> An episode has three actions a<sub>0</sub>, a<sub>1</sub>, a<sub>2</sub> with rewards r<sub>1</sub> = 0, r<sub>2</sub> = 0, r<sub>3</sub> = 1 and γ = 0.9. G<sub>2</sub> = r<sub>3</sub> = 1. G<sub>1</sub> = r<sub>2</sub> + γr<sub>3</sub> = 0.9. G<sub>0</sub> = r<sub>1</sub> + γr<sub>2</sub> + γ²r<sub>3</sub> = 0.81. All three actions are reinforced, but later actions (closer to the reward) more strongly. REINFORCE assigns credit to every action in the episode, including bad ones.

## 16.4 The variance problem

REINFORCE is **unbiased** (correct on average across many episodes) but has **high variance** (the estimate fluctuates a lot from episode to episode), which makes learning noisy. Two standard remedies: **baseline subtraction**, replacing G<sub>t</sub> by G<sub>t</sub> − b(s) where b(s) is often an estimate of V(s). This does not change the expected gradient but reduces variance; G<sub>t</sub> − b(s) estimates the *advantage*. And **actor–critic**, which uses a learned value function as the baseline (next section).

> **Check Q16.1. In the worked example, why does a 0 get less credit than a 2 ?**
>
> **Answer.** The reward is further in the future from a<sub>0</sub>, so it is discounted more heavily. a<sub>2</sub> comes immediately before the reward and gets full credit.

> **Activity 16.1 — Compute a return**
>
> Rewards (r<sub>1</sub>…r<sub>4</sub>) are 0, 2, 0, 1 and γ = 0.5. Compute G<sub>0</sub>, G<sub>1</sub>, G<sub>2</sub>, G<sub>3</sub>.

> **Answer**
>
> Work backwards: G<sub>3</sub> = 1. G<sub>2</sub> = 0 + 0.5 × 1 = 0.5. G<sub>1</sub> = 2 + 0.5 × 0.5 = 2.25. G<sub>0</sub> = 0 + 0.5 × 2.25 = 1.125.

> **Activity 16.2 — Predict the outcome prediction**
>
> A learner uses a constant baseline b(s) = 100 when typical returns are 0–10. Predict what happens to learning.

> **Answer**
>
> The expected gradient is unchanged (the average of ∇ ln π over actions is zero, so a constant baseline adds no bias). But G<sub>t</sub> − 100 is about −90 to −100 for every action, so every update is large and pushes down whatever was taken; with a fixed learning rate this makes learning noisy and unstable. Fix: learn the baseline alongside the policy so it tracks typical returns.

# 17. Actor–Critic Algorithms

## 17.1 The idea

Actor–critic combines policy-based and value-based learning. Two components learn together: the **actor**, the policy π<sub>θ</sub>(a \| s) updated by policy gradients; and the **critic**, a value function V<sub>w</sub>(s) that evaluates the actor’s choices and provides a lower-variance signal.

![Figure 8 — The actor–critic loop: the critic’s TD error tells the actor how good its action was.](figures/behavioural_ai/fig-08.svg)

*Figure 8 — The actor–critic loop: the critic’s TD error tells the actor how good its action was.*

## 17.2 The advantage function

> A<sub>π</sub>(s, a) = Q<sub>π</sub>(s, a) − V<sub>π</sub>(s)

It measures how much better action a is than the average action under the policy in state s. Positive means “better than usual”; negative “worse than usual”. A practical estimate is the TD error:

> δ = r + γ V<sub>w</sub>(s′) − V<sub>w</sub>(s)

If δ \> 0 the outcome was better than the critic expected, so the actor increases the probability of that action; if δ \< 0 it decreases it. The two updates are

> Actor: θ ← θ + α δ ∇<sub>θ</sub> ln π<sub>θ</sub>(a \| s) Critic: w ← w + β δ ∇<sub>w</sub> V<sub>w</sub>(s)

where β is the critic’s learning rate.

> **Worked example — one actor–critic update**
>
> V<sub>w</sub>(s) = 0.5, reward r = 1, V<sub>w</sub>(s′) = 0.4, γ = 0.9. δ = 1 + 0.9 × 0.4 − 0.5 = 1 + 0.36 − 0.5 = **0.86**. δ is positive, so the actor increases the probability of that action in s. The critic moves V<sub>w</sub>(s) toward the target r + γV<sub>w</sub>(s′) = 1.36, reducing future error.

## 17.3 Why this helps

The critic gives the actor a **dense** learning signal (every step produces a TD error) whereas REINFORCE learns only at the end of an episode. This reduces variance and speeds learning. Modern algorithms such as A2C and PPO are actor–critic methods.

> **Check Q17.1. If δ = −0.3, what should the actor do to the probability of the taken action? Why?**
>
> **Answer.** Decrease it. A negative TD error means the outcome was worse than the critic expected, so the action was worse than average.

> **Activity 17.1 — Compute a TD error**
>
> V(s) = 2.0, r = 1, V(s′) = 1.5, γ = 0.9. Compute δ. Should the actor increase or decrease the action’s probability?

> **Answer**
>
> δ = 1 + 0.9 × 1.5 − 2.0 = 1 + 1.35 − 2.0 = 0.35. Positive, so increase the probability.

> **Activity 17.2 — Explain a decision explain a decision**
>
> In your own words, explain why actor–critic typically learns faster than REINFORCE. Do not use the word “variance” without explaining it.

> **Answer**
>
> REINFORCE learns only at the end of an episode: it collects a return and then updates. Actor–critic learns at every step: the critic produces a TD error each step telling the actor “this action was better or worse than expected right now”. So the actor makes many more updates from the same experience. “Variance” here means how much a single return fluctuates from episode to episode; REINFORCE’s per-episode return fluctuates a lot, so its updates are noisy, whereas a one-step TD error fluctuates less.

# 18. Examples of Applications in the Real World

For each application, identify **what is learned** and **what reward is optimised**: that is the behavioural core of the system.

| Domain                      | Example                                                                                                    | What is learned                                            | Reward optimised                                       |
|-----------------------------|------------------------------------------------------------------------------------------------------------|------------------------------------------------------------|--------------------------------------------------------|
| Recommender systems         | A content platform ranks items; the ranking policy is adjusted from user feedback                          | A ranking policy                                           | Engagement signals (clicks, watch time)                |
| Robotics                    | A robot arm learns to pour, assemble or manipulate, trained in simulation and transferred to hardware      | A control policy mapping sensor readings to motor commands | Task success, with penalties for dropping or colliding |
| Healthcare / rehabilitation | A prosthesis controller adapts to an individual patient; a rehabilitation robot adapts exercise difficulty | A personalisation policy                                   | Clinical outcome measures                              |
| Game playing                | Agents learn Atari, Go or chess from pixels or board states                                                | A policy and/or value function                             | Game score or win/loss                                 |
| Energy management           | A building’s heating/cooling controller learns when to pre-heat or pre-cool                                | A control policy                                           | Energy cost minus comfort penalty                      |
| Traffic signal control      | Intersection signals learn timing that reduces waiting                                                     | A signalling policy                                        | Negative average vehicle delay                         |

> **The ethical point, stated plainly**
>
> Every system above shapes behaviour by optimising a reward. A recommender optimised for clicks reinforces whatever increases clicks; a robot optimised for speed may learn unsafe shortcuts; a prosthesis optimised for one gait metric may produce a gait that is efficient by that metric but uncomfortable for the patient. The reward function is a design choice with ethical consequences. Leave this section able to ask: **“What is the reward, who chose it, and whose behaviour does it shape?”**

> **Check Q18.1. For the energy-management example, why is a comfort penalty needed in the reward?**
>
> **Answer.** Without it the agent learns to minimise energy by switching heating and cooling off entirely: optimal for the stated reward but unacceptable for occupants. The penalty encodes the real trade-off.

> **Activity 18.1 — Design a reward, predict the behaviour**
>
> A delivery drone is trained with RL. Propose a reward function, predict one behaviour it will learn, then identify one behaviour you did not intend.

> **Answer**
>
> Reward: +10 for on-time delivery, −20 for a crash, −1 per minute late, −0.1 per unit of energy. Intended: efficient, punctual routes. Unintended: it may fly aggressively fast or cut close to obstacles to save time, because near-misses are not penalised. Fix: add a proximity penalty and test in simulation before deployment.

> **Activity 18.2 — Find the error find the error**
>
> A cleaning robot is trained with: +10 for cleaning a dirty patch, −5 for bumping furniture, +1 per minute of operation. It learns to walk in circles and keep “cleaning” the same patch. Find the flaw and fix it.

> **Answer**
>
> The +1 per minute rewards staying on, and the +10 can be re-triggered if “dirty” is re-detected, so the robot farms the reward instead of cleaning. Fix: remove the per-minute bonus or make it a −1 per minute penalty; flag cleaned patches so they cannot be rewarded twice; add a completion bonus for cleaning all patches. Any term in the reward that can be exploited will be.

# 19. Mind Map and Summary

![Figure 9 — Mind map of the Behavioural AI module.](figures/behavioural_ai/fig-09.svg)

*Figure 9 — Mind map of the Behavioural AI module.*

| Idea          | One line to remember                                           |
|---------------|----------------------------------------------------------------|
| RL            | Learn from reward by trial and error; no labels                |
| MDP           | (S, A, P, R, γ) plus the Markov property                       |
| Return        | G<sub>t</sub> = R<sub>t+1</sub> + γR<sub>t+2</sub> + …         |
| Value         | V = expected return; Q = expected return after a given action  |
| Bellman       | Value = reward + γ × (value of next state)                     |
| DP            | Needs the model: evaluate, improve, or merge (value iteration) |
| Q-learning    | Off-policy; target uses max                                    |
| SARSA         | On-policy; target uses the action actually taken               |
| REINFORCE     | Policy gradient from complete episodes; high variance          |
| Actor–critic  | Actor picks actions; critic’s TD error trains it               |
| Reward design | The reward is a design choice with ethical consequences        |

# 20. Case Studies

> **Case study 1 — The video recommender**
>
> A streaming service trains an RL recommender whose reward is total watch time. After launch, users watch more hours but report feeling worse and complain of repetitive, extreme content.
>
> **Tasks:** (a) identify agent, environment, action, state and reward; (b) explain what the agent has learned that nobody intended; (c) propose a better reward and one safeguard; (d) say who chose the reward and whose behaviour it shapes.

> **Model answer**
>
> \(a\) Agent = recommendation policy; environment = users and the catalogue; action = which item to show; state = user history and context; reward = watch time. (b) Whatever maximises watch time: autoplay chains, sensational or repetitive content that keeps people watching, whether or not it benefits them. (c) Combine watch time with satisfaction signals (surveys, “not interested” clicks, diversity of content) and cap daily exposure; monitor for harmful drift and test changes on a small group first. (d) The company designed the reward; it shapes the behaviour of every user, so it carries an ethical responsibility.

> **Case study 2 — The cliff-side delivery robot**
>
> A delivery robot crosses a campus with a steep drop beside the shortest path. It is trained in simulation with ε-greedy exploration and keeps exploring (ε = 0.1) after deployment so it can adapt to new routes.
>
> **Tasks:** (a) which of Q-learning and SARSA would you choose, and why; (b) what would the other algorithm learn; (c) name two further safeguards.

> **Model answer**
>
> \(a\) SARSA: on-policy, so it learns the value of the policy it really follows, including the occasional random step, and therefore keeps away from the edge. (b) Q-learning would learn the shortest path along the edge, which is optimal only if exploration stops; with ε = 0.1 it would sometimes step off. (c) Reduce ε in dangerous areas (or explore only in simulation); add a large penalty for edge proximity; add a hardware safety layer (barrier or speed limit) that does not rely on the learning algorithm.

> **Case study 3 — The smart thermostat**
>
> A school wants an RL controller for the heating in one classroom. Every 10 minutes it can set the heater to Off, Low or High. Sensors give the room temperature, the outside temperature, the time and whether the room is occupied.
>
> **Tasks:** (a) write the MDP: states, actions, reward; (b) say whether you would use a model-based or model-free method and why; (c) which family of algorithm would suit a discrete choice of three actions; (d) identify one unintended behaviour of the reward you chose.

> **Model answer**
>
> \(a\) State = (room temperature, outside temperature, time of day, occupied?). Actions = {Off, Low, High}. Reward per step = −(energy used) − (penalty for being outside 19–22°C while occupied). (b) Model-free is simpler if no accurate model of the building exists, but training would be done in a simulator because real exploration is slow and uncomfortable; a model-based method suits it if a good physical model is available. (c) Value-based (e.g. DQN, since the state is continuous) works well with three discrete actions. (d) If the comfort penalty applies only when occupied, the heater may switch off completely and leave the room cold at the start of each day; add a pre-heating term or a penalty for the temperature when people arrive.

# 21. Mixed Practice

Attempt each question before reading the answer.

P1. A policy receives rewards 1, 0, 3 on a three-step episode with γ = 0.5. Compute G<sub>0</sub>.

> **Answer:** G<sub>0</sub> = 1 + 0.5×0 + 0.25×3 = 1.75.

P2. In a state, action A gives reward 0 and next-state value 4; action B gives reward 2 and next-state value 3. With γ = 0.9 which is better and what is V\*(s)?

> **Answer:** A: 0 + 0.9×4 = 3.6. B: 2 + 0.9×3 = 4.7. B is better; V\*(s) = 4.7.

P3. An action succeeds with probability 0.8 (reward 10) and fails with probability 0.2 (reward 0), both leading to a terminal state. Compute its Q-value.

> **Answer:** Q = 0.8×10 + 0.2×0 = 8.

P4. Q(s,a) = 4, r = 2, γ = 0.9, max Q(s′,·) = 5, α = 0.5. Compute the new Q-learning value.

> **Answer:** Target = 2 + 4.5 = 6.5; TD error = 2.5; new Q = 4 + 1.25 = 5.25.

P5. Same numbers as above, but the action actually taken next has Q(s′,a′) = 2. Compute the SARSA value.

> **Answer:** Target = 2 + 0.9×2 = 3.8; TD error = −0.2; new Q = 4 − 0.1 = 3.9.

P6. State whether each is on- or off-policy: (a) learning the best policy from a log of another robot’s data; (b) REINFORCE; (c) SARSA.

> **Answer:** (a) Off-policy. (b) On-policy. (c) On-policy.

P7. Why does V(terminal state) = 0 in every example in this module?

> **Answer:** No further reward can be collected after the episode ends; the goal reward is counted in the value of the previous state.

P8. Give one reason to use γ \< 1 and one reason γ = 1 can cause problems.

> **Answer:** γ \< 1 makes the infinite sum finite and prefers sooner rewards. With γ = 1 returns can be infinite or very large in tasks that never end.

# 22. End-of-Module Test

Total: 52 marks. Suggested time: 50 minutes. Attempt without notes, then mark yourself.

## Questions

1.  Define reinforcement learning and say how it differs from supervised learning. \[3\]
2.  A thermostat learns to control heating. Identify the agent, environment and one reward. \[3\]
3.  Rewards in an episode are 0, 0, 4 and γ = 0.5. Compute G<sub>0</sub>. \[2\]
4.  State the Markov property and give one example of a state that violates it. \[3\]
5.  Corridor of cells 1, 2, 3 (goal +1 on entering 3), γ = 0.8, policy always Right. Compute V(1) and V(2). \[3\]
6.  Distinguish model-based from model-free learning. \[2\]
7.  Write the Bellman optimality equation in words and say what γ does in it. \[3\]
8.  Action A: r = 1, next V\* = 2. Action B: r = 0, next V\* = 3. γ = 0.9. Find V\*(s) and the best action. \[3\]
9.  Why does dynamic programming need the model? \[2\]
10. Give two differences between value iteration and policy iteration. \[2\]
11. Define behaviour policy and target policy. \[2\]
12. Why is Q-learning off-policy? \[2\]
13. Q(s,a) = 2, r = 1, γ = 0.9, max Q(s′,·) = 3, α = 0.2. Compute the new Q (Q-learning). \[3\]
14. Same numbers but SARSA with Q(s′,a′) = 1. Compute the new Q. \[3\]
15. In the cliff-walk which algorithm learns the safer path and why? \[2\]
16. Name the two stabilising ideas in DQN and say what each does. \[2\]
17. Why does REINFORCE have high variance? Give one remedy. \[2\]
18. V(s) = 1.2, r = 0.5, V(s′) = 1, γ = 0.9. Compute δ and say what the actor does. \[3\]
19. Explain the roles of actor and critic. \[3\]
20. A recommender is rewarded for watch time. Describe two possible unintended behaviours and one ethical consequence. \[4\]

## Mark scheme

| \#  | Answer                                                                                                                                                                                                 |
|-----|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1   | An agent learns to act by interacting with an environment and receiving rewards; supervised learning is given the correct output for each input, RL only a reward telling how good the outcome was.    |
| 2   | Agent: the controller; environment: the room (and weather); reward e.g. −energy used minus a penalty for being too cold.                                                                               |
| 3   | 0 + 0 + 0.25 × 4 = 1.                                                                                                                                                                                  |
| 4   | The current state contains all information needed to predict the future; e.g. a single camera frame that cannot show what is behind the robot, or only the cards in hand.                              |
| 5   | V(2) = 1; V(1) = 0 + 0.8 × 1 = 0.8.                                                                                                                                                                    |
| 6   | Model-based uses (or learns) P and R and plans; model-free learns values or a policy directly from experience.                                                                                         |
| 7   | The value of a state is the best action’s expected immediate reward plus discounted value of the next state; γ weights future value less than immediate reward.                                        |
| 8   | A: 1 + 1.8 = 2.8; B: 0 + 2.7 = 2.7; V\*(s) = 2.8, action A.                                                                                                                                            |
| 9   | The update sums over P(s′\|s,a) and R(s,a,s′), so these must be known.                                                                                                                                 |
| 10  | VI merges evaluation and improvement; PI alternates full evaluation and improvement; VI stops on small value change, PI when the policy is stable; VI sweeps cheap, PI iterations costlier.            |
| 11  | Behaviour: the policy used to choose actions while learning. Target: the policy being learned.                                                                                                         |
| 12  | Its target uses max over next actions, whatever the agent actually does next.                                                                                                                          |
| 13  | Target 1 + 2.7 = 3.7; TD error 1.7; new Q = 2 + 0.34 = 2.34.                                                                                                                                           |
| 14  | Target 1 + 0.9 = 1.9; TD error −0.1; new Q = 2 − 0.02 = 1.98.                                                                                                                                          |
| 15  | SARSA: its on-policy target includes the exploratory steps that can fall off the cliff.                                                                                                                |
| 16  | Experience replay: random minibatches break correlation. Target network: slowly updated copy keeps the target steady.                                                                                  |
| 17  | Single-episode returns fluctuate a lot; remedy: baseline subtraction or a critic.                                                                                                                      |
| 18  | δ = 0.5 + 0.9 − 1.2 = 0.2 \> 0, so increase the probability of the action.                                                                                                                             |
| 19  | Actor: the policy that picks actions. Critic: a value function that evaluates them and supplies the TD error used to update the actor (and itself).                                                    |
| 20  | Promotes sensational or addictive content; ignores user wellbeing or diversity; ethical: it shapes user behaviour for the platform’s benefit, so designers carry responsibility for the reward chosen. |

# 23. Learning Material List

Titles are given so you can find them; check availability before relying on a link.

| Resource                                                                                          | Type         | Use it for                                                          |
|---------------------------------------------------------------------------------------------------|--------------|---------------------------------------------------------------------|
| Sutton & Barto, *Reinforcement Learning: An Introduction* (2nd ed.), free online from the authors | Textbook     | The standard reference: MDPs, DP, TD, Q-learning, policy gradient   |
| David Silver, *Introduction to Reinforcement Learning* lecture series (UCL / DeepMind, YouTube)   | Video        | Ten lectures matching Sections 4–17                                 |
| OpenAI, *Spinning Up in Deep RL*                                                                  | Web tutorial | Plain-language introduction to policy gradients and actor–critic    |
| Hugging Face, *Deep Reinforcement Learning Course*                                                | Course       | Hands-on Q-learning and DQN with exercises                          |
| Gymnasium (library) and its documentation                                                         | Software     | Environments (e.g. FrozenLake, CliffWalking) to test the algorithms |
| Stable-Baselines3                                                                                 | Software     | Ready-made DQN, A2C and PPO implementations                         |
| Mnih et al. (2015), *Human-level control through deep reinforcement learning*                     | Paper        | The DQN paper (Section 15.3)                                        |
| Computerphile and DeepMind channels (YouTube)                                                     | Video        | Short explainers and demonstrations of game-playing agents          |
| Puterman, *Markov Decision Processes*                                                             | Textbook     | Rigorous treatment (beyond this module)                             |

## Suggested path

1.  Sections 1–7 with Sutton & Barto chapters 1–3.
2.  Sections 8–11 with Silver lectures 2–3 (DP).
3.  Sections 12–15: implement Q-learning on CliffWalking in Gymnasium and compare it with SARSA.
4.  Sections 16–17 with Spinning Up.

# 24. Master Glossary

| Term                                  | Definition                                                                                 |
|---------------------------------------|--------------------------------------------------------------------------------------------|
| **Action (a)**                        | A choice available to the agent.                                                           |
| **Actor–critic**                      | An RL method combining a policy (actor) and a value function (critic).                     |
| **Advantage A(s,a)**                  | Q(s,a) − V(s): how much better an action is than average.                                  |
| **Agent**                             | The learner or decision-maker.                                                             |
| **Baseline**                          | A quantity subtracted from the return to reduce variance.                                  |
| **Behaviour policy**                  | The policy used to select actions during learning.                                         |
| **Bellman equation**                  | Value = immediate reward + discounted next-state value.                                    |
| **Contraction**                       | A mapping that brings any two points closer; guarantees convergence of value iteration.    |
| **Credit assignment**                 | Deciding which earlier actions contributed to a later reward.                              |
| **Discount factor (γ)**               | Weight of future rewards relative to immediate ones, in \[0,1).                            |
| **DQN**                               | Deep Q-Network: a neural network replacing a Q-table.                                      |
| **Dynamic programming**               | Solving MDPs by iterating the Bellman equation over the full state space.                  |
| **Environment**                       | Everything the agent interacts with.                                                       |
| **Episode**                           | A run from a start state to a terminal state.                                              |
| **ε-greedy**                          | With probability ε choose a random action; otherwise the best-known action.                |
| **Experience replay**                 | Sampling random minibatches from a stored buffer of transitions.                           |
| **Exploration / exploitation**        | Trying new actions / choosing the best-known action.                                       |
| **Fixed point**                       | A value function that no longer changes when the update is applied.                        |
| **Greedy policy**                     | Always choosing the action with the highest current value estimate.                        |
| **Learning rate (α)**                 | How far each update moves the estimate.                                                    |
| **Markov property**                   | The current state is sufficient to predict the future.                                     |
| **MDP**                               | Markov Decision Process: (S, A, P, R, γ).                                                  |
| **Minibatch**                         | A small random sample of stored transitions.                                               |
| **Model-based / model-free**          | Learning or using an environment model / learning values or policy directly.               |
| **Monte-Carlo method**                | An algorithm that learns from complete episodes rather than step by step (e.g. REINFORCE). |
| **Neural network**                    | A model of layers of simple units connected by adjustable weights.                         |
| **Off-policy / on-policy**            | Target policy differs from / equals the behaviour policy.                                  |
| **Policy (π)**                        | A rule for choosing actions.                                                               |
| **Policy evaluation**                 | Computing V<sub>π</sub> for a fixed policy.                                                |
| **Policy gradient**                   | A method that adjusts policy parameters in the direction that increases expected return.   |
| **Policy improvement**                | Making a policy greedy with respect to its value function.                                 |
| **Policy iteration**                  | Alternating policy evaluation and policy improvement.                                      |
| **Q-learning**                        | Off-policy value-based algorithm learning Q\*.                                             |
| **Q-value Q(s,a)**                    | Expected return from taking a in s and then following a policy.                            |
| **REINFORCE**                         | Policy-gradient algorithm that updates after each complete episode.                        |
| **Return (G<sub>t</sub>)**            | Total discounted reward from time t.                                                       |
| **Reward (r)**                        | Feedback signal in RL.                                                                     |
| **SARSA**                             | On-policy value-based algorithm using (s, a, r, s′, a′).                                   |
| **State (s)**                         | A description of the current situation.                                                    |
| **State value V(s)**                  | Expected return from state s under a policy.                                               |
| **Target network**                    | A slowly updated copy of the Q-network used for stable TD targets.                         |
| **Target policy**                     | The policy the agent is trying to learn or improve.                                        |
| **TD error (δ)**                      | Target minus current estimate: the “surprise”.                                             |
| **Transition probability P(s′\|s,a)** | Chance of landing in s′ after action a in s.                                               |
| **Unbiased**                          | An estimate that is correct on average across many episodes.                               |
| **Value function**                    | Predicted total future reward (V or Q).                                                    |
| **Value iteration**                   | Iterating the Bellman optimality equation until convergence.                               |
| **Variance**                          | How much an estimate fluctuates from episode to episode.                                   |

# 25. References and Revision Notes

## 25.1 References

1.  Sutton, R. S., & Barto, A. G. (2018). *Reinforcement Learning: An Introduction* (2nd ed.). MIT Press.
2.  Bellman, R. (1957). *Dynamic Programming*. Princeton University Press.
3.  Watkins, C. J. C. H., & Dayan, P. (1992). Q-learning. *Machine Learning*, 8, 279–292.
4.  Rummery, G. A., & Niranjan, M. (1994). *On-line Q-learning using connectionist systems*. Technical Report CUED/F-INFENG/TR 166, Cambridge University Engineering Department.
5.  Williams, R. J. (1992). Simple statistical gradient-following algorithms for connectionist reinforcement learning. *Machine Learning*, 8, 229–256.
6.  Konda, V. R., & Tsitsiklis, J. N. (2000). Actor-critic algorithms. *Advances in Neural Information Processing Systems*, 12.
7.  Mnih, V., et al. (2015). Human-level control through deep reinforcement learning. *Nature*, 518, 529–533.
8.  Puterman, M. L. (1994). *Markov Decision Processes*. Wiley.
9.  Skinner, B. F. (1938). *The Behavior of Organisms*. Appleton-Century.

## 25.2 Revision notes (version 2.0)

| Change                                                                                                                                                                                                 | Where               |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
| Corrected the policy-iteration worked example: “always Right” does *not* give the Section 8.4 values; the evaluation is recomputed and the policy-improvement steps shown in full                      | 11.2                |
| Corrected the Q-learning vs SARSA example: the 2×2 grid has no Left action, so the exploratory action is now Up (blocked)                                                                              | 15.1                |
| Return G<sub>t</sub> is now defined before it is used (it was referenced to Section 5.4 but not defined there); added to the notation box                                                              | Notation; 5.4       |
| Blocked actions are now handled correctly in the policy-improvement example (staying in place has value γV(s))                                                                                         | 9.3                 |
| Added the missing P(s′\|s,a) and γ entries to the MDP component table                                                                                                                                  | 4.2                 |
| Policy-gradient formulas written in the standard form, with the γ<sup>t</sup> factor explained; added the actor and critic update rules and the corridor value-iteration and policy-iteration examples | 16; 17; 10.3; 11    |
| Monte-Carlo, baseline and policy gradient are now defined where first used and in the glossary                                                                                                         | 16; 24              |
| Added figures (loop, grid, model-based/model-free, algorithm map, cliff-walk, actor–critic) and a mind map                                                                                             | Throughout; 19      |
| Added study plan, learning suggestions, three case studies, mixed practice, a 20-question test with mark scheme and a learning material list                                                           | How to study; 20–23 |

## 25.3 Topics not covered

Exploration strategies beyond ε-greedy (softmax, UCB), convergence conditions and the “deadly triad”, PPO/TRPO in detail, offline RL and multi-agent RL. Learner testing: have someone who did not write Sections 14–17 complete the activities as a beginner and record any remaining confusion.
