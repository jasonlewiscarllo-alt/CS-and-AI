# Project Plan — Max Medium

**Selected Module:** Hardware, Networks and Behaviourist AI  
**Team of 5** | Stage 1 plan resubmitted 27 October 2026 | Final project submission (Stage 3): 28 November 2026  
**Revised Stage 1 plan (Task 1.8)** | Snapshot as at 27 October 2026

| Item | Detail |
|---|---|
| **Team name** | Max Medium |
| **Module** | Hardware, Networks and Behaviourist AI (binary and denary are taught within the Hardware topic, Topic 1) |
| **GitHub repository** | https://github.com/jasonlewiscarllo-alt/CS-and-AI |
| **Task list location** | Section 8 of this document (snapshot as at 27 Oct 2026); live task list: https://github.com/jasonlewiscarllo-alt/CS-and-AI/blob/main/All%20Logs%20and%20plan/plan.md |
| **Submission lead** | Kenzo Vernard |
| **Key deadlines** | Stage 1: 24 Oct 2026 (plan revised and resubmitted under Task 1.8) \| Stage 2: 7 Nov 2026 \| Stage 3: 28 Nov 2026 |

---

## Contents

1. Team Members and Roles
2. Workload Distribution Strategy
3. Target Learners and Learning Goals
4. Content Outline, Scope Boundaries and Open Questions
5. Planned Learning Resources and Mini Lecture
6. Workflow, Schedule and Coordination
7. Risk Management
8. Master Task List by Stage
9. Submission, Evidence and AI Use

---

## 1. Team Members and Roles

| Name (class roster) | Student ID | Strengths and experience | Skills to develop | Assigned responsibilities |
|---|---|---|---|---|
| Jason Lewis Carillo | 1820262145 | Beginner Python; mediocre at GitHub | Creating effective visual diagrams; GitHub (pull requests, issues) | Markdown drafting of core technical topics (Topic 1, including binary and denary); repository management; checking Markdown for mistakes; leads Study Guide assembly and the propagation of corrections to every deliverable |
| Kenzo Vernard | 1820262125 | Logical thinking, problem-solving, learning new technologies | Time management | Team coordinator and submission lead: coordination, final consistency check and packaging; leads Topic 2, the Behaviourist AI research (Task 2.9) and learner testing; GitHub support for teammates |
| Rysen Reicania Santosa | 1820262077 | Beginner in visual design and multimedia creation | Video editing; visual design | Visual lead and video design lead: diagrams, Video 1 and Video 2 scripts and recordings; leads Topic 3 (topologies and protocols) |
| Kelton James Mahendra | 1820262114 | Visual design, multimedia creation, public speaking / lecture delivery | Using GitHub | Live mini-lecture lead; project log, personal-log checks, meeting summaries and AI-use record; visual feedback on diagrams and video drafts; leads Topic 4 and the Topic 1 re-review |
| Louis Tjoekro Pranata | 1820262354 | Analytical skills and problem solving | Designing | PPT slide designer (main deck and mini-lecture slides); test bank and answer file lead; Topic 5 lead; final peer review lead |

---

## 2. Workload Distribution Strategy

Roles describe responsibilities, not exclusive areas of work. Every member studies the subject, makes a substantive contribution, peer-reviews drafted Markdown files, tests learner activities and must be able to explain the team's core content. Specific members lead the final production of the Study Guide, PPT slides or videos, but all content originates from the shared Markdown repository.

**Fairness rule:** every task has one named lead, no member leads more than six open tasks, and the table below is recalculated from the Master Task List (Section 8) at each weekly meeting. Where a member's stated strength and role do not match yet (for example video editing), the task is paired with a teammate who can coach it.

### How strengths are used and learning needs are supported

| Member | Role and how it uses strengths | Learning need and support |
|---|---|---|
| Jason | Markdown drafting, error checking, repository management and Study Guide assembly | Diagrams: pairs with Rysen and Kelton on visual assets (Task 2.6). GitHub: cheat sheet and pairing session led by Kenzo (Task 2.16) |
| Kenzo | Logical thinking and problem-solving: coordination, Topic 2, Behaviourist AI research, learner testing, final consistency check | Time management: every task has an internal deadline on the GitHub Projects board, checked at each meeting |
| Rysen | Diagrams, topologies and video production, as a hands-on way to build his visual skills; leads Topic 3 | Video editing and visual design: paired with Kelton, who has visual design and multimedia experience and reviews the first video draft (Task 2.14) |
| Kelton | Public speaking: leads the live mini lecture; visual design and multimedia: gives visual feedback on diagrams and the first video draft; keeps logs and meeting summaries | GitHub: pairs with Jason on first pull requests and log commits (Task 2.16) |
| Louis | Analytical skills: test bank, answer file, feedback analysis, final review lead | Designing: leads the PPT deck using Rysen's diagrams and Kelton's visual guidance |

### Workload check (open tasks only, generated from the Master Task List)

| Member | Open tasks led | Open tasks involved in |
|---|---|---|
| Jason | 6 | 15 |
| Kenzo | 5 | 17 |
| Rysen | 6 | 16 |
| Kelton | 6 | 15 |
| Louis | 6 | 17 |

