# Commands

```bash
solana-keygen pubkey #to view your public key => BF8r4BB2W9gSEGLj6ku6JZYRFsRESKgo8NDuxfTFXxb6
solana balance --url devnet # to check your balance
solana airdrop 1 $(pubkey) --url devnet # to air drop sol to your pubkey wallet address

```

## Creating a token

```bash
# use the solana package library (spl)

spl-token create-token --url devnet

# created token with address 
# token id :=>   9Ui5fMorbyhM6dYdZieAuUHkxezm1ZeM3fR8kWg9fJBt
```

## Mint a token

```bash
# create an account
# an account is specif to a particular type of token, we can have multiple accounts on a sol wallet based on the type of token.

spl-token create-account $(token type id) --url devnet

# created account for above token id 
# account :=>   Bp62Q58Md4SNiXbNqVKEMHabQ2FLFpRtT9uqjsieF8WT
```

```bash
# to check token balance 
spl-token balance $(token type id) --url devnet

# to mint tokens 
spl-token mint $(token type id) $(number of tokens) --url devnet # eg : spl-token mint 9Ui5fMorbyhM6dYdZieAuUHkxezm1ZeM3fR8kWg9fJBt 1000 --url devnet

```

```bash
# disaable anymore minting and never be able to enable it again for this acccount

spl-token authorize $(token type id) mint --disable --url devnet 
```

```bash
# to burn some tokens
spl-token burn $(account address) $(number of tokens) --url devnet
```

# solana dev net phantom address : DUZ5pqPALXXyPVGSGMs5QqxB7sCZaAzB8AatuBpSSNkt

```bash
# spl-token transfer $(token id) 150 $(phantom wallet address) --url devnet
spl-token transfer 9Ui5fMorbyhM6dYdZieAuUHkxezm1ZeM3fR8kWg9fJBt 150 DUZ5pqPALXXyPVGSGMs5QqxB7sCZaAzB8AatuBpSSNkt --url devnet --allow-unfunded-recipient --fund-recipient
```