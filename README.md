# NoobChain - A Simple Blockchain Implementation

Welcome to NoobChain! This is a beginner-friendly blockchain implementation that helps you understand how blockchains work. Think of it as a digital ledger (like a notebook) where each page (block) is connected to the previous one in a special way that makes it impossible to cheat or change past entries.

## What is a Blockchain?

Imagine you have a chain of blocks, where each block contains some information (like a message or transaction) and is connected to the previous block. The special thing about this chain is:
- You can't change any block once it's added
- Each block is connected to the previous one using a special code (hash)
- To add a new block, you need to solve a puzzle (mining)

## How NoobChain Works

### 1. Creating Blocks
Think of each block like a page in a notebook:
- It has some information (like "Alice sent 5 coins to Bob")
- It knows about the previous page (block)
- It has a timestamp (when it was created)
- It has a special code (hash) that makes it unique

### 2. Mining Blocks
Mining is like solving a puzzle:
- The computer tries to find a special number (nonce)
- When combined with the block's information, this number creates a hash that starts with a certain number of zeros
- The more zeros required, the harder the puzzle is to solve
- In our implementation, we require 5 zeros at the start of the hash

### 3. Connecting Blocks
Each block is connected to the previous one:
- The first block (genesis block) is special - it doesn't have a previous block
- Every other block contains the hash of the previous block
- This creates an unbreakable chain - if you change any block, all the following blocks become invalid

### 4. Checking if Everything is Valid
The system regularly checks if the blockchain is valid by:
- Making sure each block's hash is correct
- Verifying that each block correctly references its previous block
- Confirming that all blocks have been properly mined

## Let's See It in Action!

Here's a simple example of how blocks are created and added to the chain:

```java
// Create the first block
Block firstBlock = new Block("First Block", "0");
firstBlock.mineBlock(5);  // Solve the puzzle
blockchain.add(firstBlock);

// Create the second block
Block secondBlock = new Block("Second Block", firstBlock.hash);
secondBlock.mineBlock(5);  // Solve the puzzle
blockchain.add(secondBlock);
```

## Key Features Explained

### 1. Security
- **Cryptographic Hashing**: Like a unique fingerprint for each block
- **Proof of Work**: The puzzle that needs to be solved to add a block
- **Immutability**: Once a block is added, it can't be changed
- **Chain Validation**: Regular checks to ensure everything is correct

### 2. Mining
- **Difficulty Level**: How many zeros are required at the start of the hash
- **Nonce**: A number that miners try different values of to solve the puzzle
- **Hash Finding**: The process of finding the right nonce to create a valid hash

### 3. Data Integrity
- **Block Linking**: Each block is connected to the previous one
- **Validation**: Regular checks to ensure no blocks have been tampered with
- **Tamper Detection**: The system can detect if anyone tries to change the data

### 4. Transparency
- **JSON Format**: All blocks can be viewed in a readable format
- **Clear Structure**: Easy to understand how blocks are organized
- **Validation Process**: Simple to verify if the chain is valid

## Getting Started

### What You Need
- Java Development Kit (JDK) 11 or higher
- Maven 3.6.0 or higher

### How to Run
1. Clone this repository
2. Build the project:
   ```bash
   mvn clean package
   ```
3. Run the application:
   ```bash
   java -jar target/noobchain-1.0-SNAPSHOT-jar-with-dependencies.jar
   ```

## What You'll Learn
By studying this implementation, you'll understand:
- How blocks are created and connected
- How mining works
- How the blockchain stays secure
- How to validate the chain
- The basic principles of blockchain technology

## Contributing
Feel free to:
1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## License
This project is licensed under the MIT License.

## Acknowledgments
- Built for educational purposes
- Inspired by basic blockchain concepts
- Uses Google's Gson library for JSON handling 
