Headzoo\CoinTalk\Wallet
===============

JsonRPC wrapper class

Wraps a JsonRPCInterface instance, and provides concrete methods for each of the
methods provided by the server.

Example:
```php
 $conf = [
     "user" => "test",
     "pass" => "pass",
     "host" => "localhost",
     "port" => 9332
 ];
 $rpc    = new JsonRPC($conf);
 $wallet = new Wallet($rpc);
 $info   = $wallet->getInfo();
```


* Class name: Wallet
* Namespace: Headzoo\CoinTalk





Properties
----------


### $rpc
Used to query the coin server



```
protected Headzoo\CoinTalk\JsonRPCInterface $rpc
```



### $minconf
Only include transactions confirmed at least this many times



```
protected int $minconf = 1
```



Methods
-------


### Headzoo\CoinTalk\Wallet::__construct
Constructor



```
public mixed Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::__construct(Headzoo\CoinTalk\JsonRPCInterface $server, int $minconf)
```


##### Arguments

* **[Headzoo\CoinTalk\JsonRPCInterface](Headzoo-CoinTalk-JsonRPCInterface.md)** $server - Needed to communicate with the server
* **int** $minconf - Only include transactions confirmed at least this many times



### Headzoo\CoinTalk\Wallet::getJsonRPC
Returns the JsonRPCInterface instance being wrapped



```
public Headzoo\CoinTalk\JsonRPCInterface Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::getJsonRPC()
```




### Headzoo\CoinTalk\Wallet::getMinConf
Returns the minimum number of confirmations needed when checking balances



```
public int Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::getMinConf()
```




### Headzoo\CoinTalk\Wallet::setMinConf
Sets the minimum number of confirmations needed when checking balances



```
public Headzoo\CoinTalk\Wallet Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::setMinConf(int $minconf)
```


##### Arguments

* **int** $minconf - Only include transactions confirmed at least this many times



### Headzoo\CoinTalk\Wallet::getInfo
Returns an array containing various state info

The returned array contains the following keys:
```
 "version"           - (int)     The server version.
 "protocolversion"   - (int)     The protocol version.
 "walletversion"     - (int)     The wallet version.
 "balance"           - (double)  The total bitcoin balance of the wallet.
 "blocks"            - (int)     The current number of blocks processed in the server.
 "timeoffset"        - (int)     The time offset.
 "connections"       - (int)     The number of connections.
 "proxy"             - (string)  The proxy used by the server.
 "difficulty"        - (double)  The current difficulty.
 "testnet"           - (boolean) If the server is using testnet or not.
 "keypoololdest"     - (int)     The timestamp (seconds since GMT epoch) of the oldest pre-generated key in the key pool.
 "keypoolsize"       - (int)     How many new keys are pre-generated.
 "unlocked_until"    - (int)     The timestamp in seconds since epoch (midnight Jan 1 1970 GMT) that the wallet is unlocked for transfers, or 0 if the wallet is locked.
 "paytxfee"          - (double)  The transaction fee set in btc/kb.
 "errors"            - (string)  Any error messages.
```

```
public array Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::getInfo()
```




### Headzoo\CoinTalk\Wallet::getConnectionCount
Returns the number of connections to other nodes



```
public int Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::getConnectionCount()
```




### Headzoo\CoinTalk\Wallet::getDifficulty
Returns the proof-of-work difficulty as a multiple of the minimum difficulty



```
public double Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::getDifficulty()
```




### Headzoo\CoinTalk\Wallet::getGenerate
Returns true or false whether the wallet is currently generating hashes



```
public bool Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::getGenerate()
```




### Headzoo\CoinTalk\Wallet::getHashesPerSec
Returns a recent hashes per second performance measurement while generating

See the getGenerate() and setGenerate() calls to turn generation on and off.

```
public int Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::getHashesPerSec()
```




### Headzoo\CoinTalk\Wallet::getMiningInfo
Returns an array of mining related information

The returned array contains the following keys:
 "blocks"            - (int)     The current block.
 "currentblocksize"  - (int)     The last block size.
 "currentblocktxt"   - (int)     The last block transaction.
 "difficulty"        - (double)  The current difficulty.
 "errors"            - (string)  Current errors.
 "generate"          - (boolean) If the generation is on or off.
 "genproclimit"      - (int)     The processor limit for generation. -1 if no generation.
 "hashespersec"      - (int)     The hashes per second of the generation, or 0 if no generation.
 "networkhashps"     - (double)  The estimated network hashes per second based on the last n blocks.
 "pooledtxt"         - (int)     The size of the mem pool.
 "testnet"           - (boolean) If using testnet or not.

```
public array Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::getMiningInfo()
```




### Headzoo\CoinTalk\Wallet::getPeerInfo
Returns an array describing each connected node