---

## 3. Target Learners and Learning Goals

### Assumed Background Knowledge

Learners need no prior knowledge of computing. Binary and denary are taught in the Hardware topic (Topic 1), so learners do not need to study them beforehand. At most, they may know that computers use 0s and 1s. Topic 1 builds binary and denary step by step from place value, before it moves on to hardware components, so later topics can use them.

### Learning Goals

After using the module materials, beginners will be able to:

1. Explain what a bit is and why computers use binary (two states, stored as 1 and 0).
2. State binary place values (1, 2, 4, 8, 16, 32, 64, 128).
3. Convert binary numbers of up to 8 bits to denary, and denary numbers from 0 to 255 to binary, showing the working.
4. State how many different values a number of bits can store (for example 8 bits store 256 values, 0 to 255) and check a conversion by converting back.
5. Name the main hardware components and explain what each one is used for.
6. Explain the different types of RAM and ROM and compare them (for example SRAM and DRAM; PROM, EPROM and EEPROM).
7. Name the main network components and state the purpose of each.
8. Describe four network topologies and list two advantages and two disadvantages of each; choose a suitable topology for a simple scenario.
9. State the purpose of every network protocol listed in the course materials and match each protocol to a use (the final list is taken from the course materials in Task 2.1b).
10. Identify common network threats and explain basic defences against them.
11. Explain in simple words what **Behaviourist AI** is: Brooks-style reactive AI designed around observable behaviour — sensory inputs, motor actions, and reactive rules — rather than internal world models or human-like deliberation.
12. Describe the sense–decide–act loop using an everyday example, such as a robot vacuum or a game guard.
13. Draw a simple finite state machine (three or four states with labelled transitions) for a game character such as a guard.
14. Explain how a finite state machine controls a game character's behaviour, and explain Q-learning conceptually as learning from rewards.
15. Give one benefit and one risk of Behaviourist AI (for example, fast reactions in dynamic environments; privacy concerns in camera-equipped robots).

### Beginner questions: binary and denary (Topic 1: Hardware)

- What is a bit, and why do computers use only 0s and 1s?
- What is each place in a binary number worth?
- How do I turn 1011 0110 into denary, and 150 into binary?
- How many different values can 8 bits store?
- How can I check that my conversion is right?

### Beginner questions: Behaviourist AI (Topic 5)

**Q1. What does "behaviourist" mean when we talk about AI?**  
A: It means the AI is designed around observable behaviour — sensory inputs and motor actions, coupled directly by rules or reflexes — rather than trying to reproduce internal human thoughts. The classic example is Brooks-style reactive robotics: a robot that senses and acts without building a detailed internal world model.

**Q2. How does a Behaviourist AI sense, decide and act?**  
A: Sensors receive input; reactive rules, a state machine or the current state decide what to do; an actuator performs the action; the loop repeats immediately. This is the sense–decide–act loop.

**Q3. What is a state, and what makes a game character change from one state to another?**  
A: A state is a named behaviour mode, such as patrol, chase or attack. A transition happens when a condition or event is met, such as seeing the player or losing health.

**Q4. How does a robot vacuum stop when it hits a wall?**  
A: A bumper sensor triggers a reactive rule — Layer 0 in subsumption — that immediately stops the motors, reverses, and rotates 45° before Layer 1 (wandering) takes over again. Higher layers cannot override this survival behaviour.

**Q5. What is the difference between a behaviour tree and a state machine?**  
A: A state machine uses explicit states and transitions; a behaviour tree organises tasks hierarchically using sequences, selectors and tasks.

**Q6. What does "subsumption" mean?**  
A: It is a layered approach where simple behaviours run together and a lower-level behaviour, such as avoiding obstacles, can override a higher-level behaviour such as wandering. Suppression replaces the input to a lower layer; inhibition blocks the output of a lower layer.

**Q7. How does Q-learning learn from rewards?**  
A: The agent tries actions, receives rewards or penalties, and gradually adjusts a table of action-values Q(s,a) so that actions leading to higher reward are chosen more often. It learns from observable consequences, not from an internal model of the world.

**Q8. Why is privacy an ethical concern for camera-equipped robots?**  
A: Even though the AI is reactive, the cameras and sensors collect data that can identify people and reveal behaviour. Consent, retention and anonymisation matter, especially when telemetry is sent to the cloud.

---

## 4. Content Outline, Scope Boundaries and Open Questions

### Content Outline

