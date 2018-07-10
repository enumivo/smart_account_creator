# Smart Account Creator for ENU

This is a smart contract for ENU specifically designed for people who have their ENU 
on an exchange and don't have their own ENU account yet. It removes the need for a third-party like a friend or
an account creation service. Since it's a smart contract, the account creation happens instantly, automatically and trustless.

## How to use?
Send at least 3 ENU to the contract which is deployed at the ENU account ```accountcreat```. In the memo, 
you give the desired account name, the owner public key and the active public key separated by the ```:``` character. 

For example, if your account name is ```mynewaccount```, your owner key is ```ENU6ra2QHsDr6yMyFaPaNwe3Hz8XmYRj3B68e5tbDchyPTTasgFH9``` 
and your active key is ```ENU8WcL1CroNrXfdphkohCmea1Jgp7TpqQXrkpcF1gETweeSnphmJ```, the memo string would be:

```
mynewaccount:ENU6ra2QHsDr6yMyFaPaNwe3Hz8XmYRj3B68e5tbDchyPTTasgFH9:ENU8WcL1CroNrXfdphkohCmea1Jgp7TpqQXrkpcF1gETweeSnphmJ
```

If you want to use the same key for owner and active. The second key including the ```:``` separator can be omitted. 
So that would be a valid memo string as well:

```
mynewaccount:ENU6ra2QHsDr6yMyFaPaNwe3Hz8XmYRj3B68e5tbDchyPTTasgFH9
```
## How does it work?
When you withdraw your ENU to the accountcreat smart contract, it will perform the following steps in order:

1. Create a new account using your specified name, owner key and active key
1. Buy 4KB of RAM for your new account with parts of the transferred ENU. Every account that is created on the ENU network needs 4 KB of RAM to exist.
1. Delegate and transfer 0.1 ENU for CPU and 0.1 ENU for NET.

Should any of the above actions fail, the transaction will be rolled back which 
means the money will automatically be refunded to you.