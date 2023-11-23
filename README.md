# PANDA WALLET 
(click->click->click->your gateway to blockchain is ready)

The Panda wallet simplifies the user onboarding experience through a smooth one-click process. Leveraging the functionalities of account abstraction and passkeys, users can easily generate passkey credentials, set up a smart account, and deploy—all with just a single click on their smartphone or computer. The wallet operates discreetly, ensuring a seamless and hassle-free experience for users.

# Motivation

Blockchain is a transformative technology capable of addressing numerous societal challenges, with applications spanning across various sectors such as decentralized finance (DeFi), gaming, healthcare, and more. However, for an average user without extensive technical knowledge, navigating the blockchain landscape can be overwhelming, involving terms like wallet, private key, gas fees, secure private key, and others. Onboarding becomes a substantial hurdle for the ordinary user.

# Objective of Panda Wallet

Panda Wallet aims to address challenges through the integration of account abstraction and passkeys. This approach ensures a seamless onboarding experience for users with just a single click on their smartphone or laptop. Users can effortlessly generate passkey credentials and set up their smart accounts, streamlining the process for enhanced user convenience.

# Details

## UX OPTIMIZATION

Panda Wallet offers an optimal user experience with seamless one-click onboarding. This optimization is chosen to alleviate user concerns, as there is no need to worry about saving private key – all information is securely stored on the client's system.

## passkey implementation

Currently, the implementation of passkey-powered user operations involves the utilization of the secpR1 library from FCL. The system comprises an entrypoint contract and a custom paymaster contract designed to handle user fees. This configuration enables more individuals to easily access the realm of cryptocurrency.

## what about security?

Passkeys represent a contemporary evolution in Web2 security, poised to supplant traditional password management and its associated risks with robust ECC authentication, serving as an EoA. This transformative shift is facilitated through ERC-4337, promising to revolutionize accessibility and inclusivity in the realm of web3. Passkeys introduce a novel approach where the private key is securely stored in a hardened enclave, resilient against advanced attacks. This contrasts with keys stored in browsers, providing a heightened level of security. Additionally, passkeys mitigate phishing risks by linking them to a specific website, such as the dApp's site.

# Documentation

Panda Wallet aims to introduce blockchain technology to <strike>millions</strike> billions, of people worldwide. Users won't need to worry about any complexities— with just a single click, their wallet is ready for use. Accessible with a passkey, the Panda Wallet provides a user-friendly entry into the world of blockchain. All fees are sponsored, ensuring that users experience nothing but a classic, seamless web2 experience without any visible charges.

Step 1: **We are set to develop a smart contract wallet utilizing passkeys. Users will simply need to click on the 'Create Wallet' button to initiate the process.**

<img src="images/1.png" height="500"/>

Step 2: **In this step, users are required to enter a username for the wallet. The passkey associated with this username will be securely stored in the system.**

<img src="images/2.png" height="500"/>

Step 3: **In this step, users are prompted to undergo biometric verification, with options such as Face ID and Touch ID currently available. The system is designed to accommodate additional biometric methods, such as voice recognition, in the future. The provided credentials are utilized to derive the public key used in ERC-4337**

<img src="images/3.png" height="500"/>

Step 4: **After providing the biometric verification, the credential details are securely saved in the local system. Users will be prompted to grant permission for this process, which can be conveniently done using either a mobile or laptop. The system ensures a seamless experience, with the permission prompt triggered automatically, requiring no additional action from the user.**

<img src="images/5.png" height="500"/>

Step 5: **After granting permission, a pop-up notification will appear confirming the secure local storage of the passkey**

<img src="images/6.png" height="500"/>

After completing all the steps, a transaction containing essential information, including wallet initcode ,signature,entry contract etc is sent to the user operation mempool. Upon the execution of this user operation, your wallet will be fully prepared for use.

# Use cases

- Versatile Use Cases: Pandwallet offers a diverse range of applications within the blockchain space.

- Effortless User Onboarding: Any application can seamlessly utilize Pandwallet for user onboarding. With just a simple click, users can easily onboard into the decentralized application (dApp).

- Biometric Support: The passkey generation supports various biometric methods for enhanced security.

- Background Processing: Users experience a Web2-like interface where all processes occur seamlessly in the background.

