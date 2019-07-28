# codefundo++ 2019 : Secure Electronic Voting using Azure Blockchain
Building a secure electronic voting system that offers the fairness and privacy of current voting schemes, while providing the transparency and flexibility offered by electronic systems has been a challenge for a long time. Here, we propose a new e-voting system based on the voting requirements and blockchain as a service.

## What is blockchain ?
The blockchain is an append-only data structure, where data is stored in a distributed ledger that cannot be tampered with or deleted. This makes the ledger immutable. The blocks are chained in such a way that each block has a hash that is a function of the previous block, and thus by induction the complete prior chain, thereby providing assurance of immutability.

## System description :
The system will contain identification data for every voter. It will also show analytical data for each candidate of constituencies based on data from [Election Commision of India](https://eci.gov.in/candidate-political-parties/link-to-candidate-affidavits). For the voting,  the idea is to form a blockchain of all votes cast, wherein each node represents data of one particular voter and this system will be built on Azure Blockchain platform. The entire scenario can be carried out in 3 main stages.

### Before voting :
- First the data of all eligible voters will be fetched from UIDAI database. Each voter can enter their Aadhar ID to generate OTP on their registered mobile number, using that they will be able to set password for their voting account. Now once the registration process is complete, voters will be assigned to their respective constituencies according to their permanent address data. 
- The candidates for each constituency have to go through a similar registration process after which each voter will get a notification about the list of the candidates. Upon clicking on a candidate name, analytical data will be displayed for that candidate. 

### During voting :
#### Voter authentication :
During the voting procedure, the voter will have a retina scan which will then be matched with the retinal image in UIDAI database. In this way the voter will be authenticated and once the credentials are matched, then the voter will be allowed to cast his/her vote. Verification of credentials will be performed by programming a Smart Contract into the network of nodes, which maps the details of the user (fingerprint, retinal image, age, sex, date of birth) to the registered constituency and he/she has already casted the vote or not.
#### Casting of vote :
Now, the application will show the list of candidates on the interface and the voter will submit his/her response. The casted vote will be hashed using a hashing algorithm, and then encrypted using the voter’s biometric details. The corresponding node will then be inserted into the blockchain. A node will contain voter’s details, counter of votes cast and, the encrypted vote. This system enables the concerned voter to digitally sign his/her vote, which he/she only could’ve gained access.
### After voting :
#### Counting and result declaration :
Once the voting finishes, each node will be decrypted using the public key (kept by the Election Commission) to yield the hash value, which in turn will be mapped to the candidate. Thus, the counting will take place.As the whole system is based on blockchain environment the counting will be finished securely and instantly.So, there is no need for a vote counting day, also most of the corruption and crimes related to this procedure can be eradicated.