| Topic | Subtopics | Status label |
|---|---|---|
| **Topic 1: Hardware fundamentals, binary and denary** | Binary and denary (taught in detail as part of the Hardware topic): (a) Bits and why computers use binary: two states, on and off, stored as 1 and 0; (b) Denary (base 10) place values: ones, tens, hundreds; (c) Binary (base 2) place values: 1, 2, 4, 8, 16, 32, 64, 128; (d) Converting binary to denary by adding the place values of the 1s; (e) Converting denary to binary using place values (repeated division by 2 as a second method); (f) How many values n bits can store (8 bits: 256 values, 0 to 255) and how to check an answer. Hardware: (g) Main hardware components and their uses (for example CPU, RAM, ROM, secondary storage, motherboard, input and output devices); (h) Types of RAM (SRAM, DRAM) and types of ROM (ROM, PROM, EPROM, EEPROM); (i) RAM versus ROM comparison | **[Drafted]** V1.0, revised (Task 1.4b); binary and denary expanded in Task 2.18; to be marked [Checked] (Task 2.10) |
| **Topic 2: Network components** | Components of a network (for example NIC, hub, switch, router, modem, wireless access point, server, client) and the purpose of each | **[Outline Only]**; drafted in Task 2.1a |
| **Topic 3: Topologies and protocols** | Four topologies (bus, star, ring, mesh), each with 2 advantages and 2 disadvantages; purpose and use of each protocol on the course list (placeholder examples only, to be replaced by the course list: HTTP, HTTPS, FTP, SMTP, IMAP, TCP/IP) | **[Outline Only]**; drafted in Task 2.1b |
| **Topic 4: Network threats and security** | Common threats (for example malware, phishing, denial of service, weak passwords); basic defences (firewalls, encryption, anti-malware, updates, strong authentication) | **[Outline Only]**; drafted in Task 2.1c |
| **Topic 5: Behaviourist AI** | 5.1 What Behaviourist AI means: Brooks-style reactive, behaviour-based AI — sensory inputs coupled directly to motor actions without complex internal world models; pioneered by Rodney Brooks in the late 1980s. 5.2 The sense–decide–act loop, with a robot vacuum or game guard example. 5.3 Rule-based behaviour: finite state machines (states and transitions), with a brief look at behaviour trees. 5.4 Layers of behaviour: the subsumption idea (layers, suppression and inhibition), for example avoid obstacles before wandering. 5.5 Motor schema / artificial potential fields: attraction to goal, repulsion from obstacles, and the local minima trap. 5.6 Benefits and risks: limitations of reactive systems, privacy in camera-equipped robots, and bias in simple rules, at beginner level. | **[Outline Only]**; research notes in Task 2.9, drafted in Task 2.11 |
| **Review and Assessment** | Chapter summaries, self-check questions, test bank, separate answer file | **[Outline Only]**; Tasks 2.5, 2.15 |

Binary and denary sit inside Topic 1 (Hardware) rather than in a separate topic. They are taught first, so learners can apply them to memory and storage in the hardware subtopics.

Topic names and subtopic lists are the team's working proposal and will be corrected against the course materials.

### Starting sources for the Behaviourist AI research (Task 2.9)

- Wikipedia: *Behaviorism*, *Behavior-based robotics*, *Subsumption architecture* and *Situated approach (artificial intelligence)*.
- University of Liverpool COMP310, Chapter 5: *Reactive and Hybrid Architectures*.
- GameDev.net, beginner tutorial on finite state machines, for the guard example.
- Brooks, R. A. (1986). "A Robust Layered Control System for a Mobile Robot." *IEEE Journal on Robotics and Automation*.
- Brooks, R. A. (1991). "Intelligence Without Representation." *Artificial Intelligence*.
- Arkin, R. C. (1998). *Behavior-Based Robotics*. MIT Press.

Each source is checked against the course materials and one more source before any fact is used.

### Scope Boundaries

| Detailed explanation (with worked examples and exercises) | Brief introduction only |
|---|---|
| Binary and denary, taught in detail within the Hardware topic (Topic 1): place value, converting both ways for numbers up to 8 bits (0 to 255), and how many values n bits can store | Hexadecimal, binary addition, negative numbers and fractions in binary |
| RAM and ROM types and their differences | How text, images and sound are stored as bits |
| Main hardware components and their uses | Internal workings of the CPU and the fetch-decode-execute cycle |
| Network components and their purposes | Layered network models and packet structure |
| Four topologies with advantages and disadvantages | The mathematics of encryption |
| Purpose and typical use of each listed protocol | Behaviourist AI extras: behaviour trees, artificial potential fields (concept), Q-learning update rule (concept) |
| Common network threats and basic defences | |
| **Behaviourist AI basics:** what it is (Brooks-style reactive robotics — sensory inputs coupled directly to motor actions), the sense–decide–act loop, finite state machines, subsumption architecture (layers, suppression and inhibition), robotic vacuum case study, APF concept (attraction, repulsion, local minima trap), Q-learning conceptually, limitations and ethics | |

### Beginner questions answered in detail vs short answer

| Answered in detail | Short answer only |
|---|---|
| What is Behaviourist AI? | How is a behaviour tree different from a state machine? |
| How does a Behaviourist AI sense, decide and act? | What does "subsumption" mean? |
| How does a game guard switch between patrol, chase and attack? | How does Q-learning learn from rewards? |
| How does a robot vacuum stop when it hits a wall? | Why is privacy an ethical concern for camera-equipped robots? |

### Scope and difficulty uncertainties identified, and how the team settles them

