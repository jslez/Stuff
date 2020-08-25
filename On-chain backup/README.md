## HashShot - Token teams could avoid restarting from scratch if bug or systemic error. 

![lensOfTruth](http://www.i2symbol.com/pictures/emojis/f/2/0/4/f2042fedcbc0cdaee2967c4449b62845_256.png)

| Address        | Balance (ABCtoken)       | lastTxId  | 
| ------------- |:-------------:| -----:|
| 0x12345       | 410.31411    | 0x12313....6E234 |
| 0xABCDE      | 0.00041      | 0xABCDE....6E234 |
| 0x1F223 | 1.1       | 0x56789....UE2v4 |

Periodic snapshots of current balances/asset holders, hashed, and then applied into a transaction on the chain with the longest duration of immutability (basically the hardest in the room to bs).

# How It Works - Example using a team who has an ERC-20 token.

We deploy our new cool DeFi project, sadly, given the market momentum hustling us to go live earlier than we'd like, we didn't get audited and 5 days later we have a critical bug found. Our options are:

* Broadcast that the party is over, and "stay tuned, thanks for participating in our experiment!"
* Redeploy with a fix, from point X before the incident. Software update basically.

Lets assume this is our ledger of holders below:

(A)
```js
| Address        | Balance (ABCtoken)       | lastTxId  | 
| ------------- |:-------------:| -----:|
| 0x12345       | 410.31411    | 0x12313....6E234 |
| 0xABCDE      | 0.00041      | 0xABCDE....6E234 |
| 0x1F223 | 1.1       | 0x56789....UE2v4 |
```

The hash of this snapshot (copy paste the text in the box as is, and put through SHA256) is:

(B)`86a5f89df0e950c6fcf72240b51dd5e20be0e8d4771939497319746d1e3816b6`.

To redeploy with a fix/path the contract will redeploy only if **SHA256(A) == B**

Essentially, it's a restart button.

- Pay for opt-in insurance. If you pay x% of your yield earnings or whatever, you will be considered part of the hashshot redeployment. If you don't you gamble with smart contract risk bugging out.

- Bearer assets are put to work (e.g. held externally and a minted reproducable one is used for day-to-day).

- Teams can use this as a safety net, and be transparent instead of tip-toeing "decentralized" while they're always holding an admin key.

## How come?

The premise that teams don't must operate as if things will be immutable is likely going to create unneccessary risk to the ecosystem. Even more as the "smart contract composability" hype train keeps it's pace.

A fantastic problem to have of course, but it poses a risk for the longer term should a contract bug/hack/compromize/etc... It's set a good foundation for best practices, and cautiously executing which is great. Moving forward, assets that are going to move faster, and expirement would likely want to have something like this.

## Muh immutable

I don't think that there's problems with other chains or tokens reverting some sort of deployment. Such early days means experimentation will likely yield faster iterations to see what sticks.

The main key part is to manage expectations. If you are very transparent to the token holders that in the future this may/may not be a thing etc... People won't mind. If people are under a different assumption, then likely turns into pitchforks.