Returns an mutlidimentional array, which each sub-array containing the following keys:
 "addr"              - (string)  The ip address and port of the peer.
 "addrlocal"         - (string)  The local address.
 "services"          - (string)  The supported services.
 "lastsend"          - (int)     The time in seconds since epoch (Jan 1 1970 GMT) of the last send.
 "lastrecv"          - (int)     The time in seconds since epoch (Jan 1 1970 GMT) of the last receive.
 "bytessent"         - (int)     The total bytes sent.
 "bytesrecv"         - (int)     The total bytes received.
 "conntime"          - (int)     The connection time in seconds since epoch (Jan 1 1970 GMT).
 "pingtime"          - (double)  The ping time.
 "version"           - (int)     The peer version, such as 7001.
 "subver"            - (string)  The string version, such as "Satoshi:0.8.5".
 "inbound"           - (boolean) Inbound (true) or Outbound (false).
 "startingheight"    - (int)     The starting height (block) of the peer.
 "banscore"          - (int)     The ban score (stats.nMisbehavior).
 "syncnode"          - (boolean) True if sync node.

```
public array Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::getPeerInfo()
```




### Headzoo\CoinTalk\Wallet::getBestBlockHash
Returns the hash of the best (tip) block in the longest block chain



```
public string Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::getBestBlockHash()
```




### Headzoo\CoinTalk\Wallet::getBlockCount
Returns the number of blocks in the longest block chain



```
public int Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::getBlockCount()
```




### Headzoo\CoinTalk\Wallet::setTransactionFee
Sets the transaction fee amount



```
public bool Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::setTransactionFee(double $amount)
```


##### Arguments

* **double** $amount - Amount to use for transaction fees



### Headzoo\CoinTalk\Wallet::setGenerate
Sets whether the wallet should generate coins

Generation is limited to $gen_proc_limit processors, -1 is unlimited.

```
public bool Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::setGenerate(bool $generate, int $gen_proc_limit)
```


##### Arguments

* **bool** $generate - Turn coin generation on (true) or off (false)
* **int** $gen_proc_limit - The processor limit, or -1 for unlimited



### Headzoo\CoinTalk\Wallet::addNode
Attempts add or remove a node from the addnode list or try a connection to it once



```
public bool Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::addNode(string $node, string $type)
```


##### Arguments

* **string** $node - The node ip address and port in &lt;ip&gt;:&lt;port&gt; format (see getPeerInfo() for nodes)
* **string** $type - Use &quot;add&quot; to add a node to the list, &quot;remove&quot; to remove a node from the list, &quot;onetry&quot; to try a connection to the node once



### Headzoo\CoinTalk\Wallet::getNodeInfo
Returns information about the given added node, or all added nodes

If dns is false, only a list of added nodes will be provided, otherwise connected information will also
be available.

Note: Nodes added using the addnode configuration and "onetry" nodes are not returned.

When $dns is false, returns multidimensional array, with sub-arrays containing the keys:
 "addednode"     - (string) The node ip address and port in format <ip>:<port>.

When $dns is true, returns a mutlidimentional array, with the sub-arrays containing the keys:
 "addednode"     - (string)  The node ip address and port in format <ip>:<port>.
 "connected"     - (boolean) If connected.
 "addresses"     - (array)   Array of node peers. Each sub-array contains the keys:
     "address"   - (string)  The node ip address and port in format <ip>:<port>.
     "connected" - (bool)    If connected.

```
public array Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::getNodeInfo(bool $dns, string $node)
```


##### Arguments

* **bool** $dns - If false, only a list of added nodes will be provided, otherwise connected information will also be available
* **string** $node - If provided, return information about this specific node, otherwise all nodes are returned



### Headzoo\CoinTalk\Wallet::signMessage
Sign a message with the private key of an address



```
public string Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::signMessage(string $address, string $message)
```


##### Arguments

* **string** $address - The coin address
* **string** $message - The message to sign



### Headzoo\CoinTalk\Wallet::signRawTransaction
Adds signatures to a raw transaction and returns the resulting raw transaction

If provided, the $prev_txs argument should be a multidimensional array, with the sub-arrays having the
following keys:
 "txid"          - (string)  The transaction id.
 "vout"          - (int)     The output number.
 "scriptPubKey"  - (string)  The script key.
 "redeemScript"  - (string)  The redeem script.

Example return value:
 [
     // The raw transaction with signature(s) (hex-encoded string).
     "hex" => "010000000263f2dde1d550b081d59c09ccb3f8a83b01...",

     // If transaction has a complete set of signature (0 if not).
     "complete" => 1
 ]

```
public array Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::signRawTransaction(string $hex_data, array $prevtxs, array $priv_keys, string $sighashtype)
```


##### Arguments