- No Need for Separate Private Key Storage: Users are relieved from the task of storing private keys separately.

- Enhanced Security: Pandwallet provides a higher level of security compared to externally owned accounts (EOA).

# business plan

**Market details and descriptions have been incorporated.**

**1.1 Product/Service Offering**

- Panda Wallet simplifies user onboarding through a one-click process, provides secure passkey generation, and ensures a hassle-free smart account setup. This eliminates the complexities associated with traditional blockchain onboarding.

**1.2 Unique Selling Points**

- Seamless one-click onboarding.
- Enhanced security through passkey and account abstraction.
- Inclusive accessibility to blockchain for a global audience.

**2.1 Customer Acquisition**

- We will employ digital marketing channels, establish partnerships, and engage with the community to acquire users.

**2.2 Pricing Strategy**

- Our pricing strategy may include freemium models, subscription plans, or transaction-based pricing.

**2.3 Sales Channels**

- We plan to leverage online platforms and strategic partnerships for effective distribution.

# Roadmap

**Some future plans have been included here. They will be implemented based on priority and need at the time**

## 1. Enhanced Authentication

- **Web Authentication Support:** Strengthen web authentication capabilities to enhance security and user verification.
- **Biometric Authentication Support:** Integrate additional biometric authentication methods for improved user authentication and access control.

## 2. Security Measures

- **Quantum-Resistant Signatures for ECDSA using STARKs:** Implement advanced quantum-resistant signature algorithms, leveraging STARKs, to fortify the security of the ECDSA against potential quantum threats. (
  Falcon can be a superior option, as Stark requires more gas for proof verification)

## 3. Integration and Interoperability

- **Panda SDK for Other Application Integration with Panda Wallet:** Develop and provide a Panda Software Development Kit (SDK) to facilitate seamless integration with other applications, enhancing overall interoperability with Panda Wallet.

## 4. Privacy and Confidentiality

- **Shielded Transaction Support (Mixer):** Implement support for shielded transactions, similar to a mixer, to enhance privacy and confidentiality in transactions conducted through Panda Wallet.

## 5. Wallet Functionality

- **Multisig Wallet Support in Panda Wallet:** Integrate support for multisignature (multisig) wallets within Panda Wallet, providing users with increased security and shared control over their digital assets.

# implementation details

**Off-chain Smartphone Signer:**

Upon initiating the "create account" process, our system employs a sophisticated off-chain smartphone signer. This signer generates a secure passkey by utilizing the biometric identification capabilities of the smartphone. Importantly, the FIDO passkey is securely stored within the smartphone's enclave, offering a formidable defense against potential phishing attempts. This is a notable improvement over conventional practices that store private keys in less secure memory zones, such as those within browsers. The resulting public key, derived from the passkey credential, is then transmitted to the main contract on the blockchain. Subsequent transactions within the system are authenticated using this passkey, enhancing security through biometric identification and decentralized passkey management.

**On-chain Transaction:**

Within the on-chain transaction process, the JavaScript front-end application facilitates the transmission of an authenticator challenge to the secure enclave of the smartphone. This method ensures a secure and reliable initiation and validation of transactions directly on the blockchain. The on-chain transaction mechanism introduces an additional layer of security and transparency to the overall system, bolstering the reliability of transaction processing.

# installation setup

The current implementation implementation seamlessly integrates with the Infinitism ERC4337 Entrypoint and a customized PayMaster. This integration facilitates the effortless payment of user fees, ensuring accessibility for users of all expertise levels.

#### Deploy contracts

```bash
forge script script/DeployAllAnvil.s.sol --private-key <PRIVATE_KEY> --broadcast -vvv --rpc-url <RPC_URL>
```

To execute the PayMaster, Bundler, and Frontend components, Docker containers would be utilized. This approach ensures a consistent and reproducible environment for running these elements, streamlining deployment and management across various systems.

webAuthAccount contracts control the passkey authentication.

## Live contracts addresses

polygon mumbai
entrypoint 0x549Cf000FAdd57400a4Cbf84158F4A619c08282A
webAuthn 0x9d7811F2d9905A9D4C596F935DAdef1A6b1235D8
webAuthnAccountFactory 0xeCCD0B7faE8aD2590E606D6cb149B426401cDBF0
paymaster 0x5AA3e7259015208F89874F0522bDB209061AD26C
