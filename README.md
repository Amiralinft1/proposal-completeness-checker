# Proposal Completeness Checker

A GenLayer Intelligent Contract that checks whether a short project proposal clearly covers five planning items.

## Checklist

The contract evaluates whether the proposal includes:

1. The goal or problem
2. Planned work or milestones
3. A timeline
4. A budget or required resources
5. A measurable success criterion

## Results

- `COMPLETE`: all five items are clearly present.
- `NEEDS_WORK`: at least one item is clearly missing.
- `UNCLEAR`: the proposal is too vague to assess.

The contract returns a classification, not detailed feedback.

## How It Works

The user submits proposal text to the contract. A language model evaluates it against the fixed checklist, and GenLayer's strict equality principle checks that validators agree on the result. The contract stores the latest classification.

Input length must be between 20 and 2,000 characters.

## Deployment

- Network: GenLayer StudioNet
- Contract address: [`0x957F6d6503f91F3F6AFD971847a03FA18cE8226e`](https://explorer-studio.genlayer.com/address/0x957F6d6503f91F3F6AFD971847a03FA18cE8226e)
- Deployment transaction: [View on GenLayer Explorer](https://explorer-studio.genlayer.com/tx/0x8dd6022632ac2921f8f09c9f6ab6a81939cb178e398a2a1ef3ec8a276caf8029)

## Verified Test Transactions

All three test transactions were finalized, accepted, and returned the expected classification. Each result was also checked through the contract's read method.

| Case | Input | Result | Transaction |
| --- | --- | --- | --- |
| Complete proposal | Community garden irrigation proposal with work, timeline, budget, and measurable target | `COMPLETE` | [View transaction](https://explorer-studio.genlayer.com/tx/0x547d6a0a595bc7848b674ce71fdc93551d1ca8f4a1a62b4fec923bb977d650b9) |
| Missing details | "We will build a garden irrigation system to save water." | `NEEDS_WORK` | [View transaction](https://explorer-studio.genlayer.com/tx/0xb5a3c503c4c7873e3a57cf9288db6b958d3b3da4d61c0006537b5aa16771fc43) |
| Vague proposal | "This idea might help in some way." | `UNCLEAR` | [View transaction](https://explorer-studio.genlayer.com/tx/0x06902e48eb2b20f66e364cacd61a8c64b0280e92c195107307e171518870e9d9) |

## Limitations

- This tool checks completeness only. It does not assess the quality, feasibility, or funding eligibility of a proposal.
- The result is not an official grant or funding decision.
- Proposal text is included in public on-chain transaction data. Do not submit confidential information.
- Testing currently covers three example inputs.

## Disclaimer

This prototype provides an automated checklist result for demonstration purposes only. Users should review proposals themselves before making decisions.
