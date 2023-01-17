---
cover: ../../.gitbook/assets/GITBOOK.png
coverY: 0
---

# 🔹 AI Executor Incentive Mechanism

#### _1. Passive income_

_When the executor program is running, it periodically invokes a ping transaction onto a ping smart contract, which will increment the number of times the executor pings. The total ping value is used as proof that the executor is online. It is also a value to calculate the total reward that an executor will receive._

_An executor can claim the ping reward anytime by invoking the claim reward transaction function through Future-ai or CLI. However, the transaction will fail if the contract does not have enough funds, and the Future-AI team will have to deposit some tokens before anyone can claim._

_One note is that, at the moment, there is a maximum reward parameter for executors which is used as an upper bound for the reward one can receive. If an executor receives, for example, 5 Future-AI in total due to not claiming the rewards for a long time while the maximum reward value is 4Future-AI , then that executor can only receive 4 Future-AI . The purpose of the parameter is to limit the executor rewards within the first months. When the Future-AI becomes more stable, we will remove this parameter._

_<mark style="color:blue;">Below is the basic formula for the passive incentive mechanism:</mark>_

```js
reward_amount = executor_total_ping + base_reward_unit
if (reward_amount < maximum_reward_can_claim) reward_amount = maximum_reward_can_claim
```

_where the `base_reward_unit` is a contract parameter set by the contract owner, which is currently the Future-AI  team. In the future, this parameter will be only adjusted through DAO._

_<mark style="color:blue;">After sending the reward successfully, the executor's total ping will reset to 0.</mark>_

#### _2. Rewards from executing Future-AI requests_

#### _2.1 Accumulating the reward pool_

_AI Executors can also earn active rewards by executing_ Future-AI _requests. Each request will accumulate to the total reward that an executor will receive. Each executor has a reward pool to measure such rewards. Below is the equation to calculate the executor's reward when executing an_ Future-AI _request:_

```
new_total_reward = current_total_reward + (minimum value between preference_requester_fee & preference_executor_fee)
```

_where `preference_requester_fee` & `preference_executor_fee` are set by the requester and executor, respectively. We choose the minimum value between the two to prevent a specific case, where an executor sets a low preference fee at first, then immediately increases it after finishing a request to try getting more rewards. Typically, executors with higher fee preferences will not execute requests that have lower fee preferences._

_The reward pool is accumulated automatically through the Future-AI smart contract. Nevertheless, the pool's rewards can be slashed for a certain amount if an executor acts maliciously when executing a request. Currently, the process of slashing is being designed & implemented at the moment._

#### 2.2 Claiming the reward

_In order to claim the rewards, executors must trigger a `claim reward` transaction either on_ Future-AI _or through CLI, which will move such rewards from a normal to an unbonding state. During the unbonding period, the slashing mechanism still applies to the unbonding amount, which prevents executors from executing requests poorly that yet can still claim the rewards before getting slashed._

_After the unbonding period ends, the executors can trigger the `claim reward` transaction again to finally receive the rewards_
