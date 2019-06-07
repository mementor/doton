Credits to https://github.com/copperbits/TON

# DoTON

TON Test Lite Client
```
➭ docker run -it -v "$(pwd):/data/mount" --name doton mentro/doton
```

## New wallet with free Grams from testgiver
Attach to running container and generate new wallet and request to testgiver:
```
➭ docker exec -it doton bash
cd mount && mkdir doton

../new-wallet.fif -1 doton/wallet
../testgiver.fif new_wallet_init_addr 0x30E 10 doton/giver-ask
```

In lite-client console:
```
sendfile mount/doton/giver-ask.boc
last

sendfile mount/doton/wallet-query.boc
last
```

## Send Grams from your wallet to some another wallet
In attached session:
```
../wallet.fif doton another_wallet_address 0x1 5 doton/send-to-query
```

In lite-client console:
```
sendfile mount/doton/send-to-query.boc
```
