
Staking 

To stake to a module you need to convert your tokens into stake onto a module. This stake can then be used by the module to vote. The delegation_fee is the percentage the module gets from the dividends only. If alice has a validator with 10 tokens with a fee of 20 and bob comes in and puts 100 tokens onto alice, alice will recieve 20% + (10 Alice Tokens / 110 Total Tokens) * 80% of the emission. Alice can raise the fee between 5 and 100 percent. Please note that the fee is only taken from the dividends, and not the total emission. 


```python
c.stake(module='5E2SmnsAiciqU67pUT3PcpdUL623HccjarKeRv2NhZA2zNES', amount=100, netuid=10)
```

![Alt text](image_stake_single.png)

or to stake multiple amounts to multiple keys, you can do so like this

```python
c.stake_multiple(modules=['5E2SmnsAiciqU67pUT3PcpdUL623HccjarKeRv2NhZA2zNES', '5ERLrXrrKPg9k99yp8DuGhop6eajPEgzEED8puFzmtJfyJES'], amounts=[100, 100], netuid=10)
```

![Alt text](image_stake_multiple.png)


to transfer 100 between two registered modules you can do so like this.

```python
c.stake_transfer('5E2SmnsAiciqU67pUT3PcpdUL623HccjarKeRv2NhZA2zNES', '5ERLrXrrKPg9k99yp8DuGhop6eajPEgzEED8puFzmtJfyJES', 100, netuid=10)
```



Staking Rewards

The staking rewards are calculated by the following formula:

```python
reward = emission * (1 - delegation_fee) * (stake / total_stake)
```

The reward is then added to the stake of the module. The total stake is the sum of all stakes on the module. The delegation_fee is the fee the module takes from the reward. The emission is the total emission of the module.

![Alt text](image_stake_rewards.png)