a Markov process is the process that future doesn't depend on the past, it only depend on where you are.
 
Formalize problem about reinforcement learning

-   There is no **supervisor**, only a reward signal. i.e. nobody telling the agent "you did well"
-   **Reward** is a **scalar** - a single number, may be negative
    -   Reward may be delayed
- Agents **actions** affects its **current** and **future** rewards

 
To Maximize Reward
-   We can represent the environment as a process
-   The agent must model this environment process
-   Agent mush formulate winning strategy based on model of environment


Lets formalize the system
At each time $t$ the **agent**:
-   Makes an observation $O_t$ of the environment
-   Receives a reward $R_t$
-   Performs an action $A_t$

At each time $t$ the **environment**:
-   Receives an action $A_t$
-   Emits a reward $R_{t+1}$
-   Changes and produces an observation $O_{t+1}$


From the perspective of the agent:
The following history:
$H_t = O_0, R_0, A_0, O_1, R_1, A_1, ... , O_t, R_t$

The total history at any time is the sequence of observations, rewards and actions

We need to model this sequence such that at any time t, the best $A_t|H_t$ can be chosen


Markov property
A well-defined state fully captures all information needed to predict the future
**No additional information from the past required**
$P(S_{t+1}|S_0, S_1, ... ,S_t) = P(S_{t+1}|S_{t})$ 
That is the environment's future only depends on its present

Any causal system can be viewed as Markov, with appropirately defined state
-   The Markov state $S_t$ may differ from the apparent state $s_t$
-   Defining $S_t = s_1, s_2, ..., s_t$
-   $P(S_{t+1}|S_0, S_1, ... ,S_t) = P(S_{t+1}|S_{t})$


To be able to maximize his reward, the agent must ideally know all about the environment state and its dynamics.
- Agent has an internal representation of the environment state
    - May not match the true one at all 
