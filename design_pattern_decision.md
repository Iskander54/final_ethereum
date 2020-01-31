# design_pattern_decision

withdrawal pattern in mortgage;


The following pattern decisions were used in the creation of this dApp

## Access Restriction

The contract inherits the Ownable contract from OpenZepplin which allows for certain functions such as ownership and renouncing ownership to be restircted to a Owner address

## Mapped Struct
I used a mapped Structs with Delete-enabled Index in registry to deal have the add,delete,update features for the registry

## Withdrawal Pattern
Withdrawal pattern ensures that direct transfer call is not made which poses a security threat.
In withdrawal pattern, we'll reset the pending amount before each transfer. It will ensure that only caller contract fails.

## Guard Checks
Several Guard Checks are used to ensure that some functions are only run after certain conditions are met.

As an example, here is the confirmTransaction Function in the mortgage contract, that check if caller is involved in the transaction and hasn't already confirmed:

        ```function confirmTransaction(uint transactionId,address addr) public checkIfPaused() {
        require(confirmations[transactionId][msg.sender] == false);
        require(isParty[transactionId][msg.sender]==true);
        confirmations[transactionId][msg.sender] = true;
        emit Confirmation(msg.sender, transactionId);
        executeTransaction(transactionId,addr);
    }```

This is also used in places such as when we want to check if a property exists
```require(propertyList.length>0,"There is no property yet");```




