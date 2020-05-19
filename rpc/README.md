git clone https://github.com/thaichain/mainnet.git

cd mainnet/rpc

docker run --rm -it -v $PWD:/gochain -w /gochain thaichain/gochain gochain --datadir /gochain/node init genesis.json
