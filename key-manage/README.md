Notes on the new changes/tools
------------------------------

* where should "Bitcoin Armory" be?
    - new subsection as "Bitcoin wallet manager"? Cold Storage?
    - It is dependent on bitcoin-qt for the blockchain synchronization (https://bitcoinarmory.com/about/armory-and-bitcoin-qt)
    - Manage multiple wallets (deterministic and watching-only), print paper backups that work forever, import or sweep private keys, and keep your savings in a computer that never touches the internet, while still being able to manage incoming payments, and create outgoing payments with the help of a USB key
    - https://github.com/etotheipi/BitcoinArmory/




###Other Bitcoin Clients (Not yet in the paper)###
* Electrum (http://electrum.org)
    - wallet can be recovered from a secret phrase that you can write on paper or learn by heart.
    - Instant on: Your client does not download the blockchain, it uses a remote server.
    - Forgiving: Your wallet can be recovered from a secret seed.
    - Safe: Your seed or private keys are not sent to the server. Information received from the server is verified using SPV
    - No downtimes: Several public servers are available, you can switch instantly.
    - Ubiquitous: You can use the same wallet on different computers, it will auto-synchronize.
    - Cold Storage: You can have secure offline wallets and still safely spend from an online computer.
    - Open: You can export your private keys into other Bitcoin clients.
    - Tested and audited: Electrum is open source and was first released in November 2011.
	- Also for Android
	
* CoinBase (https://coinbase.com)
    - Mobile and Online
	- Android: https://play.google.com/store/apps/details?id=com.coinbase.android
	- Android Source: https://github.com/coinbase/coinbase-android

###Links (Not mentioned in the paper)###
* multibit github: https://github.com/jim618/multibit
* Bitcoin-wallet mobile source:  https://code.google.com/p/bitcoin-wallet
* Mycelium Bitcoin wallet for android: https://github.com/mycelium-com/wallet

* bitcoinpaperwallet (foldable design): https://bitcoinpaperwallet.com/bitcoinpaperwallet/generate-wallet.html
* bitcoinpaperwallet github: https://github.com/cantonbecker/bitcoinpaperwallet



Notes.txt
---------
###Introduction###

###Background###
* Bitcoin Introdution

###Motivation###
* Different paradigm: protecting a key vs protecting a password. 
* Thesis: users aren't ready to manage keys. 
* State of the art in terms of usability is to somehow convert the key into a password
    - security and deployability (availability) problems
    - keys=something you have. 

You're serious about using your keys
* manage wallet.dat (default)
    - malware getting the file
    - hard drive failure, switch computer, format
    - unintentional sharing (p2p, backups, work computer IT staff, shared computer)

* password protecting your keys
    - malware, offline attack
    - mental model. you may think that you're making your password into a key, but it's actually 2 factor

* offline storage
    - print privkey to paper (paper wallet) (bitbills)
    - put key onto usb
    - mini cog walkthrough. how easy is it to import they back. 

###How to convert your key into a password###
* PBKDF2 aka brain wallets
    - entropy reduction. cf online banking (cormac herley). 
    - salt?
    - parsing (spec that was followed) requires a tool. if you lose the tool, you may not be able to recover your keys. standard may not be detailed enough, or not properly implemented.

* HOSTED WALLETS (hot storage)
    - trusted party. they can steal if malicious.
    - they're good, but don't have good security. external hackers stealing
    - legitimate shutdown. legal implications (affidavit)
    - web service, so any attack (phishing, xss)

HOSTED WALLETS (cold storage)
* Offline wallets aka cold storage. not immediately available, transactions queueing up (coinbase). 

###RESEARCH AGENDA###
* better import/export of keys
* better language and guidance on key management 
* how do you know the key is in wallet.dat ?  
* publishing public keys. people need to keep these around, and they can use to check if they have the right privkey. 
* if you have your pubkey and you have the salt, you can avoid rainbow tables, but your pubkeys get longer. (add salt via commitcoin) 
* boyen iterated hashing of passwords -> compute amount of iterations based on money, script
* digital death
* sinkhole accounts
* incentives are there because it's money. not like ssh or ssl. 
* bitbills
* making it easier to split wallets to hedge lost 

