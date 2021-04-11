## Pledging and delegation options

Ada that is held on the Cardano network represents a user’s stake in the protocol, the size of which is proportional to the amount of ada held. Users who hold a stake in Cardano can earn passive rewards for validating blocks. The amount of rewards they can earn is proportional to the amount of ada they pledge or delegate to a stake pool.

There are three options ada holders can consider for delegating their stake:

1. Run their own stake pool
2. Agree with a third party to run a private stake pool for them
3. Delegate to other stake pools

To create and register a stake pool, see the [create transaction instructions](https://docs.cardano.org/projects/cardano-node/en/latest/stake-pool-operations/simple_transaction.html#) explaining how to pledge and delegate to earn rewards.

Stake pools must maintain **high-availability**, which means that they should always be online and available to validate and create new blocks. The rewards a stake pool can earn is directly proportional to the amount of ada that is pledged or delegated, and the number of blocks the stake pool can create in a given epoch. Ouroboros (the protocol that runs on Cardano) elects the slot leader that grants the permissions to validate transactions and create new blocks, based on the above criteria.

> Note: It is strongly recommended to test all stake pool functionality on the testnet prior to any mainnet deployment.

### Pledging

The pledge is the amount of ada that the stake pool operator ‘delegates’ to their own pool when it is created. This pledge represents the commitment of the operator to maintain their pool and support network activity. Making a pledge is not required, however, it is recommended to pledge some ada to the stake pool prior to running it. The more ada that is pledged, the higher the pool rewards, which are dependent on the pool’s level of uptime and its [performance](https://docs.cardano.org/en/latest/getting-started/stake-pool-operators/stake-pool-performance.html).

> **Further reading:**
> -   [Pledging and rewards](https://docs.cardano.org/en/latest/explore-cardano/understanding-pledging-and-rewards.html)
> -   [Delegation and pledging advice for large SPOs](https://docs.cardano.org/en/latest/getting-started/guidelines-for-operating-large-stake-pools/index.html#delegation-and-pledging-advice)

### Delegation

Ada holders who do not have technical expertise in maintaining a stake pool can earn rewards by delegating to any stake pool available on the network. The Daedalus wallet provides a convenient user-friendly interface that allows users to easily start delegating to any registered stake pool. 

> Note: ada holders and SPOs who pledge or delegate will always have access to their ada. If the delegated ada is spent or removed from the pool, the rewards decrease respectively. 

> **Related documentation:**
> -   [Registering a stake pool](https://docs.cardano.org/projects/cardano-node/en/latest/stake-pool-operations/register_stakepool.html#)
> -   [Creating a delegation certificate](https://github.com/cardano-community/guild-operators/blob/alpha/docs/Staking/Delegates.md#create-a-delegation-certificate-and-submit-to-the-network)

> **Further reading:**
> -   [Advice for Stakeholders - Delegators and Stake Pool Operators](https://iohk.io/en/blog/posts/2020/11/13/the-general-perspective-on-staking-in-cardano/)

### Rewards

Delegators earn rewards for participating in staking (either pledging or delegating) and these rewards are automatically distributed between the participants according to the rewards scheme. The rewards scheme in Cardano is designed to be decentralized, which means that there is no single controlling party. 

> **Related documentation:**
> -   [Withdrawing rewards](https://docs.cardano.org/projects/cardano-node/en/latest/stake-pool-operations/withdraw-rewards.html) 
> -   [Understanding pledging and rewards](https://docs.cardano.org/en/latest/explore-cardano/understanding-pledging-and-rewards.html)

### FAQs

1. **Q: How do I create and register a stake pool?**

   **A**: Please review the steps in the documentation [here.](https://docs.cardano.org/projects/cardano-node/en/latest/stake-pool-operations/getConfigFiles_AND_Connect.html)

2. **Q: How do I generate staking addresses?**

   **A**: Please review the steps in the documentation [here.](https://docs.cardano.org/projects/cardano-node/en/latest/stake-pool-operations/register_key.html)
   
3. **Q: How do I determine an optimal amount of ada to pledge to each pool?**
   
   **A**: This is a personal preference, the more you pledge the higher the rewards.

4. **Q: How do I know if my pool is oversaturated?**

   **A**: If the amount of ada delegated to the pool is over 32 million, the pool is oversaturated.

5. **Q: How do I know who has delegated to my pool?**

   **A**: You can query the ledger state.

6. **Q: How can I calculate rewards?**

   **A**: This is calculated automatically by the Ouroboros protocol. 
   
7. **Q: How can I verify whether my pool was successfully registered on mainnet?**

   **A**: You can check [pooltool.io](https://pooltool.io/) or run the following curl command:
```
curl -X POST -H "Content-Type: application/json" -d '{"query": "query getStake_pool($id: StakePoolID!){ stakePools(limit: 1 where: { id: { _eq: $id } }){ id } }","variables":{"id":"$My_Pool_id_here"}}' https://explorer.cardano.org/graphql:
```