* **string** $hex_data - The transaction hex string
* **array** $prevtxs - An array of previous dependent transaction outputs
* **array** $priv_keys - Array of base58-encoded private keys for signing
* **string** $sighashtype - The signature hash type, one of &quot;ALL&quot;, &quot;NONE&quot;, &quot;SINGLE&quot;, &quot;ALL|ANYONECANPAY&quot;, &quot;NONE|ANYONECANPAY&quot;, &quot;SINGLE|ANYONECANPAY&quot;



### Headzoo\CoinTalk\Wallet::isSignedMessageValid
Verify a signed message

Returns a boolean value indicating whether the message was successfully verified.

```
public bool Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::isSignedMessageValid(string $address, string $signature, string $message)
```


##### Arguments

* **string** $address - A coin address
* **string** $signature - The signature
* **string** $message - The message



### Headzoo\CoinTalk\Wallet::getBalance
Returns the balance for the entire wallet



```
public double Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::getBalance()
```




### Headzoo\CoinTalk\Wallet::getBalances
Returns balances by for every address

Returns an mutlidimentional array, which each sub-array containing the following keys:
 "address"       - (string)  The receiving address.
 "account"       - (string)  The account of the receiving address, using "" to represent the default account.
 "amount"        - (double)  The total amount received by the address.
 "confirmations" - (int)     The number of confirmations of the most recent transaction included.
 "txids"         - (array)   An array of transaction ids.

To get a list of accounts on the system, call getReceivedByAddress(0, true).

```
public array Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::getBalances(bool $include_empty)
```


##### Arguments

* **bool** $include_empty - Whether to include addresses that haven&#039;t received any payments



### Headzoo\CoinTalk\Wallet::getBalanceByAccount
Returns the balance for the given account



```
public double Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::getBalanceByAccount(string $account)
```


##### Arguments

* **string** $account - The account name, using &quot;&quot; for the default account



### Headzoo\CoinTalk\Wallet::getBalanceByAddress
Returns the balance for a given address



```
public double Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::getBalanceByAddress(string $address)
```


##### Arguments

* **string** $address - The address



### Headzoo\CoinTalk\Wallet::move
Move from one account in your wallet to another



```
public bool Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::move(string $from_account, string $to_account, double $amount, string $comment)
```


##### Arguments

* **string** $from_account - Name of the from account
* **string** $to_account - Name of the to account
* **double** $amount - The amount to transfer
* **string** $comment - Comment to record with this transaction



### Headzoo\CoinTalk\Wallet::send
Sends coins to the given address

Returns the transaction id if successful.

```
public string Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::send(string $address, double $amount, string $comment, string $comment_to)
```


##### Arguments

* **string** $address - Address to send to
* **double** $amount - The amount to send
* **string** $comment - Comment to record with this transaction
* **string** $comment_to - Comment sent to the network with the transaction



### Headzoo\CoinTalk\Wallet::sendFromAccount
Sends coins from the given account to the given address



```
public string Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::sendFromAccount(string $account, string $address, double $amount, string $comment, string $comment_to)
```


##### Arguments

* **string** $account - Name of the from account
* **string** $address - Address to send to
* **double** $amount - The amount to send
* **string** $comment - Comment to record with this transaction
* **string** $comment_to - Comment sent to the network with the transaction



### Headzoo\CoinTalk\Wallet::sendManyFromAccount
Sends coins to multiple addresses



```
public array Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::sendManyFromAccount(string $account, array $addresses, string $comment)
```


##### Arguments

* **string** $account - Name of the from account
* **array** $addresses - [&quot;address1&quot; =&gt; &quot;amount1&quot;, &quot;address2&quot; =&gt; &quot;amount2&quot;]
* **string** $comment - A comment on this transaction



### Headzoo\CoinTalk\Wallet::getAccounts
Returns the wallet accounts

Example return value:
 [
     "",
     "Paper1",
     "Mining"
 ]

```
public array Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::getAccounts()
```




### Headzoo\CoinTalk\Wallet::setAccount
Sets the account associated with the given address

Assigning address that is already assigned to the same account will create a new address associated with
that account.

```
public bool Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::setAccount(string $address, string $account)
```


##### Arguments

* **string** $address - A coin address from the wallet
* **string** $account - Name of the account



### Headzoo\CoinTalk\Wallet::getAccountByAddress
Returns the account associated with the given address

Returns null when an account does not exist for the given address.

```
public string|null Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::getAccountByAddress(string $address)
```


##### Arguments

* **string** $address - The address for account lookup



### Headzoo\CoinTalk\Wallet::getAddresses
Returns the wallet addresses

Example return value:
 [
     "1Headz2mYtpBRo6KFaaUEtcm5Kce6BZRJM",
     "1JBKAM8W9jEnuGNvPRFjtpmeDGvfQx6PLU",
     "19tjsa4nBeAtn48kcmW9Gg2wRFtm24GRG2"
 ]

