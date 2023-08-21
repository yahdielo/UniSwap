# Uniswap

Uniswap is a decentralized exchange on the Ethereum network, with a revolutionary change un like traditional finance uniswap uses AMM (automatic market maker) for the token trading pairs, basically, liquidity is divided in two  pools for example, DAI/WETH you will have one pool containing weth and the other pool holding DAI tokens.

As AMM's prices are related to the pools fluctuations, if you want some dai you deposit some WETh, and Dai becomes more scarce and so it becomes more expensive, and this also opens opportunities for arbitrage, because pools prices are a contract product of the pool balances. so prices might change from DEX to DEX

In the  SWAPTOKEN repo contains a smart contract that can swap tokens assuming the tokens are in possession of the smart contract, and not on a external wallet.

Also all contracts will be interacting directly with the uniswap v3-core smart contracts, wish we can find at this address: 0x8eB105CFc7ec7ebF126586689683a9104E6ec91b.

The reason for this is that we want to be testing and developinf using the same exact contracts bytecode deploy by unilabs to the mainnet.

## SwapTokenContract

in the repo Swap token contract contains a smart contract that inherits from uni swap IswapRouter and 
is able to swap ERC-20 tokens, assuming the funds are inside the smart contract and not in an external wallet.

 The idea of this is to implement the function to swap tokens inside the flash loan contract to e able to trade the borrowed funds.

more info in the token contract README directory

## compile and deploy
To compile the solidity contract run :

 npx hardhat compile

to depploy the contract to the goerli testnet:

 npx hardhat run scripts/deploy.js --network goerli

* todo: create POOL contract

# ERROR to look out

if you are cloning this repo make sure to run:

    npm init

    npm install --save-dev hardhat

    npm install --save-dev @nomicfoundation/hardhat-toolbox

    npm install dotenv --save

    npm install @uniswap/v3-core

you might have a problem at the compilation where it doesn't recognize some dependencies, in that case delet the package.json, package-loch.json and last node_modules, ones you deleted them install all the dependencies again. and you might have to do that one or two times.

when you are executing the contract functions make sure is loaded with some tokens to perform the swaps.

currently, the executesingleswap is hardcoded to swap some link tokens for WETH , the parameter amount is how much link you want to swap for weth, Note to self, make this a dinamic fucntion, to pass the desire token we want to swap and the amount as arguments
