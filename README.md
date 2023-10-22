## CelebXperience- Decentralized Knowledge Exchange


<!-- Description -->

##### CelebXperience is a decentralized knowledge exchange platform that enables creators and communities to grow, engage, and improve by providing an easy way to exchange “Knowledge NFTs” containing exclusive content such as techniques, strategies, theories, and experiences.

<hr>

## Table of Contents
  - [Features](#features)
  - [Getting Started](#getting-started)
  - [Reset Wallets](#reset-wallets)
  - [Mint NFT](#mint-nft)
  - [Sell NFT](#sell-nft)
  - [Buy NFT](#buy-nft)
  - [Accept Buy Offer](#accept-buy-offer)
  - [Accept Sell Offer](#accept-sell-offer)
  - [Cancel Buy Offer](#cancel-buy-offer)
  - [Cancel Sell Offer](#cancel-sell-offer)
  - [Get NFT Data from IPFS](#get-nft-data-from-ipfs)
  - [List Account NFTs](#list-account-nfts)
  - [List Account NFT Offers](#list-account-nft-offers)
  - [List Account NFT Buy Offers](#list-account-nft-buy-offers)
  - [List All CelebXperience Accounts](#list-all-CelebXperience-accounts)
  - [List All NFTs in CelebXperience](#list-all-nfts-in-CelebXperience)
  - [List All NFT Offers in CelebXperience](#list-all-nft-offers-in-CelebXperience)
  - [Append Address to Database](#append-address-to-database)

<hr>

## Features
- Mint, Sell, Purchase, Cancel and Exchange NFTs in the Ripple Ledger using the latest XLS-20 standard
- Check the latest offers and bids for NFTs with all addresses registered
- Sign & Submit transactions asyncronously
- Decentralized file storage system using IPFS & NFT.Storage
- Simulate Account Generation and Transaction Execution
- Easy to use API for implementing the XLS-20 standard in a python script
<hr>

## Getting Started

#### To first get started with the functional demo, you need to clone the project using git.
<br>

```
1. git clone https://github.com/KingofHackathons/CelebXperience.git
```

#### Now go inside the project folder `CelebXperienceopen` and run the following command to install the dependencies (python 3+ required)
<br>

```
2. pip install -r requirements.txt
```

#### Now you have to create an NFT.Storage account and put the API Key in the `.env` file.
<br>

```
3. IPFS_KEY=KEY_HERE
```

#### Now you can run the following command to fire up the demo.
<br>

```
4. python3 xluxApiDemo.py
```

#### A request creator tool like CURL, Postman, or Swagger can be used to experiment with the API.
<hr>

# API

<!-- Make an API table -->
## Reset Wallets

All API requests interact with NFT-Devnet wallets that are currently stored in memory. You are able to change the default wallets in the API and you are also able to generate complete new ones throughout the demo.

<br>

Sets the account for the NFT issuer:
```http
POST /set_seller_account
```

Body Parameter:

```json
{
    "secret": "NFT-Devnet-Secret"
    "sequence": "NFT-Devnet-Sequence"
    "address": "NFT-Devnet-Address"
}
```

<br>

Sets the account for the NFT Buyer:
```http
POST /set_buyer_account
```

Body Parameter:

```json
{
    "secret": "NFT-Devnet-Secret"
    "sequence": "NFT-Devnet-Sequence"
    "address": "NFT-Devnet-Address"
}
```

<br>

Generate two random accounts to act as the NFT issuer and buyer:

```http
POST /generate_accounts
```

<hr>

## Mint NFT

Mint an NFT to the NFT issuer's account.

<br>

```http
POST /mint
```

Form Parameter:

```json
    "name": "NFT-Name"
    "description": "NFT-Description"
    "sellprice": "NFT-Sell-Price"
```

<br>

File Parameter:

```json
    "files[]": "NFT-Image"
```

<hr>




## Sell NFT

Sell an NFT to the NFT buyer's account.

<br>

```http
POST /sell-nft
```

Form Parameter:

```json
    "NFTokenID": "NFT-Token-ID"
    "sellprice_in_xrp": "NFT-Sell-Price"
```

<hr>




## Buy NFT

Buy an NFT from the NFT issuer's account.

<br>

```http
POST /buy-nft
```

Form Parameter:

```json
{
    "NFTokenID": "NFT-Token-ID",
    "buyprice_in_xrp": "NFT-Buy-Price"
}
```

<hr>


## Accept Buy Offer

Accept a buy offer for an NFT.

<br>

```http
POST /accept_buy_offer
```

Form Parameter:

```json
{
    "buy_offer_index": "NFT-Buy-Offer-Index"
}
```

<hr>




## Accept Sell Offer

Accept a sell offer for an NFT.

<br>

```http
POST /accept_sell_offer
```

Form Parameter:

```json
{
    "sell_offer_index": "NFT-Sell-Offer-Index"
}
```

<hr>




## Cancel Buy Offer

Cancel a buy offer for an NFT.

<br>

```http
POST /cancel_buy_offer
```

Form Parameter:

```json
{
    "buy_offer_index": "NFT-Buy-Offer-Index"
}
```

<hr>




## Cancel Sell Offer

Cancel a sell offer for an NFT.

<br>

```http
POST /cancel_sell_offer
```

Form Parameter:

```json
{
    "sell_offer_index": "NFT-Sell-Offer-Index"
}
```

<hr>




## Get NFT Data from IPFS

Get NFT data from IPFS.

<br>

```http
GET /get-nft-data-ipfs
```

Query Parameter:

```json
{
    "url": "ipfs.io/ipfs/<hash>/metadata.json"
}
```

<hr>




## List Account NFTs

List all NFTs in an account.

<br>

```http
GET /list-acc-nfts
```

<hr>




## List Account NFT Offers

List all sell offers in a NFT.

<br>

```http
GET /list-acc-sell-nft-offers
```

Form Parameter:

```json
{
    "NFTokenID": "NFT-Token-ID"
}
```

<hr>




## List Account NFT Buy Offers

List all NFT buy offers in an account.

<br>

```http
GET /list-acc-nft-buy-offers
```

Form Parameter:

```json
{
    "NFTokenID": "NFT-Token-ID"
}
```

<hr>




## List All CelebXperience Accounts

List all accounts registered in the CelebXperience platform.

<br>

```http
GET /list-all-CelebXperience-accs
```

<hr>




## List All NFTs in CelebXperience

List all NFTs in the CelebXperience platform.

<br>

```http
GET /list-all-nfts-in-CelebXperience
```

<hr>




## List All NFT Offers in CelebXperience

List all NFT offers in the CelebXperience platform.

<br>

```http
GET /list-all-nft-offers-in-CelebXperience
```

<hr>




## Append Address to Database

Append an address to the database.

<br>

```http
POST /append-add-to-db
```

Body Parameter:

```json
{
    "address": "NFT-Devnet-Address"
}
```

<hr>

Inspiration
The inspiration behind CelebXperience stemmed from the growing desire for unprecedented access to the minds of the world's brightest and most influential figures. We envisioned a platform where individuals could transcend the boundaries of conventional learning and entertainment, gaining access to the rarefied knowledge and unique experiences of their favorite celebrities, influencers, creators, doctors, artists, and experts. This vision was fueled by the notion that in an age of digital innovation, the fusion of blockchain technology and non-fungible tokens (NFTs) offered the perfect means to democratize access to exclusive content.

The idea of owning a piece of Albert Einstein's thought process or receiving personalized coaching from LeBron James is inherently fascinating. We wanted to make this dream a reality, bridging the gap between fans and their idols by enabling the buying and selling of unique techniques, strategies, theories, and experiences. CelebXperience, driven by the XRP Ledger, is not just a platform but a gateway to the extraordinary, where every NFT represents a portal into the world of expertise and inspiration.

What it does
CelebXperience is an innovative platform that enables individuals to purchase and trade exclusive techniques, strategies, theories, and experiences from celebrities, influencers, creators, doctors, artists, and experts at the pinnacle of their respective fields. Using cutting-edge Non-Fungible Tokens (NFTs) built on the XRPL (XRP Ledger), CelebXperience connects buyers with extraordinary, one-of-a-kind content.

How we built it
The CelebXperience platform is powered by a sophisticated Python backend developed using the Flask framework. We deployed the backend API on Heroku and integrated it with the XRPL testnet to facilitate wallet creation, transaction processing, NFT minting, sales, and purchases. To enhance our understanding of the XRPL environment, we also conducted testnet transaction tests with Node.js.

On the front end, we used React.js, employing JavaScript, JSX, and CSS for a seamless user experience. We designed all logos and icons from scratch to ensure a unique and engaging interface.

To make NFTs compatible with the XRP Ledger, we adopted the standards outlined in "0014 XLS-14d" (https://github.com/XRPLF/XRPL-Standards/discussions/30). These standards suggest representing NFTs with a quantity of "1000000000000000e-96" (1) NFT on the ledger.

To mint an NFT, users provide necessary information through our front-end, after which our backend API sets the accounts for the issuer and distributor. Trust lines are configured between these accounts to enable NFT transactions. The issuer sends a payment equivalent to the NFT to the distributor account, effectively minting the token. Subsequently, our backend API creates an offer to sell the NFT at a user-defined XRP price.

Once listed for sale (OfferCreate), the NFT becomes available for purchase within our platform. Other users can acquire the NFT by creating an OfferCreate transaction that meets the seller's price and conditions. Upon completion of the transaction, the buyer takes possession of the NFT, and the seller's NFT is transferred.

Challenges we ran into
The CelebXperience team encountered several challenges during this project. It was our first experience with the XRPL environment, and the goal of minting NFTs, conducting wallet-to-wallet transactions, and displaying NFTs was ambitious. It took time to become fully acquainted with managing fungible and non-fungible tokens within the XRP ledger.

We initially faced OpenSSL issues on Google Cloud when attempting to deploy a functional API. This led us to switch to Heroku to resolve the problem. However, the XRPL's transaction validation process caused timeout issues on Heroku. To address this challenge, we implemented a data streaming solution that prevented the API from timing out, which proved to be highly effective.

Accomplishments that we're proud of
The CelebXperience team is immensely proud of delivering a product that aligns with our initial vision and ambition for CelebXperience. We deepened our understanding of blockchain technology and gained insights into the advantages that XRPL brings to the blockchain industry. Additionally, we developed expertise in managing cold and hot wallets, executing AccountSet and TrustSet transactions, and mastering various concepts within XRPL.

What we learned
Throughout the development of CelebXperience, our team embarked on a profound learning journey. We delved into the intricacies of the XRP Ledger, acquiring an in-depth understanding of how blockchain technology and NFTs function within this environment. This experience deepened our knowledge of cryptographic assets, cold and hot wallets, and the intricacies of executing AccountSet and TrustSet transactions, all while navigating the challenges and intricacies of deploying a functional API.

Beyond the technical aspects, we learned the power of persistence and problem-solving. Overcoming challenges such as OpenSSL issues and API timeouts on Heroku required innovative solutions, and this experience instilled in us the importance of adaptability and teamwork. Our journey with CelebXperience was not only a lesson in blockchain technology but also in resourcefulness and determination, reminding us that even ambitious projects can be successfully realized with dedication and the right mindset.

What's next for CelebXperience
CelebXperience is now focused on establishing partnerships with celebrities, influencers, creators, doctors, artists, and experts to enrich our platform with exclusive content. We aim to create a vibrant ecosystem where individuals can buy, sell, and trade unique experiences and knowledge, fostering a dynamic community of learning and collaboration.