```
public array Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::getAddresses()
```




### Headzoo\CoinTalk\Wallet::getAddressByAccount
Returns the current address for receiving payments to this account

The account does not need to exist, it will be created and a new address created if there is no account by
the given name.

```
public string Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::getAddressByAccount(string $account)
```


##### Arguments

* **string** $account - The account name for the address, using &quot;&quot; to represent the default account



### Headzoo\CoinTalk\Wallet::getAddressesByAccount
Returns the addresses for the given account



```
public array Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::getAddressesByAccount(string $account)
```


##### Arguments

* **string** $account - The account name, using &quot;&quot; to represent the default account



### Headzoo\CoinTalk\Wallet::getRawChangeAddress
Returns a new address for receiving change

This is for use with raw transactions, NOT normal use.

```
public string Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::getRawChangeAddress(string $account)
```


##### Arguments

* **string** $account - Name of the account, using &quot;&quot; to represent the default account



### Headzoo\CoinTalk\Wallet::getNewAddress
Returns a new address for receiving payments

If $account is specified (recommended), it is added to the address book so payments received with the address
will be credited to $account.

```
public string Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::getNewAddress(string $account)
```


##### Arguments

* **string** $account - The account name for the address to be linked to, using &quot;&quot; to represent the default account



### Headzoo\CoinTalk\Wallet::getAddressInfo
Returns address information

The returned array will contain one or more of the following keys:
 "isvalid"      - (bool)     Whether the address is valid.
 "address"      - (string)   The address.
 "ismine"       - (bool)     Whether the address belongs to the wallet.
 "isscript"     - (bool)     Is this a script address?
 "pubkey"       - (string)   The address public key.
 "iscompressed" - (bool)     Is the address compressed?
 "account"      - (string)   The account the address belongs to.

The returned array will only contain ["isvalid" => false] when the address is not valid.

```
public array Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::getAddressInfo(string $address)
```


##### Arguments

* **string** $address - The coin address



### Headzoo\CoinTalk\Wallet::getNewMultiSignatureAddress
Returns a new multi-signature address

Returns an array with the following keys:
 "address"       - (string) The multi-signature address
 "redeemScript"  - (string) The redeem script

```
public array Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::getNewMultiSignatureAddress(int $nrequired, array $keys)
```


##### Arguments

* **int** $nrequired - Number of keys needed to redeem
* **array** $keys - Array of public keys



### Headzoo\CoinTalk\Wallet::addMultiSignatureAddress
Add a nrequired-to-sign multisignature address to the wallet

Each key is a address or hex-encoded public key. If $account is specified, assign address to $account.

Returns the the multi-signature address.

```
public string Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::addMultiSignatureAddress(int $nrequired, array $keys, string $account)
```


##### Arguments

* **int** $nrequired - Number of keys needed to redeem
* **array** $keys - Array of public keys
* **string** $account - Name of account which receives the address



### Headzoo\CoinTalk\Wallet::getPrivateKeyByAddress
Returns the private key for the given address

Returns null when the address does not belong to any wallet account.

```
public string Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::getPrivateKeyByAddress(string $address)
```


##### Arguments

* **string** $address - The address for the private key



### Headzoo\CoinTalk\Wallet::addPrivateKey
Adds a private key to the wallet

Rescanning may take a while looking for existing transactions, and may even freeze up the wallet.

```
public bool Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::addPrivateKey(string $priv_key, string $label, bool $rescan)
```


##### Arguments

* **string** $priv_key - The private key
* **string** $label - An optional label
* **bool** $rescan - Whether to rescan the wallet for transactions



### Headzoo\CoinTalk\Wallet::getBlock
Returns information about the block with the given hash

When $verbose is set to false, this method returns the serialized and hex-encoded block data.

When $verbose is set to true, the return value will be an array with the following keys:
 "hash"              - (string)  The block hash (same as provided).
 "confirmations"     - (int)     The number of confirmations.
 "size"              - (int)     The block size.
 "height"            - (int)     The block height or index.
 "version"           - (int)     The block version.
 "merkleroot"        - (string)  The merkle root.
 "tx"                - (array)   The transaction ids.
 "time"              - (int)     The block time in seconds since epoch (Jan 1 1970 GMT).
 "nonce"             - (double)  The nonce.
 "bits"              - (string)  The bits.
 "difficulty"        - (double)  The difficulty.
 "previousblockhash" - (string)  The hash of the previous block.
 "nextblockhash"     - (string)  The hash of the next block.

```
public array|string Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::getBlock(string $hash, bool $verbose)
```


##### Arguments

* **string** $hash - The block hash
* **bool** $verbose - True for an array, false for the hex encoded data



### Headzoo\CoinTalk\Wallet::getBlockHash
Returns hash of block in best-block-chain at $index

Index 0 is the genesis block.

