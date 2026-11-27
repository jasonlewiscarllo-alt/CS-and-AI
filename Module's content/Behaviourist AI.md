# Behavioural AI: Reinforcement Learning for Beginners

**Stage 8 · Part of *Hardware, Networks and Behavioural AI***
Version 3.0, beginner edition (24 November 2026)

> **Start here**
>
> This module teaches how a computer can **learn by trial and error**, the same way you learn a new video game: try something, see what happens, and do more of what works. You do not need any programming or machine-learning knowledge. If you can add, multiply and work out an average, you can follow every example.
>
> Every section starts with **The big idea** in one or two sentences. Read that first. The maths always comes *after* the explanation in words, and every number in the examples is worked out step by step.

## Contents

- Module overview, learners and learning outcomes
- How to study this module
- Our two running examples
- The eight symbols you need (read first)
- 1\. What Behavioural AI is
- 2\. The learning loop and the grid world
- 3\. What makes reinforcement learning different
- 4\. Describing a problem: states, actions, rewards (the MDP)
- 5\. Chance, plans and values
- 6\. Learning with or without a map (model-based vs model-free)
- 7\. The Bellman equation: the one idea behind everything
- 8\. Dynamic programming (1): measuring a plan
- 9\. Dynamic programming (2): improving a plan
- 10\. Value iteration
- 11\. Policy iteration
- 12\. On-policy and off-policy
- 13\. Learning from experience: the algorithm families, Monte Carlo and TD
- 14\. Q-learning
- 15\. SARSA and Deep Q-Networks
- 16\. Learning the plan directly: REINFORCE
- 17\. Actor–critic
- 18\. Real-world applications and reward design
- 19\. Mind map and summary
- 20\. Case studies
- 21\. Mixed practice
- 22\. End-of-module test with mark scheme
- 23\. Learning material list
- 24\. Glossary
- 25\. References and revision notes

---

# Module Overview

## What this module is about

**Behavioural AI** (in this module) means AI that learns *what to do* by acting in a world and getting a score, called a **reward**, for how well things went. Nobody tells it the right answer. It has to find out by trying. The technical name for this is **reinforcement learning (RL)**.

The module follows one path: first we describe a problem clearly (Sections 1–6), then we learn the single equation that every method uses (Section 7), then we solve small problems when we know all the rules (Sections 8–11), and finally we learn when the rules are unknown and the agent must learn from experience (Sections 12–17). We finish with real uses, ethics, case studies and a test (Sections 18–25).

## Who this is for

- **Intended learners:** first- and second-year college students, including those outside computer science, who want to understand how game-playing and robot-controlling AI learns.
- **Prerequisites:** basic arithmetic (adding, multiplying decimals), the idea of an average, and reading a simple table. No programming. No calculus: the only formulas with advanced symbols are in boxes marked **Going deeper (optional)**, which you can skip.

## Learning outcomes

| # | By the end of this module you can… | Where it is assessed |
|---|---|---|
| LO1 | Explain what Behavioural AI is and how it differs from supervised and unsupervised learning. | Section 1; Activity 1.1; Test Q1 |
| LO2 | Describe the agent–environment loop and name its five parts. | Section 2; Activity 2.1; Test Q2 |
| LO3 | Write down a small problem as states, actions, rewards and chances (an MDP) and explain the Markov property. | Sections 4–5; Activities 4.1, 5.2; Test Q4 |
| LO4 | Explain the Bellman equation in words and do a one-step calculation by hand. | Section 7; Activity 7.1; Test Q7–Q8 |
| LO5 | Tell model-based from model-free learning, and trace policy evaluation, value iteration and policy iteration on a small grid. | Sections 6, 8–11; Activities 8.1, 10.1, 11.1; Test Q5–Q6, Q9–Q10 |
| LO6 | Explain how an agent learns from experience (Monte Carlo, TD, Q-learning, SARSA, DQN, REINFORCE, actor–critic), say which are on- or off-policy, and predict the cliff-walk behaviour. | Sections 12–17; Activities 12.1, 13.3, 14.1, 15.1, 17.1; Test Q11–Q19, Q21 |
| LO7 | Design a reward for a real application, predict one behaviour you did not intend, and name an ethical consequence. | Section 18; Activities 18.1, 18.2; Case studies; Test Q20 |

**How the parts fit together.** Every outcome has a worked example (watch it done), an activity with a checked answer (do it yourself) and a quick check question. The end-of-module test covers all seven outcomes.

## How to study this module

| Week | Sections | Focus | Do this |
|---|---|---|---|
| 1 | 1–3 | What RL is; the loop; exploring | Activities 1.1–3.1; explain the loop to a friend in two minutes |
| 2 | 4–6 | Describing problems; values; maps | Write the states, actions and rewards for a game you know |
| 3 | 7–9 | Bellman; measuring and improving a plan | Redo the 2×2 grid tables by hand without looking |
| 4 | 10–12 | Value and policy iteration; on/off-policy | Do the corridor activities; classify four algorithms |
| 5 | 13–17 | Learning from experience | Trace one update of each algorithm by hand |
| 6 | 18–22 | Real uses, case studies, test | Take the test closed-book, then mark it |

> **Learning suggestions**
>
> - Draw the 2×2 grid on paper once and keep it beside you for every section.
> - Always try the calculation **before** you read the answer.
> - Read the words first, then the formula. If a formula scares you, read the **Formula in words** line again.
> - After each section, try to say **Remember** from memory. If you cannot, re-read the big idea.
> - Skip every **Going deeper (optional)** box on your first read. Come back to them later if you want more.
> - After Section 15, try the free CliffWalking or FrozenLake environment in Gymnasium (see Section 23) and watch the values change.

### Core path and optional boxes

Everything outside a **Going deeper (optional)** box is the core course: it is complete, checked and enough for the test. The optional boxes show the full mathematical form for readers who want it. The test never requires them.

---

# Our Two Running Examples

> **The big idea**
>
> We use one everyday story (a mouse learning a maze) to build intuition, and one tiny puzzle (the 2×2 grid) for every calculation. Keep both in mind.

## Example 1: a mouse learning a maze

Imagine a mouse placed at the entrance of a maze, with a piece of cheese hidden at the far end. Nobody shows it the way. At every junction it can go left, right or straight on. The only "reward" is the cheese at the end.

- At first it wanders randomly, bumps into walls and takes a long time to find the cheese.
- Slowly it remembers which turns led to the cheese sooner, and takes them more often.
- After many runs it goes straight to the cheese without a wrong turn.

That is reinforcement learning. Psychologists studied exactly this kind of maze learning in animals in the early 1900s, and the computer methods in this module grew out of the same idea.

## Example 2: the 2×2 grid world

Even a small maze has too many junctions to calculate by hand, so for every worked example we shrink it to four squares.

![The 2×2 grid world. The agent starts at (0,0); the goal (1,1) is the top-right square.](figures/grid-world-2x2.png)

*Figure 1. The 2×2 grid world. Squares are named (x, y): x counts across, y counts up.*

| Part | In the grid world |
|---|---|
| Squares (states) | (0,0) start, (1,0), (0,1), (1,1) goal |
| Moves (actions) | **Right** (x + 1) or **Up** (y + 1). Walking into the edge leaves you where you are. |
| Points (reward) | +1 for stepping onto the goal (1,1); 0 for every other move |
| End | The game ends as soon as you reach the goal |
| Discount γ | 0.9 (Section 5.3 explains this) |

**Two maze ↔ grid matches to remember:** reaching the goal square is like finding the cheese; a move into the edge is like the mouse running into a wall: it stays where it is and wastes time.

---

# The Eight Symbols You Need

You do not need to memorise this. Come back whenever a symbol appears.

| Symbol | Say it as | Meaning in plain words |
|---|---|---|
| s, s′ | "s", "s-prime" | The current situation (state) and the next one |
| a | "a" | An action (a move) |
| r | "r" | The reward (points) just received |
| γ | "gamma" | The **discount**: how much a reward one step in the future is worth now (e.g. 0.9 = 90%) |
| α | "alpha" | The **learning rate**: how big a step each update takes (e.g. 0.5 = halfway) |
| V(s) | "V of s" | The **value** of a state: how many points you expect to collect from here on |
| Q(s, a) | "Q of s, a" | The value of taking action a in state s, then carrying on |
| ← | "becomes" | Update: x ← x + 1 means "x becomes x + 1" |

> **Going deeper (optional): the other symbols**
>
> These appear only in optional boxes. **G<sub>t</sub>**: the return from step t. **π(a | s)**: the chance the plan picks action a in state s ("|" means "given"). **P(s′ | s, a)**: the chance of landing in s′ after doing a in s. **Σ**: "add up over all". **max<sub>a</sub>**: "the biggest over all actions". **E[·]**: the average in the long run. **δ** (delta): the surprise, target minus estimate. **θ** (theta): the adjustable numbers inside a plan. **∇** (nabla): the direction that increases a quantity fastest.

---

# 1. What Behavioural AI Is

> **The big idea**
>
> Behavioural AI learns what to do from rewards, by trial and error, without being shown the right answer.

## 1.1 Learning from consequences

Most AI you hear about learns from examples with answers attached: "this photo is a cat". Behavioural AI is different. It is never told the right move. It acts, gets a reward afterwards, and changes its behaviour to get more reward next time.

The name comes from **behaviourism** in psychology (Pavlov, Thorndike, Skinner): behaviour that is followed by a reward happens more often; behaviour followed by punishment happens less. A dog that gets a treat for sitting learns to sit. **Reinforcement learning** is the computer version of that idea.

![Three families of machine learning: supervised, unsupervised and reinforcement learning.](figures/three-families-of-ml.png)

*Figure 2. The three families of machine learning. This module is about the third.*

| Family | What it is given | Everyday example |
|---|---|---|
| Supervised learning | Examples **with** the right answer | A spam filter trained on emails marked "spam" or "not spam" |
| Unsupervised learning | Examples **without** answers; it finds groups | Grouping shoppers by what they buy |
| Reinforcement learning | **No** answers, only a reward after acting | A mouse that learns a maze because it finds cheese at the end |

## 1.2 Key words

| Word | Meaning | In the maze |
|---|---|---|
| **Agent** | The learner that makes decisions | The mouse |
| **Environment** | Everything outside the agent | The maze |
| **State (s)** | A description of the situation right now | Which junction the mouse is at |
| **Action (a)** | A choice the agent can make | Go left, right or straight on |
| **Reward (r)** | Points given after an action; higher is better | +1 for reaching the cheese |
| **Policy (π)** | The agent's plan: which action to take in each state | "At the first junction, turn left" |
| **Value** | How many points the agent expects from here on | "From this junction the cheese is close" |
| **Episode** | One complete run from start to finish | One run from the entrance to the cheese |

> **Check Q1.1. A chess program is trained on millions of positions, each with the "correct" move. Is that behavioural AI?**
>
> **Answer.** No, that is supervised learning (it is given the right answers). A behavioural-AI chess program would play games and only be told win, lose or draw, then work out which moves helped.

> **Activity 1.1 — Name the parts**
>
> A robot vacuum learns to clean a room. It can go forward, turn left, turn right or stop. It gets +1 when it cleans a dirty patch, −5 when it bumps furniture and 0 otherwise. Name the agent, environment, actions, rewards and one possible state.

> **Answer**
>
> Agent = the vacuum's control program. Environment = the room, furniture and dirt. Actions = forward, left, right, stop. Rewards = +1, −5, 0. One possible state = "where I am, which way I face, and what my dirt sensor reads".

