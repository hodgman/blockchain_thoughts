
A "blockchain wallet" is basically just a unique 256-bit number (that's a big number!), and operates based on the digital signature tools of a "Secret Key" and an "Address".

**Secret Key (AKA Private Key, AKA "WIF")**: pick a random number from 0 to 2^256. If truly random, there's a 0% chance in practice that anyone else will ever pick the same number as you. 

**Address (aka Public Key)**: we do some math to produce a new number from the private one. This math is (practically) impossible to reverse, so you can safely share this number as a unique ID for yourself. Cryptocurrencies will use your address to identify the owner of each account / balance.

This mathematical magic can turn the secret key into something analogous to a physical object, like a forge-proof stamp.

## Digital signatures:

Using your Secret Key, you can produce a "Signature" for a particular file or block of data. 

Someone else can compare the signature, the file, and your Public-key/Address, and check if the signature is correct or not. It's (practically) impossible to forge a digital signature (*except for by taking physical possession of the secret key, which is often stored in a special hardware device the size of a USB thumb-drive*).

This technology is widely used for secure software updates, reputation and security on app stores, and secure internet (HTTPS).

## Blockchain:

A blockchain is much like a traditional database, or spreadsheet, but can be updated by multiple people. Individual changes (e.g. "add 1 to row number 6") are grouped together into a "block" of changes for sharing between different users who are hosting the database.

There are rules to how the data can be changed -- e.g. "*if moving money from one row to another, the user who owns the row that is sending the money must sign the transaction*". When receiving a block of changes, everyone must check that these fixed rules were followed (and if not, that entire block is discarded).

## Bitcoin - the 1st generation of Blockchain:

If anyone in the world can make changes at any time, the system could be flooded with so many new blocks that it would be impossible to synchronise and agree on the order that blocks should be applied, so impossible to agree on the balance of each account.

So, Bitcoin's big invention was to apply "Proof of Work" to deliberately slow the network down. A rule is added to the system so that when receiving a new block, you should discarded it unless it comes attached with a proof for an arbitrary puzzle that is known to take a long time to solve. The puzzle difficulty is tuned over time, so that on average, a new (valid) block will only turn up once every few minutes or so, which gives everyone a chance to check it and agree on the current state of things.

This was an amazing proof of concept at the time (there's no authority but consensus is reached globally!) but in the long run has turned out to require an almost inconceivable amount of useless work to be done. This has made a lot of people very angry and been widely regarded as a bad move.

## Mining:

To encourage people to contribute to the Bitcoin network by processing transactions and checking if blocks are correct, the concept of "mining" was added. Every time someone solves the arbitrary puzzle to produces a new block of valid transactions, they get to invent a small amount of new Bitcoin currency and give it to themselves. This eventually incentivized industrial-scale "bitcoin mines".

Mining has a similar economic effect to inflation, where the newly increased supply of the currency is equivalent to devaluing everyone else's accounts by a small percentage. So in effect, everyone who holds Bitcoin is indirectly paying the miners for this operation.

## Transaction fees:

The bulk of a miner's income comes from the mining bonus, but they also gain a small amount from transaction fees. The main driver of high transaction fees is that these "Proof of Work" networks are incredibly slow -- typically processing about one transaction per second, globally. Each miner can only accept so many transactions, so in busy periods, they only accept ones where the users have volunteered to pay higher fees (think Uber surge pricing). Users then end up bidding against each other to ensure their transactions actually get processed.

## Etherium - the 2nd generation of Blockchain:

Bitcoin was a simple spreadsheet where each row contains a user's Address, and a balance of "money" (bitcoins). The only transactions possible are moving "money" between different addresses.

Etherium took this system and added the ability for users to write programs for it -- much like how adding Javascript in a web browser changed the web from static pages to allowing actual apps, like YouTube or Google docs. This allows people to develop apps that are not hosted in any specific place, but can complete tasks securely with global consensus on the outcomes.

## Etherium 2.0:

Etherium uses the same consensus mechanism as Bitcoin, where semi-industrial "mines" run hundreds of computers, competing against each other to complete the puzzle first, so they can get the mining reward. 

As this is **incredibly** inefficient, they have been slowly moving to adopt "Proof of Stake" instead of "Proof of Work". In this system, instead of solving an arbitrarily hard problem, miners are chosen at random in a lottery mechanism, with the number of tickets equivalent to the amount of "money" (Etherium tokens) that each miner has placed into escrow (aka "staked").

This is not an ideal democracy, as your chance of gaining a mining reward is linearly proportional to your amount of capital... but, that's still an improvement on the previous system. Bitcoin and Eth1.0 mining has large "economy of scale" effects, where industrial mining is much more efficient than home mining, gaining a super-linear proportion of rewards based on their capital.

Also, this system is still competitive, with large numbers of people being incentivised to add as many nodes as possible to the network, which again hurts efficiency and limits speed.

## Delegated Proof Of Stake blockchain projects - the 3rd generation of Blockchain:

Etherium 2.0 will supposedly require 1% of the energy that Eth1.0 currently uses, however, even that is still an almost unimaginable amount of energy! This is because there are still over 10k "miners" running computers that are competing against each other in that lottery - and the act of mining is still siphoning "money" from regular developers and users to these large capital holders.

So, several other blockchains use different variations of "Proof of Stake". A popular one is "delegated proof of stake" where mining and the lottery system can be removed entirely. Instead, only the number of computers that are actually required to run the network are required to be active - as few as a dozen servers - and these slots are chosen via an election (again though: with votes based on capital).

Instead of competing for rewards, this small number of nodes cooperates to create an efficient schedule of when each PC will be in the role of "block producer", and they are funded only through transaction fees instead of large mining rewards.

The parameters of the system itself (such as how high/low the transaction fees are) can be voted on by the user-base, and to create a stable ecosystem, hopefully different users who are aiming to be elected to host a processing node, should compete on price to keep fees low enough to only barely be profitable.

## Phantasma:

When we (GOATi) decided to experiment with some of this technology, we picked a fairly small project - Phantasma - that had a vision of an efficient and sustainable system like this, and were still in early development. This meant we could hopefully help guide the development to stay on that vision.

So far, transactions on the Phantasma network are remaining at cost price -- lower than a fraction of a cent each (*cheap enough that we can cover that cost and can hide all blockchain details from the users of our Apps*). Meanwhile, simple Etherium transactions can range from $5 up to $100 -- sometimes over a million times more expensive than cost price, because the network is so slow and inefficient that people have to competitively bid to get their transactions processed.

Not only is this kind of modern network more efficient (using literally **a billion times** less electricity) it's also much faster due to the cooperative scheduling. The performance target for the phantasma network is to cope with 5000 transactions per second, compared to the typical 1-per-second on "Proof of Work" networks.

Phantasma is not the only network of this kind -- there are literally hundreds of similar blockchain systems being developed that make use of more modern research than the 1st and 2nd generation blockchains used.

## Energy use:

Bitcoin's energy use is estimated at 115.84TWh ($5.8Bn worth @ 5c/kWh)

Etherium's energy use is estimated at 48.37TWh ($4.8Bn worth @ 10c/kWh)

^ Bitcoin's estimated electricity price is lower (5c vs 10c) due to higher industrialization of mining.

https://digiconomist.net/ethereum-energy-consumption

https://cbeci.org/

My estimate of Phantasma's energy use is 0.00000548TWh ($548 worth @ 10c/kWh).

That's the planned 10-node ring, with each node requiring on one quarter (e.g. 2 of 8 CPU cores rented as a virtual server) of a 500W server rack, utilized at half power load.

500W * half load * 1/4 occupancy * 10 nodes = 625W

Annulaized: 625W * 24hr * 365 days = 5475kWh

A single Etherium transaction is estimated to use 98kWh.

Phantasma can process 5000 transactions per second - so up about 157 billion transactions per year (per each 10-node ring deployed). 5475kWh / 157680000000 = 0.035 milliwatt hours per transaction

One hour of Netflix streaming is estimated (by the Shift Project) to use 0.8kWh, so:

- Running the entire Phantasma network for a year is equivalent to ONE person leaving Netflix running for 285 days straight.
- Running the entire Etherium network for a year is equivalent to 7 million people leaving Netflix running for 365 days straight.
- Running one Phantasma transaction is equivalent to one person watching Netflix for 0.15 milliseconds.
- Running one Etherium transaction is equivalent to one person watching Netflix for 5 days straight.

Boiling 1L of water in your electric kettle takes about 0.1 kWh, so:

- Running the entire Phantasma network for a year is equivalent to 55 thousand kettles.
- Running the entire Etherium network for a year is equivalent to 484 billion kettles.
- Running one Phantasma transaction is equivalent to one person flicking on an empty kettle and having it turn off immediately.
- Running one Etherium transaction is equivalent to boiling 980 kettles.

## Tokens:

The Bitcoin network has one token (currency): Bitcoin. The Etherium network has one built-in token (ETH), which is used for mining rewards and transaction fees, but due to it being programmable, app developers can create their own "tokens". 

Most of these tokens act like currency, in that you can just imagine them as a spreadsheet item containing a "balance" per row. These kinds of tokens are called "fungible" - meaning that balances of the token are interchangeable (If I give you $10 and you give me 2x $5, it's even).

## NFTs:

Etherium (and other programmable blockchains) also allow other kinds of tokens to be created by applications. If a token does not act like a currency, then it is called non-fungible. This is more like a typical database row that could contain any information. It could contain the names of basketball players -- If we trade the text "Michael Jordan" for the text "Andrew Gaze", that's not a simple mathematical equality any more, so it's "non fungible".

At this point, the system acts like a regular database (or file-system), but rows in that database (or files in that folder) can be locked so that only a particular user is allowed to modify them.

## The NFT controversy:

In the past year, NFT's moved beyond a tech jargon for "a row in a spreadsheet, but blockchain", and took on a life of its own in a weird art-driven speculation bubble.

People were selling their art "as an NFT", which meant putting *something* into an NFT (that's "a row in a spreadsheet, but blockchain"), often a URL to the picture, and then charging huge amounts of money to transfer control of that "row in a spreadsheet" to another user. Does this transfer constitute licensing the artwork? Not really - there's no license agreement present / maybe - money did change hards for *something* / unknown - no one has challenged it in court. Most places selling cryptoart leave it vague as to what rights are being transferred, and a few actually come with a EULA that specifically outlines that *no* rights are being transferred as part of the sale.

There is a popular screenshot going around that explains cryptoart like this:
>> https://i.redd.it/dye9khpxddw61.jpg
>> Imagine if you went up to the mona lisa and you were like "i'd like to own this" and someone nearby went "give me 65 million dollars and I'll give you this receipt of purchase". So you paid them and they went "here's your receipt, thank you for your purchase" and went to an unmarked supply closet in the back of the museum and posted a handmade label inside it behind the brooms that said "mona lisa currently owned by <your name>". So if anyone wants to know who owns it they'd have to find this specific closet in this specific hallway and look behind the correct brooms. And you went "can i take the mona lisa home now?" and they went "oh god no are you stupid? you only bought the receipt that says you own it, you didn't actually buy the mona lisa itself, you can't take the real mona lisa you idiot. You CAN take this though." And gave you the replica print in a cardboard tube that's sold in the gift shop. Also the person selling you the receipt of purchase has at no point in time ever owned the mona lisa. Unfortunately, if this doesn't really make sense or seem like any logical person would be happy about this exchange, then you've understood it perfectly

Unfortunately, that's a pretty accurate description of *some* of the ways that NFTs have been used recently!

There are wonderful sections of community supporting artists with new income streams... and there are people "selling" NFTs containing links to artwork that they didn't create. It's a messy space.

So now in 2021, this weird, sometimes honest but often ill-defined to outright-scammy speculation bubble, combined with the ecological impact of Bitcoin/Etherium's Proof-of-Work industrial-scale mining operations, have been described in a lot of articles, explaining that *this phenomenon* is what an NFT is. I'd like to get pedantic and point out that an NFT is just jargon for "*a spreadsheet row with a permission system, in a community hosted database*", and that *this phenomenon* is what the highest-profile use for these spreadsheets has been for the past year is... but it may be too late for that nuance. Any mention of that tech jargon is met with instant hatred on social media now, not matter what you're using it for.

If you take any discourse about NFTs and replace "NFT" with "a spreadsheet row", it all starts to sound rather silly. That's expected for a new buzzword in a controversial field... but it's reached the point where a huge amount of the internet has been educated as to what "an NFT is" as a much higher level concept/phenomenon than what the original bit of jargon was limited to. So if you are working on a project that really does just use *a spreadsheet row with a permission system, in a community hosted database*, what should we call that now?