```
public string Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::getBlockHash(int $index)
```


##### Arguments

* **int** $index - The block index



### Headzoo\CoinTalk\Wallet::getSinceBlock
Get all transactions in blocks since block $hash

Returns all transactions if $hash is omitted.

The return value will be an mutlidimentional array with the following keys:
 "lastblock"             - (string)  The hash of the last block.
 "transactions"          - (array)   One or more transactions. Each transaction will contain the following keys:
     "account"           - (string)  The account name associated with the transaction, using "" to represent the default account.
     "address"           - (string)  The address of the transaction. Not present for move transactions (category = move).
     "category"          - (string)  The type of transaction, eg "send", "receive", or "move".
     "amount"            - (double)  The transaction amount. This is negative for the "send" category, and for the 'move' category for moves outbound, otherwise it's positive.
     "fee"               - (double)  The transaction fee. This is negative and only available for the 'send' category of transactions.
     "confirmations"     - (int)     The number of confirmations for the transaction. Available for 'send' and 'receive' category of transactions.
     "blockhash"         - (string)  The block hash containing the transaction. Available for 'send' and 'receive' category of transactions.
     "blockindex"        - (int)     The block index containing the transaction. Available for 'send' and 'receive' category of transactions.
     "blocktime"         - (int)     The block time in seconds since epoch (1 Jan 1970 GMT).
     "txid"              - (string)  The transaction id.
     "time"              - (int)     The transaction time in seconds since epoch (Jan 1 1970 GMT).
     "timereceived"      - (int)     The time received in seconds since epoch (Jan 1 1970 GMT). Available for 'send' and 'receive' category of transactions.
     "comment"           - (string)  If a comment is associated with the transaction.
     "to"                - (string)  If a comment to is associated with the transaction.

```
public array Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::getSinceBlock(string $hash, int $target_confirmations)
```


##### Arguments

* **string** $hash - The block hash to list transactions since
* **int** $target_confirmations - The confirmations required, must be 1 or more



### Headzoo\CoinTalk\Wallet::getTransaction
Returns detailed information about in-wallet transaction

This method cannot be used to get information about non-wallet transactions. Use getRawTransaction() for
non-wallet transactions.

The returned array will contain the following keys:
 "amount"        - (double)  The transaction amount.
 "fee"           - (double)  The transaction fee.
 "confirmations" - (int)     The number of confirmations.
 "blockhash"     - (string)  The block hash.
 "blockindex"    - (int)     The block index.
 "blocktime"     - (int)     The time in seconds since epoch (1 Jan 1970 GMT).
 "txid"          - (string)  The transaction id.
 "time"          - (int)     The transaction time in seconds since epoch (1 Jan 1970 GMT).
 "timereceived"  - (int)     The time received in seconds since epoch (1 Jan 1970 GMT).
 "details"       - (array)   The transaction details. Each array contains the following keys:
     "account"   - (string)  The account name involved in the transaction, using "" to represent the default account.
     "address"   - (string)  The address involved in the transaction.
     "category"  - (string)  The category, either "send" or "receive".
     "amount"    - (double)  The amount.
     "fee"       - (double)  The transaction fee.

```
public array Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::getTransaction(string $txid)
```


##### Arguments

* **string** $txid - The transaction id



### Headzoo\CoinTalk\Wallet::getTransactions
Returns up to $count most recent transactions

The first $from transactions are skipped. If $account not provided will return recent transaction from all
accounts.

The return value will be an mutlidimentional array, with each sub-array containing the following keys:
 "account"           - (string)  The account name associated with the transaction, using "" to represent the default account.
 "address"           - (string)  The address of the transaction. Not present for move transactions (category = move).
 "category"          - (string)  The type of transaction, eg "send", "receive", or "move".
 "amount"            - (double)  The transaction amount. This is negative for the "send" category, and for the 'move' category for moves outbound, otherwise it's positive.
 "fee"               - (double)  The transaction fee. This is negative and only available for the 'send' category of transactions.
 "confirmations"     - (int)     The number of confirmations for the transaction. Available for 'send' and 'receive' category of transactions.
 "blockhash"         - (string)  The block hash containing the transaction. Available for 'send' and 'receive' category of transactions.
 "blockindex"        - (int)     The block index containing the transaction. Available for 'send' and 'receive' category of transactions.
 "blocktime"         - (int)     The block time in seconds since epoch (1 Jan 1970 GMT).
 "txid"              - (string)  The transaction id.
 "time"              - (int)     The transaction time in seconds since epoch (Jan 1 1970 GMT).
 "timereceived"      - (int)     The time received in seconds since epoch (Jan 1 1970 GMT). Available for 'send' and 'receive' category of transactions.
 "comment"           - (string)  If a comment is associated with the transaction.