> **Remember**
>
> RL = learn from rewards by trial and error. No right answers are given.

---

# 2. The Learning Loop and the Grid World

> **The big idea**
>
> Every RL system repeats one loop: look, act, the world changes, get a reward, learn. Then do it again.

## 2.1 The agent–environment loop

![The agent–environment loop: the agent sends an action; the environment returns a new state and a reward.](figures/agent-environment-loop.png)

*Figure 3. The agent–environment loop.*

1. **Look** — the agent sees the current state s.
2. **Act** — it picks an action a using its current policy.
3. **Change** — the world moves to a new state s′.
4. **Reward** — the world gives a reward r.
5. **Learn** — the agent updates what it knows, then the loop repeats from the new state.

In the maze: the mouse is at a junction → turns left → arrives in a new corridor → finds the cheese, +1 → remembers "turning left there was good" → carries on next time from the start.

> **Going deeper (optional): time-step notation**
>
> Textbooks number the steps. S<sub>t</sub> is the state at step t, A<sub>t</sub> the action, and R<sub>t+1</sub> and S<sub>t+1</sub> the reward and state that follow. One step of experience is written (S<sub>t</sub>, A<sub>t</sub>, R<sub>t+1</sub>, S<sub>t+1</sub>), or simply (s, a, r, s′).

## 2.2 Worked example: one game in the grid world

> **Worked example — one episode**
>
> Start at (0,0). Move **Right** → now at (1,0), reward 0. Move **Up** → now at (1,1), the goal, reward +1. The game ends.
>
> Written as steps of experience (s, a, r, s′): Step 1: ((0,0), Right, 0, (1,0)). Step 2: ((1,0), Up, +1, (1,1)).

> **Check Q2.1. The agent is at (1,0) and chooses Up. What is the next state and reward?**
>
> **Answer.** Next state (1,1); reward +1; the game ends.

> **Activity 2.1 — Trace a game**
>
> Starting at (0,0), the agent does Right, Right, Up. (a) Write the square after each move. (b) Write the reward after each move. (c) What is the total reward?

> **Answer**
>
> (a) (0,0) → Right → (1,0) → Right → (1,0) (hit the edge, stayed) → Up → (1,1). (b) 0, 0, +1. (c) Total = 1. The second Right was wasted: exactly the kind of mistake learning should remove.

> **Remember**
>
> Look → act → change → reward → learn, again and again.

---

# 3. What Makes Reinforcement Learning Different

> **The big idea**
>
> RL is hard for three reasons: nobody gives the right answer, rewards often come late, and the agent must choose between using what it knows and trying something new.

## 3.1 Three special features

1. **Trial and error.** The agent is never told the correct action; it must try things and see what happens.
2. **Delayed reward.** The reward for a good move may come much later. The mouse only gets the cheese at the very end, but the turn that really mattered may have been the first one at the entrance. Working out which earlier actions deserve the credit is called the **credit assignment problem**.
3. **The agent's actions change what it sees next.** If it never goes into a cave, it never learns what is inside.

> **Common mistake**
>
> "RL is just supervised learning with rewards as labels." No. A label says *what the right answer was*. A reward only says *how good the result was*. If a chess agent wins, every move gets some credit, even the bad ones.

## 3.2 Exploration vs exploitation

- **Exploitation:** do what currently looks best.
- **Exploration:** try something else, because it might be better.

If you always order your usual dish at a restaurant (exploiting), you will never find out that another dish is even better (exploring). The usual compromise is called **ε-greedy** (say "epsilon-greedy"): most of the time do the best-known action, but with a small chance ε (for example 0.1, so 1 time in 10) do a random action instead. ε is often lowered over time: explore a lot early, then mostly exploit.

> **Worked example — two slot machines**
>
> Machine A paid 1 on its first pull, so the agent's estimate for A is 1. Machine B has never been tried, so its estimate is 0. A purely greedy agent pulls A forever. Suppose B really pays 5 on average: the greedy agent never finds out. With ε = 0.1, about one pull in ten is random, so B gets tried, its estimate rises, and the agent switches to B.

> **Check Q3.1. Why is "always exploit" dangerous?**
>
> **Answer.** The agent may never discover a better action and can get stuck with a mediocre plan for ever.

> **Activity 3.1 — Predict what happens**
>
> A learner sets ε = 0 from the very start. Predict what happens to learning, then suggest one fix.

> **Answer**
>
> With ε = 0 the agent never explores. If all estimates start equal (for example 0) it keeps picking the same arbitrary action; if that action is poor it never finds the good one. Fix: keep ε above 0 for a while, or start all estimates high ("optimistic") so untried actions look attractive and get tried.

> **Remember**
>
> No right answers, late rewards, and a balance between exploring and exploiting.

---

# 4. Describing a Problem: States, Actions, Rewards

> **The big idea**
>
> Before a computer can learn, we must describe the problem precisely: the situations, the moves, the points and the chances. That description is called a Markov Decision Process (MDP).

## 4.1 Why we need a precise description

"Get to the goal" is clear to a person but not to a computer. To calculate anything, we list exactly what the situations are, what moves exist and what each move earns. Every method in this module works on such a list.

## 4.2 The five parts of an MDP

| Part | Question it answers | 2×2 grid |
|---|---|---|
| **States** | What situations can happen? | (0,0), (1,0), (0,1), (1,1) |
| **Actions** | What can the agent do? | Right, Up |
| **Transitions** | Where does each move lead (and with what chance)? | Every move works for certain, or is blocked by the edge |
| **Rewards** | How many points does each move earn? | +1 for entering (1,1), otherwise 0 |
| **Discount γ** | How much is a later reward worth now? | 0.9 |

> **Going deeper (optional): the formal tuple**
>
> An MDP is written (S, A, P, R, γ): the set of states S, the set of actions A, the transition probabilities P(s′ | s, a), the reward R(s, a, s′) and the discount γ.

## 4.3 The Markov property

The **Markov property** means: *the current state tells you everything you need to decide what happens next; the history adds nothing extra.*

In the grid, knowing your square is enough. In chess, the board position is enough. But in a card game, the cards in your hand are **not** enough, because you also need to know which cards have already been played.

> **Why this matters**
>
> Choosing what goes into the state is a design decision. If the state leaves out something important, the agent cannot tell apart two situations that need different actions, and learning becomes much harder.

> **Check Q4.1. In a card game, is "the cards in my hand" a good enough state?**
>
> **Answer.** No. You also need which cards have been played, because that changes what can still be drawn.

> **Activity 4.1 — Describe a corridor**
>
> A 1×3 corridor has cells 1, 2, 3. Cell 3 is the goal (+1 for entering, game ends). Actions: Left, Right. Walking into a wall leaves you in place (reward 0). Write (a) the states, (b) the actions, (c) where Right from cell 1 leads and where Left from cell 1 leads, (d) the reward for Right from cell 2.

> **Answer**
>
> (a) {1, 2, 3}. (b) {Left, Right}. (c) Right from 1 → cell 2 (for certain); Left from 1 → stays in 1 (blocked). (d) +1, because it enters the goal.

> **Remember**
>
> An MDP = states + actions + transitions + rewards + discount. "Markov" = the present state is enough.

---

# 5. Chance, Plans and Values

> **The big idea**
>
> Moves can be uncertain, a plan (policy) says what to do in each state, and a value says how many points a state is worth if you follow the plan.

## 5.1 When moves are uncertain

Real worlds are not perfectly predictable: a robot's wheels slip, a door in the maze is sometimes stuck. We describe this with chances.

> **Worked example — a slippery grid**
>
> Suppose Right works 8 times out of 10, and 2 times out of 10 the agent slips and stays put. Then from (0,0), Right leads to (1,0) with chance 0.8 and stays at (0,0) with chance 0.2. The chances for one move always add up to 1 (0.8 + 0.2 = 1).

## 5.2 Policy: the agent's plan

A **policy** is the agent's plan: for every state, which action to take. "In (0,0) go Right; in (1,0) go Up" is a policy. A plan can also be random, for example "go Right 70% of the time". The **optimal policy** is the plan that collects the most reward.

## 5.3 The discount γ: why later points are worth less

Points you get later count for a little less than points you get now. With γ = 0.9, a reward one step away is worth 90% of its size, two steps away 0.9 × 0.9 = 0.81 (81%), and so on. There are three reasons:

1. **Uncertainty:** something far in the future might not happen.
2. **Sooner is better:** reaching the goal in fewer moves is usually what we want.
3. **Maths:** in a game that never ends, the total stays a finite number.

> **Worked example — cheese at the end of the maze**
>
> The mouse gets 0, 0, 0 for its first three moves and then +10 for reaching the cheese on the fourth move. With γ = 0.9 that +10, three steps after the first reward, is worth 0.9 × 0.9 × 0.9 × 10 = 0.729 × 10 = **7.29** now. With γ = 0.5 it would be worth only 0.125 × 10 = **1.25**: a smaller γ makes the agent care much less about far-away rewards.

## 5.4 The return and the value

The **return** is the total of all the rewards from now on, each one discounted by how far away it is:

**Formula in words:** return = this reward + 0.9 × next reward + 0.81 × the one after + …

The **value** V(s) of a state is the return you expect if you start there and follow your plan. **Q(s, a)** is the same, but you first take action a and then follow the plan.

> **Worked example — computing a value by hand**
>
> Plan: "in (0,0) go Right; in (1,0) go Up". From (0,0) you get 0 (moving to (1,0)) and then +1 (moving into the goal). So V((0,0)) = 0 + 0.9 × 1 = **0.9**.
>
> From (1,0) the very next move earns +1, so V((1,0)) = **1**. The goal itself has V((1,1)) = **0**, because the game is over and nothing more can be collected.

> **Common mistake**
>
> The +1 for reaching the goal belongs to the square **before** the goal, not to the goal. That is why V((1,0)) = 1 but V((1,1)) = 0. This is the most common beginner error in this module.

> **Going deeper (optional): the formal definitions**
>
> Return: G<sub>t</sub> = R<sub>t+1</sub> + γR<sub>t+2</sub> + γ²R<sub>t+3</sub> + … State value: V<sub>π</sub>(s) = E<sub>π</sub>[G<sub>t</sub> | S<sub>t</sub> = s]. Action value: Q<sub>π</sub>(s, a) = E<sub>π</sub>[G<sub>t</sub> | S<sub>t</sub> = s, A<sub>t</sub> = a]. E means "average over many runs", needed when moves are uncertain.

> **Check Q5.1. With a plan that goes Right from (0,1), what is V((0,1))?**
>
> **Answer.** Right enters the goal and earns +1, then nothing more: V = 1 + 0.9 × 0 = 1.

> **Activity 5.1 — Change the discount**
>
> Using the plan from the worked example, what is V((0,0)) if γ = 0.5? Explain the change in one sentence.

> **Answer**
>
> V((0,0)) = 0 + 0.5 × 1 = 0.5. The reward is one step away, so a smaller γ shrinks it more.

> **Activity 5.2 — Find the error**
>
> A student describes a card game with the state "the cards in the player's hand". A classmate says this breaks the Markov property. Who is right, and how should the state be fixed?

> **Answer**
>
> The classmate is right. Two situations with the same hand but different cards already played need different actions. Fix: add the cards already played, the discard pile and the opponent's visible cards to the state.

