# Elephant CLI Workshop Guide

This document provides step-by-step instructions for interacting with the Elephant Protocol using the Elephant CLI tool.

## Prerequisites

Ensure you have the following:

* Node.js 22+
* `npx` (comes bundled with Node.js)
* Exported private keys
* Account on Polygon with some POL balance (you can set this up via [MetaMask](https://metamask.io/))
* Pinata JWT token ([Create an account on Pinata](https://pinata.cloud/))

## Getting Started

### Windows Users

* Install Git for Windows: [Git for Windows](https://git-scm.com/download/win).
* Use Command Prompt, PowerShell, or Git Bash for executing commands.

### Linux/macOS Users

Use Terminal for executing commands.

### 1. Clone the Repository

Clone the repository from GitHub:

* For Linux/macOS:

```bash
git clone git@github.com:elephant-xyz/elephant-workshop.git
cd elephant-workshop
```

* For Windows:

```bash
git clone https://github.com/elephant-xyz/elephant-workshop.git
cd elephant-workshop
```

### 2. Create the Environment File

* For Linux/macOS:

```bash
cp .env.example .env
```

* For Windows (Command Prompt):

```cmd
copy .env.example .env
```

### 3. Configure Environment Variables

Edit the `.env` file and update the following variables:

- **PINATA_JWT**: Your Pinata JWT Token
- **PRIVATE_KEY**: Your private key for transaction signing

Example:

```env
PINATA_JWT="your-pinata-jwt"
PRIVATE_KEY="your-private-key"
```

## Data Directory Structure

The `data` directory should follow this structure:

```
data
└── QmZZTvdeTonx7pGvo1Mf3Tt99mKRRtJtVUcytejZoYPKg4
    ├── Qmevin8Lnpt9i7N8K75Mw6auEzZWirsrYWn9jAeKu2soEs.json
    ├── QmfGud78cz6WWgNkhymBBBfvY1vty4Ri7iHvDkiZYMrCrz.json
    ├── QmPr4G8Jvz5UqEWz7QLZPWr3fpMgxC7MQS5twR7j5qzzyu.json
    ├── QmPVamV7C9V7PbHquQa5MzQ8UyAT214TpsZkjhLo6LLxcG.json
    └── QmTTTSdvryWnLyqL5L7omMzCVHeo76a2p2PBdpZ31rgSsd.json
```

Each subdirectory is named after the v0 CID of the root property file. Files within each subdirectory are named after the v0 CID of the schema they represent.

## Working with IPFS

### 4. Upload and Validate Files

Use the Elephant CLI to validate and upload files to IPFS:

```bash
npx @elephant-xyz/cli validate-and-upload ./data/ upload-results.csv
```

This command validates the data in the `./data/` directory and uploads valid files to IPFS, generating an output file named `upload-results.csv`.

### 5. Submit Data to Contract

After successfully uploading files, submit the data to the Elephant Protocol smart contract:

```bash
elephant-cli submit-to-contract upload-results.csv
```

This final step registers your data with the Elephant Protocol.

## What is Pinata?

Pinata is an IPFS pinning service provider, which allows you to easily upload and manage your files on the IPFS network. For more information and to create an account, visit [Pinata.cloud](https://pinata.cloud/).

## Troubleshooting

For any issues, please verify your environment configurations and ensure dependencies are correctly installed.

## Additional Resources

* [Elephant CLI Documentation](https://elephant.xyz/docs)
* [Pinata](https://pinata.cloud/)
* [MetaMask Wallet](https://metamask.io/)
* [Git for Windows](https://git-scm.com/download/win)