```
public array Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::getTransactions(string $account, int $count, int $from)
```


##### Arguments

* **string** $account - The name of the account
* **int** $count - Number of transactions to return
* **int** $from - Offset from the last transaction



### Headzoo\CoinTalk\Wallet::getTransactionsFromMemoryPool
Returns an array of transaction ids in memory pool



```
public array Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::getTransactionsFromMemoryPool()
```




### Headzoo\CoinTalk\Wallet::getRawTransaction
Returns raw transaction representation for given transaction id

Returns the raw transaction data as a string when $verbose is 0. Use decodeRawTransaction() to convert the
transaction data into an array.

Returns an array with the following keys when $verbose is 1.
 "hex"               - (string)  The serialized, hex-encoded data.
 "txid"              - (string)  The transaction id.
 "version"           - (int)     The version.
 "locktime"          - (int)     The lock time.
 "vin"               - (array)   An array with the following keys:
     "txid"          - (string)  The transaction id.
     "vout"          - (int)     The vout index.
     "scriptSig"     - (array)   The script, an array with keys:
         "asm"       - (string)  Script in asm format.
         "hex"       - (string)  Script in hex format.
     "sequence"      - (int)     The script sequence number.
 "vout"              - (array)   An array with the following keys:
     "value"         - (double)  The amount sent.
     "n"             - (int)     The index.
     "scriptPubKey"  - (array)   An array with the following keys:
         "asm"       - (string)  The script in asm format.
         "hex"       - (string)  The script in hex format.
         "reqSigs"   - (int)     The number of required sigs.
         "type"      - (string)  The type, eg 'pubkeyhash'.
         "addresses" - (array)   An array of addresses.
 "blockhash"         - (string)  The block hash.
 "confirmations"     - (int)     The number of confirmations.
 "time"              - (int)     The transaction time in seconds since epoch (Jan 1 1970 GMT).
 "blocktime"         - (int)     The block time in seconds since epoch (Jan 1 1970 GMT).

```
public array Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::getRawTransaction(string $txid, int $verbose)
```


##### Arguments

* **string** $txid - The transaction id
* **int** $verbose - If 0, return a string, other return a json object



### Headzoo\CoinTalk\Wallet::getTransactionOut
Returns details about an unspent transaction output

Returns an array with the following keys:
 "bestblock"         - (string)  The block hash.
 "confirmations"     - (int)     The number of confirmations.
 "value"             - (double)  The transaction value.
 "scriptPubKey"      - (array)   The script, an array with the following keys:
     "asm"           - (string)  The code in asm format.
     "hex"           - (string)  The code in hex format.
     "regSigs"       - (int)     Number of required signatures.
     "type"          - (string)  The type, eg "pubkeyhash".
     "addresses"     - (array)   An array of addresses.
 "version"           - (int)     The version.
 "coinbase"          - (bool)    Coinbase transaction or not.

```
public array Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::getTransactionOut(string $txid, int $n, bool $include_mem_pool)
```


##### Arguments

* **string** $txid - The transaction id
* **int** $n - The vout value
* **bool** $include_mem_pool - Whether to included the mem pool



### Headzoo\CoinTalk\Wallet::getTransactionOutSet
Returns statistics about the unspent transaction output set

Note this call may take some time.

Returns an array with the following keys:
 "height"            - (int)     The current block height.
 "bestblock"         - (string)  The best block hash hex.
 "transactions"      - (int)     The number of transactions.
 "txouts"            - (int)     The number of output transactions.
 "bytes_serialized"  - (int)     The serialized size.
 "hash_serialized"   - (string)  The serialized hash.
 "total_amount"      - (double)  The total amount.

```
public array Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::getTransactionOutSet()
```




### Headzoo\CoinTalk\Wallet::getUnspent
Returns array of unspent transaction inputs in the wallet between $minconf and $maxconf

The returned array will contain the following keys:
 "txid"          - (string)  The transaction id.
 "vout"          - (int)     The vout value.
 "address"       - (string)  The address.
 "account"       - (string)  The associated account, using "" to represent the default account.
 "scriptPubKey"  - (string)  The script key.
 "amount"        - (double)  The transaction amount.
 "confirmations" - (int)     The number of confirmations.

```
public array Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::getUnspent(int $minconf, int $maxconf)
```


##### Arguments

* **int** $minconf - The minimum confirmations to filter
* **int** $maxconf - The maximum confirmations to filter



### Headzoo\CoinTalk\Wallet::getLockUnspent
Returns list of temporarily unspendable outputs

Use the setLockUnspent() method to lock and unlock transactions for spending.

```
public array Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::getLockUnspent()
```




### Headzoo\CoinTalk\Wallet::setLockUnspent
Updates list of temporarily unspendable outputs

Temporarily lock (true) or unlock (false) specified transaction outputs.

