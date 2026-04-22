## Day 2: Solidity Deep Dive (CryptoZombies)

### What I Learned Today:
1. **Function Declarations:**
   - How to pass reference types (like `string`) using the `memory` keyword.
   - Convention: Using `_` for function parameters to avoid "Shadowing" with state variables.

2. **Working with Structs & Arrays:**
   - Efficiently pushing new data into an array using: `zombies.push(Zombie(_name, _dna));`.
   - Understanding that `struct` initialization works like a constructor.

3. **Function Visibility (Security Basics):**
   - **Public:** Anyone can call it.
   - **Private:** Only internal functions within the same contract can call it.
   - Security Tip: Always default to `private` unless you specifically need it to be `public`.

### Code Snippet:
```solidity
// Creating a private function to safely create zombies
function _createZombie(string memory _name, uint _dna) private {
    zombies.push(Zombie(_name, _dna));
}