> **Remember**
>
> Policy = plan. γ makes later rewards smaller. Value = the points you expect from here if you follow the plan.

---

# 6. Learning With or Without a Map

> **The big idea**
>
> A "model" is the agent's map of how the world works. Model-based agents plan with the map; model-free agents learn good habits directly from experience.

## 6.1 What a model is

A **model** answers: "if I am here and do this, where will I end up and how many points will I get?" For the grid, the model is the table in Example 2 (Our Two Running Examples).

![Model-based learning plans with a map of the world; model-free learning learns values or habits directly from experience.](figures/model-based-vs-model-free.png)

*Figure 4. Model-based versus model-free learning.*

- **Model-based:** the agent has (or learns) the map, then plans by imagining moves ahead.
- **Model-free:** the agent never builds a map; it learns which actions are good straight from experience.

## 6.2 An everyday comparison

A **model-based** person in a new city studies the map first, then plans routes without walking them. A **model-free** person just learns "leave home, turn left, arrive at work" by repetition. No map, but the habit works, until a road closes and they have to find a detour by trial and error.

In the maze: a mouse that has explored before and remembers the layout can plan a route in its head (model-based); a mouse that simply repeats "left, left, right" because it worked last time is model-free.

> **Check Q6.1. A robot vacuum has a stored floor plan and calculates a route from it. Model-based or model-free?**
>
> **Answer.** Model-based: the floor plan is the model, and the route is planned on it.

> **Activity 6.1 — Choose an approach**
>
> Robot A works in a fixed warehouse with an accurate stored floor plan. Robot B works in a new building every week with no map. Which should be model-based and which model-free? Give one reason each.

> **Answer**
>
> Robot A: model-based, because an accurate map already exists, so planning on it is efficient. Robot B: model-free, because there is no map and building one every week is costly, so it learns directly from experience.

> **Remember**
>
> Model = map of the world. Sections 8–11 have the map; Sections 13–17 do not.

---

# 7. The Bellman Equation: The One Idea Behind Everything

> **The big idea**
>
> The value of where you are = the reward for your next step + the discounted value of where you land. Every method in this module is a way of using this one sentence.

## 7.1 The idea in one sentence

Think of the mouse at a junction: "how good is this junction?" equals "the reward I get for my next move" plus "90% of how good the next junction is". You do not have to think about the whole game at once, only one step plus the value of what comes next.

**Formula in words:** value here = reward now + γ × value of the next state.

For the grid, where every move has a certain result, that is simply:

**V(s) = r + γ × V(s′)**

## 7.2 The best possible value

If you can choose your action, work out "reward + γ × next value" for **each** action and keep the **biggest**:

**best V(s) = the largest of ( r + γ × V(s′) ) over all actions**

The best possible values are written V\* (say "V-star").

> **Worked example — one Bellman step**
>
> In the 2×2 grid, suppose we already know V\*((1,0)) = 1 and V\*((0,1)) = 1. What is V\*((0,0))?
>
> - Right: reward 0, land in (1,0) → 0 + 0.9 × 1 = 0.9
> - Up: reward 0, land in (0,1) → 0 + 0.9 × 1 = 0.9
>
> The biggest is 0.9, so V\*((0,0)) = **0.9**. Both moves are equally good: there can be more than one best plan.

> **Going deeper (optional): the general Bellman equations**
>
> When moves are uncertain and the plan may be random, we average over both. Expectation form (fixed plan π): V<sub>π</sub>(s) = Σ<sub>a</sub> π(a | s) Σ<sub>s′</sub> P(s′ | s, a) [ R(s, a, s′) + γ V<sub>π</sub>(s′) ]. Optimality form: V\*(s) = max<sub>a</sub> Σ<sub>s′</sub> P(s′ | s, a) [ R(s, a, s′) + γ V\*(s′) ]. The action-value version, Q\*(s, a) = Σ<sub>s′</sub> P(s′ | s, a) [ R + γ max<sub>a′</sub> Q\*(s′, a′) ], is what Q-learning (Section 14) learns from experience.

## 7.3 Why it is so powerful

"Get the most points over the whole game" sounds impossible to calculate. Bellman turns it into a small step repeated many times: "best next move, given how good the next state is". Sections 8–17 are all different ways of repeating that small step.

> **Check Q7.1. Suppose V\*((1,0)) = 1 but V\*((0,1)) = 0. What is the best action from (0,0), and V\*((0,0))?**
>
> **Answer.** Right: 0 + 0.9 × 1 = 0.9. Up: 0 + 0.9 × 0 = 0. Right is best and V\*((0,0)) = 0.9.

> **Activity 7.1 — Find the error**
>
> A classmate writes the Bellman equation as "V(s) = r + V(s′)". Compared with this section, what is missing? Give three things (one is in the main text, two are in the optional box).