```
public bool Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::setLockUnspent(bool $unlock, array $objs)
```


##### Arguments

* **bool** $unlock - Whether to unlock (true) or lock (false) the specified transactions
* **array** $objs - An array of objects. Each object has &quot;txid&quot; (string) and &quot;vout&quot; (numeric)



### Headzoo\CoinTalk\Wallet::getBlockTemplate
Returns data needed to construct a block to work on

If the $mode argument is set, that is used to explicitly select between the default "template"
request or a "proposal".

The returned array contains the following keys:
 "version"               - (int)     The block version.
 "previousblockhash"     - (string)  The hash of current highest block.
 "transactions"          - (array)   Array of non-coinbase transactions which should be included in the block. Each contains the following keys:
     "data"              - (string)  Transaction data encoded in hexadecimal (byte-for-byte).
     "hash"              - (string)  Hash/id encoded in little-endian hexadecimal.
     "depends"           - (array)   Array of numbers.
     "fee"               - (int)     Difference in value between transaction inputs and outputs (in Satoshis); for coinbase transactions, this is a negative Number of the total collected block fees (ie, not including the block subsidy); if key is not present, fee is unknown and clients MUST NOT assume there isn't one.
     "sigops"            - (int)     Total number of SigOps, as counted for purposes of block limits; if key is not present, sigop count is unknown and clients MUST NOT assume there aren't any.
     "required"          - (boolean) If provided and true, this transaction must be in the final block.
 "coinbaseaux"           - (array)   Array of data that should be included in the coinbase's scriptSig content. Contains the following key:
     "flags"             - (string)  The data to include.
 "coinbasevalue"         - (double)  Maximum allowable input to coinbase transaction, including the generation award and transaction fees (in Satoshis).
 "coinbasetxn"           - (array)   Information for coinbase transaction.
 "target"                - (string)  The hash target.
 "mintime"               - (int)     The minimum timestamp appropriate for next block time in seconds since epoch (Jan 1 1970 GMT).
 "mutable"               - (array)   List of ways the block template may be changed. Contains the following keys:
     "value"             - (string)  A way the block template may be changed, e.g. 'time', 'transactions', 'prevblock'.
 "noncerange"            - (string)  A range of valid nonces.
 "sigoplimit"            - (int)     Limit of sigops in blocks.
 "sizelimit"             - (int)     Limit of block size.
 "curtime"               - (int)     Current timestamp in seconds since epoch (Jan 1 1970 GMT).
 "bits"                  - (string)  Compressed target of next block.
 "height"                - (int)     The height of the next block.

```
public array Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::getBlockTemplate(array $capabilities, string|null $mode)
```


##### Arguments

* **array** $capabilities - An array of supported features, &quot;longpoll&quot;, &quot;coinbasetxn&quot;, &quot;coinbasevalue&quot;, &quot;proposal&quot;, &quot;serverlist&quot;, &quot;workid&quot;
* **string|null** $mode - This must be set to &quot;template&quot; or omitted



### Headzoo\CoinTalk\Wallet::getWork
Returns work data, or works on existing data

Returns formatted hash data to work on if $data is not specified. Tries to solve the block if $data is provided,
and returns a boolean value indicating success or failure.

When $data is not specified, the return value will be an array with the following keys:
 "midstate"  - (string) The precomputed hash state after hashing the first half of the data (DEPRECATED).
 "data"      - (string) The serialized block data.
 "hash1"     - (string) The formatted hash buffer for second hash (DEPRECATED).
 "target"    - (string) The little endian hash target.

```
public array|bool Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::getWork(string $data)
```


##### Arguments

* **string** $data - The hex-encoded data to solve



### Headzoo\CoinTalk\Wallet::submitRawBlock
Submits a raw (serialized, hex-encoded) block to the network

The $params argument is currently ignored, but may contain the following keys:
 "workid"    - (string) If the server provided a work id, it MUST be included with the submission.

```
public array Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::submitRawBlock(string $hex_data, array $params)
```


##### Arguments

* **string** $hex_data - The hex string of the raw block
* **array** $params - Optional parameters



### Headzoo\CoinTalk\Wallet::submitRawTransaction
Submits a raw (serialized, hex-encoded) transaction to the network



```
public array Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::submitRawTransaction(string $hex_data)
```


##### Arguments

* **string** $hex_data - The hex string of the raw transaction



### Headzoo\CoinTalk\Wallet::createRawTransaction
Returns a hex-encoded raw transaction spending the given inputs and sending to the given addresses

The $transactions argument is a multidimensional array, which each value being an array with the following keys:
 "txid"  - (string) The transaction id.
 "vout"  - (int)    The output number.

