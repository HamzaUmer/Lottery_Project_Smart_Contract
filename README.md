# Lottery_Project_Smart_Contract

This is a Solidity smart contract that implements a simple lottery system. Let's take a look at how it works:

The contract has a state variable manager that stores the address of the contract creator. This variable is set in the constructor function, which is automatically called when the contract is deployed.

The contract has a dynamic array participants that stores the addresses of all participants who have sent the required amount of ether to the contract. The receive() function is a special function that is automatically called whenever ether is sent to the contract. It checks that the sender has sent exactly 0.05 ether, and then adds their address to the participants array.

The getBalance() function returns the balance of the contract in wei, but only if the caller of the function is the contract manager. This function can be used to check how much ether has been collected in the contract.

The random() function generates a random number using the hash of the block difficulty, the current timestamp, and the length of the participants array.

The selectWinner() function can be called by the contract manager to select a winner from the participants array. It first checks that the contract manager is calling the function, and that there are at least three participants in the array. It then generates a random number using the random() function, selects a winner based on the random number, transfers the entire balance of the contract to the winner, and resets the participants array to an empty array.

Note that this is a very simple implementation of a lottery and is not suitable for use in the real world. It is missing many important features such as preventing multiple entries from the same participant, preventing the contract manager from cheating, and ensuring fairness of the selection algorithm.