> **Answer**
>
> (1) The discount γ in front of V(s′). (2) The choice of the best action (or, for a fixed plan, the average over the plan's actions). (3) The average over the possible next states when moves are uncertain.

> **Remember**
>
> Value here = reward now + γ × value next. For the best value, try every action and keep the biggest.

---

# 8. Dynamic Programming (1): Measuring a Plan

> **The big idea**
>
> If we have the map, we can work out how good a plan is by applying the Bellman sentence to every square, over and over, until the numbers stop changing.

## 8.1 What "dynamic programming" means here

**Dynamic programming (DP)** means solving a big problem by solving small pieces and reusing the answers. Here the small piece is the Bellman step from Section 7. DP needs the map (the model), so it is **model-based**.

## 8.2 The question: how good is this plan?

**Policy evaluation** answers one question: *for a fixed plan, what is the value of each square?* It measures the plan; it does not change it.

## 8.3 The method, step by step

1. Start with every value at 0.
2. Do a **sweep**: for every square, recompute value = reward + γ × value of the square the plan leads to. Use the values from the *previous* sweep on the right-hand side.
3. Repeat sweeps until no value changes (or changes by less than a tiny amount, such as 0.001).

## 8.4 Worked example: sweeps on the 2×2 grid

Plan: "go Right if you can; otherwise go Up". So (0,0) goes Right, (1,0) goes Up (Right is blocked) and (0,1) goes Right. γ = 0.9.

| Sweep | V((1,1)) goal | V((1,0)) | V((0,1)) | V((0,0)) |
|---|---|---|---|---|
| 0 (start) | 0 | 0 | 0 | 0 |
| 1 | 0 | 1 | 1 | 0 |
| 2 | 0 | 1 | 1 | 0.9 |
| 3 | 0 | 1 | 1 | 0.9 (no change: finished) |

> **Worked example — how each number was found**
>
> **Sweep 1.** (1,0): the plan goes Up into the goal, reward +1, so V = 1 + 0.9 × 0 = **1**. (0,1): the plan goes Right into the goal, so V = **1**. (0,0): the plan goes Right to (1,0), reward 0, and the *old* value of (1,0) is still 0, so V = 0 + 0.9 × 0 = **0**.
>
> **Sweep 2.** Only (0,0) changes: 0 + 0.9 × 1 = **0.9**, now using the sweep-1 value of (1,0).
>
> **Sweep 3.** Nothing changes, so we stop.

![Value spreads backwards from the goal, one square per sweep.](figures/value-spreads-backwards.png)

*Figure 5. Value travels backwards from the goal, one step per sweep. Squares next to the goal fill in first.*

> **Check Q8.1. Why does V((1,0)) become 1 in sweep 1, and not 0?**
>
> **Answer.** The +1 is earned on the move from (1,0) into the goal, so it counts in the value of (1,0). The goal itself is worth 0.

> **Activity 8.1 — One more sweep**
>
> Start from the finished values above, but change γ to 0.5. Do one sweep. What are the new values?

> **Answer**
>
> V((1,1)) = 0; V((1,0)) = 1; V((0,1)) = 1; V((0,0)) = 0 + 0.5 × 1 = 0.5. The squares next to the goal keep 1; the start square drops because its reward is one step away and is discounted more.

> **Activity 8.2 — Find the error**
>
> A student reports these sweep-2 values with γ = 0.9 (and V((1,0)) = 1 from sweep 1): V((1,0)) = 0, V((0,1)) = 1, V((0,0)) = 0.5. Find the errors and correct them.

> **Answer**
>
> V((1,0)) = 0 is wrong: the plan goes Up into the goal, so V((1,0)) = 1 + 0.9 × 0 = 1. Then V((0,0)) = 0 + 0.9 × 1 = 0.9, not 0.5. Correct values: 0, 1, 1, 0.9.

> **Going deeper (optional): the update as a formula**
>
> V(s) ← Σ<sub>a</sub> π(a | s) Σ<sub>s′</sub> P(s′ | s, a) [ R(s, a, s′) + γ V(s′) ], applied to every state in each sweep. Using the previous sweep's values on the right is called a synchronous sweep.

> **Remember**
>
> Policy evaluation = sweep the Bellman sentence over every square until the values settle. Value flows backwards from the goal.

---

# 9. Dynamic Programming (2): Improving a Plan

> **The big idea**
>
> Once you know the values, look at each square and ask: "is there a move that does better than my plan's move?" If yes, switch to it.

## 9.1 The idea

At each square, try every action once, using the values you already have: score = reward + γ × value of where you land. Pick the action with the highest score. This is called being **greedy** with respect to the values.

## 9.2 Why it always helps

The **policy improvement theorem** promises that the new plan is never worse than the old one, in any square. If nothing changes, the plan was already the best possible. This is why "measure, then improve" works.

> **Worked example — improving the Section 8.4 plan**
>
> Values: V((0,0)) = 0.9, V((1,0)) = 1, V((0,1)) = 1, goal = 0. γ = 0.9.
>
> - **At (0,0):** Right → 0 + 0.9 × 1 = 0.9; Up → 0 + 0.9 × 1 = 0.9. A tie, so the plan is already as good as possible here.
> - **At (1,0):** Up → 1 + 0.9 × 0 = 1; Right is blocked, so you stay: 0 + 0.9 × 1 = 0.9. Up is best (1 > 0.9).
> - **At (0,1):** Right → 1; Up is blocked: 0 + 0.9 × 1 = 0.9. Right is best.
>
> No square changes, so this plan is already optimal.

> **Going deeper (optional): argmax**
>
> The improved plan is π′(s) = argmax<sub>a</sub> Σ<sub>s′</sub> P(s′ | s, a) [ R(s, a, s′) + γ V<sub>π</sub>(s′) ]. "argmax" means "the action that gives the biggest value" (the action itself, not the number). If Q(Left) = 2 and Q(Right) = 5, argmax is Right.

> **Check Q9.1. If V((0,1)) were 0.5 instead of 1, which action would improvement choose at (0,0)?**
>
> **Answer.** Right: 0 + 0.9 × 1 = 0.9, versus Up: 0 + 0.9 × 0.5 = 0.45. Right wins.

> **Remember**
>
> Improve = at every square, switch to the move with the best "reward + γ × next value". It can never make things worse.

---

# 10. Value Iteration

> **The big idea**
>
> Value iteration skips the separate "measure the plan" stage: at every square it immediately uses the best move. It is the Bellman "keep the biggest" step, swept again and again.

## 10.1 How it works

1. Start with every value at 0.
2. In each sweep, for every square, try every action and keep the **biggest** reward + γ × next value (using last sweep's values).
3. Stop when the values stop changing.
4. Read off the plan: in each square, pick the action that gave the biggest number.

## 10.2 Worked example: the 2×2 grid

| Sweep | V((1,1)) goal | V((1,0)) | V((0,1)) | V((0,0)) |
|---|---|---|---|---|
| 0 (start) | 0 | 0 | 0 | 0 |
| 1 | 0 | 1 | 1 | 0 |
| 2 | 0 | 1 | 1 | 0.9 |
| 3 | 0 | 1 | 1 | 0.9 (finished) |

**Reading off the plan.** At (0,0) Right and Up both give 0.9, so either is best. At (1,0) Up is best. At (0,1) Right is best.

> **Worked example — value iteration on the 1×3 corridor**
>
> Cells 1, 2, 3; cell 3 is the goal (+1 for entering); actions Left and Right; walls leave you in place; γ = 0.9. The goal's value is always 0.
>
> | Sweep | V(1) | V(2) | V(3) |
> |---|---|---|---|
> | 0 | 0 | 0 | 0 |
> | 1 | 0 | 1 | 0 |
> | 2 | 0.9 | 1 | 0 |
> | 3 | 0.9 | 1 | 0 (finished) |
>
> **Sweep 1.** Cell 2: Right = 1 + 0.9 × 0 = 1; Left = 0 + 0.9 × 0 = 0 → keep 1. Cell 1: Right = 0 + 0.9 × 0 = 0 (cell 2 was still 0); Left = 0 → 0.
> **Sweep 2.** Cell 1: Right = 0 + 0.9 × 1 = 0.9 → 0.9. The best plan is Right in both cells.

> **Going deeper (optional): why it always finishes**
>
> The update is V<sub>k+1</sub>(s) ← max<sub>a</sub> Σ<sub>s′</sub> P(s′ | s, a) [ R(s, a, s′) + γ V<sub>k</sub>(s′) ]. When γ < 1, each sweep shrinks the difference between any two guesses by at least the factor γ (mathematicians call this a **contraction**), so the values must settle on one final answer (a **fixed point**).

> **Check Q10.1. Why does V((0,0)) stay 0 in sweep 1?**
>
> **Answer.** Sweep 1 uses the old values, and at the start (1,0) and (0,1) were both 0. Value moves back one square per sweep.

> **Activity 10.1 — Change the discount**
>
> Run value iteration on the 2×2 grid with γ = 0.5. What is the final V\*((0,0))? Why did it change?

> **Answer**
>
> V\*((1,0)) = 1, V\*((0,1)) = 1, V\*((0,0)) = 0 + 0.5 × 1 = 0.5. It is smaller because its reward is one step away and is discounted more when γ is smaller.

> **Activity 10.2 — Choose a method**
>
> A grid world has 10,000 squares. Would you try value iteration or policy iteration (Section 11) first? Why?

> **Answer**
>
> Value iteration first: each sweep is cheap, while each round of policy iteration must fully measure the plan, which is expensive with 10,000 squares. Policy iteration is worth trying if you already have a good starting plan, because it then finishes in very few rounds.

> **Remember**
>
> Value iteration = repeat "keep the biggest reward + γ × next value" everywhere until it settles, then read off the plan.

---

# 11. Policy Iteration

> **The big idea**
>
> Policy iteration alternates two stages, measure the plan, then improve it, until the plan stops changing.

## 11.1 The method

1. Start with any plan (for example "always Right").
2. **Measure:** work out the plan's values (Section 8).
3. **Improve:** at each square switch to the best move (Section 9).
4. If no square changed, stop: the plan is optimal. Otherwise go back to step 2.

![Value iteration and policy iteration are two routes to the same optimal plan.](figures/value-vs-policy-iteration.png)

*Figure 6. Two routes to the same optimal plan.*

## 11.2 Value iteration vs policy iteration

| | Value iteration | Policy iteration |
|---|---|---|
| What repeats | One "keep the biggest" sweep | Full measuring, then improving |
| When is the plan read off? | At the end | At every improve step |
| Cost per round | Cheap, but many rounds | Expensive, but few rounds |
| Stops when | Values stop changing | The plan stops changing |
| Good for | Very large worlds | When measuring is affordable or a good starting plan exists |

Both reach the same best plan. Choosing between them is about speed, not correctness.

> **Worked example — policy iteration on the 2×2 grid (γ = 0.9)**
>
> **Start:** plan = "always Right".
>
> **Measure.** (0,1): Right enters the goal → V = 1. (1,0): Right is blocked, so the agent stays for ever and earns nothing → V = 0. (0,0): Right leads to (1,0), worth 0 → V = 0 + 0.9 × 0 = 0.
>
> **Improve.** At (1,0): Up = 1 + 0.9 × 0 = 1 versus Right = 0 + 0.9 × 0 = 0 → switch to **Up**. At (0,1): Right = 1 versus Up (blocked) = 0.9 × 1 = 0.9 → keep **Right**. At (0,0): Right = 0.9 × 0 = 0 versus Up = 0.9 × 1 = 0.9 → switch to **Up**.
>
> **Measure the new plan.** V((1,0)) = 1, V((0,1)) = 1, V((0,0)) = 0.9 × 1 = 0.9.
>
> **Improve again.** At (0,0) Right = 0.9 and Up = 0.9 tie, so keep Up. Nothing changes, so the plan is optimal. It took two improve steps.

> **Check Q11.1. Why does policy iteration stop when the plan stops changing, but value iteration stops when the values stop changing?**
>
> **Answer.** Policy iteration keeps an explicit plan, so "no move changed" is a clear stopping signal. Value iteration has no explicit plan until the end, so it watches the values instead.

> **Activity 11.1 — Policy iteration on the corridor**
>
> On the 1×3 corridor (goal +1 for entering cell 3, γ = 0.9), start with the plan "always Left". Run policy iteration. If two actions tie, keep the current one.

> **Answer**
>
> **Measure:** V(1) = V(2) = V(3) = 0 (the agent never reaches the goal). **Improve:** at 2, Right = 1 beats Left = 0 → Right; at 1, Right = 0.9 × 0 = 0 ties Left → keep Left. **Measure** (1: Left, 2: Right): V(2) = 1, V(1) = 0 (Left keeps it stuck). **Improve:** at 1, Right = 0.9 × 1 = 0.9 beats Left = 0 → Right. **Measure** (Right, Right): V(2) = 1, V(1) = 0.9. **Improve:** no change. Best plan: Right in both cells, with values (0.9, 1).

> **Remember**
>
> Policy iteration = measure → improve → repeat until the plan stops changing.

---

# 12. On-Policy and Off-Policy

> **The big idea**
>
> While learning, an agent may *behave* one way (with some random exploring) but be *learning about* a different plan (the best one). If the two are the same, it is on-policy; if they differ, it is off-policy.

> **Why this comes before the algorithms**
>
> The algorithms in Sections 13–17 are described as on-policy or off-policy, so we define the words first.

## 12.1 Two plans inside one agent

- The **behaviour policy** is the plan the agent actually follows while learning, for example ε-greedy with its random moves.
- The **target policy** is the plan the agent is trying to learn.

**On-policy:** the two are the same. The agent learns the value of exactly what it is doing, random mistakes included. Examples: SARSA, REINFORCE.

**Off-policy:** the two are different. The agent explores, but learns about the best plan. Examples: Q-learning, DQN.

| | On-policy | Off-policy |
|---|---|---|
| Behaviour vs target | The same | Different |
| What the update looks at next | The action actually taken next | The best possible next action |
| Examples | SARSA, REINFORCE | Q-learning, DQN |
| Can it learn from old data or another agent's data? | Not directly | Yes |
| What it learns | The value of the plan it really follows, mistakes included | The best plan, even while exploring |

## 12.2 In everyday terms

Think of a learner driver. Learning **on-policy** is like judging the routes you really drive, wrong turns included. Learning **off-policy** is like watching your own drives (or someone else's) but always asking "what would the *best* route have been?". Neither is always better: off-policy can reuse old experience; on-policy is often steadier and more realistic about the mistakes you will really make.

> **Check Q12.1. A robot explores with ε-greedy and learns with Q-learning. Is the plan it follows the same as the plan it is learning?**
>
> **Answer.** No. It behaves ε-greedily (sometimes random) but learns the best, fully greedy plan. That is off-policy.

> **Activity 12.1 — Classify the algorithm**
>
> Say whether each is on-policy or off-policy and what its update "looks at next": (a) SARSA, (b) Q-learning, (c) REINFORCE, (d) DQN.

> **Answer**
>
> (a) On-policy; the next action actually taken. (b) Off-policy; the best next action. (c) On-policy; the full return from its own episode. (d) Off-policy; the best next action, using a slowly updated copy of its network (Section 15.3).

> **Remember**
>
> On-policy learns about what it does. Off-policy learns about the best thing it could do.

---

# 13. Learning From Experience: The Algorithm Families, Monte Carlo and TD

> **The big idea**
>
> Without a map, an agent must learn values from what actually happens. It can wait for the end of a game and average the real total (Monte Carlo), or update after every single step using its next guess (TD). Everything after this section builds on TD.

## 13.1 The three families (a map of the rest of the module)

Up to Section 11 the agent knew the map. From now on it does not: it only has its own **experience**.

![The three model-free families: value-based, policy-based and actor–critic, with example algorithms.](figures/three-model-free-families.png)

*Figure 7. The three model-free families and their example algorithms.*

| Family | What it keeps | What it learns from | Sections |
|---|---|---|---|
| **Value-based** | A score Q(s, a) for each move | The surprise (TD error) after each step | 14–15 |
| **Policy-based** | The plan itself, as adjustable numbers | The total reward of whole games | 16 |
| **Actor–critic** | Both a plan (actor) and a score-keeper (critic) | The critic's surprise after each step | 17 |

> **Check Q13.1. Which family suits a smooth action such as a steering angle, and why?**
>
> **Answer.** Policy-based or actor–critic. Value-based methods must find the best of all actions, which is awkward when there are infinitely many angles; a plan can output an angle directly.

## 13.2 The learning rate: the step every update takes

All the methods from here on update in the same way: they nudge the old estimate part of the way towards a better guess called the **target**.

**Formula in words:** new estimate = old estimate + α × (target − old estimate)

The gap "target − old estimate" is the **surprise**: how wrong we were. α, the learning rate, says how much of the gap to close. With α = 0.5 we move halfway; with α = 0.1 we move a tenth of the way, which is slower but steadier.

> **Everyday version**
>
> You guess your bus journey takes 20 minutes. Today it takes 30. You do not throw your old guess away, and you do not trust one day completely either. With α = 0.5 you move halfway: new guess = 20 + 0.5 × (30 − 20) = **25 minutes**. Every method from here on learns exactly like this.

![An update moves the old estimate part of the way towards the target.](figures/update-step-toward-target.png)

*Figure 8. One update with α = 0.5: the old estimate 0.2 moves halfway towards the target 1.0, giving 0.6.*

## 13.3 Monte Carlo: wait until the end and average

**Monte Carlo (MC)** learning plays a whole game, then looks back: for each square it visited, it adds up the actual discounted rewards that followed (the **return**). That return is the target. Over many games, the values become the average of what really happened. No map is needed.

Everyday version: you only update your guess of how long your journey home takes **when you arrive**, using the real total time.

**Formula in words:** new V(square) = old V + α × (actual return after that square − old V)

Because the return is only known when the game ends, MC **updates only after the game finishes**, and so it only works for tasks that end.

> **Worked example — Monte Carlo on the 2×2 grid**
>
> The game from Activity 2.1: (0,0) —Right→ (1,0), reward 0; (1,0) —Right (blocked)→ (1,0), reward 0; (1,0) —Up→ goal, reward +1. γ = 0.9, α = 0.5, all values start at 0.
>
> | Step | Square | Actual return after this step | Return |
> |---|---|---|---|
> | 1 | (0,0) | 0 + 0.9 × 0 + 0.81 × 1 | 0.81 |
> | 2 | (1,0) | 0 + 0.9 × 1 | 0.9 |
> | 3 | (1,0) | 1 | 1 |
>
> **Updates** (using the first time each square was visited): V((0,0)) = 0 + 0.5 × (0.81 − 0) = **0.405**. V((1,0)) = 0 + 0.5 × (0.9 − 0) = **0.45**.
>
> After just one game, the reward at the end has already reached the start square.

> **Going deeper (optional): first-visit and every-visit**
>
> If a square is visited twice in one game, **first-visit MC** uses only the return after the first visit (as above); **every-visit MC** uses all of them. Every-visit would average 0.9 and 1 for (1,0), giving 0.95. Formally: V(S<sub>t</sub>) ← V(S<sub>t</sub>) + α [G<sub>t</sub> − V(S<sub>t</sub>)].

## 13.4 TD learning: update after every step

Waiting until the end is slow, and impossible if the game never ends. **Temporal-difference (TD)** learning updates after **every single step**. It does not know the full return yet, so it uses a shortcut target: the reward it just got plus γ × its *current guess* for the next square.

Everyday version: on your journey home you **update your arrival estimate at every stop**. If the first stop took longer than usual, you already know you will be late. You do not wait until you get home.

**Formula in words:** new V(here) = old V(here) + α × (reward + γ × V(next) − old V(here))

The bracket, target minus old guess, is the **TD error**, written δ ("delta"). It is the surprise from Figure 8. Using a guess to improve a guess is called **bootstrapping**; dynamic programming did the same (Section 8), but with the map instead of real experience. The goal's value is always 0.

> **Worked example — TD on the same game, played twice**
>
> γ = 0.9, α = 0.5, all values start at 0. Each row is one step, and the value changes immediately.
>
> | Game | Step | Target = reward + 0.9 × V(next) | δ = target − old | New value |
> |---|---|---|---|---|
> | 1 | (0,0) → (1,0) | 0 + 0.9 × 0 = 0 | 0 − 0 = 0 | V((0,0)) = 0 |
> | 1 | (1,0) → (1,0) | 0 + 0.9 × 0 = 0 | 0 − 0 = 0 | V((1,0)) = 0 |
> | 1 | (1,0) → goal | 1 (goal is worth 0) | 1 − 0 = 1 | V((1,0)) = 0.5 |
> | 2 | (0,0) → (1,0) | 0 + 0.9 × 0.5 = 0.45 | 0.45 − 0 = 0.45 | V((0,0)) = 0.225 |
> | 2 | (1,0) → (1,0) | 0 + 0.9 × 0.5 = 0.45 | 0.45 − 0.5 = −0.05 | V((1,0)) = 0.475 |
> | 2 | (1,0) → goal | 1 | 1 − 0.475 = 0.525 | V((1,0)) = 0.7375 |
>
> In game 1 only (1,0) changes, because only the last step had a reward. In game 2 the value spreads one more step back, to (0,0). This is the same "value flows backwards" pattern as Figure 5, but learned from experience instead of the map. With more games (and α made smaller over time), a learner following the Section 8.4 plan reaches the Section 8.4 values: V((1,0)) = 1 and V((0,0)) = 0.9.

> **Going deeper (optional): TD(0) in symbols**
>
> V(S<sub>t</sub>) ← V(S<sub>t</sub>) + α [ R<sub>t+1</sub> + γ V(S<sub>t+1</sub>) − V(S<sub>t</sub>) ], and δ = R<sub>t+1</sub> + γV(S<sub>t+1</sub>) − V(S<sub>t</sub>). The "0" in TD(0) means it looks just one step ahead.

## 13.5 From scoring squares to choosing moves

Sections 13.3–13.4 *score* squares for a fixed plan (**prediction**). To *improve* the plan without a map (**control**), the agent scores moves, Q(s, a), instead of squares, because choosing a move from square values would need the map to look ahead. Using the TD idea on Q gives the next two algorithms:

- **SARSA** (on-policy): target = reward + γ × Q(next square, the move actually taken next).
- **Q-learning** (off-policy): target = reward + γ × Q(next square, the best next move).

REINFORCE (Section 16) instead uses the Monte Carlo idea: the full return of the game.

## 13.6 DP vs Monte Carlo vs TD

| | Dynamic programming | Monte Carlo | TD |
|---|---|---|---|
| Needs the map? | Yes | No | No |
| Learns from | The map: all possible next squares | Whole games | Single steps |
| Target | Reward + γ × next value, averaged using the map | The actual return | Reward + γ × current guess of next value |
| Updates | Each sweep | After each game | After each step |
| Uses a guess to update a guess? | Yes | No | Yes |
| Works if the game never ends? | Yes | No | Yes |
| How noisy? | Not noisy (no sampling) | Noisy: one game's return can vary a lot | Steadier, but starts from rough guesses |
| Leads to | Value and policy iteration (10–11) | REINFORCE (16) | SARSA, Q-learning, DQN, actor–critic (14–17) |

![How far each method looks: DP looks one step at every possibility; MC follows one game to the end; TD takes one real step.](figures/dp-mc-td-compared.png)

*Figure 9. How far each method looks ahead to build its target.*

> **Check Q13.3. Why can Monte Carlo not be used for a task that never ends?**
>
> **Answer.** The return is only known when the game ends, so MC would never get to make an update.

> **Activity 13.3 — One MC update and one TD update**
>
> V(s) = 0.4, γ = 0.9, α = 0.1. (a) A game from s produced a return of 1.0. What is the new V(s) with Monte Carlo? (b) Instead, one step from s gave reward 0 and the next square has V = 0.8. What are δ and the new V(s) with TD?

> **Answer**
>
> (a) 0.4 + 0.1 × (1.0 − 0.4) = 0.4 + 0.06 = **0.46**. (b) Target = 0 + 0.9 × 0.8 = 0.72; δ = 0.72 − 0.4 = 0.32; new V = 0.4 + 0.1 × 0.32 = **0.432**.

> **Exam-style practice**
>
> **Question (4 marks).** Compare Monte Carlo and TD learning, giving one advantage of each.
>
> **Checked answer.** MC updates from the actual full return at the end of a game **(1)**; TD updates after every step using reward + γ × the current guess of the next value **(1)**. MC advantage: it does not rely on other guesses, so it is correct on average **(1)**. TD advantage: it learns during the game, works when the game never ends, and is less noisy **(1)**.

> **Remember**
>
> Every update: new = old + α × (target − old). MC's target is the real total at the end; TD's target is reward + γ × next guess, after every step.

---

# 14. Q-Learning

> **The big idea**
>
> Q-learning keeps a score for every move in every square. After each step it nudges that score towards "the reward I just got + γ × the best score available next". In the end, the best move in each square is simply the one with the highest score.

## 14.1 The Q-table

Think of a table with a row for every square and a column for every move. Each cell holds Q(s, a): "how good is this move here?". At the start every cell is 0. The agent plays, and after every step it updates one cell.

| Square | Q(·, Right) | Q(·, Up) |
|---|---|---|
| (0,0) | starts 0 | starts 0 |
| (1,0) | starts 0 | starts 0 |
| (0,1) | starts 0 | starts 0 |

Once learning is done, the plan is: in each square, pick the column with the bigger number.

## 14.2 The update rule

**Formula in words:** new Q(here, move) = old Q + α × (reward + γ × best Q in the next square − old Q)

It is the same "step towards the target" as Figure 8. The target uses the **best** score in the next square. For the goal, the best next score is 0 because the game is over.

> **Worked example — one Q-learning update**
>
> Old Q(s, a) = 0.2. The agent gets reward r = 1 and lands on the goal, so the best next score is 0. γ = 0.9, α = 0.5.
>
> 1. Target = 1 + 0.9 × 0 = 1
> 2. Surprise (TD error) = 1 − 0.2 = 0.8
> 3. New Q = 0.2 + 0.5 × 0.8 = **0.6**
>
> These are exactly the numbers in Figure 8.

> **Going deeper (optional): the update in symbols**
>
> Q(s, a) ← Q(s, a) + α [ r + γ max<sub>a′</sub> Q(s′, a′) − Q(s, a) ]. max<sub>a′</sub> Q(s′, a′) means "the biggest Q-value over all moves a′ in the next state s′".

## 14.3 Exploring while learning

If the agent always picked its highest score, it might never try a move that is secretly better (Section 3.2). So it behaves ε-greedily: mostly the best move, sometimes a random one, with ε lowered over time.

## 14.4 Why Q-learning is off-policy

Its target uses the **best** next move, even if the agent is about to take a random one. So it learns about the best plan while behaving in an exploratory way: off-policy (Section 12).

> **Common mistake**
>
> "Q-learning always takes the greedy move." No. It *learns about* the greedy (best) plan, but it *behaves* ε-greedily so that it keeps exploring.

> **Check Q14.1. Why is Q-learning called off-policy?**
>
> **Answer.** Its target uses the best possible next move, whatever the agent actually does next, so it learns the best plan while behaving exploratorily.

> **Activity 14.1 — Trace a Q-learning update**
>
> Old Q(s, a) = 1.5, reward r = 0, γ = 0.9, best Q in the next square = 2, α = 0.1. Find the target, the surprise and the new Q.

> **Answer**
>
> Target = 0 + 0.9 × 2 = 1.8. Surprise = 1.8 − 1.5 = 0.3. New Q = 1.5 + 0.1 × 0.3 = **1.53**.

> **Activity 14.2 — Explain a decision**
>
> An engineer wants a robot vacuum to learn from data already recorded by other vacuums in the building. She chooses Q-learning, not SARSA. Explain why.

> **Answer**
>
> Q-learning is off-policy, so it can learn from data produced by a different behaviour (the other vacuums). SARSA is on-policy: its updates assume the actions came from its own current plan, so it cannot directly reuse other agents' data.

> **Remember**
>
> Q-learning: score every move; target = reward + γ × best next score; learns the best plan while exploring.

---

# 15. SARSA and Deep Q-Networks

> **The big idea**
>
> SARSA is Q-learning's careful twin: its target uses the move it will *really* take next, mistakes included. DQN replaces the Q-table with a neural network so the idea works in huge worlds such as video games played from the screen.

## 15.1 SARSA

**Formula in words:** new Q(here, move) = old Q + α × (reward + γ × Q(next square, the move actually taken next) − old Q)

The name lists the five things one update uses: **S**tate, **A**ction, **R**eward, next **S**tate, next **A**ction. Because it uses the move it really takes, SARSA is **on-policy**.

> **Worked example — Q-learning and SARSA side by side**
>
> In the 2×2 grid the agent is at (0,0), moves Up to (0,1) and gets reward 0. Old Q((0,0), Up) = 0.5, α = 0.1, γ = 0.9. In (0,1) the scores are Q(Right) = 1 and Q(Up) = 0 (Up hits the edge). This time the exploring agent is going to choose **Up** next.
>
> - **Q-learning** uses the *best* next score, 1: target = 0 + 0.9 × 1 = 0.9; new Q = 0.5 + 0.1 × (0.9 − 0.5) = **0.54**.
> - **SARSA** uses the move it *will* take, Up, worth 0: target = 0 + 0.9 × 0 = 0; new Q = 0.5 + 0.1 × (0 − 0.5) = **0.45**.
>
> Q-learning is optimistic ("I will play perfectly next"). SARSA is realistic ("I know I sometimes explore badly").

> **Going deeper (optional): SARSA in symbols**
>
> Q(s, a) ← Q(s, a) + α [ r + γ Q(s′, a′) − Q(s, a) ], where a′ is the action the agent actually chooses in s′.

## 15.2 The cliff walk: where the difference matters

![The cliff walk: the shortest path runs along the cliff edge; a safer path goes further away.](figures/cliff-walk.png)

*Figure 10. The cliff walk. Falling off the cliff gives a big penalty and sends the agent back to the start.*

A grid has a cliff along the bottom. The shortest path hugs the edge; a safer path stays further away.

- **Q-learning** learns the edge path, because its target assumes perfect play from now on. That is best *if exploring stops* when the robot is used for real.
- **SARSA** learns the safer path, because its target includes the occasional random step that could fall off the edge.

In everyday terms: Q-learning happily walks right along the edge of a cliff path because it is the shortest route "if I never slip"; SARSA keeps a step away from the edge because it knows it sometimes stumbles.

> **Check Q15.1. In the cliff walk, which algorithm would a safety engineer prefer if the robot keeps exploring while in use?**
>
> **Answer.** SARSA. Its on-policy updates include the random steps the robot really takes, so it learns a path that is safe even with continued exploring.

## 15.3 Deep Q-Networks (DQN)

A Q-table needs one row for every state. A video-game screen has millions of pixels, so there are far too many possible screens to list. A **Deep Q-Network (DQN)** replaces the table with a **neural network**: a function made of layers of simple adjustable units. You give it the screen, and it gives back one score for each move.

Think of it like this: you have never walked down most streets in the world, but you can still guess whether a new street looks safe, because it looks like streets you know. In the same way, the network gives similar screens similar scores, so it can score screens it has never seen before.

Two tricks keep DQN stable:

- **Experience replay:** keep a memory of past steps and learn from small random handfuls of them (**minibatches**). Learning only from the last few steps is like revising only yesterday's lesson: they are all too similar.
- **Target network:** work out the targets with a second copy of the network that is updated only now and then. Otherwise the target moves every time the network learns, like trying to hit a goal that keeps sliding away.

DQN learned to play many Atari games from the screen alone (Mnih et al., 2015).

> **Activity 15.1 — DQN vs Q-table**
>
> Why can a DQN be used where a Q-table cannot? Give one example.

> **Answer**
>
> A Q-table needs one entry per state–move pair, which is impossible for states such as raw screen pixels. A DQN uses a neural network that gives similar scores to similar states, so it does not need a row for each one. Example: Atari games played from the screen.

> **Activity 15.2 — Choose a method**
>
> A robot's state is 512 continuous sensor readings. Is a Q-table or a DQN feasible? Why?

> **Answer**
>
> A DQN. With 512 continuous numbers there are infinitely many states, so a table is impossible. The network approximates the scores and generalises between similar readings, at the cost of being harder to train and debug.

> **Remember**
>
> SARSA = on-policy, uses the move it really takes, safer. DQN = Q-learning with a neural network instead of a table.

---

# 16. Learning the Plan Directly: REINFORCE

> **The big idea**
>
> Instead of scoring moves, adjust the plan itself: after each game, make the moves you took more likely if the game went well and less likely if it went badly.

## 16.1 Why learn the plan directly?

- When actions are amounts, not a short list. A steering wheel can turn to any angle, so there is no small table of moves to score.
- When the best plan is to be unpredictable. In rock–paper–scissors, always playing the same move loses.
- When we want behaviour to change gradually as learning goes on, not jump suddenly.

## 16.2 The idea in words

Think of the plan as a set of dials, one setting how likely each move is. **REINFORCE** plays a whole game, works out the return after each move, and then turns the dials so that each move it took becomes more likely, more so when the return after it was big. Moves followed by big returns are pushed up strongly; moves followed by poor returns are pushed up only a little (or pushed down, with a baseline, Section 16.3).

Everyday version: a basketball player who scores tends to repeat that shot more often; a shot that misses badly gets used less.

Because it uses whole-game returns, REINFORCE is a **Monte Carlo** method (Section 13.3) and is **on-policy**.

> **Worked example — the returns REINFORCE uses**
>
> A game has three moves with rewards 0, 0, then 1, and γ = 0.9. Work backwards from the end:
>
> - Return after the last move = 1
> - Return after the middle move = 0 + 0.9 × 1 = 0.9
> - Return after the first move = 0 + 0.9 × 0.9 = 0.81
>
> All three moves are made more likely, the last one most strongly because it was closest to the reward. Notice that every move gets some credit, even if one of them was actually a poor move.

> **Going deeper (optional): the policy gradient formula**
>
> With the plan written π<sub>θ</sub>(a | s) (θ = its adjustable numbers), REINFORCE updates θ ← θ + α G<sub>t</sub> ∇<sub>θ</sub> ln π<sub>θ</sub>(A<sub>t</sub> | S<sub>t</sub>) for each step t. ∇<sub>θ</sub> ln π<sub>θ</sub> points in the direction that makes the chosen action more likely, and G<sub>t</sub> scales the push by how good the result was. This comes from the policy gradient theorem, ∇<sub>θ</sub>J(θ) = E[ G<sub>t</sub> ∇<sub>θ</sub> ln π<sub>θ</sub>(A<sub>t</sub> | S<sub>t</sub>) ], where J(θ) is the expected return. (Some books include an extra factor γ<sup>t</sup>; practical code usually leaves it out.)

## 16.3 The noise problem and the fix

The return from one game can vary a lot just by luck, so REINFORCE's pushes are **noisy** (statisticians say it has *high variance*): correct on average, but jumpy from game to game, which makes learning slow.

The standard fix is a **baseline**: instead of the return, use "return minus what we normally expect here". A move then only gets pushed up if it did *better than usual*, and down if it did worse. The quantity "better than usual" is called the **advantage**. Actor–critic (Section 17) learns that baseline automatically.

> **Check Q16.1. In the worked example, why does the first move get less credit than the last one?**
>
> **Answer.** The reward is further away from the first move, so it is discounted more (0.81 versus 1).

> **Activity 16.1 — Compute returns**
>
> Rewards after moves 1 to 4 are 0, 2, 0, 1 and γ = 0.5. Find the return after each move (work backwards).

> **Answer**
>
> After move 4: 1. After move 3: 0 + 0.5 × 1 = 0.5. After move 2: 2 + 0.5 × 0.5 = 2.25. After move 1: 0 + 0.5 × 2.25 = **1.125**.

> **Activity 16.2 — Predict what happens**
>
> A learner uses a fixed baseline of 100 when returns are usually between 0 and 10. Predict what happens.

> **Answer**
>
> On average the direction of learning is unchanged, but every "return − 100" is about −90 to −100, so every move taken is pushed down hard each game. The updates are huge and jumpy, so learning becomes unstable. Fix: learn the baseline so that it tracks the returns you normally get.

> **Remember**
>
> REINFORCE: after each game, make the moves you took more likely, in proportion to how well things went. Noisy; a baseline helps.

---

# 17. Actor–Critic

> **The big idea**
>
> Two parts learn together: the **actor** chooses moves (the plan) and the **critic** judges them after every step ("better or worse than I expected?"). The actor listens to the critic.

## 17.1 How it works

![The actor–critic loop: the actor picks an action; the critic's TD error tells the actor how good it was.](figures/actor-critic-loop.png)

*Figure 11. The actor–critic loop.*

- The **actor** is a plan, like REINFORCE's.
- The **critic** keeps a value V(s) for each state, learned by TD (Section 13.4).

After every step, the critic works out its surprise:

**Formula in words:** δ = reward + γ × V(next) − V(here)

- If δ > 0, things went **better** than expected, so the actor makes that move **more** likely.
- If δ < 0, things went **worse** than expected, so the actor makes that move **less** likely.
- The critic also moves V(here) towards its target, so its predictions improve.

This δ is the same TD error as in Section 13.4, and it plays the role of the "better than usual" advantage from Section 16.3.

> **Worked example — one actor–critic step**
>
> V(here) = 0.5, reward = 1, V(next) = 0.4, γ = 0.9.
>
> δ = 1 + 0.9 × 0.4 − 0.5 = 1 + 0.36 − 0.5 = **0.86**.
>
> δ is positive, so the actor makes this move more likely. The critic moves V(here) towards its target, 1 + 0.36 = 1.36.

> **Going deeper (optional): the two update rules**
>
> Advantage: A<sub>π</sub>(s, a) = Q<sub>π</sub>(s, a) − V<sub>π</sub>(s), estimated by δ = r + γV<sub>w</sub>(s′) − V<sub>w</sub>(s). Actor: θ ← θ + α δ ∇<sub>θ</sub> ln π<sub>θ</sub>(a | s). Critic: w ← w + β δ ∇<sub>w</sub> V<sub>w</sub>(s), where w are the critic's numbers and β its learning rate.

## 17.2 Why it learns faster than REINFORCE

REINFORCE waits until the end of a game and then uses one noisy total. Actor–critic gets a judgement after **every** step, and each one-step surprise is much less noisy than a whole-game total. More, steadier feedback means faster learning. Modern methods such as A2C and PPO, which have been used to train game-playing and robot agents, are actor–critic methods.

> **Check Q17.1. If δ = −0.3, what should the actor do to the probability of the move it took? Why?**
>
> **Answer.** Lower it: the result was worse than the critic expected.

> **Activity 17.1 — Compute a surprise**
>
> V(here) = 2.0, reward = 1, V(next) = 1.5, γ = 0.9. Find δ. Should the actor make the move more or less likely?

> **Answer**
>
> δ = 1 + 0.9 × 1.5 − 2.0 = 1 + 1.35 − 2.0 = **0.35**. Positive, so more likely.

> **Activity 17.2 — Explain in your own words**
>
> Explain why actor–critic usually learns faster than REINFORCE. If you use the word "variance", explain what it means.

> **Answer**
>
> REINFORCE updates once per game, using the game's total reward. Actor–critic updates after every step, using the critic's surprise, so it gets many more learning signals from the same play. "Variance" means how much a number jumps around from one try to the next: a whole game's total jumps around a lot, while a one-step surprise is steadier, so actor–critic's updates are less noisy.

> **Remember**
>
> Actor = plan, critic = judge. The critic's surprise δ after each step tells the actor what to do more or less often.

---

# 18. Real-World Applications and Reward Design

> **The big idea**
>
> RL is used wherever a system must make a sequence of decisions. In every case, the reward decides what behaviour is learned, so choosing the reward is a design decision with real consequences.

## 18.1 Where RL is used

For each example, ask two questions: **what is learned?** and **what reward is it chasing?**

| Area | Example | What is learned | Reward |
|---|---|---|---|
| Games | Agents for Atari, Go and chess | A plan and/or a value function | Game score, or win/loss |
| Recommendations | A video platform choosing what to show next | A ranking plan | Clicks, watch time |
| Robotics | A robot arm learning to grasp or pour, trained in simulation first | A control plan from sensors to motors | Task success, minus penalties for drops or collisions |
| Healthcare | A rehabilitation robot adjusting exercise difficulty | A personalisation plan | Measured patient progress |
| Energy | A building's heating learning when to pre-heat | A control plan | Minus energy cost, minus a discomfort penalty |
| Traffic | Traffic lights learning their timing | A signalling plan | Minus the average waiting time |

## 18.2 Reward design: "you get what you reward"

An RL agent will find **any** way to collect reward, including ways nobody intended. This is called **reward hacking**.

- In a real example, a boat-racing game agent rewarded for hitting targets learned to drive in circles hitting the same targets again and again, and never finished the race (Clark & Amodei, 2016).
- A recommender rewarded only for watch time may push extreme or repetitive videos that keep people watching but leave them feeling worse.
- A robot rewarded only for speed may learn unsafe shortcuts.

> **Why this matters**
>
> The reward is chosen by people, and it shapes the behaviour of the agent and, often, of the people using it. Before you trust an RL system, ask: **"What is the reward, who chose it, and whose behaviour does it shape?"**

> **Check Q18.1. In the heating example, why is a discomfort penalty needed?**
>
> **Answer.** Without it, the cheapest plan is to switch the heating off completely: "optimal" for the reward but unacceptable for the people in the building.

> **Activity 18.1 — Design a reward, predict the behaviour**
>
> A delivery drone is trained with RL. Propose a reward, predict one behaviour it will learn, then name one behaviour you did *not* intend.

> **Answer**
>
> Reward: +10 for an on-time delivery, −20 for a crash, −1 per minute late, −0.1 per unit of battery used. Intended: quick, efficient routes. Unintended: flying very close to buildings or trees to save time, because near-misses are not penalised. Fix: add a penalty for coming too close to obstacles, and test in simulation first.

> **Activity 18.2 — Find the error**
>
> A cleaning robot gets +10 for cleaning a dirty patch, −5 for bumping furniture and +1 per minute of running. It learns to circle and "clean" the same patch again and again. Find the flaw and fix it.

> **Answer**
>
> The +1 per minute rewards simply staying switched on, and the +10 can be earned repeatedly if the same patch is detected as dirty again. Fix: remove the per-minute bonus (or make it −1 per minute), mark patches as cleaned so they cannot pay twice, and add a bonus for finishing the whole room. Any part of a reward that can be exploited will be.

> **Remember**
>
> The agent learns whatever the reward pays for. Design it carefully and check for loopholes.

---

# 19. Mind Map and Summary

![Mind map of the Behavioural AI module.](figures/mind-map.png)

*Figure 12. Mind map of the module.*

| Idea | One line to remember |
|---|---|
| Reinforcement learning | Learn from rewards by trial and error; no right answers given |
| MDP | States, actions, transitions, rewards, discount; the present state is enough (Markov) |
| Discount γ | Later rewards count less: 0.9, 0.81, 0.729, … |
| Value | Points you expect from here if you follow the plan |
| Bellman | Value here = reward now + γ × value next |
| Dynamic programming | Have the map: measure the plan, improve it, or do both at once (value iteration) |
| Update rule | new = old + α × (target − old) |
| Monte Carlo | Target = real total at the end of the game |
| TD | Target = reward + γ × next guess, after every step |
| Q-learning | Off-policy; target uses the best next move |
| SARSA | On-policy; target uses the move really taken next; safer |
| DQN | Q-learning with a neural network instead of a table |
| REINFORCE | Make taken moves more likely in proportion to the return; noisy |
| Actor–critic | Actor = plan; critic's surprise δ trains it every step |
| Reward design | You get what you reward; check for loopholes |

---

# 20. Case Studies

> **Case study 1 — The video recommender**
>
> A streaming service trains an RL recommender whose reward is total watch time. After launch, people watch more hours but report feeling worse and complain about repetitive, extreme content.
>
> **Tasks:** (a) name the agent, environment, action, state and reward; (b) explain what the agent learned that nobody intended; (c) propose a better reward and one safeguard; (d) who chose the reward, and whose behaviour does it shape?

> **Answer**
>
> (a) Agent = the recommendation plan; environment = the users and the video catalogue; action = which video to show; state = the user's history and context; reward = watch time. (b) It learned whatever keeps people watching, such as autoplay chains and sensational or repetitive content, whether or not it is good for them. (c) Combine watch time with satisfaction signals (surveys, "not interested" clicks, variety of content) and cap daily exposure; test changes on a small group first and monitor for harmful drift. (d) The company chose the reward; it shapes the behaviour of every user, so the company carries an ethical responsibility.

> **Case study 2 — The cliff-side delivery robot**
>
> A delivery robot crosses a campus where the shortest path runs beside a steep drop. It is trained in simulation with ε-greedy exploring and keeps exploring (ε = 0.1) after it starts work, so that it can adapt to new routes.
>
> **Tasks:** (a) would you choose Q-learning or SARSA, and why? (b) what would the other algorithm learn? (c) name two more safeguards.

> **Answer**
>
> (a) SARSA: it is on-policy, so it learns the value of what it really does, including the occasional random step, and therefore keeps away from the edge. (b) Q-learning would learn the shortest path right along the edge, which is only safe if exploring stops; with ε = 0.1 the robot would sometimes step off. (c) Explore only in simulation or switch exploring off near danger; add a large penalty for being near the edge; add a physical barrier or speed limit that does not depend on the learning at all.

> **Case study 3 — The smart classroom thermostat**
>
> A school wants an RL controller for one classroom's heating. Every 10 minutes it can set the heater to Off, Low or High. Sensors give the room temperature, the outside temperature, the time and whether the room is occupied.
>
> **Tasks:** (a) write the states, actions and reward; (b) would you use a model-based or a model-free method, and why? (c) which algorithm family suits three discrete actions? (d) name one behaviour your reward might cause that you did not intend.

> **Answer**
>
> (a) State = (room temperature, outside temperature, time of day, occupied?). Actions = Off, Low, High. Reward each step = −(energy used) − (a penalty for being outside 19–22 °C while the room is occupied). (b) Model-free is simpler if no accurate model of the building exists, but training should happen in a simulator because real-world trial and error is slow and uncomfortable; a model-based method is a good choice if a reliable physical model is available. (c) Value-based, for example DQN, because the temperature readings are continuous but there are only three actions. (d) If the comfort penalty only applies when the room is occupied, the heater may switch off overnight and leave the room cold when the first class arrives; add a penalty for the temperature at arrival time, or a pre-heating reward.

---

# 21. Mixed Practice

Try each question before you read the answer.

**P1.** A game gives rewards 1, 0, 3 and γ = 0.5. What is the return from the start?

> **Answer:** 1 + 0.5 × 0 + 0.25 × 3 = **1.75**.

**P2.** In one state, action A gives reward 0 and leads to a state worth 4; action B gives reward 2 and leads to a state worth 3. With γ = 0.9, which is better, and what is the best value?

> **Answer:** A: 0 + 0.9 × 4 = 3.6. B: 2 + 0.9 × 3 = 4.7. B is better; best value = **4.7**.

**P3.** An action succeeds with chance 0.8 (reward 10) and fails with chance 0.2 (reward 0); both end the game. What is its Q-value?

> **Answer:** Q = 0.8 × 10 + 0.2 × 0 = **8** (the average reward).

**P4.** Q(s, a) = 4, reward = 2, γ = 0.9, best next score = 5, α = 0.5. What is the new Q with Q-learning?

> **Answer:** Target = 2 + 0.9 × 5 = 6.5; surprise = 6.5 − 4 = 2.5; new Q = 4 + 0.5 × 2.5 = **5.25**.

**P5.** Same numbers, but the move actually taken next has a score of 2. What is the new Q with SARSA?

> **Answer:** Target = 2 + 0.9 × 2 = 3.8; surprise = 3.8 − 4 = −0.2; new Q = 4 + 0.5 × (−0.2) = **3.9**.

**P6.** On-policy or off-policy? (a) Learning the best plan from a log of another robot's moves; (b) REINFORCE; (c) SARSA.

> **Answer:** (a) Off-policy. (b) On-policy. (c) On-policy.

**P7.** Why is the goal (terminal) square always worth 0?

> **Answer:** The game is over, so no more reward can be collected; the reward for reaching the goal is counted in the square before it.

**P8.** Give one reason to use γ less than 1, and one problem with γ = 1.

> **Answer:** γ < 1 prefers sooner rewards and keeps totals finite. With γ = 1, a game that never ends can have an endless (infinite) total.

**P9.** V(s) = 0.6, reward = 0, V(next) = 1, γ = 0.9, α = 0.5. Do one TD update.

> **Answer:** Target = 0 + 0.9 × 1 = 0.9; δ = 0.9 − 0.6 = 0.3; new V = 0.6 + 0.5 × 0.3 = **0.75**.

---

# 22. End-of-Module Test

Total: 55 marks. Suggested time: 55 minutes. Answer without notes, then mark yourself with the scheme below.

## Questions

1. Define reinforcement learning and say how it differs from supervised learning. [3]
2. A thermostat learns to control heating. Identify the agent, the environment and one reward. [3]
3. Rewards in a game are 0, 0, 4 and γ = 0.5. Compute the return from the start. [2]
4. State the Markov property and give one example of a state that does not satisfy it. [3]
5. Corridor of cells 1, 2, 3 (+1 for entering 3, the goal), γ = 0.8, plan "always Right". Compute V(1) and V(2). [3]
6. Explain the difference between model-based and model-free learning. [2]
7. Write the Bellman optimality equation in words and say what γ does in it. [3]
8. Action A: reward 1, next best value 2. Action B: reward 0, next best value 3. γ = 0.9. Find the best value and the best action. [3]
9. Why does dynamic programming need the model? [2]
10. Give two differences between value iteration and policy iteration. [2]
11. Define behaviour policy and target policy. [2]
12. Why is Q-learning off-policy? [2]
13. Q(s, a) = 2, reward = 1, γ = 0.9, best next score = 3, α = 0.2. Compute the new Q with Q-learning. [3]
14. Same numbers, but SARSA, where the move actually taken next has score 1. Compute the new Q. [3]
15. In the cliff walk, which algorithm learns the safer path, and why? [2]
16. Name the two stabilising ideas in DQN and say what each does. [2]
17. Why are REINFORCE's updates noisy? Give one remedy. [2]
18. V(here) = 1.2, reward = 0.5, V(next) = 1, γ = 0.9. Compute δ and say what the actor does. [3]
19. Explain the roles of the actor and the critic. [3]
20. A recommender is rewarded for watch time. Describe two possible unintended behaviours and one ethical consequence. [4]
21. V(s) = 0.5, reward = 1, the next state is the goal, γ = 0.9, α = 0.2. Do one TD update and say why TD can learn before the game ends but Monte Carlo cannot. [3]

## Mark scheme

| Q | Answer (marks) |
|---|---|
| 1 | An agent learns to act by interacting with an environment and receiving rewards (1); trial and error, no correct answers given (1); supervised learning is given the correct output for each input, RL only a reward saying how good the result was (1). |
| 2 | Agent: the heating controller (1); environment: the room and the weather (1); reward, e.g. −energy used minus a penalty for being too cold (1). |
| 3 | 0 + 0.5 × 0 + 0.25 × 4 (1) = 1 (1). |
| 4 | The current state contains everything needed to predict what happens next; the history adds nothing (2); example: only the cards in your hand, or one camera image that cannot show what is behind a robot (1). |
| 5 | V(2) = 1 + 0.8 × 0 = 1 (1); V(1) = 0 + 0.8 × 1 = 0.8 (2). |
| 6 | Model-based uses or learns the map (transitions and rewards) and plans with it (1); model-free learns values or a plan directly from experience (1). |
| 7 | The best value of a state is the best action's reward now plus the discounted value of the next state (2); γ makes future value count less than immediate reward (1). |
| 8 | A: 1 + 0.9 × 2 = 2.8; B: 0 + 0.9 × 3 = 2.7 (2); best value 2.8, action A (1). |
| 9 | Its update adds up over every possible next state using the transition chances and rewards, so these must be known (2). |
| 10 | Any two: value iteration merges measuring and improving, policy iteration alternates them; value iteration stops when values settle, policy iteration when the plan stops changing; value iteration sweeps are cheap, policy iteration rounds are expensive (1 each). |
| 11 | Behaviour policy: the plan used to choose actions while learning (1). Target policy: the plan being learned (1). |
| 12 | Its target uses the best next move (1), whatever the agent actually does next, so it learns the best plan while exploring (1). |
| 13 | Target = 1 + 0.9 × 3 = 3.7; surprise = 1.7 (1); new Q = 2 + 0.2 × 1.7 (1) = 2.34 (1). |
| 14 | Target = 1 + 0.9 × 1 = 1.9; surprise = −0.1 (1); new Q = 2 + 0.2 × (−0.1) (1) = 1.98 (1). |
| 15 | SARSA (1): its on-policy target includes the exploring steps that could fall off the cliff (1). |
| 16 | Experience replay: learning from random handfuls of stored steps breaks the link between similar consecutive steps (1). Target network: a copy updated only now and then keeps the target steady (1). |
| 17 | One game's return varies a lot by luck (1); remedy: subtract a baseline, or use a critic (actor–critic) (1). |
| 18 | δ = 0.5 + 0.9 × 1 − 1.2 (1) = 0.2 (1); positive, so the actor makes the move more likely (1). |
| 19 | Actor: the plan that chooses moves (1). Critic: a value function that judges them (1) and supplies the TD error used to update the actor and itself (1). |
| 20 | Any two unintended behaviours, e.g. promoting sensational or addictive content, ignoring wellbeing, showing repetitive content (1 each); ethical consequence, e.g. it shapes users' behaviour for the platform's benefit, so its designers are responsible for the reward chosen (2). |
| 21 | Target = 1 + 0.9 × 0 = 1; δ = 1 − 0.5 = 0.5; new V = 0.5 + 0.2 × 0.5 = 0.6 (2); TD's target uses the next state's current guess, available after one step, whereas MC needs the full return, known only at the end (1). |

---

# 23. Learning Material List

Titles are given so that you can find them; check availability before relying on a link.

| Resource | Type | Use it for |
|---|---|---|
| Sutton & Barto, *Reinforcement Learning: An Introduction* (2nd ed.), free online from the authors | Textbook | The standard reference; chapters 1–6 match Sections 1–14 |
| David Silver, *Introduction to Reinforcement Learning* lectures (UCL / DeepMind, YouTube) | Video lectures | Lectures 1–7 match Sections 4–17 |
| Hugging Face, *Deep Reinforcement Learning Course* | Free online course | Hands-on Q-learning and DQN with exercises |
| OpenAI, *Spinning Up in Deep RL* | Web tutorial | Policy gradients and actor–critic (Sections 16–17) |
| Gymnasium (Python library) | Software | Try FrozenLake and CliffWalking (Sections 14–15) |
| Stable-Baselines3 (Python library) | Software | Ready-made DQN, A2C and PPO |
| Mnih et al. (2015), *Human-level control through deep reinforcement learning* | Paper | The original DQN paper (Section 15.3) |

## Suggested path

1. Sections 1–7 with Sutton & Barto chapters 1–3.
2. Sections 8–11 with Silver lectures 2–3.
3. Sections 12–15: run Q-learning on CliffWalking in Gymnasium and compare it with SARSA.
4. Sections 16–17 with Spinning Up.

---

# 24. Glossary

| Term | Meaning |
|---|---|
| **Action (a)** | A choice available to the agent. |
| **Actor–critic** | A method with a plan (actor) and a value function (critic) that learn together. |
| **Advantage** | How much better a move did than usual; estimated by the TD error δ. |
| **Agent** | The learner and decision-maker. |
| **Baseline** | "What we normally expect", subtracted from the return to make REINFORCE less noisy. |
| **Behaviour policy** | The plan the agent actually follows while learning. |
| **Bellman equation** | Value here = reward now + γ × value of the next state. |
| **Bootstrapping** | Updating a guess using another guess (DP and TD do this; Monte Carlo does not). |
| **Contraction** | (Optional) An update that always brings two guesses closer together; why value iteration settles. |
| **Credit assignment** | Working out which earlier actions deserve credit for a later reward. |
| **Discount (γ)** | How much a reward one step later is worth now (between 0 and 1). |
| **DQN** | Deep Q-Network: Q-learning with a neural network instead of a table. |
| **Dynamic programming** | Solving an MDP with the map, by sweeping the Bellman equation over all states. |
| **Environment** | Everything the agent interacts with. |
| **Episode** | One complete run from start to finish (one game). |
| **ε-greedy** | With chance ε do a random action; otherwise the best-known action. |
| **Experience replay** | Learning from random handfuls of stored past steps. |
| **Exploration / exploitation** | Trying something new / using what currently looks best. |
| **First-visit / every-visit MC** | Monte Carlo using only the first visit to a state in a game / every visit. |
| **Fixed point** | (Optional) A set of values that no longer changes when updated. |
| **Greedy** | Always choosing the action with the highest current score. |
| **Learning rate (α)** | How much of the gap between the old estimate and the target each update closes. |
| **Markov property** | The current state is enough to predict what happens next. |
| **MDP** | Markov Decision Process: states, actions, transitions, rewards, discount. |
| **Minibatch** | A small random handful of stored steps. |
| **Model** | The agent's map of the world: where each move leads and what it earns. |
| **Model-based / model-free** | Planning with a map / learning directly from experience without one. |
| **Monte Carlo (MC)** | Learning values by averaging the actual returns of complete games. |
| **Neural network** | A function made of layers of simple adjustable units; used in DQN. |
| **On-policy / off-policy** | Learns about the plan it follows / learns about a different (usually the best) plan. |
| **Policy (π)** | The agent's plan: which action to take in each state. |
| **Policy evaluation** | Working out the value of every state for a fixed plan. |
| **Policy gradient** | (Optional) Adjusting a plan's numbers in the direction that increases expected return. |
| **Policy improvement** | Switching, in every state, to the action with the best "reward + γ × next value". |
| **Policy iteration** | Repeating: evaluate the plan, then improve it, until it stops changing. |
| **Prediction / control** | Scoring a fixed plan / improving the plan. |
| **Q-learning** | Off-policy method that learns move scores using the best next move. |
| **Q-value Q(s, a)** | Expected return from taking action a in state s, then following the plan. |
| **REINFORCE** | Policy method that, after each game, makes the moves taken more likely in proportion to the return. |
| **Return** | The total of the rewards from now on, each discounted by how far away it is. |
| **Reward (r)** | The points given after an action. |
| **Reward hacking** | The agent exploiting a loophole in the reward instead of doing the intended task. |
| **SARSA** | On-policy method that learns move scores using the move actually taken next. |
| **State (s)** | A description of the current situation. |
| **Target** | The better guess an update moves towards. |
| **Target network** | A copy of the DQN network, updated only occasionally, used to compute steady targets. |
| **Target policy** | The plan the agent is trying to learn. |
| **TD error (δ)** | The surprise: target minus current estimate. |
| **TD learning** | Updating values after every step using reward + γ × the next state's current guess. |
| **Transition** | Where a move leads (and, if uncertain, with what chance). |
| **Value V(s)** | The return the agent expects from state s if it follows its plan. |
| **Value iteration** | Sweeping "keep the biggest reward + γ × next value" over all states until it settles. |
| **Variance** | How much a number jumps around from one try to the next ("noisiness"). |

---

# 25. References and Revision Notes

## 25.1 References

1. Sutton, R. S., & Barto, A. G. (2018). *Reinforcement Learning: An Introduction* (2nd ed.). MIT Press.
2. Bellman, R. (1957). *Dynamic Programming*. Princeton University Press.
3. Watkins, C. J. C. H., & Dayan, P. (1992). Q-learning. *Machine Learning*, 8, 279–292.
4. Rummery, G. A., & Niranjan, M. (1994). *On-line Q-learning using connectionist systems* (Technical Report CUED/F-INFENG/TR 166). Cambridge University Engineering Department.
5. Williams, R. J. (1992). Simple statistical gradient-following algorithms for connectionist reinforcement learning. *Machine Learning*, 8, 229–256.
6. Konda, V. R., & Tsitsiklis, J. N. (2000). Actor-critic algorithms. *Advances in Neural Information Processing Systems*, 12.
7. Mnih, V., et al. (2015). Human-level control through deep reinforcement learning. *Nature*, 518, 529–533.
8. Puterman, M. L. (1994). *Markov Decision Processes*. Wiley.
9. Skinner, B. F. (1938). *The Behavior of Organisms*. Appleton-Century.
10. Clark, J., & Amodei, D. (2016). Faulty reward functions in the wild. *OpenAI Blog*.

**Attribution.** The grid world, corridor and cliff-walk examples follow the standard teaching examples in Sutton & Barto (2018); all numbers in them were recalculated for this module.

## 25.2 Revision notes

| Version | Change | Where |
|---|---|---|
| 3.0 | Rewritten for beginners: every section now opens with **The big idea** and closes with **Remember**; plain-words explanation before every formula, with a **Formula in words** line | All sections |
| 3.0 | Symbols cut from 16 to the 8 needed for the core path; the rest moved into clearly labelled **Going deeper (optional)** boxes | Notation; Sections 2, 4, 5, 7–10, 13–17 |
| 3.0 | Added everyday analogies (a mouse learning a maze, a restaurant, a learner driver, a bus journey) alongside the 2×2 grid used for all calculations | Running examples; Sections 1–3, 5–7, 12, 13, 15, 18 |
| 3.0 | Added two figures: value spreading back from the goal, and an update as a step towards a target | Sections 8 and 13 |
| 3.0 | Merged the add-on Monte Carlo and TD material into Section 13, with a shared learning-rate explanation (13.2) used by Sections 14–17 | Section 13 |
| 3.0 | Added a Q-table illustration, a reward-hacking subsection, Mixed Practice P9, and test Q21 (TD learning); test total now 55 marks | 14.1, 18.2, 21, 22 |
| 3.0 | Mark scheme now shows how each mark is earned | 22 |
| 3.0 | Merged the glossary and its supplement into one alphabetical list in plain language | 24 |
| 3.0 | Removed edition labels (NEW badges, "What's new" page) from the learning path; duplicated activity titles fixed | Throughout |
| 2.1 | Added Monte Carlo and TD learning between dynamic programming and Q-learning | 13 |
| 2.0 | Corrected the policy-iteration and Q-learning vs SARSA examples; defined the return before first use; added figures, case studies, practice, test and learning material list | 5, 11, 15, 19–23 |

## 25.3 Optional extensions (beyond this module)

These are not part of the completed module and are not tested: exploration methods beyond ε-greedy (softmax, UCB), multi-step TD and eligibility traces, PPO and TRPO in detail, offline RL and multi-agent RL.
