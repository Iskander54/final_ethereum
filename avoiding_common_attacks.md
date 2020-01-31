# avoiding common attacks

## Permissions
There is a underlying whitelist and blacklist in addition to an Owner privelage using the OpenZepplin Ownable Contract

## Withdrawal Pattern for re-entrancy attack
Withdrawal pattern ensures that direct transfer call is not made which poses a security threat.
In withdrawal pattern, we'll reset the pending amount before each transfer. It will ensure that only caller contract fails.

## Static Analysis
Use of linters and other tools like Mythril, Solium and Solhint



