
<h1 align="center">
The decentralized Off-chain Non-transferable (dONT) system
  <br/>
</h1>

Very much a **WIP**

dONT will be composed of the following components:
1. An AWS Lambda [Authorizer](https://docs.aws.amazon.com/apigateway/latest/developerguide/apigateway-use-lambda-authorizer.html) uses ECDSA over the Koblitz curve secp256k1 to verify the source and integrity of the message (same method used by Ethereum to validate transactions). This authorizer will also check the public key against a smart contract so that only smart contract authorized addresses (e.g. token holders) have access to a given lambda function. This Authorizer will be completely portable. 

2. A client-side watermarking scheme based off this [paper](https://www.researchgate.net/publication/265388939_TTP-Free_Asymmetric_Fingerprinting_Based_on_Client_Side_Embedding), in which a client generates an identifyer, encrypts it with a homomorphic encryption scheme, and sends it to a server who uses it to generate a personalized decryption key. When the client uses this decryption key to decrypt a copy righted piece of work (encrypted with AES is output feedback mode), the video is watermarked during the process of decryption. 

3. An escrow-like system that ties off-chain service provision with on-chain clients.



To use:
from top-most directory: 

`npm install`  
`stack build`

To run tests:
`stack test`

To run lambda functions locally:
`serverless offline start`


To run locally, you will need an installation of [cryptol](https://github.com/GaloisInc/cryptol), with the binary added to your path. You will also need an installation of [z3](https://github.com/Z3Prover/z3)

