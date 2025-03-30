## Stacks-AgriFund
# Decentralized Crowdfunding Smart Contract for Agricultural Projects

## Overview
This smart contract enables decentralized crowdfunding for agricultural projects on the Stacks blockchain. Farmers can create projects, set funding goals, and allow investors to contribute STX tokens. If the project is successfully funded, farmers can withdraw the funds and later return profits to investors based on the predefined return on investment (ROI). If the project fails to meet its funding goal within the set duration, investors can receive refunds.

## Features
- **Project Creation**: Farmers can create new projects with funding goals, duration, and ROI.
- **Investment**: Investors can contribute STX tokens to fund projects.
- **Fund Withdrawal**: Farmers can withdraw funds once the project is successfully funded.
- **Profit Distribution**: Farmers return profits to investors based on their investment and ROI.
- **Investor Refunds**: If a project fails to reach its funding goal within the given duration, investors can receive refunds.

## Smart Contract Details

### Constants
- **contract-owner**: The contract deployer's address.

### Data Structures
#### Maps
- **projects**: Stores details of each project, including the farmer, funding goal, raised amount, duration, ROI, end-time, and status.
- **investments**: Stores investment details for each investor in a project.

#### Variables
- **project-counter**: Keeps track of the total number of projects created.

### Public Functions
#### 1. `create-project (funding-goal uint) (duration uint) (roi uint)`
- Allows farmers to create a new project.
- Returns the new project ID.

#### 2. `invest-in-project (project-id uint) (amount uint)`
- Allows investors to contribute STX tokens to a project.
- Updates the total amount raised for the project.
- Transfers the investment to the contract.

#### 3. `withdraw-funds (project-id uint)`
- Allows farmers to withdraw funds once the project is fully funded.
- Transfers the raised amount to the farmer's wallet.
- Updates the project status to "Closed".

#### 4. `get-investors (project-id uint)`
- Read-only function that retrieves a list of investors for a given project.

#### 5. `return-profits (project-id uint)`
- Allows farmers to distribute profits to investors based on ROI.
- Transfers profits and initial investments back to investors.

#### 6. `refund-investors (project-id uint)`
- Allows investors to claim refunds if the project fails to meet its funding goal within the set duration.
- Transfers invested STX back to investors.

## How It Works
1. A farmer creates a project with a funding goal, duration, and ROI.
2. Investors contribute STX tokens to the project.
3. If the funding goal is met:
   - The farmer withdraws the funds.
   - After the project is completed, profits are distributed to investors.
4. If the funding goal is not met within the given duration:
   - Investors can claim refunds.

## Deployment & Usage
1. Deploy the smart contract on the Stacks blockchain.
2. Use Clarity functions to interact with the contract.
3. Investors and farmers interact via a Stacks-compatible wallet.