| Uncertainty | How the team settles it |
|---|---|
| Which protocols are on the course list, and how much detail each needs | Copy the list from the course materials as the first step of Task 2.1b; give each protocol one purpose and one typical use. |
| How far into CPU architecture Topic 1 should go | Keep it to a brief introduction unless the course materials require more; check at the Topic 1 re-review (Task 2.10). |
| Whether 8-bit binary and denary conversion is the right difficulty for beginners | Limit conversions to 8 bits (0 to 255) with practice graded from 4-bit; test with someone who did not write the questions (Task 2.7) and adjust. |
| Whether binary and denary should be a separate topic or part of Hardware | The team teaches them inside Topic 1 (Hardware), taught first. The team checks this against the course materials at the Topic 1 re-review (Task 2.10). |

Each answer is recorded in the project log and this section is updated.

---

## 5. Planned Learning Resources and Mini Lecture

### Shared Markdown Content

The single source of truth for every other resource. One modular `.md` file per topic, kept in `content/`, with diagrams in `assets/`, review and project records in `docs/`, and the Study Guide, slides and videos in their own folders. Each topic file uses the same order: learning objectives, key terms (explicit definitions), beginner explanation, worked example, visual reference, learner exercises, answer key, and references. Each file carries a status label (`[Outline Only]`, `[Drafted]`, `[Checked]`). Binary and denary are part of the Topic 1 (Hardware) file. They are not a separate file, so every resource draws on the same Topic 1 content.

### Study Guide and Test Bank

| Part | Plan |
|---|---|
| **Structure** | A study booklet compiled from the Markdown chapters: objectives, explanations, key terms, worked examples (including place-value tables for binary and denary, taught in the Hardware chapter), chapter summary. First version in Stage 2 (Task 2.15); final version in Stage 3 (Task 3.1). |
| **How learners study** | Read a chapter, answer its self-check questions, then attempt the test bank for that topic. |
| **Practice and checking** | Self-check concept questions after each chapter; a test bank mixing recall, explain and apply questions mapped to the learning goals, including binary and denary conversion sets graded from 4-bit to 8-bit numbers; a separate answer file so learners can check whether they have really understood. Topic 5 questions and answers use **Behaviourist AI** consistently. |

### PPT Slides

Slides turn the `[Checked]` Markdown into visual explanations. In the Hardware section, a binary place-value table fills in step by step as 1011 0110 is converted to denary (182) and 150 is converted to binary (1001 0110), followed by a RAM versus ROM comparison diagram, a network components diagram, one diagram per topology, and a step-by-step animated worked example showing a message travelling across a star network, plus a state-machine diagram of a game guard for **Behaviourist AI**. Slides use concise bullet points with full speaker notes. A separate short deck supports the mini lecture (Task 2.12).

### Video Tutorials

| Video (5–10 min) | Concepts that benefit from narration and demonstration |
|---|---|
| **Video 1: RAM and ROM explained** | Opens with a 1–2 minute recap of the binary and denary already taught in Topic 1 (Hardware), including one worked conversion, then compares the memory types: what is stored, what is lost when power is off, and where each is used. Script in Task 2.13, first draft in Task 2.14. |
| **Video 2: How data travels through a network** | Animated data flow through network components, a chosen topology and a protocol, with step-by-step narration. Script in Task 3.7, both videos finalised in Task 3.2. |

Each video follows a written script and storyboard taken from the `[Checked]` Markdown, so what is said matches the Study Guide and slides.

### How the Three Resources Support One Another

The Markdown files are the foundation. The Study Guide compiles them for reading and practice; the slides turn the same explanations and diagrams into visuals; the videos narrate the slide animations for the hardest processes. Test bank questions map to the same learning goals, so a learner can read, watch, then self-test on the same ideas. Any correction is made in Markdown first and then carried to every deliverable (Section 6).

### Live Mini Lecture