The $addresses argument is an associative array using addresses for keys, and amounts to send to the address
as values. For example:
 [
     "1Headz2mYtpBRo6KFaaUEtcm5Kce6BZRJM" => 0.5,
     "1FVCaRTKQtpxeE4gypz69NvDkyZUd7Y3SJ" => 0.08
 ]

Note: This method only creates the raw transaction data. The transaction's inputs are not signed, and it is not
stored in the wallet or transmitted to the network.

Example:
<code>
 $transactions = [
     [
         "txid" => "7de4c9a1e715a9aaf6f8573ce16f8bc3c06f927826e2d0c39424e1524eccda89",
         "vout" => 1
     ],
     [
         "tdid" => "d2e611dcb3348c315dadeaa959cff662328f124e3a3e80fe8f33056bac95b9fe",
         "vout" => 2
     ]
 ];
 $addresses = [
     "1Headz2mYtpBRo6KFaaUEtcm5Kce6BZRJM" => 0.5,
     "13P4LpjYyBvWt283DffjsHpoFWFprr9dVq" => 0.08
 ];
 $raw = $api->createRawTransaction($transactions, $addresses);
</code>

```
public array Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::createRawTransaction(array $transactions, array $addresses)
```


##### Arguments

* **array** $transactions - The transactions
* **array** $addresses - Array using addresses for keys, and amounts for values



### Headzoo\CoinTalk\Wallet::decodeRawTransaction
Decodes a raw serialized transaction

Given a serialized, hex-encoded transaction, the method decodes it, and returns an array of the transaction
information.

Returns an array with the following keys:
 "hex"               - (string)  The serialized, hex-encoded data.
 "txid"              - (string)  The transaction id.
 "version"           - (int)     The version.
 "locktime"          - (int)     The lock time.
 "vin"               - (array)   An array with the following keys:
     "txid"          - (string)  The transaction id.
     "vout"          - (int)     The vout index.
     "scriptSig"     - (array)   The script, an array with keys:
         "asm"       - (string)  Script in asm format.
         "hex"       - (string)  Script in hex format.
     "sequence"      - (int)     The script sequence number.
 "vout"              - (array)   An array with the following keys:
     "value"         - (double)  The amount sent.
     "n"             - (int)     The index.
     "scriptPubKey"  - (array)   An array with the following keys:
         "asm"       - (string)  The script in asm format.
         "hex"       - (string)  The script in hex format.
         "reqSigs"   - (int)     The number of required sigs.
         "type"      - (string)  The type, eg 'pubkeyhash'.
         "addresses" - (array)   An array of addresses.
 "blockhash"         - (string)  The block hash.
 "confirmations"     - (int)     The number of confirmations.
 "time"              - (int)     The transaction time in seconds since epoch (Jan 1 1970 GMT).
 "blocktime"         - (int)     The block time in seconds since epoch (Jan 1 1970 GMT).

```
public array Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::decodeRawTransaction(string $hex_string)
```


##### Arguments

* **string** $hex_string - The serialized, hex-encoded transaction data



### Headzoo\CoinTalk\Wallet::encrypt
Encrypts the wallet with the given pass phrase

After this, any calls that interact with private keys such as sending or signing will require the passphrase to
be set prior the making these calls. Use the unlock() for this, and then lock().

Note: This will shutdown the server.

```
public bool Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::encrypt(string $pass_phrase)
```


##### Arguments

* **string** $pass_phrase - The pass phrase to encrypt the wallet with. It must be at least 1 character, but should be long



### Headzoo\CoinTalk\Wallet::lock
Removes the wallet encryption key from memory, locking the wallet

After calling this method, you will need to call unlock() again before being able to call any methods
which require the wallet to be unlocked.

```
public bool Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::lock()
```




### Headzoo\CoinTalk\Wallet::unlock
Stores the wallet decryption key in memory for $timeout seconds



```
public bool Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::unlock(string $passphrase, int $timeout)
```


##### Arguments

* **string** $passphrase - The wallet pass phrase
* **int** $timeout - Number of seconds to keep the pass phrase in memory



### Headzoo\CoinTalk\Wallet::changePassPhrase
Updates the wallet passphrase



```
public array Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::changePassPhrase(string $old_passphrase, string $new_passphrase)
```


##### Arguments

* **string** $old_passphrase - The old pass phrase
* **string** $new_passphrase - The new pass phrase



### Headzoo\CoinTalk\Wallet::backup
Safely copies wallet.dat to $destination

The destination can be a directory or a path with filename.

```
public bool Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::backup(string $destination)
```


##### Arguments

* **string** $destination - The destination directory or file



### Headzoo\CoinTalk\Wallet::stop
Shutdown the wallet



```
public string Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::stop()
```




### Headzoo\CoinTalk\Wallet::fillKeyPool
Fills the keypool



```
public bool Headzoo\CoinTalk\Wallet::Headzoo\CoinTalk\Wallet::fillKeyPool()
```


