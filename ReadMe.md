### HowTo

`sudo apt install libssl-dev`

Leave `genesisgen.c` to default to generate your own Block 0 hash

>or Set initial value of `uint32_t startNonce = 2083236893` and `uint32_t unixtime = 1231006505` in `genesisgen.c` to generate original Bitcoin Block `0` hash

### Compile
`gcc genesisgen.c -o genesisgen -lcrypto`

### Usage

##### Syntax
`./genesisgen [PubKey] [TimeStamp] [nBits]`

##### Example 
`./genesisgen 041e4ff547106e832e9b2cd7f2ef2702344621fada0d60236d46686acda52e13c0f9194d3a7f0618f8f05859feba164ec0df15ed0909b1e6d6b3ac2625061ea65f "03/Nov/2017 Tribute to Soldiers , Suraj Singh (25) and Kushwah Pradip Singh (22)" 486604799`

>where nBits are : echo $((0x1d00ffff)) => 486604799

##### Output
```
[+] Coinbase = 04ffff001d01045030332f4e6f762f32303137205472696275746520746f20536f6c6469657273202c20537572616a2053696e6768202832352920616e64204b757368776168205072616469702053696e67682028323229
[+] scriptPubKey = 41041e4ff547106e832e9b2cd7f2ef2702344621fada0d60236d46686acda52e13c0f9194d3a7f0618f8f05859feba164ec0df15ed0909b1e6d6b3ac2625061ea65fac
[+] hashMerkleRoot = 5337c1b8586924cf578ac2908228dcee0bd10eaa79f0581678b43034479cb59e
[+] Byteswapped = 9eb59c473430b4781658f079aa0ed10beedc288290c28a57cf246958b8c13753
[/] Generating block => 1454614 Hashes/s, Nonce 460983670
[/] Block found!
[+] hashGenesisBlock = 000000001ffb0a98e199ba6951acdc8ed306c58abcbe2d278fe47e1193a49ece
[+] nNonce = 461434383
[+] nTime = 1512560179
```