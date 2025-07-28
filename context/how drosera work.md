# How Does Drosera Work?

### Traps

Traps are a set of smart contracts that define the conditions for detecting invariants and performing on-chain responses. Traps have an on-chain and off-chain component that are described below:

- **Trap** - An off-chain smart contract that performs data collection and analysis to signal the execution of an on-chain response function.
- **Trap Config** - An on-chain smart contract that configures the trap and defines the on-chain response callback function. Example: "pause(uint256)" , "react(address)", etc.

The Trap Config holds a hash of the Trap contract and the address of the on-chain response function. It is used to help coordinate the execution of the Trap and the on-chain response function with Operators as well as holding them accountable for doing so.

:::info
The term analysis here is used to describe **analysis of on-chain state** and does not mean smart contract code analysis with tools like Slither, etc. A trap is collecting state data every block and analyzing the state data to make a decision if the logical criteria have been met or not to trigger the execution of an on-chain response function.
:::

### Operators

Operators are crucial players in Drosera, consisting of organizations and solo stakers who run the Drosera Operator Client software to help maintain and protect the DeFi ecosystem. These dedicated individuals are responsible for executing Traps and performing on-chain response actions, ensuring the security and stability of the network.

To execute a Trap, an Operator must first gain permission by opting into the specific Trap. Once opted in, the Operator gains access to the off-chain Trap and the current peers in the network. This allows them to actively participate in monitoring and evaluating every new block based on the conditions set by the Trap.

In the event that the conditions of a Trap are met, the Operator will promptly execute the on-chain response function. This swift action helps to mitigate potential threats and exploits.
