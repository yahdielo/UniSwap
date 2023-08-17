# UniSwap

this repo will hold the basic logic on how to create a smart contract to interact with uni swap and perform swaps of ERC-20
tokens.

* todo: create POOL contractß

## SwapTokenContract

in the repo Swap token contract contains a smart contract that inherits from uni swap IswapRouter and 
is able to swap ERC-20 tokens, assuming the funds are inside the smart contract and not in an external wallet.

 The idea of this is to implement the function to swap tokens inside the flash loan contract to e able to trade the borrowed funds.

more info in the token contract README directory
