Node
1. git clone https://github.com/thaichain/mainnet.git
2. cd mainnet
3. docker run --rm -it -v $PWD:/gochain -w /gochain thaichain/gochain gochain --datadir /gochain/node init genesis.json
4. docker run -itd --restart=always --name thaichain-node -v $PWD:/gochain -p 40333:40333 thaichain/gochain gochain --networkid 7  --datadir /gochain/node  --cache 4096 --port 40333
    =-=-= OR =-=-=
  docker run -itd --restart=always --name thaichain-node -v $PWD:/gochain --net=host thaichain/gochain gochain --networkid 7  --datadir /gochain/node  --cache 4096 --port 40333

Signer
1. git clone https://github.com/thaichain/mainnet.git
2. cd mainnet
3. echo "password" > password.txt 
4. docker run --rm -it -v $PWD:/gochain -w /gochain thaichain/gochain gochain --datadir /gochain/node --password password.txt account new 
5. docker run --rm -it -v $PWD:/gochain -w /gochain thaichain/gochain gochain --datadir /gochain/node init genesis.json
4. docker run -itd --restart=always --name thaichain-node -v $PWD:/gochain -p 40333:40333 thaichain/gochain gochain --networkid 7  --datadir /gochain/node  --cache 4096 --port 40333 --mine --unlock [account from step 3] --password password.txt
    =-=-= OR =-=-=
  docker run -itd --restart=always --name thaichain-node -v $PWD:/gochain --net=host thaichain/gochain gochain --networkid 7  --datadir /gochain/node  --cache 4096 --port 40333 --mine --unlock [account from step 3] --password password.txt