| Item | Detail |
|---|---|
| **Topic** | Network Threats and Network Security (the team's decided topic) |
| **Focus question** | How can one phishing email put a whole network at risk, and which simple defences stop it? |
| **Why it matters** | Every learner uses networks daily. Threats are common and many are stopped by habits and basic tools, so the topic is both practical and linked to network components and protocols in the module. |
| **Example / demo** | Trace one phishing email step by step: delivery, click, spread, and the point where a firewall, update or careful user stops it. |
| **Audience activity** | Show four short sample emails (written by the team, Task 2.3a). The audience votes which are phishing, then the team reveals the warning signs. |
| **Roles** | Kelton (public speaking) leads and presents, supported by Kenzo in preparation (Task 2.3a); mini-lecture slides by Louis (Task 2.12); Louis leads the collection of audience feedback (Task 2.17). |

---

## 6. Workflow, Schedule and Coordination

### Stage Deadlines and Key Milestones

| Stage | Deadline | Milestone |
|---|---|---|
| **Stage 1** | 24 Oct 2026 | Project planning, repository setup, module outline and V1.0 substantive Markdown draft; plan revised and resubmitted (Task 1.8). |
| **Stage 2** | 7 Nov 2026 | First complete version of module content, test bank, initial slide deck, first Study Guide and first Video 1 draft; preparation and delivery of the live mini lecture per class schedule. |
| **Stage 3** | 28 Nov 2026 | Comprehensive peer review, revision and final polishing of the Study Guide, PPT and videos; final package submission. |

### Study, Review and Coordination Protocol

| Area | Approach |
|---|---|
| **Studying and investigating** | Each member reads the course materials for their assigned topic, makes notes, and checks key facts against at least one more source before drafting. |
| **Drafting Markdown** | Members draft in a branch per topic and open a pull request for team visibility. |
| **Checking before production** | Before a topic is marked `[Checked]`, a reviewer who is not an author checks technical accuracy, clarity for beginners and asset link integrity (review pairs below). Only `[Checked]` files are used for slides, videos and the Study Guide. |
| **GitHub use** | Issues with an assignee and deadline for every task; a GitHub Projects board with columns Not started, In progress, Under review and Completed; branches and pull requests for all content; the commit history and review log serve as contribution evidence. |
| **Communication and meetings** | A team group chat for day-to-day messages (blockers posted straight away, replies within 24 hours); a weekly meeting every Monday (first Stage 2 meeting: Mon 2 Nov) plus a checkpoint on Wed 4 Nov after the mini-lecture rehearsal, in person if possible and otherwise online; asynchronous tracking on GitHub Projects; review comments on pull requests. Kelton writes a summary of each meeting in the project log within 24 hours (Task 2.8). |
| **Getting corrections to every deliverable** | Fix the Markdown first. Then open a correction issue listing every affected deliverable (Study Guide, test bank and answer file, slides, speaker notes, video script, video) and tick each off. Task 3.4 applies the corrections and Task 3.3 re-checks that all resources match. |

### Who reviews what (the reviewer is never the author or producer)

| Output | Author / producer | Reviewer |
|---|---|---|
| Topic 1 Markdown | Jason | Kelton |
| Topic 2 Markdown | Kenzo | Jason |
| Topic 3 Markdown | Rysen | Louis |
| Topic 4 Markdown | Kelton | Kenzo |
| Topic 5 Markdown (Behaviourist AI) | Louis | Kenzo |
| Test bank and answer file | Louis | Jason |
| PPT main deck | Louis | Kelton |
| PPT mini-lecture deck | Louis | Kenzo |
| Video 1 draft | Rysen | Kelton |
| Video 2 draft | Rysen | Kelton |
| Study Guide v1 | Jason | Louis |
| Study Guide final | Jason | Louis |
| Stage 1 plan | Kenzo | All members |
| Stage 3 final ZIP | Kenzo | Louis |

---

## 7. Risk Management

| Risk | Detail | Response |
|---|---|---|
| **Unfamiliar tools** | Jason and Kelton are still new to GitHub; Rysen is new to video editing and design tools. | Jason and Kelton pair on their first pull requests with a one-page GitHub cheat sheet in `docs/` (Task 2.16); Rysen's first video draft is reviewed early by Kelton (Task 2.14); Rysen's diagrams guide Louis's slides. |
| **Delayed tasks** | Stage 1 finished late (the plan was revised and resubmitted on 27 Oct under Task 1.8) and time management is a stated development need. | Internal deadlines sit 2–3 days before stage deadlines; the board is checked at every weekly meeting; Kenzo flags any task more than two days behind and the team reassigns or reduces scope. |
| **Scope and depth uncertainty** | The protocol list and the CPU depth are not fixed (Section 4). | Use the course materials as the reference. Task 2.1b copies the protocol list; Task 2.10 checks the CPU depth. Differences found while drafting are logged in the project log and the outline is updated. |
| **Mini-lecture date changes** | The class schedule date for the mini lecture is not yet known. | Slides and rehearsal are planned for 3–4 Nov, ahead of the assumed 6 Nov slot; if the slot moves earlier, Kenzo moves the rehearsal and the Topic 4 review forward. |

---

## 8. Master Task List by Stage

### Progress Summary

| Stage | Deadline | Tasks | Completed | In progress | Not started | Progress |
|---|---|---|---|---|---|---|
| **Stage 1** | 24 Oct 2026 | 9 | 9 | 0 | 0 | 100% complete |
| **Stage 2** | 7 Nov 2026 | 22 | 0 | 1 | 21 | 0% complete (1 in progress) |
| **Stage 3** | 28 Nov 2026 | 7 | 0 | 0 | 7 | 0% complete |

Status colours: green = completed, amber = in progress / WIP, grey = not started. Snapshot as at 27 Oct 2026. Stage 2 and Stage 3 statuses are the team's starting position and are updated as work happens. Live task list: https://github.com/jasonlewiscarllo-alt/CS-and-AI/blob/main/All%20Logs%20and%20plan/plan.md

### Stage 1 — Foundation and Planning (deadline 24 Oct 2026)

| ID | Task | Expected result | Responsible | Internal deadline | Status | Depends on |
|---|---|---|---|---|---|---|
| 1.1 | Establish GitHub repository, invite collaborators, author README.md | Accessible repository with team info, module scope and directory structure | Lead: Jason; All members | 22 Oct 2026 | Completed | None |
| 1.2 | Draft module outline and learning outcomes | `content/outline.md` with topics, subtopics and status labels (`[Outline Only]`, `[Drafted]`) | Lead: Jason; All members | 22–23 Oct 2026 | Completed | 1.1 |
| 1.3 | Write substantive Markdown V1.0 for Topic 1 | Markdown file with explanations, terminology, worked example, visual reference, learner activity and answer key | Lead: Jason; Jason, Rysen, Louis, Kenzo | 24 Oct 2026 | Completed | 1.2 |
| 1.4 | Conduct peer review and compile GitHub evidence | Review log (`docs/review-log.md`) and commit history screenshots | Kenzo | 24 Oct 2026 | Completed | 1.3 |
| 1.4b | Review missing content and improve all Topic 1 content (redo after review) | Missing content identified and added; improved Markdown committed | Jason | 25–26 Oct 2026 | Completed | 1.3 |
| 1.5 | Complete the Stage 1 plan (fill gaps), all members review it, submission lead submits | Final PDF named `MaxMedium_Stage1_ProjectPlan`, reviewed by all five members and submitted by the submission lead | Lead: Kenzo; All members | 27 Oct 2026 | Completed | 1.4 |
| 1.6 | Set up project log and personal logs; record the planning discussion and contributions | `docs/project-log.md` plus one personal log per member, with planning discussion recorded | Lead: Kelton; All members | 27 Oct 2026 | Completed | 1.1 |
| 1.7 | Record significant AI assistance used in planning and task breakdown (Section 6 rules) | AI-use record entries in the project log (tool, date, purpose, what the team changed) | Lead: Kelton; Kelton, Kenzo | 27 Oct 2026 | Completed | None |
| 1.8 | Redo the Stage 1 plan: close every gap found against the assignment requirements (resubmission after the 24 Oct deadline) | Revised plan (this document) covering assignment sections A–F, reviewed by all five members and resubmitted by Kenzo | Lead: Kenzo; All members | 27 Oct 2026, 23:59 | Completed | 1.5 |

Stage 1 dates after 24 Oct 2026 show that Stage 1 was finished late; the plan was revised and resubmitted on 27 Oct 2026 (Task 1.8).

### Stage 2 — Production and Live Teaching (deadline 7 Nov 2026)

| ID | Task | Expected result | Responsible | Internal deadline | Status | Depends on |
|---|---|---|---|---|---|---|
| 2.1 | Draft remaining module topics (Topics 2–5) | Complete draft text covering all planned module outcomes (umbrella for 2.1a–2.1c and 2.11) | Lead: Jason; All members | 2 Nov 2026 | In Progress | 1.2 |
| 2.1a | Research, draft and verify Topic 2: network components | `content/02-network-components.md` with explanations, terms, worked example, activity, answer key | Lead: Kenzo; Kenzo, Louis | 2 Nov 2026 | Not Started | 1.2 |
| 2.1b | Research, draft and verify Topic 3: four topologies and protocols | `content/03-topologies-protocols.md` including a topology comparison table (2 advantages, 2 disadvantages each) and protocol purposes; first step is to list the protocols from the course materials | Lead: Rysen; Rysen, Louis | 2 Nov 2026 | Not Started | 1.2 |
| 2.1c | Research, draft and verify Topic 4: network threats and network security | `content/04-threats-security.md` with explanations, examples, activity, answer key | Lead: Kelton; Kelton, Jason | 2 Nov 2026 | Not Started | 1.2 |
| 2.11 | Research, draft and verify Topic 5: Behaviourist AI at beginner level, using the Task 2.9 notes | `content/05-behaviourist-ai.md` with beginner definitions, a state-machine worked example, an activity and an answer key | Lead: Louis; Louis, Kenzo | 2 Nov 2026 | Not Started | 2.9 |
| 2.2 | Design PPT slide deck and speaker notes | Slide deck (`.pptx`) aligned with the `[Checked]` Markdown content | Lead: Louis; Louis, Rysen, Jason, Kenzo | 5 Nov 2026 | Not Started | 2.4, 2.6, 2.10 |
| 2.3a | Define the focus question, worked example and audience activity for the mini lecture on Network Threats and Network Security; write the four sample emails and answer key | One-page mini-lecture outline in `docs/` with the topic, focus question, example, activity, four sample emails and warning signs | Lead: Kelton; Kelton, Kenzo | 31 Oct 2026 | Not Started | 1.8 |
| 2.3b | Rehearse the live mini lecture at least 48 hours before delivery | Completed rehearsal of the lecture, demo and audience activity, with fixes noted | Lead: Kelton; All members | 4 Nov 2026 (target; delivery per class schedule) | Not Started | 2.3a, 2.12, 2.4 |
| 2.4 | Peer review Topics 2–5 Markdown using the review pairs in Section 6 (accuracy, beginner clarity, asset links); mark each file `[Checked]` | Review log entries; each file labelled `[Checked]`; reviewer is never an author | Lead: Jason; All members | 3 Nov 2026 | Not Started | 2.1a, 2.1b, 2.1c, 2.11 |
| 2.5 | Prepare the test bank (first version) and separate answer file | Test bank file and answer file covering every learning goal, including graded binary and denary conversion sets; Topic 5 questions and answers use **Behaviourist AI** | Lead: Louis; Louis, Kenzo | 4 Nov 2026 | Not Started | 2.4, 2.10 |
| 2.6 | Create diagrams and visual assets (binary place-value table, hardware, network components, four topologies, a game-guard state machine) | Image files in `assets/` referenced from the Markdown files | Lead: Rysen; Rysen, Jason | 3 Nov 2026 | Not Started | 2.10, 2.1a, 2.1b, 2.11 |
| 2.7 | Test learner activities and test-bank questions with someone who did not write them; collect feedback | Feedback notes logged; list of fixes raised as GitHub issues | Lead: Kenzo; Kenzo, Louis, Rysen, Jason | 5 Nov 2026 | Not Started | 2.4, 2.5 |
| 2.8 | Write meeting summaries and update the project log after each meeting | Meeting summary and log entry committed within 24 hours of each meeting (2 Nov and 4 Nov; continues weekly in Stage 3) | Kelton | 3 Nov and 5 Nov 2026 | Not Started | 1.6 |
| 2.9 | Research Behaviourist AI from the course materials and at least two other sources; write notes with definitions, examples and sources | `docs/behaviourist-ai-notes.md` with beginner definitions, two or three worked examples and a source list; Section 4 outline corrected if the course materials differ | Lead: Kenzo; Kenzo, Louis | 29 Oct 2026 | Not Started | 1.8 |
| 2.10 | Re-review the revised Topic 1 Markdown, including the binary and denary section (accuracy, beginner clarity, asset links), and mark it `[Checked]` | Review log entry; Topic 1 file labelled `[Checked]`; reviewer is not one of its authors | Kelton | 30 Oct 2026 | Not Started | 1.4b, 2.18 |
| 2.12 | Build the mini-lecture slides (a short deck separate from the main deck) | Short `.pptx` for the mini lecture with the phishing trace, diagram and audience-vote slide | Louis | 3 Nov 2026 | Not Started | 2.3a, 2.1c |
| 2.13 | Write the narration script and storyboard for Video 1 (RAM vs ROM) | Script and storyboard committed in the videos folder, drawn from the `[Checked]` Topic 1 Markdown | Rysen | 2 Nov 2026 | Not Started | 2.10 |
| 2.14 | Record and edit a first draft (rough cut) of Video 1; Kelton reviews the early draft | Video 1 rough cut and Kelton's written feedback logged | Lead: Rysen; Rysen, Kelton | 5 Nov 2026 | Not Started | 2.13, 2.6 |
| 2.15 | Compile the first version of the Study Guide from the `[Checked]` Markdown, with chapter summaries and the first test bank | Study Guide v1 (PDF or Markdown) with self-check questions and a link to the answer file | Lead: Jason; Jason, Kenzo | 5 Nov 2026 | Not Started | 2.4, 2.5, 2.10 |
| 2.16 | Write a one-page GitHub cheat sheet and hold a pairing session so Jason and Kelton make their first pull requests | `docs/github-cheatsheet.md`; a pull request opened by each of Jason and Kelton | Lead: Kenzo; Kenzo, Jason, Kelton | 29 Oct 2026 | Not Started | 1.1 |
| 2.17 | Deliver the live mini lecture per the class schedule (presented by Kelton); collect and log audience feedback (Louis leads the feedback collection) | Feedback notes in the project log and a list of fixes raised as GitHub issues | Lead: Louis; Louis, Kelton | Per class schedule (assumed 6 Nov 2026) | Not Started | 2.3b |
| 2.18 | Expand the binary and denary section of Topic 1: place values, both conversion methods, worked examples and a graded practice set with answers | Topic 1 file updated with the binary and denary section (for example 1011 0110 = 182 and 150 = 1001 0110), a 4-bit to 8-bit practice set and its answer key, committed | Lead: Jason; Jason, Rysen | 29 Oct 2026 | Not Started | 1.4b |

### Stage 3 — Review, Refinement and Final Delivery (deadline 28 Nov 2026)

| ID | Task | Expected result | Responsible | Internal deadline | Status | Depends on |
|---|---|---|---|---|---|---|
| 3.1 | Assemble the final Study Guide and Test Bank with solution keys | Compiled PDF/Markdown study guide package with separate answer file | Lead: Jason; Jason, Kenzo, Louis | 19 Nov 2026 | Not Started | 2.15, 3.4 |
| 3.2 | Record and edit the final video tutorials (RAM vs ROM; how data travels through a network) | 1–2 video files of 5–10 minutes each demonstrating core processes | Lead: Rysen; Rysen, Kelton | 21 Nov 2026 | Not Started | 2.14, 3.7, 3.4 |
| 3.3 | Final cross-resource consistency check and packaging | Final ZIP (`MaxMedium_Stage3_Final.zip`) verified offline | Lead: Kenzo; All members | 25 Nov 2026 | Not Started | 3.1, 3.2, 3.5, 3.6 |
| 3.4 | Apply feedback and propagate every correction to all affected deliverables | Correction checklist in GitHub issues fully ticked (Markdown, Study Guide, test bank, slides, scripts, videos) | Lead: Jason; All members | 16 Nov 2026 | Not Started | 2.17, 2.7 |
| 3.5 | Final peer review of Study Guide, slides and videos (reviewer is never the producer, see Section 6) | Review log entries and a list of any last fixes, all closed | Lead: Louis; All members | 23 Nov 2026 | Not Started | 3.1, 3.2, 3.4 |
| 3.6 | Finalise project log, personal logs, contribution evidence and AI-use record | Complete logs and AI-use record committed; commit history screenshots captured | Lead: Kelton; All members | 24 Nov 2026 | Not Started | 3.5 |
| 3.7 | Write the narration script and storyboard for Video 2 (how data travels through a network) | Script and storyboard committed in the videos folder, drawn from `[Checked]` Topics 2 and 3 | Rysen | 13 Nov 2026 | Not Started | 2.4, 2.6 |

---

## 9. Submission, Evidence and AI Use

| Item | Plan |
|---|---|
| **Submission file** | One PDF named `MaxMedium_Stage1_ProjectPlan` containing this plan and the task list snapshot (Section 8). |
| **GitHub repository and task list** | Repository link and GitHub Projects link are on the cover page; the teacher is invited to both. |
| **Who submits** | Kenzo (Submission lead) submits one copy after all five members have reviewed it (Tasks 1.5 and 1.8). |
| **Keeping it current** | The plan and task list are updated after submission as work progresses and feedback arrives. |
| **Project and personal logs** | `docs/project-log.md` and a personal log per member record the planning discussion and each member's contributions (Tasks 1.6, 2.8, 3.6). Personal logs must not be placed in a publicly accessible repository; they are kept in the submission package. |
| **Contribution evidence** | Commit history, pull requests, issues and `docs/review-log.md`. |

### AI-use record (Section 6 of the Shared Assignment Rules)

| Date | Tool | Purpose | Team's review |
|---|---|---|---|
| 27 Oct 2026 | Claude (Anthropic) | Formatted the plan into a PDF, reorganised the task list into stage tables, and drafted proposed wording for the scope boundaries, topic outline, mini lecture, video topics, workflow, risks and additional tasks. | Recorded in the project log by Kelton and Kenzo (Task 1.7). All members review, correct and confirm each proposal before submission (Task 1.8). |
| 27 Oct 2026 | Claude (Anthropic) | Checked the plan against the assignment brief and revised it as the team directed: replaced old Task 1.8 with the red task set; set Stage 1 statuses; added Tasks 2.9–2.18 and 3.7 (Topic 1 re-review, GitHub pairing, Topic 5, mini-lecture slides, Video 1 script and draft, Study Guide v1, mini-lecture delivery and feedback, Video 2 script); fixed dependencies and internal deadlines; added the review-pair table, communication plan and risks; recalculated the progress and workload tables. | Recorded in the project log by Kelton and Kenzo (Task 1.7). The team directed the changes and checks each one before submission; any edits the team makes are noted in `docs/project-log.md`. |
| 27 Oct 2026 | Claude (Anthropic) | Searched the web for **Behaviourist AI** (behaviour-based AI, subsumption architecture, artificial potential fields, state machines and behaviour trees) and drafted the Topic 5 outline, beginner questions, learning goals and starting source list; added the research task (2.9); reduced Kelton's task involvement as the team directed; recalculated the progress and workload tables. | Recorded in the project log by Kelton and Kenzo (Task 1.7). The team checks the Topic 5 content against the course materials and one more source (Task 2.9) before it is used. |
| 27 Oct 2026 | Claude (Anthropic) | Checked the plan against the assignment brief and fixed the gaps: added binary and denary teaching content (Topic 1 outline, learning goals, scope boundaries, beginner questions, study guide, slides, video recap, risk) and new Task 2.18; added the scope and difficulty uncertainty table; made the source links clickable; reset three Stage 1 dates and added a note on the late Stage 1; recalculated the progress and workload tables. | Recorded in the project log by Kelton and Kenzo (Task 1.7). The team checks the binary and denary content against the course materials (Tasks 2.18 and 2.10). |
| 27 Oct 2026 | Claude (Anthropic) | Rewrote Sections 3, 4 and 5 so that binary and denary are stated as taught within the Hardware topic (Topic 1); recorded Network Threats and Network Security as the team's decided mini-lecture topic and updated Task 2.3a, the uncertainty table and the risks to match; corrected the Task 1.8 member list, the Task 2.6 dependency and the Task 2.17 roles; restored the clickable source links; marked the placeholders still to be filled in; clarified the cover dates and the coordinator title; **standardised all references to Behaviourist AI and removed all behavioural-analytics content** (click/purchase/log-in examples, bank anomaly questions, model-training questions, analytics vendor sources, and the “two common uses” framing). | Recorded in the project log by Kelton and Kenzo (Task 1.7). The team confirms the wording against the course materials (Tasks 2.10 and 2.18). |

---

