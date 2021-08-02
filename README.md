# 🏗 Scaffold-ETH - 🎟 Simple NFT Example

> Build, mint, and send around your own ERC721!

# 🏃‍♀️ Quick Start
Required: [Node](https://nodejs.org/dist/latest-v12.x/) plus [Yarn](https://classic.yarnpkg.com/en/docs/install/#mac-stable) and [Git](https://git-scm.com/downloads)

```
git clone https://github.com/austintgriffith/scaffold-eth.git simple-nft-example
```
```
cd simple-nft-example
git checkout simple-nft-example
yarn install
yarn start
```

> in a second terminal window:

```
cd simple-nft-example
yarn chain
```

First, be sure to check that you're deploying on `mumbai` by changing the `defaultNetwork` in `packages/hardhat/hardhat.config.js` and `targetNetwork` in `packages/src/App.jsx`.

![instruction1](https://ibb.co/Chq2311)

![instruction2](https://ibb.co/0hY8QY7)
 
🔐 In a third terminal window, run this to get your account address:

```
yarn generate
yarn account
```

Go to https://faucet.matic.network to get some Mumbai-MATIC.

> Once you've confirmed that your account has the gas needed for the rest of the tutorial (feel free to check on https://mumbai.polygonscan.com), run this in that terminal window:

```
cd simple-nft-example
yarn deploy
```

📱 Open http://localhost:3000 to see the app

> ✏️ Edit the mint script mint.js in packages/hardhat/scripts and update the `toAddress` to your frontend address (wallet address in the top right or localhost:3000).

![instruction3](https://ibb.co/8cpWD95)

![nft1](https://user-images.githubusercontent.com/526558/124386962-37e5dd00-dcb3-11eb-911e-0afce760d7ee.png)

> in a terminal window run the mint script:
```
yarn mint
```
![nft2](https://user-images.githubusercontent.com/526558/124386972-3d432780-dcb3-11eb-933e-dad7dfd313b2.png)

👀 You should see your collectibles show up on the frontend if you minted to the correct address:

![nft3](https://user-images.githubusercontent.com/526558/124386983-48965300-dcb3-11eb-88a7-e88ad6307976.png)

👛 Open an incognito window and navigate to http://localhost:3000 (You'll notice it has a new wallet address).

⛽️ Grab some gas for each account using the faucet:

![nft4](https://user-images.githubusercontent.com/526558/124387005-55b34200-dcb3-11eb-8565-1ee40b5634ad.png)

🎟 Send an NFT to the incognito window address:

![nft5](https://user-images.githubusercontent.com/526558/124387008-58ae3280-dcb3-11eb-920d-07b6118f1ab2.png)

🕵🏻‍♂️ Inspect the `Debug Contracts` tab to figure out what address is the `owner` of `YourCollectible`?

💼 Edit your deployment script `deploy.js` in `packages/hardhat/scripts`

🔏 Edit your smart contract `YourCollectible.sol` in `packages/hardhat/contracts`

📝 Edit your frontend `App.jsx` in `packages/react-app/src`

⬇️ Installing a new package to your frontend? You need to `cd packages/react-app` and then `yarn add PACKAGE`

# 📡 Deploy NFT smart contract!

🛰 Ready to deploy to MATIC mainnet?
> Change the `defaultNetwork` in `packages/hardhat/hardhat.config.js` to `matic`

![instruction3](https://ibb.co/b3Ftpx8)

Make sure you have some MATIC (mainnet) tokens for this. You can exchange for MATIC tokens via. a bridge like UniSwap or SushiSwap.

👛 View your deployer address using `yarn account` to ensure you have some MATIC.

![nft8](https://user-images.githubusercontent.com/526558/124387068-8004ff80-dcb3-11eb-9d0f-43fba2b3b791.png)

👨‍🎤 Deploy your NFT smart contract:
```
yarn deploy --network matic
```
> ✏️ Edit your frontend `App.jsx` in `packages/react-app/src` to change the `targetNetwork` to MATIC:

![instruction4](https://ibb.co/9sPNTy4)

You should see the correct network in the frontend:

![nft10](https://ibb.co/8cpWD95)

🎫 Ready to mint a batch of L2 NFTs for reals?
```
yarn mint
```
Once deployed, you should be able to see them on your Frontend. Check OpenSea for the smart contract and your minted NFTs too!

![nft11](https://user-images.githubusercontent.com/526558/124387132-b04c9e00-dcb3-11eb-95d1-03b8c272e52f.png)

# ⚔️ Side Quests
## 🐟 Open Sea
> Check out your contract on OpenSea's MATIC viewer (Under "My Collections")

![instruction5](https://ibb.co/rt0PwJS)

## 🔍 Maticscan Contract
> Feel free to also check your contract address on Polygonscan (extractible from the terminal where you deployed the contract).

# 🛳 Ship the app!
> ⚙️ build and upload your frontend and share the url with your friends...

```
# build it:

yarn build

# upload it:

yarn surge

yarn s3

yarn ipfs
```
![nft14](https://user-images.githubusercontent.com/526558/124387203-fe61a180-dcb3-11eb-8d68-82a76a514e43.png)

👩‍❤️‍👨 Share your public url with a friend and ask them for their address to send them a collectible :)

![nft15](https://user-images.githubusercontent.com/526558/124387205-00c3fb80-dcb4-11eb-9e2f-29585e323037.gif)

------------

# FAQs

What happens if I run into a chainID error?
		Under `packages/hardhat/deployments`, make sure that your chainID for your desired chain to deploy to is correct. The chainID file is located under their respective chain folders. For Matic, the correct chainID is 134. For Mumbai, the correct chainID is 80001.

What happens if I run into a gas error?
		This can be caused by many things. First check if you do have enough gas to deploy on your various networks. Then, try to raise the `gasPrice` as shown below under `packages/hardhat/hardhat.config.js`.

![instruction6](https://ibb.co/NyGCcRp)

# Documentation

For a more in-depth explanation, documentation, quick start guide, tutorials, tips and many more resources, visit our documentation site: [docs.scaffoldeth.io](https://docs.scaffoldeth.io) 

# 💬 Support Chat

Join the telegram [support chat 💬](https://t.me/joinchat/KByvmRe5wkR-8F_zz6AjpA) to ask questions and find others building with 🏗 scaffold-eth!
