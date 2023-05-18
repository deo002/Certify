# Certify - A Decentralized Certificate Issuance and Verification System powered by Ethereum Smart Contracts

## Documentation Contents

- [Installation & Set Up](#Installation-&-Set-Up)
  - [Downloading repository](#Downloading-repository)
  - [Setting up Blockchain on Local Network](#Setting-up-Blockchain-on-Local-Network)
  - [Setting up Client Application](#Setting-up-Client-Application)
- [Use-Cases](#Use-Cases)

---

## Installation & Set Up

Node Version Used: 14.16.1
NPM Version Used: 6.14.12

Add metamask plugin to your supported browser (chrome) from [here](https://chrome.google.com/webstore/detail/metamask/nkbihfbeogaeaoehlefnkodbefgpgknn?hl=en) and login


### Downloading repository

```bash
git clone https://github.com/deo002/Certify.git
cd Certify
```

### Setting up Blockchain on Local Network

There are two ways to set up local blockchain with Truffle Ganache, either with GUI or CLI.

1. Create a `.env` file

Populate the following environment variables:

```
LOCAL_ENDPOINT=http://127.0.0.1:7545
NETWORK_ID=1337
```

> The port number and network ID can be changed to your preference

> An example `.env.example` file is created for reference. You can copy and paste the contents of the file and edit the variables.

2. Download Truffle

Visit https://www.trufflesuite.com/truffle for more information

```bash
npm install -g truffle
```

> Truffle helps us with deployment, testing, migration, etc.

3. Install node dependencies

```bash
npm install
```

#### Option 1 - Using Ganache GUI

1. Download Ganache GUI

Visit [Truffle Ganache](https://www.trufflesuite.com/ganache) to download the application

2. Create a ganache workspace & run ganache blockchain network

Click on 'New Workspace' and under 'Add Project', select the `truffle-config.js` file in the Certify directory. This should create a new workspace project with the same truffle settings defined in the `truffle-config.js` file.

Once created with the workspace open, the local ganache blockchain network should be running on the defined port and network ID.

> Note: This blockchain network will be running as long as the Ganache GUI Application is open with the workspace.

3. Deploy Smart Contracts

Npm scripts has been included for ease of contract deployment. You may view the commands used under `package.json` for better understanding

In the root directory of Certify

```bash
truffle compile
npm run deploy:local
```

#### Option 2 - Using Ganache CLI

In your terminal/bash

1. Install Ganache CLI

```bash
npm install -g ganache-cli
```

2. Run Ganache blockchain network

```bash
npm run ganache
```

In the root directory of Certify

3. Deploy Smart Contracts

```bash
npm run deploy:local
```

### Setting up Client Application

The client application (which is built with [React.js](https://reactjs.org/)) is located under the `/client` folder in the directory.

```bash
cd client
```

1. Install dependencies

```bash
npm install
```

2. Create a `.env`file

Populate the following environment variables:

```
REACT_APP_LOCAL_ENDPOINT=http://127.0.0.1:7545
REACT_APP_NETWORK_ID=1337
```

> The port number and network ID can be changed to your preference
> Use the same Infura project endpoint with instructions given above

> An example `.env.example` file is created for reference. You can copy and paste the contents of the file and edit the variables.

3. Start application

### Option 1 - To connect to local blockchain network

```bash
npm start
```

To use the front-end application running at http://localhost:3000/, connect to the Localhost Network in metamask.

Import in the account that you used to deploy the contracts using the private key of the account, you can find it in the key symbol of the Ganache UI beside your account.


There are **4 main Use Cases**:

1. **Registering Institutes** by Central Authority

2. **Issuing Certificates** by Institutes

3. **Revoking Certificates** by Institutes

4. **Viewing Certificates** by Employers/Public
