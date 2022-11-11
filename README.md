Goal of this project : learn more about solidity. I write in this file what I learn during this work.

# events
why do we have that much events ?
Events are to publish actions to listeners outside the blockchain. Smart contracts themselves cannot listen to any events.
Generally, events are used to inform the calling application about the current state of the contract, with the help of the logging facility of EVM. Events notify the applications about the change made to the contracts and applications which can be used to execute the dependent logic.
Solidity events are crucial for smart contract developers because they allow smart contracts to index variables in order to rebuild the storage stage, help to automatically update the user interface, and allow for testing of specific variables.
We can have up to three indexed parameters per events.
https://ethereum.stackexchange.com/questions/56879/can-anyone-explain-what-is-the-main-purpose-of-events-in-solidity-and-when-to-us
https://ethereum.stackexchange.com/questions/5891/what-are-the-benefits-of-using-events-over-dedicated-indexed-variable
https://www.youtube.com/watch?v=w18c9HLEuBs&ab_channel=PatrickCollins

if we want to search a particular event by the parameter that was logged, then we use the keyword indexed
# indexed

What is the indexed keyword / when do we use it ?
The indexed parameters for logged events will allow you to search for these events using the indexed parameters as filters.


Can we use it other places ie outside of events? 
The indexed keyword is only relevant to logged events.
indexed parameters are also know as topics.
We can then filter our events according to the indexed parameters :)


# the constructor

when you call your constructor the initial parameters are given at deployment time (on remix we have an interface (not the datastructure ^^) to do so)

address(0) : we don't want the address "0", sometimes it has more rights, sometimes it is used as a burn, in short we avoid that it is in our contract
https://stackoverflow.com/questions/48219716/what-is-address0-in-solidity


# Some other interesting stuff 

store msg.sender in a local variable or call every time msg.sender : https://stackoverflow.com/questions/64854256/how-much-accessing-msg-sender-costs-is-it-useful-to-store-it-in-a-variable-an
https://ethereum.org/en/developers/docs/evm/opcodes/
solidity call function : https://www.alchemy.com/overviews/solidity-call

Assignments between storage and memory (or from calldata) always create a separate copy.
Assignments from memory to memory only create references. Therefore changing one memory variable alters all other memory variables that refer to the same data.
Assignments from storage to a local storage variable also only assign a reference.
All other assignments to storage always copy.