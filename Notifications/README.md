# EIP - Selective Notification 

An lightweight notification system for teams aiming to communicate with their holders, and providing the flexibility for notifying specific levels based on balance or age of asset deposited into the wallet, etc...

This is not intended to be a messaging play. The messaging between wallets would likely be an extension or a more robust system. For the present market size, and needs, this can satisfy and grow into a more broad offering. Teams today need to find a way to message notify holders. Current option usually is something not far from an on-chain are limited to airdrop spam

### For notification recipients
Use of the standard lends to writing _small_, _reusable_ smart contracts that are responsible for enforcing a single transfer restriction pattern.

An implementation like this provides an duel opt-in notification system (recipient and sender must agree on notifying them) which delivers transparency for all, and captures the awareness of the specific user.

To mitigate spam we ensure recipients must grant permission per broadcaster and the frequency in which they're willing to receive notifications. ABCtoken may deliver notifications to their holders every week summarizing their agenda. I may opt-in for notifications but specify a month as the minimum duration between these notifications. A monthly notification from ABCtoken. Others may opt- , just like they do with a trading venue  

### For broadcasters

DAO's currently have a difficult way of communicating on channel that's available to all holders. Twitter and other popular forms may be unavailable in particular regions and others may not be top of mind to the intended message recipient.
* Increase participation and curation of their network.
* Transparency in notifying all participants fairly.
* Broadcast to all, or deliver only to a select tier determined by balance held.

Keeping all things consistent, the one certainty is that they're a holder of a wallet that has already interacted with the token contract, unless airdropped without permission.


## The Standard
The standard builds on ERC-20's interface, adding two functions:
```solidity
// Selective Notification Interface

contract selectiveNotification is ERC20 {
  // Lookup a specific holders permissions to the DAO notifying them. 
  function noteAllowance (address to, bool allowed uint256 frequency) public view returns (uint8);
  
  // Sending out a memo  
  function memo (uint8 tier) public view returns (string);
  ? 
  struct memo { // Maybe better?
    address to;
    uint256 tier;
    string contents;
}
  
  Events Broadcast
  Events Notification
}
```

## Example Usage

MakerDAO
* Community broadcast for an emergency MakerDAO governance call.
* Notification to all CDP holders with a reference to market insight.  
* Higher level strategic for those holding MKR for >= 1 year.
