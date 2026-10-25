# proposal-contract

Proposal voting contract built during the Rise In Solidity Fundamentals course. It extends the course version with a title field for each proposal and a custom two-thirds supermajority state logic where pass votes count as abstention.

## Deployment

`RonnyContract` is deployed on Ethereum Sepolia at:

```
0x2eE3E654F6Ae60b600157286840015f00C04f110
```

View it on Etherscan: https://sepolia.etherscan.io/address/0x2eE3E654F6Ae60b600157286840015f00C04f110

## Functions

- `create(title, description, total_vote_to_end)` creates a new proposal (owner only).
- `vote(choice)` casts a vote on the current proposal: `1` approve, `2` reject, `0` pass.
- `terminateProposal()` ends the current proposal early (owner only).
- `setOwner(new_owner)` transfers ownership of the contract (owner only).
- `getCurrentProposal()` returns the current proposal.
- `getProposal(number)` returns the proposal with the given id.
- `isVoted(address)` returns whether an address has already voted on the current proposal.

## State logic

A proposal passes only if more than two thirds of the decisive votes (approve plus reject) are approve votes. Pass votes are ignored, and a proposal without decisive votes fails.
